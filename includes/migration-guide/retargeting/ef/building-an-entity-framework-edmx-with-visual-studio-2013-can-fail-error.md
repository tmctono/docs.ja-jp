---
ms.openlocfilehash: c5099f610569f7788bb829a2153006d20d8a4ea2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615686"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a><span data-ttu-id="79458-101">Visual Studio 2013 で Entity Framework edmx をビルドすると、EntityDeploySplit または EntityClean タスクを使用している場合、エラー MSB4062 で失敗することがある</span><span class="sxs-lookup"><span data-stu-id="79458-101">Building an Entity Framework edmx with Visual Studio 2013 can fail with error MSB4062 if using the EntityDeploySplit or EntityClean tasks</span></span>

#### <a name="details"></a><span data-ttu-id="79458-102">説明</span><span class="sxs-lookup"><span data-stu-id="79458-102">Details</span></span>

<span data-ttu-id="79458-103">MSBuild 12.0 ツール (Visual Studio 2013 に含まれる) は、MSBuild ファイルの位置を変更したため、古い Entity Framework のターゲット ファイルは無効になります。</span><span class="sxs-lookup"><span data-stu-id="79458-103">MSBuild 12.0 tools (included in Visual Studio 2013) changed MSBuild file locations, causing older Entity Framework targets files to be invalid.</span></span> <span data-ttu-id="79458-104">その結果、`EntityDeploySplit` および `EntityClean` タスクは、`Microsoft.Data.Entity.Build.Tasks.dll` を見つけられないために失敗します。</span><span class="sxs-lookup"><span data-stu-id="79458-104">The result is that `EntityDeploySplit` and `EntityClean` tasks fail because they are unable to find `Microsoft.Data.Entity.Build.Tasks.dll`.</span></span> <span data-ttu-id="79458-105">このエラーは、ツールセット (MSBuild/VS) の変更によるものであり、.NET Framework の変更によるものではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="79458-105">Note that this break is because of a toolset (MSBuild/VS) change, not because of a .NET Framework change.</span></span> <span data-ttu-id="79458-106">開発者ツールをアップグレードしたときにのみ発生し、.NET Framework をアップグレード下だけでは発生しません。</span><span class="sxs-lookup"><span data-stu-id="79458-106">It will only occur when upgrading developer tools, not when merely upgrading the .NET Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="79458-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="79458-107">Suggestion</span></span>

<span data-ttu-id="79458-108">Entity Framework のターゲット ファイルは、.NET Framework 4.6 以降の新しい MSBuild レイアウトで機能するように修正されます。</span><span class="sxs-lookup"><span data-stu-id="79458-108">Entity Framework targets files are fixed to work with the new MSBuild layout beginning in the .NET Framework 4.6.</span></span> <span data-ttu-id="79458-109">このバージョンの Framework にアップグレードすることで、この問題は修正されます。</span><span class="sxs-lookup"><span data-stu-id="79458-109">Upgrading to that version of the Framework will fix this issue.</span></span> <span data-ttu-id="79458-110">または、[この回避策](https://stackoverflow.com/a/24249247/131944)を使用して、ターゲット ファイルに直接パッチを当てることができます。</span><span class="sxs-lookup"><span data-stu-id="79458-110">Alternatively, [this workaround](https://stackoverflow.com/a/24249247/131944) can be used to patch the targets files directly.</span></span>

| <span data-ttu-id="79458-111">名前</span><span class="sxs-lookup"><span data-stu-id="79458-111">Name</span></span>    | <span data-ttu-id="79458-112">[値]</span><span class="sxs-lookup"><span data-stu-id="79458-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="79458-113">スコープ</span><span class="sxs-lookup"><span data-stu-id="79458-113">Scope</span></span>   | <span data-ttu-id="79458-114">Major</span><span class="sxs-lookup"><span data-stu-id="79458-114">Major</span></span>       |
| <span data-ttu-id="79458-115">バージョン</span><span class="sxs-lookup"><span data-stu-id="79458-115">Version</span></span> | <span data-ttu-id="79458-116">4.5.1</span><span class="sxs-lookup"><span data-stu-id="79458-116">4.5.1</span></span>       |
| <span data-ttu-id="79458-117">種類</span><span class="sxs-lookup"><span data-stu-id="79458-117">Type</span></span>    | <span data-ttu-id="79458-118">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="79458-118">Retargeting</span></span> |
