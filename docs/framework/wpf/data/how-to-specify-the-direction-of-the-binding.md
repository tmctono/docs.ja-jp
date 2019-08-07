---
title: '方法: バインディングの方向を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 023cd42ad5fb321e7ffa65f08673cb4145f49af4
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817912"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="1846f-102">方法: バインディングの方向を指定します</span><span class="sxs-lookup"><span data-stu-id="1846f-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="1846f-103">この例では、バインドの更新先 (バインディング ターゲット (ターゲット) のプロパティのみ、バインディング ソース (ソース) のプロパティのみ、またはターゲットのプロパティとソースのプロパティの両方) を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1846f-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1846f-104">例</span><span class="sxs-lookup"><span data-stu-id="1846f-104">Example</span></span>  
 <span data-ttu-id="1846f-105">バインディングの方向<xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType>を指定するには、プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="1846f-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="1846f-106">更新プログラムのバインドに使用できるオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1846f-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="1846f-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType>ターゲットプロパティまたはソースプロパティが変更されるたびに、ターゲットプロパティまたはプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1846f-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="1846f-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType>ソースプロパティが変更された場合にのみ、ターゲットプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1846f-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="1846f-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType>アプリケーションが開始されたとき、またはが<xref:System.Windows.FrameworkElement.DataContext%2A>変更を行ったときにのみ、ターゲットプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1846f-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="1846f-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType>ターゲットプロパティが変更されたときに、source プロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1846f-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="1846f-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType>ターゲットプロパティの<xref:System.Windows.Data.Binding.Mode%2A>既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1846f-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="1846f-112">詳細については、<xref:System.Windows.Data.BindingMode> 列挙型のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1846f-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="1846f-113"><xref:System.Windows.Data.Binding.Mode%2A> プロパティを設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1846f-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="1846f-114">ソースの変更 (および<xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay>バインドに適用可能) を検出するには、ソースがなど<xref:System.ComponentModel.INotifyPropertyChanged>の適切なプロパティ変更通知機構を実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1846f-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="1846f-115"><xref:System.ComponentModel.INotifyPropertyChanged>実装の例については、「[プロパティ変更通知の実装](how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1846f-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="1846f-116">また<xref:System.Windows.Data.BindingMode.TwoWay>は<xref:System.Windows.Data.BindingMode.OneWayToSource>のバインドでは、 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>プロパティを設定することによって、ソースの更新のタイミングを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1846f-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="1846f-117">詳細については、「<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1846f-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1846f-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1846f-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="1846f-119">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="1846f-119">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="1846f-120">方法トピック</span><span class="sxs-lookup"><span data-stu-id="1846f-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
