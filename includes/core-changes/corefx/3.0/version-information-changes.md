---
ms.openlocfilehash: 5612ebce67946e22aaeeba861115ce4f8967e1f5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344454"
---
### <a name="apis-that-report-version-now-report-product-and-not-file-version"></a><span data-ttu-id="811ad-101">バージョンをレポートする API が、ファイル バージョンではなく製品をレポートするようになりました</span><span class="sxs-lookup"><span data-stu-id="811ad-101">APIs that report version now report product and not file version</span></span>

<span data-ttu-id="811ad-102">.NET Core のバージョンを返す API の多くは、ファイル バージョンではなく製品バージョンを返すようになりました。</span><span class="sxs-lookup"><span data-stu-id="811ad-102">Many of the APIs that return versions in .NET Core now return the product version rather than the file version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="811ad-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="811ad-103">Change description</span></span>

<span data-ttu-id="811ad-104">.NET Core 2.2 およびそれ以前のバージョンでは、<xref:System.Environment.Version?displayProperty=nameWithType>、<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> などのメソッドと、.NET Core アセンブリの [ファイルのプロパティ] ダイアログにファイルのバージョンが反映されています。</span><span class="sxs-lookup"><span data-stu-id="811ad-104">In .NET Core 2.2 and previous versions, methods such as <xref:System.Environment.Version?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>, and the file properties dialog for .NET Core assemblies reflect the file version.</span></span> <span data-ttu-id="811ad-105">.NET Core 3.0 以降では、製品のバージョンが反映されています。</span><span class="sxs-lookup"><span data-stu-id="811ad-105">Starting with .NET Core 3.0, they reflect the product version.</span></span>

<span data-ttu-id="811ad-106">次の図は、.NET Core 2.2 (左側) と .NET Core 3.0 (右側) の *System.Runtime.dll* アセンブリのバージョン情報の違いを示しています。これは、**Windows Explorer** [ファイルのプロパティ] ダイアログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="811ad-106">The following figure illustrates the difference in version information for the *System.Runtime.dll* assembly for .NET Core 2.2 (on the left) and .NET Core 3.0 (on the right) as displayed by the **Windows Explorer** file properties dialog.</span></span>

![製品バージョン情報の相違点](~/docs/images/core-changes/corefx/version-information-changes/file-details.png)

#### <a name="version-introduced"></a><span data-ttu-id="811ad-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="811ad-108">Version introduced</span></span>

<span data-ttu-id="811ad-109">3.0</span><span class="sxs-lookup"><span data-stu-id="811ad-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="811ad-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="811ad-110">Recommended action</span></span>

<span data-ttu-id="811ad-111">なし。</span><span class="sxs-lookup"><span data-stu-id="811ad-111">None.</span></span> <span data-ttu-id="811ad-112">この変更により、機能性ではなく、バージョン検出を直感的に行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="811ad-112">This change should make version detection intuitive rather than obtuse.</span></span>

#### <a name="category"></a><span data-ttu-id="811ad-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="811ad-113">Category</span></span>

<span data-ttu-id="811ad-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="811ad-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="811ad-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="811ad-115">Affected APIs</span></span>

- <xref:System.Environment.Version?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType>

<!--

### Affected APIs

- `P:System.Environment.Version`
- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
