---
title: 軽減策:パスの正規化
ms.date: 03/30/2017
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
ms.openlocfilehash: 1e7b540975b84320d099ca004df5b6a87aa60f6a
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457886"
---
# <a name="mitigation-path-normalization"></a><span data-ttu-id="3e110-102">軽減策:パスの正規化</span><span class="sxs-lookup"><span data-stu-id="3e110-102">Mitigation: Path Normalization</span></span>
<span data-ttu-id="3e110-103">.NET Framework 4.6.2 以降を対象とするアプリから、.NET Framework のパスの正規化が変更されています。</span><span class="sxs-lookup"><span data-stu-id="3e110-103">Starting with apps the target  the .NET Framework 4.6.2, path normalization in the .NET Framework has changed.</span></span>  
  
## <a name="what-is-path-normalization"></a><span data-ttu-id="3e110-104">パスの正規化とは</span><span class="sxs-lookup"><span data-stu-id="3e110-104">What is path normalization?</span></span>  
 <span data-ttu-id="3e110-105">パスの正規化では、パスまたはファイルを識別する文字列を変更し、対象のオペレーティング システムの有効なパスに準拠するようにします。</span><span class="sxs-lookup"><span data-stu-id="3e110-105">Normalizing a path involves modifying the string that identifies a path or file so that it conforms to a valid path on the target operating system.</span></span> <span data-ttu-id="3e110-106">通常、正規化では次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="3e110-106">Normalization typically involves:</span></span>  
  
- <span data-ttu-id="3e110-107">コンポーネントとディレクトリの区切り記号を正規化する。</span><span class="sxs-lookup"><span data-stu-id="3e110-107">Canonicalizing component and directory separators.</span></span>  
  
- <span data-ttu-id="3e110-108">現在のディレクトリを相対パスに適用する。</span><span class="sxs-lookup"><span data-stu-id="3e110-108">Applying the current directory to a relative path.</span></span>  
  
- <span data-ttu-id="3e110-109">パスの相対ディレクトリ (`.`) または親ディレクトリ (`..`) を評価する。</span><span class="sxs-lookup"><span data-stu-id="3e110-109">Evaluating the relative directory (`.`) or the parent directory (`..`) in a path.</span></span>  
  
- <span data-ttu-id="3e110-110">指定した文字をトリミングする。</span><span class="sxs-lookup"><span data-stu-id="3e110-110">Trimming specified characters.</span></span>  
  
## <a name="the-changes"></a><span data-ttu-id="3e110-111">変更点</span><span class="sxs-lookup"><span data-stu-id="3e110-111">The changes</span></span>  
 <span data-ttu-id="3e110-112">.NET Framework 4.6.2 以降を対象とするアプリから、次のようにパスの正規化が変更されています。</span><span class="sxs-lookup"><span data-stu-id="3e110-112">Starting with apps that target the .NET Framework 4.6.2, path normalization has changed in the following ways:</span></span>  
  
- <span data-ttu-id="3e110-113">ランタイムはオペレーティング システムの [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) 関数に従って、パスを正規化します。</span><span class="sxs-lookup"><span data-stu-id="3e110-113">The runtime defers to the operating system's [GetFullPathName](/windows/desktop/api/fileapi/nf-fileapi-getfullpathnamea) function to normalize paths.</span></span>  
  
- <span data-ttu-id="3e110-114">正規化では、ディレクトリ セグメントの末尾 (ディレクトリ名の末尾のスペースなど) がトリミングされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="3e110-114">Normalization no longer involves trimming the end of directory segments (such as a space at the end of a directory name).</span></span>  
  
- <span data-ttu-id="3e110-115">`\\.\` や `\\?\` (mscorlib.dll のファイル I/O API の場合) を含む、完全に信頼できるデバイス パス構文がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3e110-115">Support for device path syntax in full trust, including  `\\.\` and, for file I/O APIs   in mscorlib.dll, `\\?\`.</span></span>  
  
- <span data-ttu-id="3e110-116">ランタイムではデバイス構文パスは検証されません。</span><span class="sxs-lookup"><span data-stu-id="3e110-116">The runtime does not validate device syntax paths.</span></span>  
  
- <span data-ttu-id="3e110-117">代替データ ストリームにアクセスするためのデバイス構文の使用はサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3e110-117">The use of device syntax to access alternate data streams is supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="3e110-118">影響</span><span class="sxs-lookup"><span data-stu-id="3e110-118">Impact</span></span>  

<span data-ttu-id="3e110-119">.NET Framework 4.6.2 以降を対象とするアプリでは、これらの変更は既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="3e110-119">For apps that target the .NET Framework 4.6.2 or later, these changes are on  by default.</span></span> <span data-ttu-id="3e110-120">パフォーマンスが向上すると同時に、以前はアクセス不可だったパスにメソッドでアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="3e110-120">They should improve performance while allowing methods to access previously inaccessible paths.</span></span>  
  
<span data-ttu-id="3e110-121">.NET Framework 4.6.1 以前のバージョンを対象とするアプリが .NET Framework 4.6.2 以降で実行される場合、この変更の影響は受けません。</span><span class="sxs-lookup"><span data-stu-id="3e110-121">Apps that target the .NET Framework 4.6.1 and earlier versions but are running under the .NET Framework 4.6.2 or later are unaffected by this change.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="3e110-122">軽減策</span><span class="sxs-lookup"><span data-stu-id="3e110-122">Mitigation</span></span>  
 <span data-ttu-id="3e110-123">.NET Framework 4.6.2 以降を対象とするアプリの場合、アプリケーション構成ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに次を追加することでこの変更を無効にし、従来の正規化を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e110-123">Apps that target the .NET Framework 4.6.2 or later can opt out of this change and use legacy normalization by adding the following to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
```  
  
<span data-ttu-id="3e110-124">.NET Framework 4.6.1 以前を対象とするが、.NET Framework 4.6.2 以降で実行されるアプリの場合、アプリケーション構成ファイルの [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) セクションに次を追加することで、パス正規化の変更を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="3e110-124">Apps that target the .NET Framework 4.6.1 or earlier but are running on the .NET Framework 4.6.2 or later can enable the changes to path normalization by adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the application .configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e110-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3e110-125">See also</span></span>

- [<span data-ttu-id="3e110-126">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="3e110-126">Application compatibility</span></span>](application-compatibility.md)
