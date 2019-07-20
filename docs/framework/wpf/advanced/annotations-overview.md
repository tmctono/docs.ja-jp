---
title: 注釈の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: 861a757effee8d68d1e41682dd91ffadba20c536
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364380"
---
# <a name="annotations-overview"></a><span data-ttu-id="e765d-102">注釈の概要</span><span class="sxs-lookup"><span data-stu-id="e765d-102">Annotations Overview</span></span>
<span data-ttu-id="e765d-103">用紙にメモやコメントを書くことは普通の行為であり、人はそれを当たり前のことと思っています。</span><span class="sxs-lookup"><span data-stu-id="e765d-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="e765d-104">そのようなメモやコメントが "注釈" です。注釈をドキュメントに追加することで情報に目印を付け、興味のある内容を強調表示し、後で参照します。</span><span class="sxs-lookup"><span data-stu-id="e765d-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="e765d-105">印刷したドキュメントにメモを書くことは簡単で一般的な行為ですが、電子ドキュメントに個人的なコメントを追加する機能は利用できるとしても一般的に非常に限定されています。</span><span class="sxs-lookup"><span data-stu-id="e765d-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="e765d-106">このトピックでは、いくつかの一般的な種類の注釈 (特に付箋と強調表示) について説明します。また、Microsoft Annotations フレームワークが Windows Presentation Foundation を通じてアプリケーションでこれらの種類の注釈を容易にする方法を示します (WPF) ドキュメントの表示コントロール。</span><span class="sxs-lookup"><span data-stu-id="e765d-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the Microsoft Annotations Framework facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]<span data-ttu-id="e765d-107">注釈をサポートするドキュメント表示コントロール<xref:System.Windows.Controls.FlowDocumentReader>に<xref:System.Windows.Controls.FlowDocumentScrollViewer>は、および、 <xref:System.Windows.Controls.DocumentViewer>および<xref:System.Windows.Controls.FlowDocumentPageViewer>などの<xref:System.Windows.Controls.Primitives.DocumentViewerBase>から派生したコントロールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e765d-107">document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  

<a name="caf1_type_stickynotes"></a>   
## <a name="sticky-notes"></a><span data-ttu-id="e765d-108">付箋</span><span class="sxs-lookup"><span data-stu-id="e765d-108">Sticky Notes</span></span>  
 <span data-ttu-id="e765d-109">典型的な付箋とは、色の付いた小さな紙切れに情報を記入し、書類に "貼り付ける" というものです。</span><span class="sxs-lookup"><span data-stu-id="e765d-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="e765d-110">デジタル付箋は電子ドキュメントのために同様の機能を提供しますが、さまざまなコンテンツを追加できるという柔軟性があります。タイプしたテキスト、手書きのメモ ([!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] の "インク" ストロークなど)、Web リンクなどです。</span><span class="sxs-lookup"><span data-stu-id="e765d-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="e765d-111">次の図では、蛍光ペン、テキスト付箋、インク付箋で注釈を付けていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e765d-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="e765d-112">![蛍光ペン、テキスト付箋、インク付箋による注釈](./media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="e765d-112">![Highlight, text and ink sticky note annotations.](./media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="e765d-113">次は、アプリケーションで注釈サポートを有効にするためのメソッドのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="e765d-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## <a name="highlights"></a><span data-ttu-id="e765d-114">強調表示</span><span class="sxs-lookup"><span data-stu-id="e765d-114">Highlights</span></span>  
 <span data-ttu-id="e765d-115">書面であれば、下線を引いたり、蛍光ペンでなぞったり、ドキュメント内の単語を囲んだり、余白に目印や注釈を付けたりするなど、さまざまな方法で書き込みを行い、興味のある項目を目立たせることができます。</span><span class="sxs-lookup"><span data-stu-id="e765d-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="e765d-116">Microsoft annotations Framework の注釈を強調表示すると、ドキュメント表示コントロールに[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]表示される情報をマークするための同様の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e765d-116">Highlight annotations in Microsoft Annotations Framework provide a similar feature for marking up information displayed in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] document viewing controls.</span></span>  
  
 <span data-ttu-id="e765d-117">次の図は、注釈の強調表示のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="e765d-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="e765d-118">![注釈の強調表示](./media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="e765d-118">![Highlight Annotation](./media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="e765d-119">通常、ユーザーは、最初にテキストまたは目的の項目を選択し、右クリックして注釈の<xref:System.Windows.Controls.ContextMenu>オプションのを表示することで、注釈を作成します。</span><span class="sxs-lookup"><span data-stu-id="e765d-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="e765d-120">次の例は、 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ユーザーが注釈を作成および<xref:System.Windows.Controls.ContextMenu>管理するためにアクセスできるルーティングコマンドを使用してを宣言するために使用できるを示しています。</span><span class="sxs-lookup"><span data-stu-id="e765d-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## <a name="data-anchoring"></a><span data-ttu-id="e765d-121">データの固定</span><span class="sxs-lookup"><span data-stu-id="e765d-121">Data Anchoring</span></span>  
 <span data-ttu-id="e765d-122">注釈フレームワークは、表示ビュー上の位置だけではなく、ユーザーが選択したデータに注釈をバインドします。</span><span class="sxs-lookup"><span data-stu-id="e765d-122">The Annotations Framework binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="e765d-123">そのため、スクロールしたり、表示ウィンドウのサイズを変更したりするなど、ドキュメントの表示が変わっても、注釈はそれが固定されているデータにとどまります。</span><span class="sxs-lookup"><span data-stu-id="e765d-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="e765d-124">たとえば、次の図をご覧ください。選択したテキストが蛍光ペンでなぞられています。</span><span class="sxs-lookup"><span data-stu-id="e765d-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="e765d-125">ドキュメントの表示が変わると (スクロール、サイズ変更、拡大/縮小、その他の移動)、蛍光ペンは元のデータ選択と一緒に移動します。</span><span class="sxs-lookup"><span data-stu-id="e765d-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="e765d-126">![注釈データ固定](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="e765d-126">![Annotation Data Anchoring](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="e765d-127">注釈と注釈付きオブジェクトを照合する</span><span class="sxs-lookup"><span data-stu-id="e765d-127">Matching Annotations with Annotated Objects</span></span>  
 <span data-ttu-id="e765d-128">注釈とそれに対応する注釈付きオブジェクトを照合できます。</span><span class="sxs-lookup"><span data-stu-id="e765d-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="e765d-129">たとえば、コメント ウィンドウが付いている単純なドキュメント リーダー アプリケーションを想像してください。</span><span class="sxs-lookup"><span data-stu-id="e765d-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="e765d-130">そのコメント ウィンドウにはリスト ボックスがあり、そのリスト ボックスに、ドキュメントに固定されている注釈の一覧からのテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e765d-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="e765d-131">リスト ボックスの項目を選択すると、それに対応する注釈オブジェクトが固定されている段落がドキュメントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e765d-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="e765d-132">次の例を見ると、コメント ウィンドウとして機能するそのようなリスト ボックスのイベント ハンドラーの実装方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="e765d-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="e765d-133">もう1つのシナリオ例では、電子メールを使用してドキュメントリーダー間で注釈と付箋を交換できるアプリケーションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e765d-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="e765d-134">そのような機能を利用すると、交換された注釈を含むページにドキュメント リーダーで移動できます。</span><span class="sxs-lookup"><span data-stu-id="e765d-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e765d-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e765d-135">See also</span></span>

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [<span data-ttu-id="e765d-136">注釈スキーマ</span><span class="sxs-lookup"><span data-stu-id="e765d-136">Annotations Schema</span></span>](annotations-schema.md)
- [<span data-ttu-id="e765d-137">ContextMenu の概要</span><span class="sxs-lookup"><span data-stu-id="e765d-137">ContextMenu Overview</span></span>](../controls/contextmenu-overview.md)
- [<span data-ttu-id="e765d-138">コマンド実行の概要</span><span class="sxs-lookup"><span data-stu-id="e765d-138">Commanding Overview</span></span>](commanding-overview.md)
- [<span data-ttu-id="e765d-139">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="e765d-139">Flow Document Overview</span></span>](flow-document-overview.md)
- <span data-ttu-id="e765d-140">[方法: MenuItem にコマンドを追加する](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="e765d-140">[How to: Add a Command to a MenuItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span></span>
