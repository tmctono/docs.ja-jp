---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538821"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="14bb3-101">Directory.Packages.props ファイルが既定でインポートされる</span><span class="sxs-lookup"><span data-stu-id="14bb3-101">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="14bb3-102">NuGet の *.props* ファイルでは、*Directory.Packages.props* という名前のファイルがプロジェクト フォルダーまたはその先祖に含まれている場合は、そのファイルのインポートが自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="14bb3-102">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="14bb3-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="14bb3-103">Version introduced</span></span>

<span data-ttu-id="14bb3-104">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="14bb3-104">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="14bb3-105">変更内容</span><span class="sxs-lookup"><span data-stu-id="14bb3-105">Change description</span></span>

<span data-ttu-id="14bb3-106">以前の .NET バージョンでは、*Directory.Packages.props* という名前のファイルをプロジェクト ファイルに含めることができ、ビルド時に NuGet の *.props* によって自動的にインポートされることはありませんでした。</span><span class="sxs-lookup"><span data-stu-id="14bb3-106">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="14bb3-107">.NET 5.0 以降では、このようなファイルがプロジェクト フォルダーまたはその先祖に存在している場合は、そのファイルのインポートが自動的に "*行われます*"。</span><span class="sxs-lookup"><span data-stu-id="14bb3-107">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="14bb3-108">この名前のファイルがプロジェクト フォルダーにある場合は、この自動インポート機能によってビルドの動作が変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14bb3-108">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="14bb3-109">たとえば、そのファイルは今後インポートされるものの以前はインポートされていなかったか、明示的にインポートした場合にインポートされる順序が変わるなどします。</span><span class="sxs-lookup"><span data-stu-id="14bb3-109">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="14bb3-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="14bb3-110">Reason for change</span></span>

<span data-ttu-id="14bb3-111">この変更は、NuGet を対象とした[パッケージのバージョン集中管理](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions)をサポートするために行われました。</span><span class="sxs-lookup"><span data-stu-id="14bb3-111">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="14bb3-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="14bb3-112">Recommended action</span></span>

<span data-ttu-id="14bb3-113">既存の *Directory.Packages.props* ファイルが自動的にインポートされないようにする場合は、そのファイルの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="14bb3-113">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

#### <a name="category"></a><span data-ttu-id="14bb3-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="14bb3-114">Category</span></span>

<span data-ttu-id="14bb3-115">MSBuild</span><span class="sxs-lookup"><span data-stu-id="14bb3-115">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14bb3-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="14bb3-116">Affected APIs</span></span>

<span data-ttu-id="14bb3-117">N/A</span><span class="sxs-lookup"><span data-stu-id="14bb3-117">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
