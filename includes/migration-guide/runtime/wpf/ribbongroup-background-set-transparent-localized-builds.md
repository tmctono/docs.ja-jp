---
ms.openlocfilehash: d6405573e476ce18513938b500041adefbeeef1b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496173"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a><span data-ttu-id="23526-101">ローカライズされたビルドで RibbonGroup の背景が透明に設定される</span><span class="sxs-lookup"><span data-stu-id="23526-101">RibbonGroup background is set to transparent in localized builds</span></span>

#### <a name="details"></a><span data-ttu-id="23526-102">説明</span><span class="sxs-lookup"><span data-stu-id="23526-102">Details</span></span>

<span data-ttu-id="23526-103">ローカライズされたビルドの <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> の背景が常に透明のブラシで塗りつぶされており、UI の操作性が低下していました。</span><span class="sxs-lookup"><span data-stu-id="23526-103"><xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> background on localized builds was always painted with Transparent brush, resulting in poor UI experience.</span></span> <span data-ttu-id="23526-104">これは、.NET Framework 4.7 WPF 修正プログラムで修正されます。<xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName> のローカライズされたリソースが更新され、正しいブラシが確実に選択されるようになります。</span><span class="sxs-lookup"><span data-stu-id="23526-104">This is fixed in .NET Framework 4.7 WPF fix by updating the localized resources for <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=fullName>, which in turn ensures that the correct brush is selected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="23526-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="23526-105">Suggestion</span></span>

<span data-ttu-id="23526-106">.NET Framework 4.7 にアップグレードします</span><span class="sxs-lookup"><span data-stu-id="23526-106">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="23526-107">名前</span><span class="sxs-lookup"><span data-stu-id="23526-107">Name</span></span>    | <span data-ttu-id="23526-108">値</span><span class="sxs-lookup"><span data-stu-id="23526-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="23526-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="23526-109">Scope</span></span>   |<span data-ttu-id="23526-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="23526-110">Edge</span></span>|
|<span data-ttu-id="23526-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="23526-111">Version</span></span>|<span data-ttu-id="23526-112">4.6.2</span><span class="sxs-lookup"><span data-stu-id="23526-112">4.6.2</span></span>|
|<span data-ttu-id="23526-113">種類</span><span class="sxs-lookup"><span data-stu-id="23526-113">Type</span></span>|<span data-ttu-id="23526-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="23526-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="23526-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="23526-115">Affected APIs</span></span>

<span data-ttu-id="23526-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="23526-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
