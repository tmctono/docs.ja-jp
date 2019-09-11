---
title: '方法: TextBox のテキストがいつ変更されたかを検出する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855622"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="ad0b3-102">方法: TextBox のテキストがいつ変更されたかを検出する</span><span class="sxs-lookup"><span data-stu-id="ad0b3-102">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="ad0b3-103">この例では、 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> <xref:System.Windows.Controls.TextBox>コントロール内のテキストが変更されるたびに、イベントを使用してメソッドを実行する方法の1つを示します。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="ad0b3-104">変更を監視する[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox>コントロールが格納されているの分離コードクラスで、イベントが<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>発生するたびに呼び出すメソッドを挿入します。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="ad0b3-105">このメソッドには、 <xref:System.Windows.Controls.TextChangedEventHandler>デリゲートによって予期されるシグネチャと一致する署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="ad0b3-106">イベントハンドラーは、ユーザーまたはプログラムによっ<xref:System.Windows.Controls.TextBox>てコントロールの内容が変更されるたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="ad0b3-107">このイベントは、コントロール<xref:System.Windows.Controls.TextBox>が作成され、最初にテキストが設定されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-107">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="ad0b3-108">例</span><span class="sxs-lookup"><span data-stu-id="ad0b3-108">Example</span></span>

<span data-ttu-id="ad0b3-109">コントロールを定義するで、イベントハンドラーメソッド<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>名と一致する値を持つ属性を指定します。 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="ad0b3-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="ad0b3-110">例</span><span class="sxs-lookup"><span data-stu-id="ad0b3-110">Example</span></span>

<span data-ttu-id="ad0b3-111">変更を監視する[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.TextBox>コントロールが格納されているの分離コードクラスで、イベントが<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>発生するたびに呼び出すメソッドを挿入します。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="ad0b3-112">このメソッドには、 <xref:System.Windows.Controls.TextChangedEventHandler>デリゲートによって予期されるシグネチャと一致する署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="ad0b3-113">イベントハンドラーは、ユーザーまたはプログラムによっ<xref:System.Windows.Controls.TextBox>てコントロールの内容が変更されるたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="ad0b3-114">このイベントは、コントロール<xref:System.Windows.Controls.TextBox>が作成され、最初にテキストが設定されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="ad0b3-114">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="ad0b3-115">コメント</span><span class="sxs-lookup"><span data-stu-id="ad0b3-115">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="ad0b3-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ad0b3-116">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="ad0b3-117">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="ad0b3-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="ad0b3-118">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="ad0b3-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
