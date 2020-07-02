---
ms.openlocfilehash: 06c699281c8890ac65be1d282b72b54774acc280
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620474"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="633fe-101">WPF DataTemplate 要素が UIA に表示されるようになった</span><span class="sxs-lookup"><span data-stu-id="633fe-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="633fe-102">説明</span><span class="sxs-lookup"><span data-stu-id="633fe-102">Details</span></span>

<span data-ttu-id="633fe-103">以前は、<xref:System.Windows.DataTemplate?displayProperty=fullName> 要素は UI オートメーションには表示されませんでした。</span><span class="sxs-lookup"><span data-stu-id="633fe-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="633fe-104">4\.5 から、UI オートメーションは、これらの要素を検出します。</span><span class="sxs-lookup"><span data-stu-id="633fe-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="633fe-105">これは、多くの場合に便利ですが、<xref:System.Windows.DataTemplate?displayProperty=fullName> 要素を含まない UIA ツリーに依存するテストは中断することがあります。</span><span class="sxs-lookup"><span data-stu-id="633fe-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="633fe-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="633fe-106">Suggestion</span></span>

<span data-ttu-id="633fe-107">このアプリの UI オートメーション テストを更新して、以前は非表示の <xref:System.Windows.DataTemplate?displayProperty=fullName> 要素を含んでいる UIA ツリーに対応できるようにしなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="633fe-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="633fe-108">たとえば、いくつかの要素が互いに隣り合っていることを予期しているテストでは、以前は非表示であった UIA 要素が間にあることを予期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="633fe-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="633fe-109">または、UIA 要素の特定のカウントまたはインデックスに依存するテストは、新しい値で更新しなければならないことがあります。</span><span class="sxs-lookup"><span data-stu-id="633fe-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="633fe-110">名前</span><span class="sxs-lookup"><span data-stu-id="633fe-110">Name</span></span>    | <span data-ttu-id="633fe-111">[値]</span><span class="sxs-lookup"><span data-stu-id="633fe-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="633fe-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="633fe-112">Scope</span></span>   |<span data-ttu-id="633fe-113">エッジ</span><span class="sxs-lookup"><span data-stu-id="633fe-113">Edge</span></span>|
|<span data-ttu-id="633fe-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="633fe-114">Version</span></span>|<span data-ttu-id="633fe-115">4.5</span><span class="sxs-lookup"><span data-stu-id="633fe-115">4.5</span></span>|
|<span data-ttu-id="633fe-116">種類</span><span class="sxs-lookup"><span data-stu-id="633fe-116">Type</span></span>|<span data-ttu-id="633fe-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="633fe-117">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="633fe-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="633fe-118">Affected APIs</span></span>

-<xref:System.Windows.DataTemplate.%23ctor></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)></li></ul>|
