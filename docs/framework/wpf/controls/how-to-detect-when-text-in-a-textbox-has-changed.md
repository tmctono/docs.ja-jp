---
title: '方法: TextBox のテキストがいつ変更されたかを検出する'
description: Windows Presentation Foundation アプリケーションで、TextBox コントロール内のテキストが変更されるたびに、TextChanged イベントを使用してメソッドを実行する方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 1e054380a8c77d32e6bb4adbbcb032e531bbefd0
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166223"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a><span data-ttu-id="84bbc-103">方法: TextBox のテキストがいつ変更されたかを検出する</span><span class="sxs-lookup"><span data-stu-id="84bbc-103">How to: Detect When Text in a TextBox Has Changed</span></span>

<span data-ttu-id="84bbc-104">この例では、<xref:System.Windows.Controls.TextBox> コントロール内のテキストが変更されるたびに、<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> イベントを使用してメソッドを実行する方法の 1 つを示します。</span><span class="sxs-lookup"><span data-stu-id="84bbc-104">This example shows one way to use the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event to execute a method whenever the text in a <xref:System.Windows.Controls.TextBox> control has changed.</span></span>

<span data-ttu-id="84bbc-105">変更を監視する <xref:System.Windows.Controls.TextBox> コントロールを含む [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の分離コード クラスで、<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> イベントが発生するたびに呼び出すメソッドを挿入します。</span><span class="sxs-lookup"><span data-stu-id="84bbc-105">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="84bbc-106">このメソッドには、<xref:System.Windows.Controls.TextChangedEventHandler> デリゲートによって予期されるものと一致するシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="84bbc-106">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

<span data-ttu-id="84bbc-107">イベント ハンドラーは、ユーザーまたはプログラムによって <xref:System.Windows.Controls.TextBox> コントロールの内容が変更されるたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="84bbc-107">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="84bbc-108">このイベントは、<xref:System.Windows.Controls.TextBox> コントロールが作成され、最初にテキストが入力されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="84bbc-108">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

## <a name="example"></a><span data-ttu-id="84bbc-109">例</span><span class="sxs-lookup"><span data-stu-id="84bbc-109">Example</span></span>

<span data-ttu-id="84bbc-110"><xref:System.Windows.Controls.TextBox> コントロールを定義する [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] で、イベント ハンドラー メソッド名と一致する値を持つ <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> 属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="84bbc-110">In the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that defines your <xref:System.Windows.Controls.TextBox> control, specify the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> attribute with a value that matches the event handler method name.</span></span>

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a><span data-ttu-id="84bbc-111">例</span><span class="sxs-lookup"><span data-stu-id="84bbc-111">Example</span></span>

<span data-ttu-id="84bbc-112">変更を監視する <xref:System.Windows.Controls.TextBox> コントロールを含む [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] の分離コード クラスで、<xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> イベントが発生するたびに呼び出すメソッドを挿入します。</span><span class="sxs-lookup"><span data-stu-id="84bbc-112">In the code-behind class for the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that contains the <xref:System.Windows.Controls.TextBox> control that you want to monitor for changes, insert a method to call whenever the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event fires.</span></span>  <span data-ttu-id="84bbc-113">このメソッドには、<xref:System.Windows.Controls.TextChangedEventHandler> デリゲートによって予期されるものと一致するシグネチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="84bbc-113">This method must have a signature that matches what is expected by the <xref:System.Windows.Controls.TextChangedEventHandler> delegate.</span></span>

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

<span data-ttu-id="84bbc-114">イベント ハンドラーは、ユーザーまたはプログラムによって <xref:System.Windows.Controls.TextBox> コントロールの内容が変更されるたびに呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="84bbc-114">The event handler is called whenever the contents of the <xref:System.Windows.Controls.TextBox> control are changed, either by a user or programmatically.</span></span>

> [!NOTE]
> <span data-ttu-id="84bbc-115">このイベントは、<xref:System.Windows.Controls.TextBox> コントロールが作成され、最初にテキストが入力されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="84bbc-115">This event fires when the <xref:System.Windows.Controls.TextBox> control is created and initially populated with text.</span></span>

<span data-ttu-id="84bbc-116">コメント</span><span class="sxs-lookup"><span data-stu-id="84bbc-116">Comments</span></span>

## <a name="see-also"></a><span data-ttu-id="84bbc-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="84bbc-117">See also</span></span>

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [<span data-ttu-id="84bbc-118">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="84bbc-118">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="84bbc-119">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="84bbc-119">RichTextBox Overview</span></span>](richtextbox-overview.md)
