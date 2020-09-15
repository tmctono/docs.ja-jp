---
ms.openlocfilehash: 04c4fb4c8e9da8c58a5e26f78a7b13aa6a0df4a0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614685"
---
### <a name="changes-in-path-normalization"></a><span data-ttu-id="03c82-101">パスの正規化の変更</span><span class="sxs-lookup"><span data-stu-id="03c82-101">Changes in path normalization</span></span>

#### <a name="details"></a><span data-ttu-id="03c82-102">説明</span><span class="sxs-lookup"><span data-stu-id="03c82-102">Details</span></span>

<span data-ttu-id="03c82-103">.NET Framework 4.6.2 を対象とするアプリより、ランタイムによってパスを正規化する方法が変わりました。パスの正規化では、パスまたはファイルを識別する文字列を変更し、対象のオペレーティング システムの有効なパスに準拠するようにします。</span><span class="sxs-lookup"><span data-stu-id="03c82-103">Starting with apps that target the .NET Framework 4.6.2, the way in which the runtime normalizes paths has changed.Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="03c82-104">通常、正規化では次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="03c82-104">Normalization typically involves:</span></span>

- <span data-ttu-id="03c82-105">コンポーネントとディレクトリの区切り記号を正規化する。</span><span class="sxs-lookup"><span data-stu-id="03c82-105">Canonicalizing component and directory separators.</span></span>
- <span data-ttu-id="03c82-106">現在のディレクトリを相対パスに適用する。</span><span class="sxs-lookup"><span data-stu-id="03c82-106">Applying the current directory to a relative path.</span></span>
- <span data-ttu-id="03c82-107">パスの相対ディレクトリ (.) または親ディレクトリ (..) を評価する。</span><span class="sxs-lookup"><span data-stu-id="03c82-107">Evaluating the relative directory (.) or the parent directory (..) in a path.</span></span>
- <span data-ttu-id="03c82-108">指定した文字をトリミングする。</span><span class="sxs-lookup"><span data-stu-id="03c82-108">Trimming specified characters.</span></span>
<span data-ttu-id="03c82-109">.NET Framework 4.6.2 を対象とするアプリより、パス正規化の次の変更が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="03c82-109">Starting with apps that target the .NET Framework 4.6.2, the following changes in path normalization are enabled by default:</span></span>
  - <span data-ttu-id="03c82-110">ランタイムはオペレーティング システムの [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) 関数に従って、パスを正規化します。</span><span class="sxs-lookup"><span data-stu-id="03c82-110">The runtime defers to the operating system's [GetFullPathName](https://docs.microsoft.com/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamew) function to normalize paths.</span></span>
- <span data-ttu-id="03c82-111">正規化では、ディレクトリ セグメントの末尾 (ディレクトリ名の末尾のスペースなど) がトリミングされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="03c82-111">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>
- <span data-ttu-id="03c82-112">`\\.\` や `\\?\` (mscorlib.dll のファイル I/O API の場合) を含む、完全に信頼できるデバイス パス構文がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="03c82-112">Support for device path syntax in full trust, including `\\.\` and, for file I/O APIs in mscorlib.dll, `\\?\`.</span></span>
- <span data-ttu-id="03c82-113">ランタイムではデバイス構文パスは検証されません。</span><span class="sxs-lookup"><span data-stu-id="03c82-113">The runtime does not validate device syntax paths.</span></span>
- <span data-ttu-id="03c82-114">代替データ ストリームにアクセスするためのデバイス構文の使用はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="03c82-114">The use of device syntax to access alternate data streams is supported.</span></span>
<span data-ttu-id="03c82-115">これらの変更でパフォーマンスが向上すると同時に、以前はアクセス不可だったパスにメソッドでアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="03c82-115">These changes improve performance while allowing methods to access previously inaccessible paths.</span></span> <span data-ttu-id="03c82-116">.NET Framework 4.6.1 以前のバージョンを対象とするアプリが .NET Framework 4.6.2 以降で実行される場合、この変更の影響は受けません。</span><span class="sxs-lookup"><span data-stu-id="03c82-116">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="03c82-117">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="03c82-117">Suggestion</span></span>

<span data-ttu-id="03c82-118">.NET Framework 4.6.2 以降を対象とするアプリの場合、アプリケーション構成ファイルの `<runtime>` セクションに次の行を追加することでこの変更を無効にし、従来の正規化を使用できます。</span><span class="sxs-lookup"><span data-stu-id="03c82-118">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the `<runtime>` section of the application configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
</runtime>
```

<span data-ttu-id="03c82-119">.NET Framework 4.6.1 以前を対象とするが、.NET Framework 4.6.2 以降で実行されるアプリの場合、アプリケーション構成ファイルの `<runtime>` セクションに次の行を追加することで、パス正規化の変更を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="03c82-119">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the `<runtime>` section of the application .configuration file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />
</runtime>
```

| <span data-ttu-id="03c82-120">名前</span><span class="sxs-lookup"><span data-stu-id="03c82-120">Name</span></span>    | <span data-ttu-id="03c82-121">値</span><span class="sxs-lookup"><span data-stu-id="03c82-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="03c82-122">スコープ</span><span class="sxs-lookup"><span data-stu-id="03c82-122">Scope</span></span>   | <span data-ttu-id="03c82-123">マイナー</span><span class="sxs-lookup"><span data-stu-id="03c82-123">Minor</span></span>       |
| <span data-ttu-id="03c82-124">バージョン</span><span class="sxs-lookup"><span data-stu-id="03c82-124">Version</span></span> | <span data-ttu-id="03c82-125">4.6.2</span><span class="sxs-lookup"><span data-stu-id="03c82-125">4.6.2</span></span>       |
| <span data-ttu-id="03c82-126">種類</span><span class="sxs-lookup"><span data-stu-id="03c82-126">Type</span></span>    | <span data-ttu-id="03c82-127">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="03c82-127">Retargeting</span></span> |
