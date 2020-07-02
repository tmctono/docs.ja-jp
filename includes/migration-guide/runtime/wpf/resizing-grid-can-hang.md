---
ms.openlocfilehash: 86169b5c9a20678647153c951550e590a5bce588
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622256"
---
### <a name="resizing-a-grid-can-hang"></a><span data-ttu-id="52dfc-101">グリッドのサイズを変更すると、ハングする可能性がある</span><span class="sxs-lookup"><span data-stu-id="52dfc-101">Resizing a Grid can hang</span></span>

#### <a name="details"></a><span data-ttu-id="52dfc-102">説明</span><span class="sxs-lookup"><span data-stu-id="52dfc-102">Details</span></span>

<span data-ttu-id="52dfc-103">次の状況では、<code>T:System.Windows.Controls.Grid</code> のレイアウト中に無限ループが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="52dfc-103">An infinite loop can occur during layout of a <code>T:System.Windows.Controls.Grid</code> under the following circumstances:</span></span><ul><li><span data-ttu-id="52dfc-104">行の定義に、MinHeight と MaxHeight の両方を宣言する、2 つの \*-row が含まれている。</span><span class="sxs-lookup"><span data-stu-id="52dfc-104">Row definitions contain two \*-rows, both declaring a MinHeight and a MaxHeight.</span></span></li><li><span data-ttu-id="52dfc-105">\*-row の内容が対応する MaxHeight を超えていない</span><span class="sxs-lookup"><span data-stu-id="52dfc-105">Content of the \*-rows doesn't exceed the corresponding MaxHeight</span></span></li><li><span data-ttu-id="52dfc-106">最初の MinHeight (その他の固定または自動の行を含む) がグリッドの利用可能な高さを超えている。</span><span class="sxs-lookup"><span data-stu-id="52dfc-106">The Grid's available height is exceeded by the first MinHeight (plus any other fixed or Auto rows)</span></span></li><li><span data-ttu-id="52dfc-107">アプリの対象を .NET Framework 4.7 とする、または <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code> を設定して、4.7 割り当てアルゴリズムを利用することを選択する。</span><span class="sxs-lookup"><span data-stu-id="52dfc-107">The app targets .NET Framework 4.7, or opts in to the 4.7 allocation algorithm by setting <code>Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=false</code></span></span></li></ul><span data-ttu-id="52dfc-108">また、3 つ以上の行または列でループが発生します。</span><span class="sxs-lookup"><span data-stu-id="52dfc-108">The loop would also happen with more than two rows, or in the analogous case for columns.</span></span> <span data-ttu-id="52dfc-109">この問題は .NET Framework 4.7.1 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="52dfc-109">The issue is fixed in .NET Framework 4.7.1.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="52dfc-110">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="52dfc-110">Suggestion</span></span>

<span data-ttu-id="52dfc-111">.NET Framework 4.7.1 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="52dfc-111">Upgrade to .NET Framework 4.7.1.</span></span>  <span data-ttu-id="52dfc-112">4\.7 割り当てアルゴリズムが必要でない場合は、次の構成設定を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="52dfc-112">Alternatively, if you don't need the 4.7 allocation algorithm you can use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.Grid.StarDefinitionsCanExceedAvailableSpace=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="52dfc-113">名前</span><span class="sxs-lookup"><span data-stu-id="52dfc-113">Name</span></span>    | <span data-ttu-id="52dfc-114">値</span><span class="sxs-lookup"><span data-stu-id="52dfc-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="52dfc-115">スコープ</span><span class="sxs-lookup"><span data-stu-id="52dfc-115">Scope</span></span>   |<span data-ttu-id="52dfc-116">エッジ</span><span class="sxs-lookup"><span data-stu-id="52dfc-116">Edge</span></span>|
|<span data-ttu-id="52dfc-117">バージョン</span><span class="sxs-lookup"><span data-stu-id="52dfc-117">Version</span></span>|<span data-ttu-id="52dfc-118">4.7</span><span class="sxs-lookup"><span data-stu-id="52dfc-118">4.7</span></span>|
|<span data-ttu-id="52dfc-119">種類</span><span class="sxs-lookup"><span data-stu-id="52dfc-119">Type</span></span>|<span data-ttu-id="52dfc-120">ランタイム</span><span class="sxs-lookup"><span data-stu-id="52dfc-120">Runtime</span></span>|
