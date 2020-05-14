---
title: '方法: TextBox テキストでソースを更新するタイミングを制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974781"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="7fff5-102">方法: TextBox テキストでソースを更新するタイミングを制御する</span><span class="sxs-lookup"><span data-stu-id="7fff5-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="7fff5-103">このトピックでは、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティを使用して、バインディング ソースの更新のタイミングを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="7fff5-104">このトピックでは、例として <xref:System.Windows.Controls.TextBox> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>

## <a name="example"></a><span data-ttu-id="7fff5-105">例</span><span class="sxs-lookup"><span data-stu-id="7fff5-105">Example</span></span>
 <span data-ttu-id="7fff5-106"><xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> プロパティの <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> の既定値は <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus> です。</span><span class="sxs-lookup"><span data-stu-id="7fff5-106">The <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="7fff5-107">つまり、アプリケーションにデータ バインドされた <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> プロパティを持つ <xref:System.Windows.Controls.TextBox> がある場合、<xref:System.Windows.Controls.TextBox> がフォーカスを失うまで (たとえば、<xref:System.Windows.Controls.TextBox> からクリックして移動したとき)、<xref:System.Windows.Controls.TextBox> に入力したテキストでソースは更新されません。</span><span class="sxs-lookup"><span data-stu-id="7fff5-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>

 <span data-ttu-id="7fff5-108">入力したらソースが更新されるようにしたい場合は、バインディングの <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> を <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> に設定します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="7fff5-109">次の例の強調表示されているコード行は、<xref:System.Windows.Controls.TextBox> と <xref:System.Windows.Controls.TextBlock> 両方の `Text` プロパティが、同じソース プロパティにバインドされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="7fff5-110"><xref:System.Windows.Controls.TextBox> バインディングの <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティは、<xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> に設定されています。</span><span class="sxs-lookup"><span data-stu-id="7fff5-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 <span data-ttu-id="7fff5-111">結果として、次のスクリーンショットの例に示すように、<xref:System.Windows.Controls.TextBlock> には、ユーザーが <xref:System.Windows.Controls.TextBox> に入力したのと同じテキストが表示されます (ソースが変更されるため)。</span><span class="sxs-lookup"><span data-stu-id="7fff5-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>

 ![簡単なデータ バインディングを示すスクリーンショット。](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 <span data-ttu-id="7fff5-113">ダイアログまたはユーザーが編集できるフォームがあり、ユーザーがフィールドの編集を終えて [OK] をクリックするまでソースの更新を遅延させる場合は、次の例のように、バインディングの <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> の値を <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> に設定します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 <span data-ttu-id="7fff5-114"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> の値を <xref:System.Windows.Data.UpdateSourceTrigger.Explicit> に設定すると、ソースの値は、アプリケーションで <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> メソッドが呼び出された場合にのみ変更されます。</span><span class="sxs-lookup"><span data-stu-id="7fff5-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="7fff5-115">次の例では、`itemNameTextBox` に対して <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> を呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> <span data-ttu-id="7fff5-116">他のコントロールのプロパティにも同じ手法を使用できますが、他のほとんどのプロパティでは <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged> の既定値が <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fff5-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="7fff5-117">詳細については、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティのページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fff5-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>

> [!NOTE]
> <span data-ttu-id="7fff5-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティではソースの更新が処理されるため、このプロパティは <xref:System.Windows.Data.BindingMode.TwoWay> または <xref:System.Windows.Data.BindingMode.OneWayToSource> のバインディングにのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="7fff5-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="7fff5-119"><xref:System.Windows.Data.BindingMode.TwoWay> および <xref:System.Windows.Data.BindingMode.OneWayToSource> のバインディングを機能させるには、ソース オブジェクトでプロパティ変更通知を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fff5-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="7fff5-120">詳しくは、このトピック内にあるサンプルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7fff5-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="7fff5-121">また、「[方法 : プロパティの変更通知を実装する](how-to-implement-property-change-notification.md)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7fff5-121">In addition, you can look at [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fff5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fff5-122">See also</span></span>

- [<span data-ttu-id="7fff5-123">方法トピック</span><span class="sxs-lookup"><span data-stu-id="7fff5-123">How-to Topics</span></span>](data-binding-how-to-topics.md)
