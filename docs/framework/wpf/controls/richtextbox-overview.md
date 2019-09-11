---
title: RichTextBox の概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], RichTextBox
- RichTextBox control [WPF], about RichTextBox control
ms.assetid: c94548b2-c1e9-4b62-b10c-dd8740eb23d8
ms.openlocfilehash: bfed42bcf3693ef744b3ed2b54ebe070931513a9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855735"
---
# <a name="richtextbox-overview"></a><span data-ttu-id="64f94-102">RichTextBox の概要</span><span class="sxs-lookup"><span data-stu-id="64f94-102">RichTextBox Overview</span></span>

<span data-ttu-id="64f94-103"><xref:System.Windows.Controls.RichTextBox>コントロールを使用すると、段落、画像、テーブルなどのフローコンテンツを表示または編集できます。</span><span class="sxs-lookup"><span data-stu-id="64f94-103">The <xref:System.Windows.Controls.RichTextBox> control enables you to display or edit flow content including paragraphs, images, tables, and more.</span></span> <span data-ttu-id="64f94-104">このトピックでは<xref:System.Windows.Controls.TextBox> 、クラスについて説明し、とC#の両方[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]で使用する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="64f94-104">This topic introduces the <xref:System.Windows.Controls.TextBox> class and provides examples of how to use it in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and C#.</span></span>

<a name="textbox_or_richtextbox"></a>

## <a name="textbox-or-richtextbox"></a><span data-ttu-id="64f94-105">TextBox か RichTextBox か</span><span class="sxs-lookup"><span data-stu-id="64f94-105">TextBox or RichTextBox?</span></span>

<span data-ttu-id="64f94-106"><xref:System.Windows.Controls.RichTextBox> と<xref:System.Windows.Controls.TextBox>はどちらもテキストの編集を許可しますが、2つのコントロールはさまざまなシナリオで使用されます。</span><span class="sxs-lookup"><span data-stu-id="64f94-106">Both <xref:System.Windows.Controls.RichTextBox> and <xref:System.Windows.Controls.TextBox> allow users to edit text, however, the two controls are used in different scenarios.</span></span> <span data-ttu-id="64f94-107">は<xref:System.Windows.Controls.RichTextBox> 、ユーザーが書式設定されたテキスト、画像、テーブル、またはその他のリッチコンテンツを編集する必要がある場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="64f94-107">A <xref:System.Windows.Controls.RichTextBox> is a better choice when it is necessary for the user to edit formatted text, images, tables, or other rich content.</span></span> <span data-ttu-id="64f94-108">たとえば、書式設定や画像などを必要とするドキュメント、記事、ブログを編集する場合は、を<xref:System.Windows.Controls.RichTextBox>使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64f94-108">For example, editing a document, article, or blog that requires formatting, images, etc is best accomplished using a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="64f94-109">には、 <xref:System.Windows.Controls.RichTextBox>より少ないシステムリソースが必要です。また、プレーンテキストのみを編集する必要がある場合(フォームの使用状況など)に最適です。<xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="64f94-109">A <xref:System.Windows.Controls.TextBox> requires less system resources then a <xref:System.Windows.Controls.RichTextBox> and it is ideal when only plain text needs to be edited (i.e. usage in forms).</span></span> <span data-ttu-id="64f94-110">の<xref:System.Windows.Controls.TextBox>詳細については、「[テキストボックスの概要](textbox-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-110">See [TextBox Overview](textbox-overview.md) for more information on <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="64f94-111">次の表は、と<xref:System.Windows.Controls.TextBox> <xref:System.Windows.Controls.RichTextBox>の主な機能をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="64f94-111">The table below summarizes the main features of <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox>.</span></span>

|<span data-ttu-id="64f94-112">コントロール</span><span class="sxs-lookup"><span data-stu-id="64f94-112">Control</span></span>|<span data-ttu-id="64f94-113">リアルタイム スペル チェック</span><span class="sxs-lookup"><span data-stu-id="64f94-113">Real-time Spellchecking</span></span>|<span data-ttu-id="64f94-114">コンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="64f94-114">Context Menu</span></span>|<span data-ttu-id="64f94-115">(Ctr + <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> B) のような書式設定コマンド</span><span class="sxs-lookup"><span data-stu-id="64f94-115">Formatting commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B)</span></span>|<span data-ttu-id="64f94-116"><xref:System.Windows.Documents.FlowDocument>画像、段落、テーブルなどのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="64f94-116"><xref:System.Windows.Documents.FlowDocument> content like images, paragraphs, tables, etc.</span></span>|
|-------------|------------------------------|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|<xref:System.Windows.Controls.TextBox>|<span data-ttu-id="64f94-117">[はい]</span><span class="sxs-lookup"><span data-stu-id="64f94-117">Yes</span></span>|<span data-ttu-id="64f94-118">[はい]</span><span class="sxs-lookup"><span data-stu-id="64f94-118">Yes</span></span>|<span data-ttu-id="64f94-119">いいえ</span><span class="sxs-lookup"><span data-stu-id="64f94-119">No</span></span>|<span data-ttu-id="64f94-120">No.</span><span class="sxs-lookup"><span data-stu-id="64f94-120">No.</span></span>|
|<xref:System.Windows.Controls.RichTextBox>|<span data-ttu-id="64f94-121">[はい]</span><span class="sxs-lookup"><span data-stu-id="64f94-121">Yes</span></span>|<span data-ttu-id="64f94-122">はい</span><span class="sxs-lookup"><span data-stu-id="64f94-122">Yes</span></span>|<span data-ttu-id="64f94-123">はい</span><span class="sxs-lookup"><span data-stu-id="64f94-123">Yes</span></span>|<span data-ttu-id="64f94-124">[はい]</span><span class="sxs-lookup"><span data-stu-id="64f94-124">Yes</span></span>|

> [!NOTE]
> <span data-ttu-id="64f94-125">は (Ctr + B) のよう<xref:System.Windows.Documents.EditingCommands.ToggleBold%2A>な書式設定関連のコマンドをサポートしていませんが、の<xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>ような多くの基本的なコマンドが両方のコントロールでサポートされています。 <xref:System.Windows.Controls.TextBox></span><span class="sxs-lookup"><span data-stu-id="64f94-125">Although <xref:System.Windows.Controls.TextBox> does not support formatting related commands like <xref:System.Windows.Documents.EditingCommands.ToggleBold%2A> (Ctr+B), many basic commands are supported by both controls such as <xref:System.Windows.Documents.EditingCommands.MoveToLineEnd%2A>.</span></span>

<span data-ttu-id="64f94-126">上の表の機能については、後で詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="64f94-126">The features from the table above are covered in more detail later.</span></span>

<a name="creating_a_richtextbox"></a>

## <a name="creating-a-richtextbox"></a><span data-ttu-id="64f94-127">RichTextBox の作成</span><span class="sxs-lookup"><span data-stu-id="64f94-127">Creating a RichTextBox</span></span>

<span data-ttu-id="64f94-128">次のコードは、 <xref:System.Windows.Controls.RichTextBox>ユーザーがのリッチコンテンツを編集できるを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64f94-128">The code below shows how to create a <xref:System.Windows.Controls.RichTextBox> that a user can edit rich content in.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#BasicRichTextBoxExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/BasicRichTextBoxExample.xaml#basicrichtextboxexamplewholepage)]

<span data-ttu-id="64f94-129">具体的には、で<xref:System.Windows.Controls.RichTextBox>編集されるコンテンツはフローコンテンツです。</span><span class="sxs-lookup"><span data-stu-id="64f94-129">Specifically, the content edited in a <xref:System.Windows.Controls.RichTextBox> is flow content.</span></span> <span data-ttu-id="64f94-130">フロー コンテンツは、書式設定されたテキスト、イメージ、リスト、テーブルなどのさまざまな種類の要素を格納できます。</span><span class="sxs-lookup"><span data-stu-id="64f94-130">Flow content can contain many types of elements including formatted text, images, lists, and tables.</span></span> <span data-ttu-id="64f94-131">フロー ドキュメントの詳細については、[フロー ドキュメントの概要](../advanced/flow-document-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-131">See [Flow Document Overview](../advanced/flow-document-overview.md) for in depth information on flow documents.</span></span> <span data-ttu-id="64f94-132">フローコンテンツを格納するために、 <xref:System.Windows.Controls.RichTextBox>はオブジェクト<xref:System.Windows.Documents.FlowDocument>をホストします。このオブジェクトには編集可能なコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="64f94-132">In order to contain flow content, a <xref:System.Windows.Controls.RichTextBox> hosts a <xref:System.Windows.Documents.FlowDocument> object which in turn contains the editable content.</span></span> <span data-ttu-id="64f94-133">でのフローの<xref:System.Windows.Controls.RichTextBox>内容を示すために、次のコードは、段落と太字のテキストを使用してを<xref:System.Windows.Controls.RichTextBox>作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64f94-133">To demonstrate flow content in a <xref:System.Windows.Controls.RichTextBox>, the following code shows how to create a <xref:System.Windows.Controls.RichTextBox> with a paragraph and some bolded text.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#RichTextBoxWithContentExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/RichTextBoxWithContentExample.xaml#richtextboxwithcontentexamplewholepage)]

[!code-csharp[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/CSharp/BasicRichTextBoxWithContentExample.cs#basicrichtextboxwithcontentcodeonlyexample)]
[!code-vb[RichTextBoxMiscSnippets_procedural_snip#BasicRichTextBoxWithContentCodeOnlyExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_procedural_snip/visualbasic/basicrichtextboxwithcontentexample.vb#basicrichtextboxwithcontentcodeonlyexample)]

<span data-ttu-id="64f94-134">次の図は、このサンプルがレンダリングする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64f94-134">The following illustration shows how this sample renders.</span></span>

<span data-ttu-id="64f94-135">![RichTextBox with content](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span><span class="sxs-lookup"><span data-stu-id="64f94-135">![RichTextBox with content](./media/editing-richtextbox-with-content.png "Editing_RichTextBox_with_Content")</span></span>

<span data-ttu-id="64f94-136">や<xref:System.Windows.Documents.Paragraph> <xref:System.Windows.Documents.Bold>のような要素は、内のコンテンツをどのように表示するかを決定します。<xref:System.Windows.Controls.RichTextBox></span><span class="sxs-lookup"><span data-stu-id="64f94-136">Elements like <xref:System.Windows.Documents.Paragraph> and <xref:System.Windows.Documents.Bold> determine how the content inside a <xref:System.Windows.Controls.RichTextBox> appears.</span></span> <span data-ttu-id="64f94-137">ユーザーがコンテンツを<xref:System.Windows.Controls.RichTextBox>編集すると、このフローの内容が変更されます。</span><span class="sxs-lookup"><span data-stu-id="64f94-137">As a user edits <xref:System.Windows.Controls.RichTextBox> content, they change this flow content.</span></span> <span data-ttu-id="64f94-138">フロー コンテンツの機能およびその操作方法の詳細については、[フロー ドキュメントの概要](../advanced/flow-document-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-138">To learn more about the features of flow content and how to work with it, see [Flow Document Overview](../advanced/flow-document-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="64f94-139">内のフローコンテンツ<xref:System.Windows.Controls.RichTextBox>は、他のコントロールに含まれるフローコンテンツとまったく同じようには動作しません。</span><span class="sxs-lookup"><span data-stu-id="64f94-139">Flow content inside a <xref:System.Windows.Controls.RichTextBox> does not behave exactly like flow content contained in other controls.</span></span> <span data-ttu-id="64f94-140">たとえば、に<xref:System.Windows.Controls.RichTextBox>は列がないため、自動サイズ変更の動作はありません。</span><span class="sxs-lookup"><span data-stu-id="64f94-140">For example, there are no columns in a <xref:System.Windows.Controls.RichTextBox> and hence no automatic resizing behavior.</span></span> <span data-ttu-id="64f94-141">また、内<xref:System.Windows.Controls.RichTextBox>では、検索、表示モード、ページナビゲーション、ズームなどの組み込み機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="64f94-141">Also, built in features like search, viewing mode, page navigation, and zoom are not available within a <xref:System.Windows.Controls.RichTextBox>.</span></span>

<a name="realtime_spellechecking"></a>

## <a name="real-time-spell-checking"></a><span data-ttu-id="64f94-142">リアルタイム スペル チェック</span><span class="sxs-lookup"><span data-stu-id="64f94-142">Real-time Spell Checking</span></span>

<span data-ttu-id="64f94-143"><xref:System.Windows.Controls.TextBox>または<xref:System.Windows.Controls.RichTextBox>でリアルタイムスペルチェックを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="64f94-143">You can enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="64f94-144">スペル チェックをオンにすると、スペル ミスの語句の下に赤色の線が表示されます (下図を参照)。</span><span class="sxs-lookup"><span data-stu-id="64f94-144">When spellchecking is turned on, a red line appears underneath any misspelled words (see picture below).</span></span>

<span data-ttu-id="64f94-145">![スペル チェックを含む Textbox](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span><span class="sxs-lookup"><span data-stu-id="64f94-145">![Textbox with spell&#45;checking](./media/editing-textbox-with-spellchecking.png "Editing_TextBox_with_Spellchecking")</span></span>

<span data-ttu-id="64f94-146">スペル チェックを有効にする方法については、「[テキスト編集コントロールでスペル チェックを有効にする](how-to-enable-spell-checking-in-a-text-editing-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-146">See [Enable Spell Checking in a Text Editing Control](how-to-enable-spell-checking-in-a-text-editing-control.md) to learn how to enable spellchecking.</span></span>

<a name="context_menu"></a>

## <a name="context-menu"></a><span data-ttu-id="64f94-147">コンテキスト メニュー</span><span class="sxs-lookup"><span data-stu-id="64f94-147">Context Menu</span></span>

<span data-ttu-id="64f94-148">既定では、 <xref:System.Windows.Controls.TextBox>と<xref:System.Windows.Controls.RichTextBox>の両方に、ユーザーがコントロール内を右クリックしたときに表示されるコンテキストメニューがあります。</span><span class="sxs-lookup"><span data-stu-id="64f94-148">By default, both <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.RichTextBox> have a context menu that appears when a user right-clicks inside the control.</span></span> <span data-ttu-id="64f94-149">コンテキスト メニューでは、ユーザーは、切り取り、コピー、または貼り付けをできます (下図を参照)。</span><span class="sxs-lookup"><span data-stu-id="64f94-149">The context menu allows the user to cut, copy, or paste (see illustration below).</span></span>

<span data-ttu-id="64f94-150">![コンテキスト メニューを含む TextBox](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span><span class="sxs-lookup"><span data-stu-id="64f94-150">![TextBox with context menu](./media/editing-textbox-with-context-menu.png "Editing_TextBox_with_Context_Menu")</span></span>

<span data-ttu-id="64f94-151">独自のカスタム コンテキスト メニューを作成して、既定のコンテキスト メニューをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="64f94-151">You can create your own custom context menu to override the default one.</span></span> <span data-ttu-id="64f94-152">詳細については、[カスタム コンテキスト メニューを RichTextBox に配置](how-to-position-a-custom-context-menu-in-a-richtextbox.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-152">See [Position a Custom Context Menu in a RichTextBox](how-to-position-a-custom-context-menu-in-a-richtextbox.md) for more information.</span></span>

<a name="detect_when_content_changes"></a>

## <a name="editing-commands"></a><span data-ttu-id="64f94-153">コマンドの編集</span><span class="sxs-lookup"><span data-stu-id="64f94-153">Editing Commands</span></span>

<span data-ttu-id="64f94-154">編集コマンドを使用すると、ユーザーが内<xref:System.Windows.Controls.RichTextBox>の編集可能なコンテンツを書式設定できます。</span><span class="sxs-lookup"><span data-stu-id="64f94-154">Editing commands enable users to format editable content inside a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="64f94-155">には、基本的な<xref:System.Windows.Controls.RichTextBox>編集コマンドに加え<xref:System.Windows.Controls.TextBox>て、でサポートされていない書式設定コマンドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="64f94-155">Besides basic editing commands, <xref:System.Windows.Controls.RichTextBox> includes formatting commands that <xref:System.Windows.Controls.TextBox> does not support.</span></span> <span data-ttu-id="64f94-156">たとえば、で編集する場合、 <xref:System.Windows.Controls.RichTextBox>ユーザーは Ctr + B キーを押して、太字のテキストの書式設定を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="64f94-156">For example, when editing in a <xref:System.Windows.Controls.RichTextBox>, a user could press Ctr+B to toggle bold text formatting.</span></span> <span data-ttu-id="64f94-157">使用<xref:System.Windows.Documents.EditingCommands>できるコマンドの完全な一覧については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-157">See <xref:System.Windows.Documents.EditingCommands> for a complete list of commands available.</span></span> <span data-ttu-id="64f94-158">キーボード ショートカットを使用するだけでなく、ボタンのようにコマンドをフックしてその他のコントロールにすることができます。</span><span class="sxs-lookup"><span data-stu-id="64f94-158">In addition to using keyboard shortcuts, you can hook commands up to other controls like buttons.</span></span> <span data-ttu-id="64f94-159">次の例では、テキストの書式設定を変更するためにユーザーが使用できるボタンを含む簡単なツールバーを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="64f94-159">The following example shows how to create a simple tool bar containing buttons that the user can use to change text formatting.</span></span>

[!code-xaml[RichTextBox_InputPanel_snip#RichTextBoxWithToolBarExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_InputPanel_snip/CS/Window1.xaml#richtextboxwithtoolbarexamplewholepage)]

<span data-ttu-id="64f94-160">次の図は、このサンプルの表示方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64f94-160">The following illustration shows how this sample displays.</span></span>

<span data-ttu-id="64f94-161">![ツールバーを含む RichTextBox](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span><span class="sxs-lookup"><span data-stu-id="64f94-161">![RichTextBox with ToolBar](./media/editing-richtextbox-with-toobar.gif "Editing_RichTextBox_with_TooBar")</span></span>

<a name="editing_commands"></a>

## <a name="detect-when-content-changes"></a><span data-ttu-id="64f94-162">コンテンツがいつ変更されたかの検出</span><span class="sxs-lookup"><span data-stu-id="64f94-162">Detect when Content Changes</span></span>

<span data-ttu-id="64f94-163">通常、 <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged>イベントは、 <xref:System.Windows.Controls.TextBox>または<xref:System.Windows.Controls.RichTextBox>のテキストが必要に<xref:System.Windows.UIElement.KeyDown>応じて変更されるたびに検出するために使用します。</span><span class="sxs-lookup"><span data-stu-id="64f94-163">Usually the <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> event should be used to detect whenever the text in a <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox> changes rather then <xref:System.Windows.UIElement.KeyDown> as you might expect.</span></span> <span data-ttu-id="64f94-164">例については、「[TextBox のテキストがいつ変更されたかを検出する](how-to-detect-when-text-in-a-textbox-has-changed.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64f94-164">See [Detect When Text in a TextBox Has Changed](how-to-detect-when-text-in-a-textbox-has-changed.md) for an example.</span></span>

<a name="save_load_and_print_richtextbox_content"></a>

## <a name="save-load-and-print-richtextbox-content"></a><span data-ttu-id="64f94-165">RichTextBox コンテンツの保存、読み込み、および印刷</span><span class="sxs-lookup"><span data-stu-id="64f94-165">Save, Load, and Print RichTextBox Content</span></span>

<span data-ttu-id="64f94-166">次の例は、の<xref:System.Windows.Controls.RichTextBox>コンテンツをファイルに保存し、その内容を<xref:System.Windows.Controls.RichTextBox>に読み込んでから、内容を印刷する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="64f94-166">The following example shows how to save content of a <xref:System.Windows.Controls.RichTextBox> to a file, load that content back into the <xref:System.Windows.Controls.RichTextBox>, and print the contents.</span></span> <span data-ttu-id="64f94-167">この例のマークアップを次に示します。</span><span class="sxs-lookup"><span data-stu-id="64f94-167">Below is the markup for the example.</span></span>

[!code-xaml[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml#saveloadprintrtbexamplewholepage)]

<span data-ttu-id="64f94-168">この例のコードを次に示します。</span><span class="sxs-lookup"><span data-stu-id="64f94-168">Below is the code behind for the example.</span></span>

[!code-csharp[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/SaveLoadPrintRTB.xaml.cs#saveloadprintrtbcodeexamplewholepage)]
[!code-vb[RichTextBoxMiscSnippets_snip#SaveLoadPrintRTBCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/SaveLoadPrintRTB.xaml.vb#saveloadprintrtbcodeexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="64f94-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="64f94-169">See also</span></span>

- [<span data-ttu-id="64f94-170">方法トピック</span><span class="sxs-lookup"><span data-stu-id="64f94-170">How-to Topics</span></span>](richtextbox-how-to-topics.md)
- [<span data-ttu-id="64f94-171">TextBox の概要</span><span class="sxs-lookup"><span data-stu-id="64f94-171">TextBox Overview</span></span>](textbox-overview.md)
