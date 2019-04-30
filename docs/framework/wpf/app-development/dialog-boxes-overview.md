---
title: ダイアログ ボックスの概要
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- modeless dialog boxes [WPF]
- dialog boxes [WPF]
- message boxes [WPF]
- modal dialog boxes [WPF]
ms.assetid: 0d23d544-a393-4a02-a3aa-d8cd5d3d6511
ms.openlocfilehash: 162414dbd4b0f5e15eceaf73c87c122701fefc4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052262"
---
# <a name="dialog-boxes-overview"></a><span data-ttu-id="bf99f-102">ダイアログ ボックスの概要</span><span class="sxs-lookup"><span data-stu-id="bf99f-102">Dialog Boxes Overview</span></span>
<span data-ttu-id="bf99f-103">スタンドアロン アプリケーションは、メインのデータをアプリケーションが動作し、使用してデータを処理する機能を公開しますが両方が表示されるメイン ウィンドウを通常がある[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]メニュー バー、ツールバー、およびステータス バーなどのメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-103">Standalone applications typically have a main window that both displays the main data over which the application operates and exposes the functionality to process that data through [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mechanisms like menu bars, tool bars, and status bars.</span></span> <span data-ttu-id="bf99f-104">重要なアプリケーションは、次のようなことをするための追加のウィンドウを表示することもあります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-104">A non-trivial application may also display additional windows to do the following:</span></span>  
  
- <span data-ttu-id="bf99f-105">固有の情報をユーザーに表示する。</span><span class="sxs-lookup"><span data-stu-id="bf99f-105">Display specific information to users.</span></span>  
  
- <span data-ttu-id="bf99f-106">ユーザーから情報を収集する。</span><span class="sxs-lookup"><span data-stu-id="bf99f-106">Gather information from users.</span></span>  
  
- <span data-ttu-id="bf99f-107">情報の表示と収集の両方を行う。</span><span class="sxs-lookup"><span data-stu-id="bf99f-107">Both display and gather information.</span></span>  
  
 <span data-ttu-id="bf99f-108">これらの種類のウィンドウと呼ばれる *ダイアログ ボックス*、し、2 種類があります: モーダルとモードレスです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-108">These types of windows are known as *dialog boxes*, and there are two types: modal and modeless.</span></span>  
  
 <span data-ttu-id="bf99f-109">A*モーダル*関数には、ユーザーに続行から追加のデータが必要がある場合、関数によってダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-109">A *modal* dialog box is displayed by a function when the function needs additional data from a user to continue.</span></span> <span data-ttu-id="bf99f-110">機能は、モーダル ダイアログ ボックスに依存してデータを収集するため、モーダル ダイアログ ボックスが開いている間、ユーザーはアプリケーション内の他のウィンドウをアクティブ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-110">Because the function depends on the modal dialog box to gather data, the modal dialog box also prevents a user from activating other windows in the application while it remains open.</span></span> <span data-ttu-id="bf99f-111">ほとんどの場合、モーダル ダイアログ ボックスにより、ユーザーを押すことによって、モーダル ダイアログ ボックスを終了するときに通知する、 **OK**または**キャンセル**ボタン。</span><span class="sxs-lookup"><span data-stu-id="bf99f-111">In most cases, a modal dialog box allows a user to signal when they have finished with the modal dialog box by pressing either an **OK** or **Cancel** button.</span></span> <span data-ttu-id="bf99f-112">キーを押して、 **OK**ボタンは、ユーザーがデータを入力し、関数がそのデータの処理を続行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-112">Pressing the **OK** button indicates that a user has entered data and wants the function to continue processing with that data.</span></span> <span data-ttu-id="bf99f-113">キーを押して、**キャンセル**ボタンは、ユーザーが、関数の実行を停止することを示します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-113">Pressing the **Cancel** button indicates that a user wants to stop the function from executing altogether.</span></span> <span data-ttu-id="bf99f-114">モーダル ダイアログ ボックスの最も一般的な例は、データを開く、保存する、および印刷するために表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-114">The most common examples of modal dialog boxes are shown to open, save, and print data.</span></span>  
  
 <span data-ttu-id="bf99f-115">A*モードレス*ダイアログ ボックスで、その一方で、できないユーザーを開いているときに、他のウィンドウをアクティブ化します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-115">A *modeless* dialog box, on the other hand, does not prevent a user from activating other windows while it is open.</span></span> <span data-ttu-id="bf99f-116">たとえば、ユーザーがドキュメント内の特定の単語の出現箇所を検索する場合、メイン ウィンドウは、多くの場合、ダイアログ ボックスを開いて、検索する単語をユーザーに尋ねます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-116">For example, if a user wants to find occurrences of a particular word in a document, a main window will often open a dialog box to ask a user what word they are looking for.</span></span> <span data-ttu-id="bf99f-117">しかし、単語の検索中もユーザーはドキュメントを編集できるため、ダイアログ ボックスがモーダルである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-117">Since finding a word doesn't prevent a user from editing the document, however, the dialog box doesn't need to be modal.</span></span> <span data-ttu-id="bf99f-118">モードレス ダイアログ ボックスは、少なくとも、**閉じます**をダイアログ ボックスを閉じるボタンをクリックしなどの特定の機能を実行するその他のボタンを提供することがあります、**次を検索**ボタン、[次へ] を検索する単語が単語の検索の検索条件に一致します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-118">A modeless dialog box at least provides a **Close** button to close the dialog box, and may provide additional buttons to execute specific functions, such as a **Find Next** button to find the next word that matches the find criteria of a word search.</span></span>  
  
 <span data-ttu-id="bf99f-119">Windows Presentation Foundation (WPF) ダイアログ ボックスに、メッセージ ボックス、コモン ダイアログ ボックスでは、カスタム ダイアログ ボックスなどのいくつかの種類を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-119">Windows Presentation Foundation (WPF) allows you to create several types of dialog boxes, including message boxes, common dialog boxes, and custom dialog boxes.</span></span> <span data-ttu-id="bf99f-120">このトピックでは、それぞれ、[ダイアログ ボックスのサンプル](https://go.microsoft.com/fwlink/?LinkID=159984)一致する例を示します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-120">This topic discusses each, and the [Dialog Box Sample](https://go.microsoft.com/fwlink/?LinkID=159984) provides matching examples.</span></span>  

<a name="Message_Boxes"></a>   
## <a name="message-boxes"></a><span data-ttu-id="bf99f-121">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="bf99f-121">Message Boxes</span></span>  
 <span data-ttu-id="bf99f-122">A*メッセージ ボックス*テキストの情報を表示し、ユーザーがボタンで意思決定できるようにするために使用できるダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-122">A *message box* is a dialog box that can be used to display textual information and to allow users to make decisions with buttons.</span></span> <span data-ttu-id="bf99f-123">次の図は、テキスト情報と質問を表示して、ユーザーが質問に回答するための 3 つのボタンを表示するメッセージ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-123">The following figure shows a message box that displays textual information, asks a question, and provides the user with three buttons to answer the question.</span></span>  
  
 ![アプリケーションの前に、ドキュメントに変更を保存するかどうかたずねるワード プロセッサ ダイアログ ボックスを閉じます。](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 <span data-ttu-id="bf99f-125">使用するメッセージ ボックスを作成する、<xref:System.Windows.MessageBox>クラス。</span><span class="sxs-lookup"><span data-stu-id="bf99f-125">To create a message box, you use the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="bf99f-126"><xref:System.Windows.MessageBox> メッセージ ボックスのテキスト、タイトル、アイコン、および、次のようなコードを使用して、ボタンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-126"><xref:System.Windows.MessageBox> lets you configure the message box text, title, icon, and buttons, using code like the following.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 <span data-ttu-id="bf99f-127">メッセージ ボックスを表示するを呼び出す、 `static` <xref:System.Windows.MessageBox.Show%2A>メソッドを次のコードに示されています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-127">To show a message box, you call the `static`<xref:System.Windows.MessageBox.Show%2A> method, as demonstrated in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 <span data-ttu-id="bf99f-128">メッセージ ボックスを表示するコードで、ユーザーの決定 (どのボタンが押されたか) を検出して処理する必要があるときには、コードは、次のコードに示されているように、メッセージ ボックスの結果を検査できます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-128">When code that shows a message box needs to detect and process the user's decision (which button was pressed), the code can inspect the message box result, as shown in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 <span data-ttu-id="bf99f-129">メッセージ ボックスの使用の詳細については、次を参照してください。 <xref:System.Windows.MessageBox>、[メッセージ ボックスのサンプル](https://go.microsoft.com/fwlink/?LinkID=160023)、および[ダイアログ ボックスのサンプル](https://go.microsoft.com/fwlink/?LinkID=159984)します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-129">For more information on using message boxes, see <xref:System.Windows.MessageBox>, [MessageBox Sample](https://go.microsoft.com/fwlink/?LinkID=160023), and [Dialog Box Sample](https://go.microsoft.com/fwlink/?LinkID=159984).</span></span>  
  
 <span data-ttu-id="bf99f-130"><xref:System.Windows.MessageBox>簡単なダイアログ ボックス ユーザー エクスペリエンスを使用する利点を提供できます<xref:System.Windows.MessageBox>が部分信頼セキュリティ サンド ボックス内で実行されるアプリケーションで表示できるウィンドウの唯一の種類 (を参照してください[セキュリティ](../security-wpf.md)) など[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-130">Although <xref:System.Windows.MessageBox> may offer a simple dialog box user experience, the advantage of using <xref:System.Windows.MessageBox> is that is the only type of window that can be shown by applications that run within a partial trust security sandbox (see [Security](../security-wpf.md)), such as [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)].</span></span>  
  
 <span data-ttu-id="bf99f-131">ほとんどのダイアログ ボックスは、テキスト、選択 (チェック ボックス)、相互に排他的な選択 (オプション ボタン)、リスト選択 (リスト ボックス、コンボ ボックス、ドロップダウン リスト ボックス) など、メッセージ ボックスの結果よりも複雑なデータを表示し、収集します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-131">Most dialog boxes display and gather more complex data than the result of a message box, including text, selection (check boxes), mutually exclusive selection (radio buttons), and list selection (list boxes, combo boxes, drop-down list boxes).</span></span> <span data-ttu-id="bf99f-132">、これらの Windows Presentation Foundation (WPF) はいくつかのコモン ダイアログ ボックスを提供し、いずれかの使用は完全な信頼で実行されているアプリケーションに制限されますが、独自のダイアログ ボックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-132">For these, Windows Presentation Foundation (WPF) provides several common dialog boxes and allows you to create your own dialog boxes, although the use of either is limited to applications running with full trust.</span></span>  
  
<a name="Common_Dialogs"></a>   
## <a name="common-dialog-boxes"></a><span data-ttu-id="bf99f-133">コモン ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="bf99f-133">Common Dialog Boxes</span></span>  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] <span data-ttu-id="bf99f-134">は、ファイルを開く、ファイルを保存する、印刷するためのダイアログ ボックスなど、すべてのアプリケーションに共通の、さまざまな再利用可能なダイアログ ボックスを実装します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-134">implements a variety of reusable dialog boxes that are common to all applications, including dialog boxes for opening files, saving files, and printing.</span></span> <span data-ttu-id="bf99f-135">これらのダイアログ ボックスはオペレーティング システムによって実装されるため、そのオペレーティング システム上で実行するすべてのアプリケーション間で共有でき、ユーザー エクスペリエンスの一貫性を保つことができます。ユーザーが 1 つのアプリケーションで、オペレーティング システムによって提供されるダイアログ ボックスの使用に慣れると、他のアプリケーションでも、そのダイアログ ボックスの使用法を学ぶ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-135">Since these dialog boxes are implemented by the operating system, they can be shared among all the applications that run on the operating system, which helps user experience consistency; when users are familiar with the use of an operating system-provided dialog box in one application, they don't need to learn how to use that dialog box in other applications.</span></span> <span data-ttu-id="bf99f-136">これらのダイアログ ボックスはすべてのアプリケーションで使用できる、一貫したユーザー エクスペリエンスを提供するのに役立つ、ために、これらと呼ばれます。*コモン ダイアログ ボックス*します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-136">Because these dialog boxes are available to all applications and because they help provide a consistent user experience, they are known as *common dialog boxes*.</span></span>  
  
 <span data-ttu-id="bf99f-137">Windows Presentation Foundation (WPF) で、開いているファイルをカプセル化しファイルを保存印刷コモン ダイアログ ボックスしそれらがスタンドアロン アプリケーションで使用するため、マネージ クラスを公開します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-137">Windows Presentation Foundation (WPF) encapsulates the open file, save file, and print common dialog boxes and exposes them as managed classes for you to use in standalone applications.</span></span> <span data-ttu-id="bf99f-138">このトピックでは、それぞれの概要を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-138">This topic provides a brief overview of each.</span></span>  
  
<a name="Open_File_Dialog"></a>   
### <a name="open-file-dialog"></a><span data-ttu-id="bf99f-139">[ファイルを開く] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="bf99f-139">Open File Dialog</span></span>  
 <span data-ttu-id="bf99f-140">[ファイルを開く] ダイアログ ボックスは、次の図に示されているように、開くファイルの名前を取得するために、ファイルを開く機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-140">The open file dialog box, shown in the following figure, is used by file opening functionality to retrieve the name of a file to open.</span></span>  
  
 ![ファイルを取得する場所を示す [開く] ダイアログ ボックス。](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 <span data-ttu-id="bf99f-142">一般的なファイルを開く ダイアログ ボックスとして実装されている、<xref:Microsoft.Win32.OpenFileDialog>クラスし、は、<xref:Microsoft.Win32>名前空間。</span><span class="sxs-lookup"><span data-stu-id="bf99f-142">The common open file dialog box is implemented as the <xref:Microsoft.Win32.OpenFileDialog> class and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="bf99f-143">次のコードは、[ファイルを開く] ダイアログ ボックスの作成、構成、および表示の方法と、結果を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-143">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 <span data-ttu-id="bf99f-144">ファイルを開く ダイアログ ボックスの詳細については、次を参照してください。<xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-144">For more information on the open file dialog box, see <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf99f-145"><xref:Microsoft.Win32.OpenFileDialog> 部分信頼で実行しているアプリケーションに安全にファイル名を取得する使用できます (を参照してください[セキュリティ](../security-wpf.md))。</span><span class="sxs-lookup"><span data-stu-id="bf99f-145"><xref:Microsoft.Win32.OpenFileDialog> can be used to safely retrieve file names by applications running with partial trust (see [Security](../security-wpf.md)).</span></span>  
  
<a name="Save_File_Dialog"></a>   
### <a name="save-file-dialog-box"></a><span data-ttu-id="bf99f-146">[ファイルの保存] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="bf99f-146">Save File Dialog Box</span></span>  
 <span data-ttu-id="bf99f-147">[ファイルの保存] ダイアログ ボックスは、次の図に示されているように、保存するファイルの名前を取得するために、ファイルを保存する機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-147">The save file dialog box, shown in the following figure, is used by file saving functionality to retrieve the name of a file to save.</span></span>  
  
 ![名前を付けて保存 ダイアログ ボックス、ファイルを保存する場所を示すです。](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 <span data-ttu-id="bf99f-149">一般的な保存ファイル ダイアログ ボックスとして実装されて、<xref:Microsoft.Win32.SaveFileDialog>クラスし、は、<xref:Microsoft.Win32>名前空間。</span><span class="sxs-lookup"><span data-stu-id="bf99f-149">The common save file dialog box is implemented as the <xref:Microsoft.Win32.SaveFileDialog> class, and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="bf99f-150">次のコードは、[ファイルを開く] ダイアログ ボックスの作成、構成、および表示の方法と、結果を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-150">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 <span data-ttu-id="bf99f-151">詳細については、保存ファイル ダイアログ ボックスを参照してください<xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-151">For more information on the save file dialog box, see <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.</span></span>  
  
<a name="Print_Dialog"></a>   
### <a name="print-dialog-box"></a><span data-ttu-id="bf99f-152">[印刷] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="bf99f-152">Print Dialog Box</span></span>  
 <span data-ttu-id="bf99f-153">次の図に示されているように、[印刷] ダイアログ ボックスは、ユーザーがデータを印刷するプリンターを選択し、構成するために、印刷機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-153">The print dialog box, shown in the following figure, is used by printing functionality to choose and configure the printer that a user would like to print data to.</span></span>  
  
 ![印刷ダイアログ ボックスのスクリーン ショット。](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
 <span data-ttu-id="bf99f-155">一般的な印刷ダイアログ ボックスとして実装されて、<xref:System.Windows.Controls.PrintDialog>クラスし、は、<xref:System.Windows.Controls>名前空間。</span><span class="sxs-lookup"><span data-stu-id="bf99f-155">The common print dialog box is implemented as the <xref:System.Windows.Controls.PrintDialog> class, and is located in the <xref:System.Windows.Controls> namespace.</span></span> <span data-ttu-id="bf99f-156">次のコードは、[印刷] ダイアログ ボックスの作成、構成、および表示の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-156">The following code shows how to create, configure, and show one.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 <span data-ttu-id="bf99f-157">[印刷] ダイアログ ボックスの詳細については、次を参照してください。<xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-157">For more information on the print dialog box, see <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bf99f-158">印刷の詳細については[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]を参照してください[印刷の概要](../advanced/printing-overview.md)します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-158">For detailed discussion of printing in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], see [Printing Overview](../advanced/printing-overview.md).</span></span>  
  
<a name="Custom_Dialog_Boxes"></a>   
## <a name="custom-dialog-boxes"></a><span data-ttu-id="bf99f-159">カスタム ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="bf99f-159">Custom Dialog Boxes</span></span>  
 <span data-ttu-id="bf99f-160">コモン ダイアログ ボックスは便利であり、可能なときにはコモン ダイアログ ボックスを使用する必要がありますが、ドメイン固有のダイアログ ボックスの要件はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-160">While common dialog boxes are useful, and should be used when possible, they do not support the requirements of domain-specific dialog boxes.</span></span> <span data-ttu-id="bf99f-161">このような場合は、独自のダイアログ ボックスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-161">In these cases, you need to create your own dialog boxes.</span></span> <span data-ttu-id="bf99f-162">これから説明するように、ダイアログ ボックスは、特殊な動作を持つウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-162">As we'll see, a dialog box is a window with special behaviors.</span></span> <span data-ttu-id="bf99f-163"><xref:System.Windows.Window> これらの動作を実装し、その結果を使用する<xref:System.Windows.Window>カスタムのモーダルとモードレスのダイアログ ボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-163"><xref:System.Windows.Window> implements those behaviors and, consequently, you use <xref:System.Windows.Window> to create custom modal and modeless dialog boxes.</span></span>  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>   
### <a name="creating-a-modal-custom-dialog-box"></a><span data-ttu-id="bf99f-164">モーダルのカスタム ダイアログ ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="bf99f-164">Creating a Modal Custom Dialog Box</span></span>  
 <span data-ttu-id="bf99f-165">このトピックでは、使用する方法を示します<xref:System.Windows.Window>一般的なモーダル ダイアログ ボックスの実装を作成するを使用して、 `Margins`  ダイアログ ボックスを例として (を参照してください[ダイアログ ボックスのサンプル](https://go.microsoft.com/fwlink/?LinkID=159984))。</span><span class="sxs-lookup"><span data-stu-id="bf99f-165">This topic shows how to use <xref:System.Windows.Window> to create a typical modal dialog box implementation, using the `Margins` dialog box as an example (see [Dialog Box Sample](https://go.microsoft.com/fwlink/?LinkID=159984)).</span></span> <span data-ttu-id="bf99f-166">`Margins`  ダイアログ ボックスは次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-166">The `Margins` dialog box is shown in the following figure.</span></span>  
  
 ![左余白、上余白、右の余白および下余白を定義するフィールドの余白 ダイアログ ボックス。](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a><span data-ttu-id="bf99f-168">モーダル ダイアログ ボックスの構成</span><span class="sxs-lookup"><span data-stu-id="bf99f-168">Configuring a Modal Dialog Box</span></span>  
 <span data-ttu-id="bf99f-169">一般的なダイアログ ボックスのユーザー インターフェイスには、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-169">The user interface for a typical dialog box includes the following:</span></span>  
  
- <span data-ttu-id="bf99f-170">必要なデータを収集するために必要なさまざまなコントロール。</span><span class="sxs-lookup"><span data-stu-id="bf99f-170">The various controls that are required to gather the desired data.</span></span>  
  
- <span data-ttu-id="bf99f-171">示す、 **OK**ユーザーがクリックすると、関数に戻り、ダイアログ ボックスを閉じるし、処理を続行ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-171">Showing an **OK** button that users click to close the dialog box, return to the function, and continue processing.</span></span>  
  
- <span data-ttu-id="bf99f-172">示す、**キャンセル**クリックするダイアログ ボックスを閉じるし、関数の処理を停止するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-172">Showing a **Cancel** button that users click to close the dialog box and stop the function from further processing.</span></span>  
  
- <span data-ttu-id="bf99f-173">表示、**閉じる**タイトル バーにボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-173">Showing a **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="bf99f-174">アイコンの表示。</span><span class="sxs-lookup"><span data-stu-id="bf99f-174">Showing an icon.</span></span>  
  
- <span data-ttu-id="bf99f-175">示す**最小化**、**最大化**、および**復元**ボタン。</span><span class="sxs-lookup"><span data-stu-id="bf99f-175">Showing **Minimize**, **Maximize**, and **Restore** buttons.</span></span>  
  
- <span data-ttu-id="bf99f-176">表示、**システム**メニューを最小限に抑える、最大化、復元、およびダイアログ ボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-176">Showing a **System** menu to minimize, maximize, restore, and close the dialog box.</span></span>  
  
- <span data-ttu-id="bf99f-177">ダイアログ ボックスは、ダイアログ ボックスを開いたウィンドウの上と中央に開きます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-177">Opening above and in the center of the window that opened the dialog box.</span></span>  
  
- <span data-ttu-id="bf99f-178">ダイアログ ボックスは、可能な場合はサイズ変更可能である必要があるため、ダイアログ ボックスが小さくなりすぎるのを避け、便利な既定サイズをユーザーに提供するために、既定の寸法と最小寸法の両方を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-178">Dialog boxes should be resizable where possible so, to prevent the dialog box from being too small, and to provide the user with a useful default size, you need to set both default and a minimum dimensions respectively.</span></span>  
  
- <span data-ttu-id="bf99f-179">原因となるキーボード ショートカットとして構成するか、ESC キーを押して、**キャンセル** ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-179">Pressing the ESC key should be configured as a keyboard shortcut that causes the **Cancel** button to be pressed.</span></span> <span data-ttu-id="bf99f-180">これを設定することで実現されます、<xref:System.Windows.Controls.Button.IsCancel%2A>のプロパティ、**キャンセル**ボタン`true`します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-180">This is achieved by setting the <xref:System.Windows.Controls.Button.IsCancel%2A> property of the **Cancel** button to `true`.</span></span>  
  
- <span data-ttu-id="bf99f-181">原因となるキーボード ショートカットとして構成する必要があります」と入力 (または RETURN) キーを押して、 **OK**  ボタンを押します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-181">Pressing the ENTER (or RETURN) key should be configured as a keyboard shortcut that causes the **OK** button to be pressed.</span></span> <span data-ttu-id="bf99f-182">これを設定することで実現されます、<xref:System.Windows.Controls.Button.IsDefault%2A>のプロパティ、 **OK**ボタン`true`します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-182">This is achieved by setting the <xref:System.Windows.Controls.Button.IsDefault%2A> property of the **OK** button `true`.</span></span>  
  
 <span data-ttu-id="bf99f-183">次のコードは、この構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-183">The following code demonstrates this configuration.</span></span>  
  
 [!code-xaml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup1)]  
[!code-xaml[DialogBoxSample#MarginsDialogBoxMainBitsMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogboxmainbitsmarkup2)]  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxmainbitscodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxMainBitsCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxmainbitscodebehind2)]  
  
 <span data-ttu-id="bf99f-184">ダイアログ ボックスのユーザー エクスペリエンスは、ダイアログ ボックスを開くウィンドウのメニュー バーにも及びます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-184">The user experience for a dialog box also extends into the menu bar of the window that opens the dialog box.</span></span> <span data-ttu-id="bf99f-185">メニュー項目が、機能の続行には、ダイアログ ボックスでのユーザーの操作を必要とする機能を実行するときには、次に示されているように、その機能のメニュー項目の見出しに省略記号を付けます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-185">When a menu item runs a function that requires user interaction through a dialog box before the function can continue, the menu item for the function will have an ellipsis in its header, as shown here.</span></span>  
  
 [!code-xaml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup1)]  
[!code-xaml[DialogBoxSample#MainWindowMarginsDialogBoxMenuItemMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#mainwindowmarginsdialogboxmenuitemmarkup2)]  
  
 <span data-ttu-id="bf99f-186">メニュー項目が、[バージョン情報] ダイアログ ボックスなど、ユーザーの操作を必要としないダイアログ ボックスを表示する機能を実行するときには、省略記号は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-186">When a menu item runs a function that displays a dialog box which does not require user interaction, such as an About dialog box, an ellipsis is not required.</span></span>  
  
#### <a name="opening-a-modal-dialog-box"></a><span data-ttu-id="bf99f-187">モーダル ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="bf99f-187">Opening a Modal Dialog Box</span></span>  
 <span data-ttu-id="bf99f-188">ダイアログ ボックスは、通常、ワード プロセッサでドキュメントの余白を設定するなど、ドメイン固有の機能を実行するためにユーザーがメニュー項目を選択した結果として表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-188">A dialog box is typically shown as a result of a user selecting a menu item to perform a domain-specific function, such as setting the margins of a document in a word processor.</span></span> <span data-ttu-id="bf99f-189">ウィンドウをダイアログ ボックスとして表示するのは、通常のウィンドウを表示するのと同様ですが、ダイアログ ボックス固有の追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="bf99f-189">Showing a window as a dialog box is similar to showing a normal window, although it requires additional dialog box-specific configuration.</span></span> <span data-ttu-id="bf99f-190">ダイアログ ボックスのインスタンス化、構成、および開くプロセスの全体を、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-190">The entire process of instantiating, configuring, and opening a dialog box is shown in the following code.</span></span>  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogcodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogcodebehind4)]  
  
 <span data-ttu-id="bf99f-191">ここでは、コードは、既定の情報 (現在の余白) をダイアログ ボックスに渡しています。</span><span class="sxs-lookup"><span data-stu-id="bf99f-191">Here, the code is passing default information (the current margins) to the dialog box.</span></span> <span data-ttu-id="bf99f-192">設定されることも、 <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType>  ダイアログ ボックスが表示されているウィンドウへの参照を持つプロパティです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-192">It is also setting the <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> property with a reference to the window that is showing the dialog box.</span></span> <span data-ttu-id="bf99f-193">すべてのダイアログ ボックスに共通するウィンドウの状態関連の動作を提供するダイアログ ボックスの所有者を設定するは常に一般に、(を参照してください[WPF Windows 概要](wpf-windows-overview.md)詳細については)。</span><span class="sxs-lookup"><span data-stu-id="bf99f-193">In general, you should always set the owner for a dialog box to provide window state-related behaviors that are common to all dialog boxes (see [WPF Windows Overview](wpf-windows-overview.md) for more information).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf99f-194">サポートするために所有者を指定する必要があります[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] ダイアログ ボックスのための自動化 (を参照してください[UI オートメーションの概要](../../ui-automation/ui-automation-overview.md))。</span><span class="sxs-lookup"><span data-stu-id="bf99f-194">You must provide an owner to support [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] automation for dialog boxes (see [UI Automation Overview](../../ui-automation/ui-automation-overview.md)).</span></span>  
  
 <span data-ttu-id="bf99f-195">呼び出しでモーダルとして表示されます ダイアログ ボックスを構成したら、<xref:System.Windows.Window.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bf99f-195">After the dialog box is configured, it is shown modally by calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  
  
#### <a name="validating-user-provided-data"></a><span data-ttu-id="bf99f-196">ユーザー指定データの検証</span><span class="sxs-lookup"><span data-stu-id="bf99f-196">Validating User-Provided Data</span></span>  
 <span data-ttu-id="bf99f-197">ダイアログ ボックスが開かれ、ユーザーが必要なデータを指定すると、ダイアログ ボックスは、指定されたデータが有効であることを確認する必要があります。これは、次のような理由からです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-197">When a dialog box is opened and the user provides the required data, a dialog box is responsible for ensuring that the provided data is valid for the following reasons:</span></span>  
  
- <span data-ttu-id="bf99f-198">セキュリティの観点から、すべての入力を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-198">From a security perspective, all input should be validated.</span></span>  
  
- <span data-ttu-id="bf99f-199">ドメイン固有の観点から、データの検証は、誤ったデータがコードによって処理されて、例外がスローされるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-199">From a domain-specific perspective, data validation prevents erroneous data from being processed by the code, which could potentially throw exceptions.</span></span>  
  
- <span data-ttu-id="bf99f-200">ユーザー エクスペリエンスの観点から、ダイアログ ボックスは、入力したデータが無効であることを示すことによって、ユーザーを支援できます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-200">From a user-experience perspective, a dialog box can help users by showing them which data they have entered is invalid.</span></span>  
  
- <span data-ttu-id="bf99f-201">パフォーマンスの観点から、多層アプリケーションでのデータの検証は、特に、アプリケーションが Web サービスまたはサーバーベースのデータベースで構成される場合、クライアント層とアプリケーション層の間のラウンド トリップの回数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-201">From a performance perspective, data validation in a multi-tier application can reduce the number of round trips between the client and the application tiers, particularly when the application is composed of Web services or server-based databases.</span></span>  
  
 <span data-ttu-id="bf99f-202">バインドされたコントロールを検証する[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]、検証規則を定義し、バインドに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-202">To validate a bound control in [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], you need to define a validation rule and associate it with the binding.</span></span> <span data-ttu-id="bf99f-203">検証規則はから派生したカスタム クラス<xref:System.Windows.Controls.ValidationRule>します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-203">A validation rule is a custom class that derives from <xref:System.Windows.Controls.ValidationRule>.</span></span> <span data-ttu-id="bf99f-204">次の例では、検証規則、 `MarginValidationRule`、バインドされている値は、ことをチェックする、<xref:System.Double>と、指定した範囲内にあります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-204">The following example shows a validation rule, `MarginValidationRule`, which checks that a bound value is a <xref:System.Double> and is within a specified range.</span></span>  
  
 [!code-csharp[DialogBoxSample#MarginValidationRuleCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs#marginvalidationrulecode)]
 [!code-vb[DialogBoxSample#MarginValidationRuleCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb#marginvalidationrulecode)]  
  
 <span data-ttu-id="bf99f-205">このコードは、オーバーライドすることで、検証規則の検証ロジックを実装、<xref:System.Windows.Controls.ValidationRule.Validate%2A>メソッドでは、データを検証し、適切な返します<xref:System.Windows.Controls.ValidationResult>します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-205">In this code, the validation logic of a validation rule is implemented by overriding the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method, which validates the data and returns an appropriate <xref:System.Windows.Controls.ValidationResult>.</span></span>  
  
 <span data-ttu-id="bf99f-206">検証規則をバインド コントロールに関連付けるには、次のマークアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-206">To associate the validation rule with the bound control, you use the following markup.</span></span>  
  
 [!code-xaml[DialogBoxSample#MarginsValidationMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup1)]  
[!code-xaml[DialogBoxSample#MarginsValidationMARKUP2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup2)]  
[!code-xaml[DialogBoxSample#MarginsValidationMARKUP3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsvalidationmarkup3)]  
  
 <span data-ttu-id="bf99f-207">検証規則が関連付けられている、[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]自動的に適用されますが、バインドされたコントロールにデータが入力されるとします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-207">Once the validation rule is associated, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] will automatically apply it when data is entered into the bound control.</span></span> <span data-ttu-id="bf99f-208">コントロールに無効なデータが含まれている場合[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]次の図に示すように、無効なコントロールでは、周囲に赤い境界線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-208">When a control contains invalid data, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] will display a red border around the invalid control, as shown in the following figure.</span></span>  
  
 ![無効な左余白の値を囲む赤い境界線付きの余白 ダイアログ ボックス。](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] <span data-ttu-id="bf99f-210">は、ユーザーが有効なデータを入力するまで、ユーザーを無効なコントロールに制限するわけではありません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-210">does not restrict a user to the invalid control until they have entered valid data.</span></span> <span data-ttu-id="bf99f-211">これは、ダイアログ ボックスとして適切な動作です。データが有効かどうかにかかわらず、ユーザーはダイアログ ボックス内のコントロールを自由に移動できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-211">This is good behavior for a dialog box; a user should be able to freely navigate the controls in a dialog box whether or not data is valid.</span></span> <span data-ttu-id="bf99f-212">ユーザーは、無効なデータとキーを押して入力してください。 ただし、これは意味、 **OK**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-212">However, this means a user can enter invalid data and press the **OK** button.</span></span> <span data-ttu-id="bf99f-213">このため、コードも必要があるダイアログ内のすべてのコントロールを検証するときにボックス、 **[ok]** ボタンを処理することによって、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="bf99f-213">For this reason, your code also needs to validate all controls in a dialog box when the **OK** button is pressed by handling the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxvalidationcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxValidationCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxvalidationcodebehind3)]  
  
 <span data-ttu-id="bf99f-214">このコードは、ウィンドウ上のすべての依存関係オブジェクトを列挙しますと、いずれかが有効でない場合 (によって返される<xref:System.Windows.Controls.Validation.GetHasError%2A>、無効なコントロールがフォーカスを取得、`IsValid`メソッドを返します。 `false`、ウィンドウは無効とみなされるとします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-214">This code enumerates all dependency objects on a window and, if any are invalid (as returned by <xref:System.Windows.Controls.Validation.GetHasError%2A>, the invalid control gets the focus, the `IsValid` method returns `false`, and the window is considered invalid.</span></span>  
  
 <span data-ttu-id="bf99f-215">ダイアログ ボックスが有効な場合は、安全に閉じて、戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-215">Once a dialog box is valid, it can safely close and return.</span></span> <span data-ttu-id="bf99f-216">復帰プロセスの一環として、呼び出し元の機能に結果を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-216">As part of the return process, it needs to return a result to the calling function.</span></span>  
  
#### <a name="setting-the-modal-dialog-result"></a><span data-ttu-id="bf99f-217">モーダル ダイアログ ボックスの結果を設定する</span><span class="sxs-lookup"><span data-stu-id="bf99f-217">Setting the Modal Dialog Result</span></span>  
 <span data-ttu-id="bf99f-218">使用してダイアログ ボックスを開く<xref:System.Windows.Window.ShowDialog%2A>メソッドを呼び出すようには、基本的に: を使用して、ダイアログ ボックスを開いたコード<xref:System.Windows.Window.ShowDialog%2A>まで待機<xref:System.Windows.Window.ShowDialog%2A>を返します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-218">Opening a dialog box using <xref:System.Windows.Window.ShowDialog%2A> is fundamentally like calling a method: the code that opened the dialog box using <xref:System.Windows.Window.ShowDialog%2A> waits until <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span> <span data-ttu-id="bf99f-219">ときに<xref:System.Windows.Window.ShowDialog%2A>返します、かどうかに基づくした処理を続行するか、処理を停止するかどうかを決定する必要がある呼び出し元コードには、ユーザーが押した、 **OK**ボタンまたは**キャンセル**ボタン。</span><span class="sxs-lookup"><span data-stu-id="bf99f-219">When <xref:System.Windows.Window.ShowDialog%2A> returns, the code that called it needs to decide whether to continue processing or stop processing, based on whether the user pressed the **OK** button or the **Cancel** button.</span></span> <span data-ttu-id="bf99f-220">として、ユーザーの選択肢を返す必要があります ダイアログ ボックスをこの決定を容易にする、<xref:System.Boolean>から返される値、<xref:System.Windows.Window.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bf99f-220">To facilitate this decision, the dialog box needs to return the user's choice as a <xref:System.Boolean> value that is returned from the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  
  
 <span data-ttu-id="bf99f-221">ときに、 **OK**ボタンがクリックされた<xref:System.Windows.Window.ShowDialog%2A>返す必要があります`true`します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-221">When the **OK** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `true`.</span></span> <span data-ttu-id="bf99f-222">これを設定することで実現されます、<xref:System.Windows.Window.DialogResult%2A>プロパティのダイアログ ボックス、 **OK**ボタンがクリックされました。</span><span class="sxs-lookup"><span data-stu-id="bf99f-222">This is achieved by setting the <xref:System.Windows.Window.DialogResult%2A> property of the dialog box when the **OK** button is clicked.</span></span>  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind3)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxokresultsetcodebehind4)]
[!code-vb[DialogBoxSample#MarginsDialogBoxOKResultSetCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxokresultsetcodebehind4)]  
  
 <span data-ttu-id="bf99f-223">その設定に注意してください、<xref:System.Windows.Window.DialogResult%2A>プロパティで明示的に呼び出す必要が自動的に閉じるウィンドウの指定も<xref:System.Windows.Window.Close%2A>します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-223">Note that setting the <xref:System.Windows.Window.DialogResult%2A> property also causes the window to close automatically, which alleviates the need to explicitly call <xref:System.Windows.Window.Close%2A>.</span></span>  
  
 <span data-ttu-id="bf99f-224">ときに、**キャンセル**ボタンがクリックされた<xref:System.Windows.Window.ShowDialog%2A>返す必要があります`false`を設定する必要があります、<xref:System.Windows.Window.DialogResult%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bf99f-224">When the **Cancel** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `false`, which also requires setting the <xref:System.Windows.Window.DialogResult%2A> property.</span></span>  
  
 [!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind1)]
 [!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind1)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind2)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind2)]  
[!code-csharp[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs#marginsdialogboxcancelresultsetcodebehind3)]
[!code-vb[DialogBoxSample#MarginsDialogBoxCancelResultSetCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb#marginsdialogboxcancelresultsetcodebehind3)]  
  
 <span data-ttu-id="bf99f-225">ボタンの<xref:System.Windows.Controls.Button.IsCancel%2A>プロパティに設定されて`true`か押すと、**キャンセル**ボタンか ESC キー、<xref:System.Windows.Window.DialogResult%2A>に自動的に設定されている`false`します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-225">When a button's <xref:System.Windows.Controls.Button.IsCancel%2A> property is set to `true` and the user presses either the **Cancel** button or the ESC key, <xref:System.Windows.Window.DialogResult%2A> is automatically set to `false`.</span></span> <span data-ttu-id="bf99f-226">次のマークアップが上記のコードで処理するために必要としない場合と同様、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベント。</span><span class="sxs-lookup"><span data-stu-id="bf99f-226">The following markup has the same effect as the preceding code, without the need to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
 [!code-xaml[DialogBoxSample#MarginsDialogDefaultCancelMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#marginsdialogdefaultcancelmarkup)]  
  
 <span data-ttu-id="bf99f-227">ダイアログ ボックスが自動的に返します`false`ユーザーが押すと、**閉じる**タイトル バーにボタンをクリックしてまたは選択、**閉じる**からメニュー項目、**システム**メニュー。</span><span class="sxs-lookup"><span data-stu-id="bf99f-227">A dialog box automatically returns `false` when a user presses the **Close** button in the title bar or chooses the **Close** menu item from the **System** menu.</span></span>  
  
#### <a name="processing-data-returned-from-a-modal-dialog-box"></a><span data-ttu-id="bf99f-228">モーダル ダイアログ ボックスから返されたデータの処理</span><span class="sxs-lookup"><span data-stu-id="bf99f-228">Processing Data Returned from a Modal Dialog Box</span></span>  
 <span data-ttu-id="bf99f-229">ときに<xref:System.Windows.Window.DialogResult%2A>設定 ダイアログ ボックスで開いた関数は、検査することによってダイアログ ボックスの結果を取得できます、<xref:System.Windows.Window.DialogResult%2A>プロパティと<xref:System.Windows.Window.ShowDialog%2A>を返します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-229">When <xref:System.Windows.Window.DialogResult%2A> is set by a dialog box, the function that opened it can get the dialog box result by inspecting the <xref:System.Windows.Window.DialogResult%2A> property when <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span>  
  
 [!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind1)]
 [!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind1)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind2)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind2)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind3)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind3)]  
[!code-csharp[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openmarginsdialogprocessreturncodebehind4)]
[!code-vb[DialogBoxSample#OpenMarginsDialogProcessReturnCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openmarginsdialogprocessreturncodebehind4)]  
  
 <span data-ttu-id="bf99f-230">ダイアログの結果が場合`true`関数を使用して、キューとを取得し、ユーザーが提供するデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-230">If the dialog result is `true`, the function uses that as a cue to retrieve and process the data provided by the user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf99f-231">後<xref:System.Windows.Window.ShowDialog%2A>が返されると、ダイアログ ボックスを再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-231">After <xref:System.Windows.Window.ShowDialog%2A> has returned, a dialog box cannot be reopened.</span></span> <span data-ttu-id="bf99f-232">代わりに、新しいインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-232">Instead, you need to create a new instance.</span></span>  
  
 <span data-ttu-id="bf99f-233">ダイアログの結果が場合`false`関数が適切に処理を終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-233">If the dialog result is `false`, the function should end processing appropriately.</span></span>  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>   
### <a name="creating-a-modeless-custom-dialog-box"></a><span data-ttu-id="bf99f-234">モードレス カスタム ダイアログ ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="bf99f-234">Creating a Modeless Custom Dialog Box</span></span>  
 <span data-ttu-id="bf99f-235">次の図に示されている [検索] ダイアログ ボックスなどのモードレス ダイアログ ボックスは、基本的な外観はモーダル ダイアログ ボックスと同じです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-235">A modeless dialog box, such as the Find Dialog Box shown in the following figure, has the same fundamental appearance as the modal dialog box.</span></span>  
  
 ![検索ダイアログ ボックスのスクリーン ショット。](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  
  
 <span data-ttu-id="bf99f-237">しかし、次のセクションで説明するように、動作は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-237">However, the behavior is slightly different, as described in the following sections.</span></span>  
  
#### <a name="opening-a-modeless-dialog-box"></a><span data-ttu-id="bf99f-238">モードレス ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="bf99f-238">Opening a Modeless Dialog Box</span></span>  
 <span data-ttu-id="bf99f-239">モードレス ダイアログ ボックスが呼び出すことによって開かれる、<xref:System.Windows.Window.Show%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="bf99f-239">A modeless dialog box is opened by calling the <xref:System.Windows.Window.Show%2A> method.</span></span>  
  
 [!code-xaml[DialogBoxSample#OpenFindDialogMARKUP1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#openfinddialogmarkup1)]  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind2)]  
[!code-csharp[DialogBoxSample#OpenFindDialogCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogcodebehind3)]
[!code-vb[DialogBoxSample#OpenFindDialogCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogcodebehind3)]  
  
 <span data-ttu-id="bf99f-240">異なり<xref:System.Windows.Window.ShowDialog%2A>、<xref:System.Windows.Window.Show%2A>が直ちに返されます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-240">Unlike <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> returns immediately.</span></span> <span data-ttu-id="bf99f-241">その結果、呼び出し元のウィンドウは、モードレス ダイアログ ボックスが閉じられたことを知ることができず、したがって、ダイアログ ボックスの結果を確認するタイミングを判断したり、ダイアログ ボックスからデータを取得して、さらに処理したりすることができません。</span><span class="sxs-lookup"><span data-stu-id="bf99f-241">Consequently, the calling window cannot tell when the modeless dialog box is closed and, therefore, does not know when to check for a dialog box result or get data from the dialog box for further processing.</span></span> <span data-ttu-id="bf99f-242">代わりに、ダイアログ ボックスは、別の方法を作成して、呼び出し元のウィンドウに処理用のデータを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-242">Instead, the dialog box needs to create an alternative way to return data to the calling window for processing.</span></span>  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a><span data-ttu-id="bf99f-243">モードレス ダイアログ ボックスから返されたデータの処理</span><span class="sxs-lookup"><span data-stu-id="bf99f-243">Processing Data Returned from a Modeless Dialog Box</span></span>  
 <span data-ttu-id="bf99f-244">この例で、 `FindDialogBox` 1 つまたは複数の検索によって特定の頻度に検索されているテキストのメイン ウィンドウに結果を返す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-244">In this example, the `FindDialogBox` may return one or more find results to the main window, depending on the text being searched for without any specific frequency.</span></span> <span data-ttu-id="bf99f-245">モーダル ダイアログ ボックスと同様、モードレス ダイアログ ボックスは、プロパティを使用して結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-245">As with a modal dialog box, a modeless dialog box can return results using properties.</span></span> <span data-ttu-id="bf99f-246">ただし、ダイアログ ボックスを所有しているウィンドウは、それらのプロパティを確認するタイミングを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-246">However, the window that owns the dialog box needs to know when to check those properties.</span></span> <span data-ttu-id="bf99f-247">これを可能にする方法の 1 つは、ダイアログ ボックスで、テキストが見つかったときに発生するイベントを実装することです。</span><span class="sxs-lookup"><span data-stu-id="bf99f-247">One way to enable this is for the dialog box to implement an event that is raised whenever text is found.</span></span> <span data-ttu-id="bf99f-248">`FindDialogBox` 実装して、`TextFoundEvent`この目的で、最初にデリゲートが必要です。</span><span class="sxs-lookup"><span data-stu-id="bf99f-248">`FindDialogBox` implements the `TextFoundEvent` for this purpose, which first requires a delegate.</span></span>  
  
 [!code-csharp[DialogBoxSample#TextFoundEventHandlerCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs#textfoundeventhandlercode)]
 [!code-vb[DialogBoxSample#TextFoundEventHandlerCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb#textfoundeventhandlercode)]  
  
 <span data-ttu-id="bf99f-249">使用して、`TextFoundEventHandler`デリゲート`FindDialogBox`実装、`TextFoundEvent`します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-249">Using the `TextFoundEventHandler` delegate, `FindDialogBox` implements the `TextFoundEvent`.</span></span>  
  
 [!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventcodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventcodebehind2)]  
  
 <span data-ttu-id="bf99f-250">その結果、`Find`検索結果が見つかった場合は、イベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="bf99f-250">Consequently, `Find` can raise the event when a search result is found.</span></span>  
  
 [!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind1)]
 [!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind1)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind2)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind2)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind3)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind3)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind4)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind4)]  
[!code-csharp[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#textfoundeventraisecodebehind5)]
[!code-vb[DialogBoxSample#TextFoundEventRaiseCODEBEHIND5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#textfoundeventraisecodebehind5)]  
  
 <span data-ttu-id="bf99f-251">そのとき、所有者ウィンドウは、このイベントを登録し、処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf99f-251">The owner window then needs to register with and handle this event.</span></span>  
  
 [!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind1)]
 [!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind1)]  
[!code-csharp[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs#openfinddialogresultcodebehind2)]
[!code-vb[DialogBoxSample#OpenFindDialogResultCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb#openfinddialogresultcodebehind2)]  
  
#### <a name="closing-a-modeless-dialog-box"></a><span data-ttu-id="bf99f-252">モードレス ダイアログ ボックスを閉じる</span><span class="sxs-lookup"><span data-stu-id="bf99f-252">Closing a Modeless Dialog Box</span></span>  
 <span data-ttu-id="bf99f-253"><xref:System.Windows.Window.DialogResult%2A>するシステムを使用して、モードレス ダイアログ ボックスを閉じることができますを設定する必要はありません、以下のメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="bf99f-253">Because <xref:System.Windows.Window.DialogResult%2A> does not need to be set, a modeless dialog can be closed using system provide mechanisms, including the following:</span></span>  
  
- <span data-ttu-id="bf99f-254">クリックすると、**閉じる**タイトル バーにボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-254">Clicking the **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="bf99f-255">Alt キーを押しながら F4 キーを押す。</span><span class="sxs-lookup"><span data-stu-id="bf99f-255">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="bf99f-256">選択**閉じる**から、**システム**メニュー。</span><span class="sxs-lookup"><span data-stu-id="bf99f-256">Choosing **Close** from the **System** menu.</span></span>  
  
 <span data-ttu-id="bf99f-257">または、コードを呼び出すことができます<xref:System.Windows.Window.Close%2A>ときに、**閉じる**ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bf99f-257">Alternatively, your code can call <xref:System.Windows.Window.Close%2A> when the **Close** button is clicked.</span></span>  
  
 [!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind1)]
 [!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind1)]  
[!code-csharp[DialogBoxSample#FindDialogCloseCODEBEHIND2](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs#finddialogclosecodebehind2)]
[!code-vb[DialogBoxSample#FindDialogCloseCODEBEHIND2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb#finddialogclosecodebehind2)]  
  
## <a name="see-also"></a><span data-ttu-id="bf99f-258">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf99f-258">See also</span></span>

- [<span data-ttu-id="bf99f-259">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="bf99f-259">Popup Overview</span></span>](../controls/popup-overview.md)
- [<span data-ttu-id="bf99f-260">ダイアログ ボックスのサンプル</span><span class="sxs-lookup"><span data-stu-id="bf99f-260">Dialog Box Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159984)
- [<span data-ttu-id="bf99f-261">ColorPicker カスタム コントロールのサンプル</span><span class="sxs-lookup"><span data-stu-id="bf99f-261">ColorPicker Custom Control Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159977)
