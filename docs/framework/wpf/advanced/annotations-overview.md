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
ms.openlocfilehash: 433fee08d44720640d3f9d1bf2511a6a267eb58e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145463"
---
# <a name="annotations-overview"></a><span data-ttu-id="3da6e-102">注釈の概要</span><span class="sxs-lookup"><span data-stu-id="3da6e-102">Annotations Overview</span></span>
<span data-ttu-id="3da6e-103">用紙にメモやコメントを書くことは普通の行為であり、人はそれを当たり前のことと思っています。</span><span class="sxs-lookup"><span data-stu-id="3da6e-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="3da6e-104">そのようなメモやコメントが "注釈" です。注釈をドキュメントに追加することで情報に目印を付け、興味のある内容を強調表示し、後で参照します。</span><span class="sxs-lookup"><span data-stu-id="3da6e-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="3da6e-105">印刷したドキュメントにメモを書くことは簡単で一般的な行為ですが、電子ドキュメントに個人的なコメントを追加する機能は利用できるとしても一般的に非常に限定されています。</span><span class="sxs-lookup"><span data-stu-id="3da6e-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="3da6e-106">このトピックでは、いくつかの一般的な種類の注釈、特に付箋と強調表示を確認し、Microsoft アノテーション フレームワークが Windows プレゼンテーション ファウンデーション (WPF) を通じてアプリケーションでこれらのタイプの注釈を容易にする方法を示します。) ドキュメント表示コントロール。</span><span class="sxs-lookup"><span data-stu-id="3da6e-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the Microsoft Annotations Framework facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  <span data-ttu-id="3da6e-107">および<xref:System.Windows.Controls.FlowDocumentReader>など<xref:System.Windows.Controls.FlowDocumentScrollViewer><xref:System.Windows.Controls.Primitives.DocumentViewerBase><xref:System.Windows.Controls.DocumentViewer>から派生したコントロールと注釈をサポートする WPF ドキュメント表示コントロールには、<xref:System.Windows.Controls.FlowDocumentPageViewer>および が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-107">WPF document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  

<a name="caf1_type_stickynotes"></a>
## <a name="sticky-notes"></a><span data-ttu-id="3da6e-108">付箋</span><span class="sxs-lookup"><span data-stu-id="3da6e-108">Sticky Notes</span></span>  
 <span data-ttu-id="3da6e-109">典型的な付箋とは、色の付いた小さな紙切れに情報を記入し、書類に "貼り付ける" というものです。</span><span class="sxs-lookup"><span data-stu-id="3da6e-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="3da6e-110">デジタル付箋は電子ドキュメントに対して同様の機能を提供しますが、入力したテキスト、手書きのメモ (たとえば、Tablet PC の "インク" ストローク)、Web リンクなど、その他多くの種類のコンテンツを含める柔軟性が追加されています。</span><span class="sxs-lookup"><span data-stu-id="3da6e-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, Tablet PC "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="3da6e-111">次の図では、蛍光ペン、テキスト付箋、インク付箋で注釈を付けていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="3da6e-112">![強調表示、テキストとインク付箋注釈。](./media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="3da6e-112">![Highlight, text and ink sticky note annotations.](./media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="3da6e-113">次は、アプリケーションで注釈サポートを有効にするためのメソッドのサンプルです。</span><span class="sxs-lookup"><span data-stu-id="3da6e-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>
## <a name="highlights"></a><span data-ttu-id="3da6e-114">ハイライト</span><span class="sxs-lookup"><span data-stu-id="3da6e-114">Highlights</span></span>  
 <span data-ttu-id="3da6e-115">書面であれば、下線を引いたり、蛍光ペンでなぞったり、ドキュメント内の単語を囲んだり、余白に目印や注釈を付けたりするなど、さまざまな方法で書き込みを行い、興味のある項目を目立たせることができます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="3da6e-116">Microsoft 注釈フレームワークで強調表示注釈は、WPF ドキュメント表示コントロールに表示される情報をマークするための同様の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="3da6e-116">Highlight annotations in Microsoft Annotations Framework provide a similar feature for marking up information displayed in WPF document viewing controls.</span></span>  
  
 <span data-ttu-id="3da6e-117">次の図は、注釈の強調表示のサンプルです。</span><span class="sxs-lookup"><span data-stu-id="3da6e-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="3da6e-118">![注釈の強調表示](./media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="3da6e-118">![Highlight Annotation](./media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="3da6e-119">通常、ユーザーは、最初にテキストまたは対象の項目を選択し、右クリックして注釈オプションを表示することで<xref:System.Windows.Controls.ContextMenu>、注釈を作成します。</span><span class="sxs-lookup"><span data-stu-id="3da6e-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="3da6e-120">次の例は、[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ユーザーが注釈を作成および<xref:System.Windows.Controls.ContextMenu>管理するためにアクセスできるルーティングされたコマンドを宣言するために使用できる例を示しています。</span><span class="sxs-lookup"><span data-stu-id="3da6e-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>
## <a name="data-anchoring"></a><span data-ttu-id="3da6e-121">データの固定</span><span class="sxs-lookup"><span data-stu-id="3da6e-121">Data Anchoring</span></span>  
 <span data-ttu-id="3da6e-122">注釈フレームワークは、表示ビューの位置だけでなく、ユーザーが選択したデータに注釈をバインドします。</span><span class="sxs-lookup"><span data-stu-id="3da6e-122">The Annotations Framework binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="3da6e-123">そのため、スクロールしたり、表示ウィンドウのサイズを変更したりするなど、ドキュメントの表示が変わっても、注釈はそれが固定されているデータにとどまります。</span><span class="sxs-lookup"><span data-stu-id="3da6e-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="3da6e-124">たとえば、次の図をご覧ください。選択したテキストが蛍光ペンでなぞられています。</span><span class="sxs-lookup"><span data-stu-id="3da6e-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="3da6e-125">ドキュメントの表示が変わると (スクロール、サイズ変更、拡大/縮小、その他の移動)、蛍光ペンは元のデータ選択と一緒に移動します。</span><span class="sxs-lookup"><span data-stu-id="3da6e-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="3da6e-126">![注釈データ固定](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="3da6e-126">![Annotation Data Anchoring](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>
## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="3da6e-127">注釈と注釈付きオブジェクトを照合する</span><span class="sxs-lookup"><span data-stu-id="3da6e-127">Matching Annotations with Annotated Objects</span></span>  
 <span data-ttu-id="3da6e-128">注釈とそれに対応する注釈付きオブジェクトを照合できます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="3da6e-129">たとえば、コメント ウィンドウが付いている単純なドキュメント リーダー アプリケーションを想像してください。</span><span class="sxs-lookup"><span data-stu-id="3da6e-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="3da6e-130">そのコメント ウィンドウにはリスト ボックスがあり、そのリスト ボックスに、ドキュメントに固定されている注釈の一覧からのテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="3da6e-131">リスト ボックスの項目を選択すると、それに対応する注釈オブジェクトが固定されている段落がドキュメントに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="3da6e-132">次の例を見ると、コメント ウィンドウとして機能するそのようなリスト ボックスのイベント ハンドラーの実装方法がわかります。</span><span class="sxs-lookup"><span data-stu-id="3da6e-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="3da6e-133">別のシナリオの例としては、電子メールを通じてドキュメント リーダー間で注釈と付箋を交換できるようにするアプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="3da6e-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="3da6e-134">そのような機能を利用すると、交換された注釈を含むページにドキュメント リーダーで移動できます。</span><span class="sxs-lookup"><span data-stu-id="3da6e-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da6e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="3da6e-135">See also</span></span>

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [<span data-ttu-id="3da6e-136">注釈スキーマ</span><span class="sxs-lookup"><span data-stu-id="3da6e-136">Annotations Schema</span></span>](annotations-schema.md)
- [<span data-ttu-id="3da6e-137">ContextMenu の概要</span><span class="sxs-lookup"><span data-stu-id="3da6e-137">ContextMenu Overview</span></span>](../controls/contextmenu-overview.md)
- [<span data-ttu-id="3da6e-138">コマンド実行の概要</span><span class="sxs-lookup"><span data-stu-id="3da6e-138">Commanding Overview</span></span>](commanding-overview.md)
- [<span data-ttu-id="3da6e-139">フロー ドキュメントの概要</span><span class="sxs-lookup"><span data-stu-id="3da6e-139">Flow Document Overview</span></span>](flow-document-overview.md)
- <span data-ttu-id="3da6e-140">[方法: メニュー アイテムにコマンドを追加する](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="3da6e-140">[How to: Add a Command to a MenuItem](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span></span>
