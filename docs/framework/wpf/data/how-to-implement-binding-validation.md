---
title: '方法: バインディングの検証の実装'
description: Windows Presentation Foundation (WPF) で、無効な値が入力されたときにバインディングの検証を使用してユーザーに視覚的フィードバックを提供する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validation of binding [WPF]
- data binding [WPF], validation of binding
- binding [WPF], validation of
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
ms.openlocfilehash: 0813be9f79a83a9dae26db1dadb58b5e973339fd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617883"
---
# <a name="how-to-implement-binding-validation"></a><span data-ttu-id="72f1b-103">方法: バインディングの検証の実装</span><span class="sxs-lookup"><span data-stu-id="72f1b-103">How to: Implement Binding Validation</span></span>

<span data-ttu-id="72f1b-104">この例では、<xref:System.Windows.Controls.Validation.ErrorTemplate%2A> とスタイル トリガーを使用して、カスタム検証規則に基づき無効な値が入力されたことをユーザーに通知するための視覚的フィードバックを提供する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="72f1b-104">This example shows how to use an <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> and a style trigger to provide visual feedback to inform the user when an invalid value is entered, based on a custom validation rule.</span></span>

## <a name="example"></a><span data-ttu-id="72f1b-105">例</span><span class="sxs-lookup"><span data-stu-id="72f1b-105">Example</span></span>

<span data-ttu-id="72f1b-106">次の例で使用されている <xref:System.Windows.Controls.TextBox> のテキストの内容は、`ods` という名前のバインディング ソース オブジェクトの `Age` プロパティ (int 型) にバインドされています。</span><span class="sxs-lookup"><span data-stu-id="72f1b-106">The text content of the <xref:System.Windows.Controls.TextBox> in the following example is bound to the `Age` property (of type int) of a binding source object named `ods`.</span></span> <span data-ttu-id="72f1b-107">バインディングは、`AgeRangeRule` という名前の検証規則を使用するよう設定されているため、ユーザーが数字以外の文字、または 21 から 130 の範囲外の値を入力すると、テキスト ボックスの横に赤の感嘆符が表示され、ユーザーがテキスト ボックス上にマウスを置くとエラー メッセージを含んだツール ヒントが示されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-107">The binding is set up to use a validation rule named `AgeRangeRule` so that if the user enters non-numeric characters or a value that is smaller than 21 or greater than 130, a red exclamation mark appears next to the text box and a tool tip with the error message appears when the user moves the mouse over the text box.</span></span>

[!code-xaml[BindValidation#2](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]

<span data-ttu-id="72f1b-108">次の例では、`AgeRangeRule` が継承され、<xref:System.Windows.Controls.ValidationRule> メソッドがオーバーライドされている、<xref:System.Windows.Controls.ValidationRule.Validate%2A> の実装を示します。</span><span class="sxs-lookup"><span data-stu-id="72f1b-108">The following example shows the implementation of `AgeRangeRule`, which inherits from <xref:System.Windows.Controls.ValidationRule> and overrides the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method.</span></span> <span data-ttu-id="72f1b-109">`Int32.Parse` メソッドは、値に無効な文字が含まれていないことを確認するために、値に対して呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-109">The `Int32.Parse` method is called on the value to make sure that it does not contain any invalid characters.</span></span> <span data-ttu-id="72f1b-110"><xref:System.Windows.Controls.ValidationRule.Validate%2A> メソッドでは、解析中に例外が発生したかどうか、および年齢値が範囲外にあるかどうかに基づいて、値が有効かどうかを示す <xref:System.Windows.Controls.ValidationResult> が返されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-110">The <xref:System.Windows.Controls.ValidationRule.Validate%2A> method returns a <xref:System.Windows.Controls.ValidationResult> that indicates if the value is valid based on whether an exception is caught during the parsing and whether the age value is outside of the lower and upper bounds.</span></span>

[!code-csharp[BindValidation#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]
[!code-vb[BindValidation#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BindValidation/VisualBasic/AgeRangeRule.vb#3)]

<span data-ttu-id="72f1b-111">次の例では、検証エラーをユーザーに通知する赤い感嘆符を作成するための、カスタム <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` を示します。</span><span class="sxs-lookup"><span data-stu-id="72f1b-111">The following example shows the custom <xref:System.Windows.Controls.ControlTemplate> `validationTemplate` that creates a red exclamation mark to notify the user of a validation error.</span></span> <span data-ttu-id="72f1b-112">コントロール テンプレートは、コントロールの外観を再定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-112">Control templates are used to redefine the appearance of a control.</span></span>

[!code-xaml[BindValidation#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]

<span data-ttu-id="72f1b-113">次の例に示すように、エラー メッセージを表示する <xref:System.Windows.Controls.ToolTip> は、`textBoxInError` という名前のスタイルを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-113">As shown in the following example, the <xref:System.Windows.Controls.ToolTip> that shows the error message is created using the style named `textBoxInError`.</span></span> <span data-ttu-id="72f1b-114"><xref:System.Windows.Controls.Validation.HasError%2A> の値が `true` である場合、トリガーによって現在の <xref:System.Windows.Controls.TextBox> のツール ヒントに、最初の検証エラーが設定されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-114">If the value of <xref:System.Windows.Controls.Validation.HasError%2A> is `true`, the trigger sets the tool tip of the current <xref:System.Windows.Controls.TextBox> to its first validation error.</span></span> <span data-ttu-id="72f1b-115"><xref:System.Windows.Data.Binding.RelativeSource%2A> には、現在の要素を参照している <xref:System.Windows.Data.RelativeSourceMode.Self> が設定されます。</span><span class="sxs-lookup"><span data-stu-id="72f1b-115">The <xref:System.Windows.Data.Binding.RelativeSource%2A> is set to <xref:System.Windows.Data.RelativeSourceMode.Self>, referring to the current element.</span></span>

[!code-xaml[BindValidation#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]

<span data-ttu-id="72f1b-116">完全な例については、[バインド検証のサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72f1b-116">For the complete example, see [Bind Validation sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/BindValidation).</span></span>
  
<span data-ttu-id="72f1b-117">カスタム <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> を提供しない場合、検証エラーがあったときにユーザーに視覚的にフィードバックするために、既定のエラー テンプレートが表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="72f1b-117">Note that if you do not provide a custom <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> the default error template appears to provide visual feedback to the user when there is a validation error.</span></span> <span data-ttu-id="72f1b-118">詳しくは、「[データ バインドの概要](../../../desktop-wpf/data/data-binding-overview.md)」の「データの検証」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="72f1b-118">See "Data Validation" in [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md) for more information.</span></span> <span data-ttu-id="72f1b-119">さらに [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] は、バインディング ソース プロパティの更新中にスローされる例外をキャッチするための、組み込みの検証規則を提供します。</span><span class="sxs-lookup"><span data-stu-id="72f1b-119">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provides a built-in validation rule that catches exceptions that are thrown during the update of the binding source property.</span></span> <span data-ttu-id="72f1b-120">詳細については、「<xref:System.Windows.Controls.ExceptionValidationRule>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72f1b-120">For more information, see <xref:System.Windows.Controls.ExceptionValidationRule>.</span></span>

## <a name="see-also"></a><span data-ttu-id="72f1b-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="72f1b-121">See also</span></span>

- [<span data-ttu-id="72f1b-122">データ バインディングの概要</span><span class="sxs-lookup"><span data-stu-id="72f1b-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="72f1b-123">方法トピック</span><span class="sxs-lookup"><span data-stu-id="72f1b-123">How-to Topics</span></span>](data-binding-how-to-topics.md)
