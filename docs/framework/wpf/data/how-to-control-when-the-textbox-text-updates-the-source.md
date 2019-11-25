---
title: '方法 : TextBox テキストでソースを更新するタイミングを制御する'
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974781"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a><span data-ttu-id="97819-102">方法 : TextBox テキストでソースを更新するタイミングを制御する</span><span class="sxs-lookup"><span data-stu-id="97819-102">How to: Control When the TextBox Text Updates the Source</span></span>
<span data-ttu-id="97819-103">このトピックでは、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティを使用して、バインディングソースの更新のタイミングを制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="97819-103">This topic describes how to use the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property to control the timing of binding source updates.</span></span> <span data-ttu-id="97819-104">このトピックでは、例として <xref:System.Windows.Controls.TextBox> コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="97819-104">The topic uses the <xref:System.Windows.Controls.TextBox> control as an example.</span></span>

## <a name="example"></a><span data-ttu-id="97819-105">例</span><span class="sxs-lookup"><span data-stu-id="97819-105">Example</span></span>
 <span data-ttu-id="97819-106"><xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> プロパティには、<xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>の既定の <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 値が設定されています。</span><span class="sxs-lookup"><span data-stu-id="97819-106">The <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property has a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>.</span></span> <span data-ttu-id="97819-107">つまり、アプリケーションにデータバインド <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> プロパティを持つ <xref:System.Windows.Controls.TextBox> がある場合、<xref:System.Windows.Controls.TextBox> に入力したテキストは、<xref:System.Windows.Controls.TextBox> がフォーカスを失うまで (たとえば、<xref:System.Windows.Controls.TextBox>から離れたときに) ソースを更新しません。</span><span class="sxs-lookup"><span data-stu-id="97819-107">This means if an application has a <xref:System.Windows.Controls.TextBox> with a data-bound <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> property, the text you type into the <xref:System.Windows.Controls.TextBox> does not update the source until the <xref:System.Windows.Controls.TextBox> loses focus (for instance, when you click away from the <xref:System.Windows.Controls.TextBox>).</span></span>

 <span data-ttu-id="97819-108">入力時にソースを更新する場合は、バインドの <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> を <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>に設定します。</span><span class="sxs-lookup"><span data-stu-id="97819-108">If you want the source to be updated as you type, set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> of the binding to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="97819-109">次の例では、強調表示されているコード行は、<xref:System.Windows.Controls.TextBox> と <xref:System.Windows.Controls.TextBlock> の両方の `Text` プロパティが同じソースプロパティにバインドされていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="97819-109">In the following example, the highlighted lines of code show that the `Text` properties of both the <xref:System.Windows.Controls.TextBox> and the <xref:System.Windows.Controls.TextBlock> are bound to the same source property.</span></span> <span data-ttu-id="97819-110"><xref:System.Windows.Controls.TextBox> binding の <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティは <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>に設定されています。</span><span class="sxs-lookup"><span data-stu-id="97819-110">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property of the <xref:System.Windows.Controls.TextBox> binding is set to <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span>

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 <span data-ttu-id="97819-111">その結果、次のサンプルのスクリーンショットに示すように、ユーザーが <xref:System.Windows.Controls.TextBox>にテキストを入力すると、<xref:System.Windows.Controls.TextBlock> に同じテキスト (ソースが変更されたため) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="97819-111">As a result, the <xref:System.Windows.Controls.TextBlock> shows the same text (because the source changes) as the user enters text into the <xref:System.Windows.Controls.TextBox>, as illustrated by the following screenshot of the sample:</span></span>

 ![単純なデータバインディングを示すスクリーンショット。](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 <span data-ttu-id="97819-113">ダイアログまたはユーザーが編集可能なフォームがあり、ユーザーがフィールドの編集を完了して [OK] をクリックするまでソースの更新を延期する場合は、次の例に示すように、バインドの <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 値を <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>に設定できます。</span><span class="sxs-lookup"><span data-stu-id="97819-113">If you have a dialog or a user-editable form and you want to defer source updates until the user is finished editing the fields and clicks "OK", you can set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of your bindings to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, as in the following example:</span></span>

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 <span data-ttu-id="97819-114"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 値を <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>に設定すると、アプリケーションが <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> メソッドを呼び出した場合にのみ、ソース値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="97819-114">When you set the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value to <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, the source value only changes when the application calls the <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> method.</span></span> <span data-ttu-id="97819-115">次の例は、`itemNameTextBox`に対して <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> を呼び出す方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="97819-115">The following example shows how to call <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> for `itemNameTextBox`:</span></span>

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> <span data-ttu-id="97819-116">他のコントロールのプロパティにも同じ手法を使用できますが、その他のほとんどのプロパティには <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>の既定の <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 値があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="97819-116">You can use the same technique for properties of other controls, but keep in mind that most other properties have a default <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> value of <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.</span></span> <span data-ttu-id="97819-117">詳細については、<xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> のプロパティページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="97819-117">For more information, see the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property page.</span></span>

> [!NOTE]
> <span data-ttu-id="97819-118"><xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> プロパティはソースの更新を処理するため、<xref:System.Windows.Data.BindingMode.TwoWay> または <xref:System.Windows.Data.BindingMode.OneWayToSource> のバインドにのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="97819-118">The <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property deals with source updates and therefore is only relevant for <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings.</span></span> <span data-ttu-id="97819-119">バインディングを機能させるには <xref:System.Windows.Data.BindingMode.TwoWay> と <xref:System.Windows.Data.BindingMode.OneWayToSource> のバインドが必要です。ソースオブジェクトでは、プロパティの変更通知を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97819-119">For <xref:System.Windows.Data.BindingMode.TwoWay> and <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings to work, the source object needs to provide property change notifications.</span></span> <span data-ttu-id="97819-120">詳しくは、このトピック内にあるサンプルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97819-120">You can refer to the samples cited in this topic for more information.</span></span> <span data-ttu-id="97819-121">また、「[方法 : プロパティの変更通知を実装する](how-to-implement-property-change-notification.md)」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97819-121">In addition, you can look at [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97819-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="97819-122">See also</span></span>

- [<span data-ttu-id="97819-123">方法トピック</span><span class="sxs-lookup"><span data-stu-id="97819-123">How-to Topics</span></span>](data-binding-how-to-topics.md)
