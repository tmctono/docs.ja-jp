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
ms.openlocfilehash: 72441e53d21df47d34a0600dafdf0b4b04c11cad
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352374"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="cbc39-102">方法: TextBox のテキストがいつ変更されたかを検出する</span><span class="sxs-lookup"><span data-stu-id="cbc39-102">How to: Detect When Text in a TextBox Has Changed</span></span>
<span data-ttu-id="cbc39-103">この例を使用する 1 つの方法を示しています、<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>イベント メソッドを実行するたびに内のテキストを<xref:System.Windows.Controls.TextBox>コントロールが変更されました。</span><span class="sxs-lookup"><span data-stu-id="cbc39-103">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>  
  
 <span data-ttu-id="cbc39-104">分離コード クラスで、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を格納している、<xref:System.Windows.Controls.TextBox>変更については、監視するコントロールに挿入されるたびに呼び出すメソッドを<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-104">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="cbc39-105">このメソッドのシグネチャが一致で予期される必要があります、<xref:System.Windows.Controls.TextChangedEventHandler>を委任します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-105">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 <span data-ttu-id="cbc39-106">イベント ハンドラーが呼び出されますたびの内容、<xref:System.Windows.Controls.TextBox>ユーザー、またはプログラムでコントロールを変更します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-106">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="cbc39-107">**注:** このイベントを発生させるときに、<xref:System.Windows.Controls.TextBox>コントロールが作成し、最初にテキストを格納します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-107">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbc39-108">例</span><span class="sxs-lookup"><span data-stu-id="cbc39-108">Example</span></span>  
 <span data-ttu-id="cbc39-109">[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]を定義する、<xref:System.Windows.Controls.TextBox>コントロールを指定、<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>イベント ハンドラー メソッドの名前に一致する値を持つ属性です。</span><span class="sxs-lookup"><span data-stu-id="cbc39-109">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]  
  
## <a name="example"></a><span data-ttu-id="cbc39-110">例</span><span class="sxs-lookup"><span data-stu-id="cbc39-110">Example</span></span>  
 <span data-ttu-id="cbc39-111">分離コード クラスで、[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]を格納している、<xref:System.Windows.Controls.TextBox>変更については、監視するコントロールに挿入されるたびに呼び出すメソッドを<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-111">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="cbc39-112">このメソッドのシグネチャが一致で予期される必要があります、<xref:System.Windows.Controls.TextChangedEventHandler>を委任します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-112">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
 [!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]  
  
 <span data-ttu-id="cbc39-113">イベント ハンドラーが呼び出されますたびの内容、<xref:System.Windows.Controls.TextBox>ユーザー、またはプログラムでコントロールを変更します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-113">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>  
  
 <span data-ttu-id="cbc39-114">**注:** このイベントを発生させるときに、<xref:System.Windows.Controls.TextBox>コントロールが作成し、最初にテキストを格納します。</span><span class="sxs-lookup"><span data-stu-id="cbc39-114">**Note:** This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>  
  
 <span data-ttu-id="cbc39-115">コメント</span><span class="sxs-lookup"><span data-stu-id="cbc39-115">Comments</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbc39-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="cbc39-116">See also</span></span>
- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="cbc39-117">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="cbc39-117">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="cbc39-118">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="cbc39-118">RichTextBox Overview</span></span>](richtextbox-overview.md)
