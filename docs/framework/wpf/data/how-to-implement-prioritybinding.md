---
title: '方法: PriorityBinding を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 4be1ce434eb1e169e8a19b56c92ca1efb48773d2
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169081"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="25c82-102">方法: PriorityBinding を実装する</span><span class="sxs-lookup"><span data-stu-id="25c82-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="25c82-103"><xref:System.Windows.Data.PriorityBinding>で[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]は、バインドのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="25c82-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="25c82-104">バインドの一覧は、優先順位が最も高い順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="25c82-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="25c82-105">最も優先順位の高いバインドが処理時に値を正常に返す場合、リスト内の他のバインドを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="25c82-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="25c82-106">最も優先度の高いバインドが評価されるまでに長い時間がかかる場合もありますが、高い優先順位のバインドによって値が正常に返されるまで、値が正常に返される次に高い優先順位が使用されます。</span><span class="sxs-lookup"><span data-stu-id="25c82-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25c82-107">例</span><span class="sxs-lookup"><span data-stu-id="25c82-107">Example</span></span>  
 <span data-ttu-id="25c82-108">がどのよう<xref:System.Windows.Data.PriorityBinding>に機能`AsyncDataSource`するかを示すために、オブジェクトは`FastDP`、 `SlowerDP`、、および`SlowestDP`の3つのプロパティを使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="25c82-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="25c82-109">の`FastDP` get アクセサーは、 `_fastDP`データメンバーの値を返します。</span><span class="sxs-lookup"><span data-stu-id="25c82-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="25c82-110">の`SlowerDP` get アクセサーは、 `_slowerDP`データメンバーの値を返す前に3秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="25c82-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="25c82-111">の`SlowestDP` get アクセサーは、5秒間待機してから、 `_slowestDP`データメンバーの値を返します。</span><span class="sxs-lookup"><span data-stu-id="25c82-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25c82-112">この例は、デモンストレーション目的のみで提供されます。</span><span class="sxs-lookup"><span data-stu-id="25c82-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="25c82-113">.NET ガイドラインでは、フィールドセットよりも速度が低いプロパティを定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="25c82-113">The .NET guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="25c82-114">詳細については、「[プロパティとメソッドの選択](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25c82-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="25c82-115">プロパティ<xref:System.Windows.Controls.TextBlock.Text%2A>は、を使用し`AsyncDS`て<xref:System.Windows.Data.PriorityBinding>上記のにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="25c82-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="25c82-116">バインディングエンジンは、 <xref:System.Windows.Data.Binding>オブジェクトを処理するときに、 `SlowestDP`プロパティに<xref:System.Windows.Data.Binding>バインドされている最初のから開始します。</span><span class="sxs-lookup"><span data-stu-id="25c82-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="25c82-117">この<xref:System.Windows.Data.Binding>処理が完了すると、5秒間スリープ状態になるため、値は正常に返されませ<xref:System.Windows.Data.Binding>ん。そのため、次の要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="25c82-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="25c82-118">次<xref:System.Windows.Data.Binding>のは、3秒間スリープ状態になるため、値を正常に返しません。</span><span class="sxs-lookup"><span data-stu-id="25c82-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="25c82-119">バインドエンジンは、 <xref:System.Windows.Data.Binding> `FastDP`プロパティにバインドされている次の要素に移動します。</span><span class="sxs-lookup"><span data-stu-id="25c82-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="25c82-120">これ<xref:System.Windows.Data.Binding>により、"Fast value" という値が返されます。</span><span class="sxs-lookup"><span data-stu-id="25c82-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="25c82-121">で<xref:System.Windows.Controls.TextBlock>値 "Fast value" が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="25c82-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="25c82-122">3秒が経過すると`SlowerDP` 、プロパティは値 "低速値" を返します。</span><span class="sxs-lookup"><span data-stu-id="25c82-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="25c82-123">次<xref:System.Windows.Controls.TextBlock>に、値 "低速値" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="25c82-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="25c82-124">5秒が経過すると`SlowestDP` 、プロパティは "低速値" という値を返します。</span><span class="sxs-lookup"><span data-stu-id="25c82-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="25c82-125">最初にリストされているので、そのバインディングの優先順位は最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="25c82-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="25c82-126">で<xref:System.Windows.Controls.TextBlock>は、"低速値" という値が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="25c82-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="25c82-127">バインディング<xref:System.Windows.Data.PriorityBinding>から成功した戻り値と見なされる内容については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25c82-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25c82-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="25c82-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="25c82-129">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="25c82-129">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="25c82-130">方法トピック</span><span class="sxs-lookup"><span data-stu-id="25c82-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
