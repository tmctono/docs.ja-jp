---
ms.openlocfilehash: f87d0dbeda6094bd745f5b580772b1161f30d0d5
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86218175"
---
### <a name="change-in-path-separator-character-in-fullname-property-of-ziparchiveentry-objects"></a><span data-ttu-id="82a31-101">ZipArchiveEntry オブジェクトの FullName プロパティのパス区切り文字の変更</span><span class="sxs-lookup"><span data-stu-id="82a31-101">Change in path separator character in FullName property of ZipArchiveEntry objects</span></span>

#### <a name="details"></a><span data-ttu-id="82a31-102">説明</span><span class="sxs-lookup"><span data-stu-id="82a31-102">Details</span></span>

<span data-ttu-id="82a31-103">.NET Framework 4.6.1 以降のバージョンを対象とするアプリでは、<xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> メソッドのオーバーロードによって作成された <xref:System.IO.Compression.ZipArchiveEntry> オブジェクトの <xref:System.IO.Compression.ZipArchiveEntry.FullName> プロパティで、パスの区切り文字が円記号 ("\\") からスラッシュ ("/") に変更されています。</span><span class="sxs-lookup"><span data-stu-id="82a31-103">For apps that target the .NET Framework 4.6.1 and later versions, the path separator character has changed from a backslash ("\\") to a forward slash ("/") in the <xref:System.IO.Compression.ZipArchiveEntry.FullName> property of <xref:System.IO.Compression.ZipArchiveEntry>  objects created by overloads of the <xref:System.IO.Compression.ZipFile.CreateFromDirectory%2A> method.</span></span> <span data-ttu-id="82a31-104">この変更によって、.NET の実装が [.ZIP ファイル形式の仕様](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT)のセクション 4.4.17.1 に準拠するようになったほか、Windows 以外のシステムで ZIP アーカイブを圧縮解除できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="82a31-104">The change brings the .NET implementation into conformity with section 4.4.17.1 of the [.ZIP File Format Specification](https://pkware.cachefly.net/webdocs/casestudies/APPNOTE.TXT) and allows .ZIP archives to be decompressed on non-Windows systems.</span></span><br /><span data-ttu-id="82a31-105">Macintosh などの Windows 以外のオペレーティング システムで以前のバージョンの .NET Framework を対象とするアプリで作成された zip ファイルを圧縮解除すると、ディレクトリ構造を保持できません。</span><span class="sxs-lookup"><span data-stu-id="82a31-105">Decompressing a zip file created by an app that targets a previous version of the .NET Framework on non-Windows operating systems such as the Macintosh fails to preserve the directory structure.</span></span> <span data-ttu-id="82a31-106">たとえば、Macintosh で、ディレクトリ パスとファイル名が円記号 ("\\") 文字で連結された名前を持つ一連のファイルを作成するとします。</span><span class="sxs-lookup"><span data-stu-id="82a31-106">For example, on the Macintosh, it creates a set of files whose filename concatenates the directory path, along with any backslash ("\\") characters, and the filename.</span></span> <span data-ttu-id="82a31-107">その場合、圧縮解除されたファイルのディレクトリ構造は保持されません。</span><span class="sxs-lookup"><span data-stu-id="82a31-107">As a result, the directory structure of decompressed files is not preserved.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="82a31-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="82a31-108">Suggestion</span></span>

<span data-ttu-id="82a31-109">.NET Framework <xref:System.IO?displayProperty=nameWithType> 名前空間の API によって Windows オペレーティング システム上に展開される .zip ファイルでは、この変更の影響は最小限になるはずです。これらの API では、パスの区切り文字としてスラッシュ ("/") または円記号 ("\\") をシームレスに処理できるためです。</span><span class="sxs-lookup"><span data-stu-id="82a31-109">The impact of this change on .ZIP files that are decompressed on the Windows operating system by APIs in the .NET Framework <xref:System.IO?displayProperty=nameWithType> namespace should be minimal, since these APIs can seamlessly handle either a forward slash ("/") or a backslash ("\\") as the path separator character.</span></span><br /><span data-ttu-id="82a31-110">この変更が望ましくない場合、アプリケーション構成ファイルの [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="82a31-110">If this change is undesirable, you can opt out of it by adding a configuration setting to the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="82a31-111">次の例では、`<runtime>` セクションと無効に切り替える処理 `Switch.System.IO.Compression.ZipFile.UseBackslash` の両方を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82a31-111">The following example shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-out switch:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=true" />
</runtime>
```

<span data-ttu-id="82a31-112">また、以前のバージョンの .NET Framework を対象とするものの、.NET Framework 4.6.1 以降のバージョンで実行されているアプリでは、アプリケーション構成ファイルの [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) セクションに構成設定を追加して、この動作を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="82a31-112">In addition, apps that target previous versions of the .NET Framework but are running on the .NET Framework 4.6.1 and later versions can opt in to this behavior by adding a configuration setting to the [`<runtime>`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the application configuration file.</span></span> <span data-ttu-id="82a31-113">次では、`<runtime>` セクションと有効に切り替える処理 `Switch.System.IO.Compression.ZipFile.UseBackslash` の両方を確認できます。</span><span class="sxs-lookup"><span data-stu-id="82a31-113">The following shows both the `<runtime>` section and the `Switch.System.IO.Compression.ZipFile.UseBackslash` opt-in switch.</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.IO.Compression.ZipFile.UseBackslash=false" />
</runtime>
```

| <span data-ttu-id="82a31-114">名前</span><span class="sxs-lookup"><span data-stu-id="82a31-114">Name</span></span>    | <span data-ttu-id="82a31-115">[値]</span><span class="sxs-lookup"><span data-stu-id="82a31-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="82a31-116">スコープ</span><span class="sxs-lookup"><span data-stu-id="82a31-116">Scope</span></span>   | <span data-ttu-id="82a31-117">エッジ</span><span class="sxs-lookup"><span data-stu-id="82a31-117">Edge</span></span>        |
| <span data-ttu-id="82a31-118">バージョン</span><span class="sxs-lookup"><span data-stu-id="82a31-118">Version</span></span> | <span data-ttu-id="82a31-119">4.6.1</span><span class="sxs-lookup"><span data-stu-id="82a31-119">4.6.1</span></span>       |
| <span data-ttu-id="82a31-120">種類</span><span class="sxs-lookup"><span data-stu-id="82a31-120">Type</span></span>    | <span data-ttu-id="82a31-121">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="82a31-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="82a31-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="82a31-122">Affected APIs</span></span>

- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean)?displayProperty=nameWithType>
- <xref:System.IO.Compression.ZipFile.CreateFromDirectory(System.String,System.String,System.IO.Compression.CompressionLevel,System.Boolean,System.Text.Encoding)?displayProperty=nameWithType>
