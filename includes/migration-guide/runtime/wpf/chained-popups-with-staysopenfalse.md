---
ms.openlocfilehash: 7bf5f7e8a49acc2918dd0d68a1c54a5c277091b0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496124"
---
### <a name="chained-popups-with-staysopenfalse"></a><span data-ttu-id="074cc-101">StaysOpen=False でポップアップがチェーンされる</span><span class="sxs-lookup"><span data-stu-id="074cc-101">Chained Popups with StaysOpen=False</span></span>

#### <a name="details"></a><span data-ttu-id="074cc-102">説明</span><span class="sxs-lookup"><span data-stu-id="074cc-102">Details</span></span>

<span data-ttu-id="074cc-103">ポップアップの外側をクリックすると、StaysOpen=False のポップアップが閉じられることが想定されます。</span><span class="sxs-lookup"><span data-stu-id="074cc-103">A Popup with StaysOpen=False is supposed to close when you click outside the Popup.</span></span> <span data-ttu-id="074cc-104">このような 2 つ以上のポップアップがチェーンされている (つまり、1 つに別のものが含まれている) 場合、次のような、多くの問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="074cc-104">When two or more such Popups are chained (i.e. one contains another), there were many problems, including:</span></span><ul><li><span data-ttu-id="074cc-105">2 つのレベルを開き、P2 の外側と、P1 の内側をクリックします。</span><span class="sxs-lookup"><span data-stu-id="074cc-105">Open two levels, click outside P2 but inside P1.</span></span>  <span data-ttu-id="074cc-106">何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="074cc-106">Nothing happens.</span></span></li><li><span data-ttu-id="074cc-107">2 つのレベルを開き、P1 の外側をクリックします。</span><span class="sxs-lookup"><span data-stu-id="074cc-107">Open two levels, click outside P1.</span></span>  <span data-ttu-id="074cc-108">両方のポップアップが閉じます。</span><span class="sxs-lookup"><span data-stu-id="074cc-108">Both popups close.</span></span></li><li><span data-ttu-id="074cc-109">2 つのレベルを開いて閉じます。</span><span class="sxs-lookup"><span data-stu-id="074cc-109">Open and close two levels.</span></span>  <span data-ttu-id="074cc-110">次に、P2 をもう一度開いてみます。</span><span class="sxs-lookup"><span data-stu-id="074cc-110">Then try to open P2 again.</span></span>  <span data-ttu-id="074cc-111">何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="074cc-111">Nothing happens.</span></span></li><li><span data-ttu-id="074cc-112">3 つのレベルを開いてみます。</span><span class="sxs-lookup"><span data-stu-id="074cc-112">Try to open three levels.</span></span>  <span data-ttu-id="074cc-113">この操作を行うことはできません</span><span class="sxs-lookup"><span data-stu-id="074cc-113">You can't.</span></span>  <span data-ttu-id="074cc-114">(クリックする場所に応じて、何も起こらないか、最初の 2 つのレベルが閉じます)。このような場合 (および他のバリアント) は、予期したとおり動作します。</span><span class="sxs-lookup"><span data-stu-id="074cc-114">(Either nothing happens or the first two levels close, depending on where you click.) These cases (and other variants) now work as expected.</span></span></li></ul>

| <span data-ttu-id="074cc-115">名前</span><span class="sxs-lookup"><span data-stu-id="074cc-115">Name</span></span>    | <span data-ttu-id="074cc-116">値</span><span class="sxs-lookup"><span data-stu-id="074cc-116">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="074cc-117">スコープ</span><span class="sxs-lookup"><span data-stu-id="074cc-117">Scope</span></span>   |<span data-ttu-id="074cc-118">エッジ</span><span class="sxs-lookup"><span data-stu-id="074cc-118">Edge</span></span>|
|<span data-ttu-id="074cc-119">バージョン</span><span class="sxs-lookup"><span data-stu-id="074cc-119">Version</span></span>|<span data-ttu-id="074cc-120">4.7.1</span><span class="sxs-lookup"><span data-stu-id="074cc-120">4.7.1</span></span>|
|<span data-ttu-id="074cc-121">種類</span><span class="sxs-lookup"><span data-stu-id="074cc-121">Type</span></span>|<span data-ttu-id="074cc-122">ランタイム</span><span class="sxs-lookup"><span data-stu-id="074cc-122">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="074cc-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="074cc-123">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.Popup.StaysOpen?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Windows.Controls.Primitives.Popup.StaysOpen`

-->
