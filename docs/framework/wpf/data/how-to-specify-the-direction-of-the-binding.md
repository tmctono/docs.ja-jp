---
title: '方法 : バインディングの方向を指定する'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 8f7d843382ee3409047d7cf9549267d582883984
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459099"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="1cd37-102">方法: バインディングの方向を指定する</span><span class="sxs-lookup"><span data-stu-id="1cd37-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="1cd37-103">この例では、バインドの更新先 (バインディング ターゲット (ターゲット) のプロパティのみ、バインディング ソース (ソース) のプロパティのみ、またはターゲットのプロパティとソースのプロパティの両方) を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cd37-104">例</span><span class="sxs-lookup"><span data-stu-id="1cd37-104">Example</span></span>  
 <span data-ttu-id="1cd37-105">バインディングの方向を指定するには、<xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="1cd37-106">更新プログラムのバインドに使用できるオプションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="1cd37-107">ターゲットプロパティまたはソースプロパティが変更されるたびに、<xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> はターゲットプロパティまたはプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="1cd37-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> は、ソースプロパティが変更された場合にのみターゲットプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="1cd37-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> は、アプリケーションが起動したとき、または <xref:System.Windows.FrameworkElement.DataContext%2A> が変更されたときにのみ、ターゲットプロパティを更新します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="1cd37-110">ターゲットプロパティが変更されると、<xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> によって source プロパティが更新されます。</span><span class="sxs-lookup"><span data-stu-id="1cd37-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="1cd37-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> を指定すると、target プロパティの既定の <xref:System.Windows.Data.Binding.Mode%2A> 値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1cd37-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="1cd37-112">詳細については、<xref:System.Windows.Data.BindingMode> 列挙型のページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1cd37-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="1cd37-113"><xref:System.Windows.Data.Binding.Mode%2A> プロパティを設定する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="1cd37-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="1cd37-114">ソースの変更を検出するには (<xref:System.Windows.Data.BindingMode.OneWay> および <xref:System.Windows.Data.BindingMode.TwoWay> バインドに適用)、ソースは <xref:System.ComponentModel.INotifyPropertyChanged>などの適切なプロパティ変更通知メカニズムを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd37-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="1cd37-115"><xref:System.ComponentModel.INotifyPropertyChanged> 実装の例については、「[プロパティ変更通知の実装](how-to-implement-property-change-notification.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd37-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="1cd37-116"><xref:System.Windows.Data.BindingMode.TwoWay> または <xref:System.Windows.Data.BindingMode.OneWayToSource> のバインドの場合、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティを設定することによって、ソースの更新のタイミングを制御できます。</span><span class="sxs-lookup"><span data-stu-id="1cd37-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="1cd37-117">詳細については、「<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1cd37-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cd37-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="1cd37-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="1cd37-119">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="1cd37-119">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1cd37-120">方法トピック</span><span class="sxs-lookup"><span data-stu-id="1cd37-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
