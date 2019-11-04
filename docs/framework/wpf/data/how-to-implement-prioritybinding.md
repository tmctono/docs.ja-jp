---
title: '方法 : PriorityBinding を実装する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
ms.openlocfilehash: 343b0aca4736905f3a0cbff5a0f76b170da0c920
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459785"
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="635fa-102">方法 : PriorityBinding を実装する</span><span class="sxs-lookup"><span data-stu-id="635fa-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="635fa-103">[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] の <xref:System.Windows.Data.PriorityBinding> は、バインドの一覧を指定することによって機能します。</span><span class="sxs-lookup"><span data-stu-id="635fa-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="635fa-104">バインドの一覧は、優先順位が最も高い順に並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="635fa-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="635fa-105">最も優先順位の高いバインドが処理時に値を正常に返す場合、リスト内の他のバインドを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="635fa-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="635fa-106">最も優先度の高いバインドが評価されるまでに長い時間がかかる場合もありますが、高い優先順位のバインドによって値が正常に返されるまで、値が正常に返される次に高い優先順位が使用されます。</span><span class="sxs-lookup"><span data-stu-id="635fa-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="635fa-107">例</span><span class="sxs-lookup"><span data-stu-id="635fa-107">Example</span></span>  
 <span data-ttu-id="635fa-108"><xref:System.Windows.Data.PriorityBinding> のしくみを示すために、`AsyncDataSource` オブジェクトは、`FastDP`、`SlowerDP`、および `SlowestDP`の3つのプロパティを使用して作成されています。</span><span class="sxs-lookup"><span data-stu-id="635fa-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="635fa-109">`FastDP` の get アクセサーは、`_fastDP` データメンバーの値を返します。</span><span class="sxs-lookup"><span data-stu-id="635fa-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="635fa-110">`SlowerDP` の get アクセサーは、`_slowerDP` データメンバーの値を返す前に3秒間待機します。</span><span class="sxs-lookup"><span data-stu-id="635fa-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="635fa-111">`SlowestDP` の get アクセサーは、5秒間待機してから `_slowestDP` データメンバーの値を返します。</span><span class="sxs-lookup"><span data-stu-id="635fa-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="635fa-112">この例は、デモンストレーション目的のみで提供されます。</span><span class="sxs-lookup"><span data-stu-id="635fa-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="635fa-113">.NET ガイドラインでは、フィールドセットよりも速度が低いプロパティを定義することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="635fa-113">The .NET guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="635fa-114">詳細については、「[プロパティとメソッドの選択](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="635fa-114">For more information, see [Choosing Between Properties and Methods](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms229054(v=vs.100)).</span></span>  
  
 [!code-csharp[PriorityBinding#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="635fa-115"><xref:System.Windows.Controls.TextBlock.Text%2A> プロパティは <xref:System.Windows.Data.PriorityBinding>を使用して上記の `AsyncDS` にバインドされます。</span><span class="sxs-lookup"><span data-stu-id="635fa-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="635fa-116">バインドエンジンは、<xref:System.Windows.Data.Binding> オブジェクトを処理するときに、最初の <xref:System.Windows.Data.Binding>から開始します。これは `SlowestDP` プロパティにバインドされています。</span><span class="sxs-lookup"><span data-stu-id="635fa-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="635fa-117">この <xref:System.Windows.Data.Binding> が処理されると、5秒間スリープ状態になっているため、値は正常に返されません。そのため、次の <xref:System.Windows.Data.Binding> 要素が処理されます。</span><span class="sxs-lookup"><span data-stu-id="635fa-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="635fa-118">次の <xref:System.Windows.Data.Binding> では、3秒間スリープ状態になるため、値は正常に返されません。</span><span class="sxs-lookup"><span data-stu-id="635fa-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="635fa-119">バインドエンジンは、次の <xref:System.Windows.Data.Binding> 要素に移動します。この要素は、`FastDP` プロパティにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="635fa-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="635fa-120">この <xref:System.Windows.Data.Binding> は、値 "Fast Value" を返します。</span><span class="sxs-lookup"><span data-stu-id="635fa-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="635fa-121"><xref:System.Windows.Controls.TextBlock> に "Fast Value" という値が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="635fa-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="635fa-122">3秒が経過すると、`SlowerDP` プロパティは値 "低速値" を返します。</span><span class="sxs-lookup"><span data-stu-id="635fa-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="635fa-123"><xref:System.Windows.Controls.TextBlock> に、値 "低速値" が表示されます。</span><span class="sxs-lookup"><span data-stu-id="635fa-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="635fa-124">5秒が経過すると、`SlowestDP` プロパティによって "低速値" という値が返されます。</span><span class="sxs-lookup"><span data-stu-id="635fa-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="635fa-125">最初にリストされているので、そのバインディングの優先順位は最も高くなります。</span><span class="sxs-lookup"><span data-stu-id="635fa-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="635fa-126"><xref:System.Windows.Controls.TextBlock> に "低速値" という値が表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="635fa-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="635fa-127">バインドから成功した戻り値と見なされる内容については、「<xref:System.Windows.Data.PriorityBinding>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="635fa-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635fa-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="635fa-128">See also</span></span>

- <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>
- [<span data-ttu-id="635fa-129">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="635fa-129">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="635fa-130">方法トピック</span><span class="sxs-lookup"><span data-stu-id="635fa-130">How-to Topics</span></span>](data-binding-how-to-topics.md)
