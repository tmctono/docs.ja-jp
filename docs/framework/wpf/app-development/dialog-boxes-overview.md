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
ms.openlocfilehash: c98d6a45d151d4b683a21e48eaeb5f4a19eaadb1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187450"
---
# <a name="dialog-boxes-overview"></a><span data-ttu-id="3855a-102">ダイアログ ボックスの概要</span><span class="sxs-lookup"><span data-stu-id="3855a-102">Dialog boxes overview</span></span>
<span data-ttu-id="3855a-103">スタンドアロン アプリケーションには、通常、メイン ウィンドウがあり、アプリケーションが動作するメイン データを表示し、メニュー バー、ツール[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]バー、ステータス バーなどのメカニズムを通じてそのデータを処理する機能を公開します。</span><span class="sxs-lookup"><span data-stu-id="3855a-103">Standalone applications typically have a main window that both displays the main data over which the application operates and exposes the functionality to process that data through [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] mechanisms like menu bars, tool bars, and status bars.</span></span> <span data-ttu-id="3855a-104">重要なアプリケーションは、次のようなことをするための追加のウィンドウを表示することもあります。</span><span class="sxs-lookup"><span data-stu-id="3855a-104">A non-trivial application may also display additional windows to do the following:</span></span>  
  
- <span data-ttu-id="3855a-105">固有の情報をユーザーに表示する。</span><span class="sxs-lookup"><span data-stu-id="3855a-105">Display specific information to users.</span></span>  
  
- <span data-ttu-id="3855a-106">ユーザーから情報を収集する。</span><span class="sxs-lookup"><span data-stu-id="3855a-106">Gather information from users.</span></span>  
  
- <span data-ttu-id="3855a-107">情報の表示と収集の両方を行う。</span><span class="sxs-lookup"><span data-stu-id="3855a-107">Both display and gather information.</span></span>  
  
 <span data-ttu-id="3855a-108">この種類のウィンドウはダイアログ*ボックス*と呼ばれ、モーダルとモードレスの 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-108">These types of windows are known as *dialog boxes*, and there are two types: modal and modeless.</span></span>  
  
 <span data-ttu-id="3855a-109">モー*ダル*ダイアログ ボックスは、関数が続行するためにユーザーからの追加データを必要とする場合に、関数によって表示されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-109">A *modal* dialog box is displayed by a function when the function needs additional data from a user to continue.</span></span> <span data-ttu-id="3855a-110">機能は、モーダル ダイアログ ボックスに依存してデータを収集するため、モーダル ダイアログ ボックスが開いている間、ユーザーはアプリケーション内の他のウィンドウをアクティブ化することはできません。</span><span class="sxs-lookup"><span data-stu-id="3855a-110">Because the function depends on the modal dialog box to gather data, the modal dialog box also prevents a user from activating other windows in the application while it remains open.</span></span> <span data-ttu-id="3855a-111">ほとんどの場合、モーダル ダイアログ ボックスを使用すると、ユーザーは **[OK]** または [**キャンセル]** ボタンを押して、モーダル ダイアログ ボックスが終了したときに通知を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-111">In most cases, a modal dialog box allows a user to signal when they have finished with the modal dialog box by pressing either an **OK** or **Cancel** button.</span></span> <span data-ttu-id="3855a-112">**[OK] ボタン**を押すと、ユーザーがデータを入力し、そのデータの処理を続行することを望んでいます。</span><span class="sxs-lookup"><span data-stu-id="3855a-112">Pressing the **OK** button indicates that a user has entered data and wants the function to continue processing with that data.</span></span> <span data-ttu-id="3855a-113">**[キャンセル]** ボタンを押すと、ユーザーは関数の実行を完全に停止します。</span><span class="sxs-lookup"><span data-stu-id="3855a-113">Pressing the **Cancel** button indicates that a user wants to stop the function from executing altogether.</span></span> <span data-ttu-id="3855a-114">モーダル ダイアログ ボックスの最も一般的な例は、データを開く、保存する、および印刷するために表示されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-114">The most common examples of modal dialog boxes are shown to open, save, and print data.</span></span>  
  
 <span data-ttu-id="3855a-115">一方、*モードレス*ダイアログ ボックスは、ユーザーが開いている間に他のウィンドウをアクティブにすることを防ぐものではありません。</span><span class="sxs-lookup"><span data-stu-id="3855a-115">A *modeless* dialog box, on the other hand, does not prevent a user from activating other windows while it is open.</span></span> <span data-ttu-id="3855a-116">たとえば、ユーザーがドキュメント内の特定の単語の出現箇所を検索する場合、メイン ウィンドウは、多くの場合、ダイアログ ボックスを開いて、検索する単語をユーザーに尋ねます。</span><span class="sxs-lookup"><span data-stu-id="3855a-116">For example, if a user wants to find occurrences of a particular word in a document, a main window will often open a dialog box to ask a user what word they are looking for.</span></span> <span data-ttu-id="3855a-117">しかし、単語の検索中もユーザーはドキュメントを編集できるため、ダイアログ ボックスがモーダルである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3855a-117">Since finding a word doesn't prevent a user from editing the document, however, the dialog box doesn't need to be modal.</span></span> <span data-ttu-id="3855a-118">モードレス ダイアログ ボックスには、少なくともダイアログ ボックスを閉じるには **[閉じる**] ボタンが用意されており、単語検索の検索条件に一致する次の単語を検索する [**次を検索**] ボタンなど、特定の機能を実行するための追加のボタンが用意されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-118">A modeless dialog box at least provides a **Close** button to close the dialog box, and may provide additional buttons to execute specific functions, such as a **Find Next** button to find the next word that matches the find criteria of a word search.</span></span>  
  
 <span data-ttu-id="3855a-119">Windows プレゼンテーションファンデーション (WPF) では、メッセージ ボックス、コモン ダイアログ ボックス、カスタム ダイアログ ボックスなど、さまざまな種類のダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3855a-119">Windows Presentation Foundation (WPF) allows you to create several types of dialog boxes, including message boxes, common dialog boxes, and custom dialog boxes.</span></span> <span data-ttu-id="3855a-120">このトピックでは、それぞれについて説明し、[ダイアログ ボックスのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)では、一致する例を示します。</span><span class="sxs-lookup"><span data-stu-id="3855a-120">This topic discusses each, and the [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox) provides matching examples.</span></span>  

<a name="Message_Boxes"></a>
## <a name="message-boxes"></a><span data-ttu-id="3855a-121">メッセージ ボックス</span><span class="sxs-lookup"><span data-stu-id="3855a-121">Message boxes</span></span>  
 <span data-ttu-id="3855a-122">*メッセージ ボックス*は、テキスト情報を表示したり、ユーザーがボタンを使用して決定を下したりするために使用できるダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="3855a-122">A *message box* is a dialog box that can be used to display textual information and to allow users to make decisions with buttons.</span></span> <span data-ttu-id="3855a-123">次の図は、テキスト情報と質問を表示して、ユーザーが質問に回答するための 3 つのボタンを表示するメッセージ ボックスを示しています。</span><span class="sxs-lookup"><span data-stu-id="3855a-123">The following figure shows a message box that displays textual information, asks a question, and provides the user with three buttons to answer the question.</span></span>  
  
 ![アプリケーションを閉じる前に文書に対する変更を保存するかどうかを確認する [ワード プロセッサ] ダイアログ ボックス。](./media/dialog-boxes-overview/word-processor-dialog.png)  
  
 <span data-ttu-id="3855a-125">メッセージ ボックスを作成するには、 クラス<xref:System.Windows.MessageBox>を使用します。</span><span class="sxs-lookup"><span data-stu-id="3855a-125">To create a message box, you use the <xref:System.Windows.MessageBox> class.</span></span> <span data-ttu-id="3855a-126"><xref:System.Windows.MessageBox>では、次のようなコードを使用して、メッセージ ボックスのテキスト、タイトル、アイコン、およびボタンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3855a-126"><xref:System.Windows.MessageBox> lets you configure the message box text, title, icon, and buttons, using code like the following.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxconfigurecodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxConfigureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxconfigurecodebehind)]  
  
 <span data-ttu-id="3855a-127">メッセージ ボックスを表示するには、次の`static`<xref:System.Windows.MessageBox.Show%2A>コードに示すように、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3855a-127">To show a message box, you call the `static`<xref:System.Windows.MessageBox.Show%2A> method, as demonstrated in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowcodebehind)]  
  
 <span data-ttu-id="3855a-128">メッセージ ボックスを表示するコードで、ユーザーの決定 (どのボタンが押されたか) を検出して処理する必要があるときには、コードは、次のコードに示されているように、メッセージ ボックスの結果を検査できます。</span><span class="sxs-lookup"><span data-stu-id="3855a-128">When code that shows a message box needs to detect and process the user's decision (which button was pressed), the code can inspect the message box result, as shown in the following code.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#msgboxshowandresultcodebehind1)]
 [!code-vb[DialogBoxesOverviewSnippets#MsgBoxShowAndResultCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#msgboxshowandresultcodebehind1)]  
  
 <span data-ttu-id="3855a-129">メッセージ ボックスの使用方法の詳細については、「 <xref:System.Windows.MessageBox> [」を](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox)参照[してください。](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)</span><span class="sxs-lookup"><span data-stu-id="3855a-129">For more information on using message boxes, see <xref:System.Windows.MessageBox>, [MessageBox Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/MessageBox), and [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox).</span></span>  
  
 <span data-ttu-id="3855a-130">単純<xref:System.Windows.MessageBox>なダイアログ ボックスのユーザー エクスペリエンスを提供する場合でも<xref:System.Windows.MessageBox>、使用の利点は、部分信頼セキュリティ サンドボックス内で実行されるアプリケーションで表示できる唯一のウィンドウです ([セキュリティ](../security-wpf.md)を参照) XAML ブラウザー アプリケーション (XAAP) など)。</span><span class="sxs-lookup"><span data-stu-id="3855a-130">Although <xref:System.Windows.MessageBox> may offer a simple dialog box user experience, the advantage of using <xref:System.Windows.MessageBox> is that is the only type of window that can be shown by applications that run within a partial trust security sandbox (see [Security](../security-wpf.md)), such as XAML browser applications (XBAPs).</span></span>  
  
 <span data-ttu-id="3855a-131">ほとんどのダイアログ ボックスは、テキスト、選択 (チェック ボックス)、相互に排他的な選択 (オプション ボタン)、リスト選択 (リスト ボックス、コンボ ボックス、ドロップダウン リスト ボックス) など、メッセージ ボックスの結果よりも複雑なデータを表示し、収集します。</span><span class="sxs-lookup"><span data-stu-id="3855a-131">Most dialog boxes display and gather more complex data than the result of a message box, including text, selection (check boxes), mutually exclusive selection (radio buttons), and list selection (list boxes, combo boxes, drop-down list boxes).</span></span> <span data-ttu-id="3855a-132">これらの場合、Windows プレゼンテーション ファンデーション (WPF) では、いくつかの共通ダイアログ ボックスが用意されており、独自のダイアログ ボックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3855a-132">For these, Windows Presentation Foundation (WPF) provides several common dialog boxes and allows you to create your own dialog boxes, although the use of either is limited to applications running with full trust.</span></span>  
  
<a name="Common_Dialogs"></a>
## <a name="common-dialog-boxes"></a><span data-ttu-id="3855a-133">コモン ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="3855a-133">Common dialog boxes</span></span>  
 <span data-ttu-id="3855a-134">Windows では、ファイルを開く、ファイルを保存する、印刷するためのダイアログ ボックスなど、すべてのアプリケーションに共通するさまざまな再利用可能なダイアログ ボックスが実装されています。</span><span class="sxs-lookup"><span data-stu-id="3855a-134">Windows implements a variety of reusable dialog boxes that are common to all applications, including dialog boxes for opening files, saving files, and printing.</span></span> <span data-ttu-id="3855a-135">これらのダイアログ ボックスはオペレーティング システムによって実装されるため、そのオペレーティング システム上で実行するすべてのアプリケーション間で共有でき、ユーザー エクスペリエンスの一貫性を保つことができます。ユーザーが 1 つのアプリケーションで、オペレーティング システムによって提供されるダイアログ ボックスの使用に慣れると、他のアプリケーションでも、そのダイアログ ボックスの使用法を学ぶ必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3855a-135">Since these dialog boxes are implemented by the operating system, they can be shared among all the applications that run on the operating system, which helps user experience consistency; when users are familiar with the use of an operating system-provided dialog box in one application, they don't need to learn how to use that dialog box in other applications.</span></span> <span data-ttu-id="3855a-136">これらのダイアログ ボックスはすべてのアプリケーションで使用でき、一貫したユーザー エクスペリエンスを提供するために役立つため、*コモン ダイアログ ボックス*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3855a-136">Because these dialog boxes are available to all applications and because they help provide a consistent user experience, they are known as *common dialog boxes*.</span></span>  
  
 <span data-ttu-id="3855a-137">Windows プレゼンテーション ファンデーション (WPF) は、開いているファイル、ファイルの保存、および共通のダイアログ ボックスの印刷をカプセル化し、スタンドアロン アプリケーションで使用するためのマネージ クラスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="3855a-137">Windows Presentation Foundation (WPF) encapsulates the open file, save file, and print common dialog boxes and exposes them as managed classes for you to use in standalone applications.</span></span> <span data-ttu-id="3855a-138">このトピックでは、それぞれの概要を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="3855a-138">This topic provides a brief overview of each.</span></span>  
  
<a name="Open_File_Dialog"></a>
### <a name="open-file-dialog"></a><span data-ttu-id="3855a-139">[ファイルを開く] ダイアログ</span><span class="sxs-lookup"><span data-stu-id="3855a-139">Open File dialog</span></span>  
 <span data-ttu-id="3855a-140">[ファイルを開く] ダイアログ ボックスは、次の図に示されているように、開くファイルの名前を取得するために、ファイルを開く機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-140">The open file dialog box, shown in the following figure, is used by file opening functionality to retrieve the name of a file to open.</span></span>  
  
 ![ファイルを取得する場所を示す [開く] ダイアログ ボックス。](./media/dialog-boxes-overview/open-file-dialog-box.png)  
  
 <span data-ttu-id="3855a-142">共通のファイルを開くダイアログ ボックスは<xref:Microsoft.Win32.OpenFileDialog>、クラスとして実装され、名前空間<xref:Microsoft.Win32>に配置されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-142">The common open file dialog box is implemented as the <xref:Microsoft.Win32.OpenFileDialog> class and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="3855a-143">次のコードは、[ファイルを開く] ダイアログ ボックスの作成、構成、および表示の方法と、結果を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3855a-143">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#openfiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#OpenFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#openfiledialogboxcodebehind)]  
  
 <span data-ttu-id="3855a-144">[ファイルを開く] ダイアログ ボックスの<xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3855a-144">For more information on the open file dialog box, see <xref:Microsoft.Win32.OpenFileDialog?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3855a-145"><xref:Microsoft.Win32.OpenFileDialog>部分信頼で実行されているアプリケーションによってファイル名を安全に取得するために使用できます[(Security](../security-wpf.md)を参照)。</span><span class="sxs-lookup"><span data-stu-id="3855a-145"><xref:Microsoft.Win32.OpenFileDialog> can be used to safely retrieve file names by applications running with partial trust (see [Security](../security-wpf.md)).</span></span>  
  
<a name="Save_File_Dialog"></a>
### <a name="save-file-dialog-box"></a><span data-ttu-id="3855a-146">[ファイルの保存] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="3855a-146">Save File dialog box</span></span>  
 <span data-ttu-id="3855a-147">[ファイルの保存] ダイアログ ボックスは、次の図に示されているように、保存するファイルの名前を取得するために、ファイルを保存する機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-147">The save file dialog box, shown in the following figure, is used by file saving functionality to retrieve the name of a file to save.</span></span>  
  
 ![ファイルを保存する場所を示す [名前を付けて保存] ダイアログ ボックス。](./media/dialog-boxes-overview/save-file-dialog-box.png)  
  
 <span data-ttu-id="3855a-149">共通の保存ファイル ダイアログ ボックスは<xref:Microsoft.Win32.SaveFileDialog>、クラスとして実装され、名前空間に<xref:Microsoft.Win32>配置されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-149">The common save file dialog box is implemented as the <xref:Microsoft.Win32.SaveFileDialog> class, and is located in the <xref:Microsoft.Win32> namespace.</span></span> <span data-ttu-id="3855a-150">次のコードは、[ファイルを開く] ダイアログ ボックスの作成、構成、および表示の方法と、結果を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3855a-150">The following code shows how to create, configure, and show one, and how to process the result.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#savefiledialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#SaveFileDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#savefiledialogboxcodebehind)]  
  
 <span data-ttu-id="3855a-151">[ファイルの保存] ダイアログ ボックスの詳細<xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3855a-151">For more information on the save file dialog box, see <xref:Microsoft.Win32.SaveFileDialog?displayProperty=nameWithType>.</span></span>  
  
<a name="Print_Dialog"></a>
### <a name="print-dialog-box"></a><span data-ttu-id="3855a-152">[印刷] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="3855a-152">Print dialog box</span></span>

<span data-ttu-id="3855a-153">次の図に示されているように、[印刷] ダイアログ ボックスは、ユーザーがデータを印刷するプリンターを選択し、構成するために、印刷機能によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-153">The print dialog box, shown in the following figure, is used by printing functionality to choose and configure the printer that a user would like to print data to.</span></span>  
  
![[印刷] ダイアログ ボックスを示すスクリーンショット。](./media/dialog-boxes-overview/print-data-dialog-box.png)  
  
<span data-ttu-id="3855a-155">共通の印刷ダイアログ ボックスは<xref:System.Windows.Controls.PrintDialog>クラスとして実装され、名前空間に<xref:System.Windows.Controls>配置されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-155">The common print dialog box is implemented as the <xref:System.Windows.Controls.PrintDialog> class, and is located in the <xref:System.Windows.Controls> namespace.</span></span> <span data-ttu-id="3855a-156">次のコードは、[印刷] ダイアログ ボックスの作成、構成、および表示の方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="3855a-156">The following code shows how to create, configure, and show one.</span></span>  
  
 [!code-csharp[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/CSharp/Window1.xaml.cs#printdialogboxcodebehind)]
 [!code-vb[DialogBoxesOverviewSnippets#PrintDialogBoxCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxesOverviewSnippets/VisualBasic/window1.xaml.vb#printdialogboxcodebehind)]  
  
 <span data-ttu-id="3855a-157">印刷ダイアログ ボックスの詳細については、「」を<xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>参照してください。</span><span class="sxs-lookup"><span data-stu-id="3855a-157">For more information on the print dialog box, see <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3855a-158">WPF での印刷の詳細については、「[印刷の概要](../advanced/printing-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3855a-158">For detailed discussion of printing in WPF, see [Printing Overview](../advanced/printing-overview.md).</span></span>  
  
<a name="Custom_Dialog_Boxes"></a>
## <a name="custom-dialog-boxes"></a><span data-ttu-id="3855a-159">カスタム ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="3855a-159">Custom dialog boxes</span></span>

<span data-ttu-id="3855a-160">コモン ダイアログ ボックスは便利であり、可能なときにはコモン ダイアログ ボックスを使用する必要がありますが、ドメイン固有のダイアログ ボックスの要件はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3855a-160">While common dialog boxes are useful, and should be used when possible, they do not support the requirements of domain-specific dialog boxes.</span></span> <span data-ttu-id="3855a-161">このような場合は、独自のダイアログ ボックスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-161">In these cases, you need to create your own dialog boxes.</span></span> <span data-ttu-id="3855a-162">これから説明するように、ダイアログ ボックスは、特殊な動作を持つウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="3855a-162">As we'll see, a dialog box is a window with special behaviors.</span></span> <span data-ttu-id="3855a-163"><xref:System.Windows.Window>これらの動作を実装し、その結果、カスタム モー<xref:System.Windows.Window>ダルおよびモードレス ダイアログ ボックスを作成するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3855a-163"><xref:System.Windows.Window> implements those behaviors and, consequently, you use <xref:System.Windows.Window> to create custom modal and modeless dialog boxes.</span></span>  
  
<a name="Creating_a_Modal_Custom_Dialog_Box"></a>
### <a name="creating-a-modal-custom-dialog-box"></a><span data-ttu-id="3855a-164">モーダル カスタム ダイアログ ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="3855a-164">Creating a modal custom dialog box</span></span>

<span data-ttu-id="3855a-165">ここでは、ダイアログ ボックスを<xref:System.Windows.Window>例として使用して、標準的なモーダル ダイアログ`Margins`ボックスの実装を作成する方法を示します (「[ダイアログ ボックスのサンプル](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3855a-165">This topic shows how to use <xref:System.Windows.Window> to create a typical modal dialog box implementation, using the `Margins` dialog box as an example (see [Dialog Box Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)).</span></span> <span data-ttu-id="3855a-166">ダイアログ`Margins`ボックスを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="3855a-166">The `Margins` dialog box is shown in the following figure.</span></span>  
  
 ![[余白] ダイアログ ボックスで、左余白、上余白、右余白、および下余白を定義するフィールドを指定します。](./media/dialog-boxes-overview/margin-size-dialog-box.png)  
  
#### <a name="configuring-a-modal-dialog-box"></a><span data-ttu-id="3855a-168">モーダル ダイアログ ボックスの構成</span><span class="sxs-lookup"><span data-stu-id="3855a-168">Configuring a modal dialog box</span></span>

<span data-ttu-id="3855a-169">一般的なダイアログ ボックスのユーザー インターフェイスには、次の項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3855a-169">The user interface for a typical dialog box includes the following:</span></span>  
  
- <span data-ttu-id="3855a-170">必要なデータを収集するために必要なさまざまなコントロール。</span><span class="sxs-lookup"><span data-stu-id="3855a-170">The various controls that are required to gather the desired data.</span></span>  
  
- <span data-ttu-id="3855a-171">ユーザーがクリックしてダイアログ ボックスを閉じ、関数に戻り、処理を続行する **[OK]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="3855a-171">An **OK** button that users click to close the dialog box, return to the function, and continue processing.</span></span>  
  
- <span data-ttu-id="3855a-172">ユーザーがクリックしてダイアログ ボックスを閉じ、関数の処理を中止する **[キャンセル]** ボタン。</span><span class="sxs-lookup"><span data-stu-id="3855a-172">A **Cancel** button that users click to close the dialog box and stop the function from further processing.</span></span>  
  
- <span data-ttu-id="3855a-173">タイトル バーの**閉じる**ボタン。</span><span class="sxs-lookup"><span data-stu-id="3855a-173">A **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="3855a-174">アイコン。</span><span class="sxs-lookup"><span data-stu-id="3855a-174">An icon.</span></span>  
  
- <span data-ttu-id="3855a-175">**最小化**、**最大化**、および**復元**の各ボタン。</span><span class="sxs-lookup"><span data-stu-id="3855a-175">**Minimize**, **Maximize**, and **Restore** buttons.</span></span>  
  
- <span data-ttu-id="3855a-176">ダイアログ ボックスを最小化、最大化、復元、および閉じる**システム**メニュー。</span><span class="sxs-lookup"><span data-stu-id="3855a-176">A **System** menu to minimize, maximize, restore, and close the dialog box.</span></span>  
  
- <span data-ttu-id="3855a-177">ダイアログ ボックスを開いたウィンドウの上および中央の位置。</span><span class="sxs-lookup"><span data-stu-id="3855a-177">A position above and in the center of the window that opened the dialog box.</span></span>  
  
- <span data-ttu-id="3855a-178">ダイアログ ボックスが小さすぎるのを防ぐために可能な場合にサイズを変更する機能と、ユーザーに便利な既定のサイズを提供する機能。</span><span class="sxs-lookup"><span data-stu-id="3855a-178">The ability to be resized where possible to prevent the dialog box from being too small, and to provide the user with a useful default size.</span></span> <span data-ttu-id="3855a-179">これには、既定の寸法と最小の寸法の両方を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-179">This requires that you set both the default and a minimum dimensions.</span></span>  
  
- <span data-ttu-id="3855a-180">Esc キーを押すと、**キャンセル**ボタンが押されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-180">The ESC key as a keyboard shortcut that causes the **Cancel** button to be pressed.</span></span> <span data-ttu-id="3855a-181">この操作を行うには、[<xref:System.Windows.Controls.Button.IsCancel%2A>**キャンセル]** ボタンのプロパティ`true`を に設定します。</span><span class="sxs-lookup"><span data-stu-id="3855a-181">You do this by setting the <xref:System.Windows.Controls.Button.IsCancel%2A> property of the **Cancel** button to `true`.</span></span>  
  
- <span data-ttu-id="3855a-182">ENTER キー (RETURN キー) をキーボード ショートカットとして押すと **、[OK]** ボタンが押されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-182">The ENTER (or RETURN) key as a keyboard shortcut that causes the **OK** button to be pressed.</span></span> <span data-ttu-id="3855a-183">これは、 **[** OK <xref:System.Windows.Controls.Button.IsDefault%2A> ] ボタン`true`のプロパティを設定することによって行います。</span><span class="sxs-lookup"><span data-stu-id="3855a-183">You do this by setting the <xref:System.Windows.Controls.Button.IsDefault%2A> property of the **OK** button `true`.</span></span>  
  
<span data-ttu-id="3855a-184">次のコードは、この構成の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="3855a-184">The following code demonstrates this configuration.</span></span>  
  
[!code-xaml[MarginsDialogBox XAML file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,106-112)]  

[!code-csharp[MarginsDialogBox C# code-behind](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-12,67-68)]
[!code-vb[MarginsDialogBox VB code-behind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-11,61-62)]  
  
<span data-ttu-id="3855a-185">ダイアログ ボックスのユーザー エクスペリエンスは、ダイアログ ボックスを開くウィンドウのメニュー バーにも及びます。</span><span class="sxs-lookup"><span data-stu-id="3855a-185">The user experience for a dialog box also extends into the menu bar of the window that opens the dialog box.</span></span> <span data-ttu-id="3855a-186">メニュー項目が、機能の続行には、ダイアログ ボックスでのユーザーの操作を必要とする機能を実行するときには、次に示されているように、その機能のメニュー項目の見出しに省略記号を付けます。</span><span class="sxs-lookup"><span data-stu-id="3855a-186">When a menu item runs a function that requires user interaction through a dialog box before the function can continue, the menu item for the function will have an ellipsis in its header, as shown here.</span></span>  
  
[!code-xaml[Menu bar of MainWindow.Xaml file](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L26-L27)]  
  
<span data-ttu-id="3855a-187">メニュー項目が、[バージョン情報] ダイアログ ボックスなど、ユーザーの操作を必要としないダイアログ ボックスを表示する機能を実行するときには、省略記号は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3855a-187">When a menu item runs a function that displays a dialog box which does not require user interaction, such as an About dialog box, an ellipsis is not required.</span></span>  
  
#### <a name="opening-a-modal-dialog-box"></a><span data-ttu-id="3855a-188">モーダル ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="3855a-188">Opening a modal dialog box</span></span>

<span data-ttu-id="3855a-189">ダイアログ ボックスは、通常、ワード プロセッサでドキュメントの余白を設定するなど、ドメイン固有の機能を実行するためにユーザーがメニュー項目を選択した結果として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-189">A dialog box is typically shown as a result of a user selecting a menu item to perform a domain-specific function, such as setting the margins of a document in a word processor.</span></span> <span data-ttu-id="3855a-190">ウィンドウをダイアログ ボックスとして表示するのは、通常のウィンドウを表示するのと同様ですが、ダイアログ ボックス固有の追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="3855a-190">Showing a window as a dialog box is similar to showing a normal window, although it requires additional dialog box-specific configuration.</span></span> <span data-ttu-id="3855a-191">ダイアログ ボックスのインスタンス化、構成、および開くプロセスの全体を、次のコードに示します。</span><span class="sxs-lookup"><span data-stu-id="3855a-191">The entire process of instantiating, configuring, and opening a dialog box is shown in the following code.</span></span>  
  
[!code-csharp[Opening a modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-11,78-88,193-195)]
[!code-vb[Opening a modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58-67,130-132)]  

<span data-ttu-id="3855a-192">ここでは、既定の情報 (現在の余白) をダイアログ ボックスに渡します。</span><span class="sxs-lookup"><span data-stu-id="3855a-192">Here, the code passes default information (the current margins) to the dialog box.</span></span> <span data-ttu-id="3855a-193">また、ダイアログ<xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType>ボックスを表示しているウィンドウへの参照を使用してプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="3855a-193">It also sets the <xref:System.Windows.Window.Owner%2A?displayProperty=nameWithType> property with a reference to the window that is showing the dialog box.</span></span> <span data-ttu-id="3855a-194">一般に、すべてのダイアログ ボックスに共通するウィンドウ状態に関連する動作を提供するには、ダイアログ ボックスの所有者を常に設定する必要があります (詳細については[、「WPF Windows の概要](wpf-windows-overview.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="3855a-194">In general, you should always set the owner for a dialog box to provide window state-related behaviors that are common to all dialog boxes (see [WPF Windows Overview](wpf-windows-overview.md) for more information).</span></span>

> [!NOTE]
> <span data-ttu-id="3855a-195">ダイアログ ボックスのユーザー インターフェイス (UI) オートメーションをサポートする所有者を指定する必要があります[(「UI オートメーションの概要](../../ui-automation/ui-automation-overview.md)」を参照)。</span><span class="sxs-lookup"><span data-stu-id="3855a-195">You must provide an owner to support user interface (UI) automation for dialog boxes (see [UI Automation Overview](../../ui-automation/ui-automation-overview.md)).</span></span>

<span data-ttu-id="3855a-196">ダイアログ ボックスを構成すると、メソッドを呼び出すことによってモーダル<xref:System.Windows.Window.ShowDialog%2A>に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-196">After the dialog box is configured, it is shown modally by calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  
  
#### <a name="validating-user-provided-data"></a><span data-ttu-id="3855a-197">ユーザーが指定したデータの検証</span><span class="sxs-lookup"><span data-stu-id="3855a-197">Validating user-provided data</span></span>

<span data-ttu-id="3855a-198">ダイアログ ボックスが開かれ、ユーザーが必要なデータを指定すると、ダイアログ ボックスは、指定されたデータが有効であることを確認する必要があります。これは、次のような理由からです。</span><span class="sxs-lookup"><span data-stu-id="3855a-198">When a dialog box is opened and the user provides the required data, a dialog box is responsible for ensuring that the provided data is valid for the following reasons:</span></span>  
  
- <span data-ttu-id="3855a-199">セキュリティの観点から、すべての入力を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-199">From a security perspective, all input should be validated.</span></span>  
  
- <span data-ttu-id="3855a-200">ドメイン固有の観点から、データの検証は、誤ったデータがコードによって処理されて、例外がスローされるのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="3855a-200">From a domain-specific perspective, data validation prevents erroneous data from being processed by the code, which could potentially throw exceptions.</span></span>  
  
- <span data-ttu-id="3855a-201">ユーザー エクスペリエンスの観点から、ダイアログ ボックスは、入力したデータが無効であることを示すことによって、ユーザーを支援できます。</span><span class="sxs-lookup"><span data-stu-id="3855a-201">From a user-experience perspective, a dialog box can help users by showing them which data they have entered is invalid.</span></span>  
  
- <span data-ttu-id="3855a-202">パフォーマンスの観点から、多層アプリケーションでのデータの検証は、特に、アプリケーションが Web サービスまたはサーバーベースのデータベースで構成される場合、クライアント層とアプリケーション層の間のラウンド トリップの回数を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-202">From a performance perspective, data validation in a multi-tier application can reduce the number of round trips between the client and the application tiers, particularly when the application is composed of Web services or server-based databases.</span></span>  

<span data-ttu-id="3855a-203">WPF でバインドされたコントロールを検証するには、検証規則を定義し、バインドに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-203">To validate a bound control in WPF, you need to define a validation rule and associate it with the binding.</span></span> <span data-ttu-id="3855a-204">検証規則は、 から<xref:System.Windows.Controls.ValidationRule>派生するカスタム クラスです。</span><span class="sxs-lookup"><span data-stu-id="3855a-204">A validation rule is a custom class that derives from <xref:System.Windows.Controls.ValidationRule>.</span></span> <span data-ttu-id="3855a-205">次の例は、`MarginValidationRule`バインドされた値が<xref:System.Double>指定された範囲内にあるかどうかをチェックする検証規則を示しています。</span><span class="sxs-lookup"><span data-stu-id="3855a-205">The following example shows a validation rule, `MarginValidationRule`, which checks that a bound value is a <xref:System.Double> and is within a specified range.</span></span>  

[!code-csharp[Margin validation rules](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginValidationRule.cs)]
[!code-vb[Margin validation rules](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginValidationRule.vb)]  

<span data-ttu-id="3855a-206">このコードでは、検証規則の検証ロジックは、<xref:System.Windows.Controls.ValidationRule.Validate%2A>メソッドをオーバーライドして実装され、メソッドはデータを検証し、適切な<xref:System.Windows.Controls.ValidationResult>を返します。</span><span class="sxs-lookup"><span data-stu-id="3855a-206">In this code, the validation logic of a validation rule is implemented by overriding the <xref:System.Windows.Controls.ValidationRule.Validate%2A> method, which validates the data and returns an appropriate <xref:System.Windows.Controls.ValidationResult>.</span></span>  

<span data-ttu-id="3855a-207">検証規則をバインド コントロールに関連付けるには、次のマークアップを使用します。</span><span class="sxs-lookup"><span data-stu-id="3855a-207">To associate the validation rule with the bound control, you use the following markup.</span></span>  
  
[!code-xaml[Associating a validation rule with a control](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml?range=1-16,57-68,111-112)]

<span data-ttu-id="3855a-208">検証規則が関連付けられると、バインドされたコントロールにデータが入力されると、WPF によって自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-208">Once the validation rule is associated, WPF will automatically apply it when data is entered into the bound control.</span></span> <span data-ttu-id="3855a-209">コントロールに無効なデータが含まれている場合、次の図に示すように、無効なコントロールの周りに赤い枠線が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-209">When a control contains invalid data, WPF will display a red border around the invalid control, as shown in the following figure.</span></span>  
  
![無効な左余白の値の周りに赤い枠線が表示された [余白] ダイアログ ボックス](./media/dialog-boxes-overview/invalid-left-margin-dialog.png)  

<span data-ttu-id="3855a-211">WPF では、ユーザーが有効なデータを入力するまで、無効なコントロールにユーザーを制限しません。</span><span class="sxs-lookup"><span data-stu-id="3855a-211">WPF does not restrict a user to the invalid control until they have entered valid data.</span></span> <span data-ttu-id="3855a-212">これは、ダイアログ ボックスとして適切な動作です。データが有効かどうかにかかわらず、ユーザーはダイアログ ボックス内のコントロールを自由に移動できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-212">This is good behavior for a dialog box; a user should be able to freely navigate the controls in a dialog box whether or not data is valid.</span></span> <span data-ttu-id="3855a-213">ただし、これはユーザーが無効なデータを入力して **[OK]ボタン**を押すことができるという意味です。</span><span class="sxs-lookup"><span data-stu-id="3855a-213">However, this means a user can enter invalid data and press the **OK** button.</span></span> <span data-ttu-id="3855a-214">このため、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>イベントを処理して **[OK]** ボタンを押したときに、ダイアログ ボックス内のすべてのコントロールを検証する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="3855a-214">For this reason, your code also needs to validate all controls in a dialog box when the **OK** button is pressed by handling the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-csharp[Validating all controls in a dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,26-29,33-68)]
[!code-vb[Validating all controls in a dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27-29,33-62)]  

<span data-ttu-id="3855a-215">このコードは、ウィンドウ上のすべての依存関係オブジェクトを列挙し、無効な場合 (無効な<xref:System.Windows.Controls.Validation.GetHasError%2A>コントロールがフォーカスを取得し、`IsValid`メソッドが返`false`し、ウィンドウが無効と見なされます)。</span><span class="sxs-lookup"><span data-stu-id="3855a-215">This code enumerates all dependency objects on a window and, if any are invalid (as returned by <xref:System.Windows.Controls.Validation.GetHasError%2A>, the invalid control gets the focus, the `IsValid` method returns `false`, and the window is considered invalid.</span></span>  
  
<span data-ttu-id="3855a-216">ダイアログ ボックスが有効な場合は、安全に閉じて、戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-216">Once a dialog box is valid, it can safely close and return.</span></span> <span data-ttu-id="3855a-217">復帰プロセスの一環として、呼び出し元の機能に結果を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-217">As part of the return process, it needs to return a result to the calling function.</span></span>  
  
#### <a name="setting-the-modal-dialog-result"></a><span data-ttu-id="3855a-218">モーダル ダイアログ結果の設定</span><span class="sxs-lookup"><span data-stu-id="3855a-218">Setting the modal dialog result</span></span>

<span data-ttu-id="3855a-219">を使用して<xref:System.Windows.Window.ShowDialog%2A>ダイアログ ボックスを開くことは、メソッドを呼び出すのと基本的に似<xref:System.Windows.Window.ShowDialog%2A>ています:<xref:System.Windows.Window.ShowDialog%2A>戻るまで待機を使用してダイアログ ボックスを開いたコード。</span><span class="sxs-lookup"><span data-stu-id="3855a-219">Opening a dialog box using <xref:System.Windows.Window.ShowDialog%2A> is fundamentally like calling a method: the code that opened the dialog box using <xref:System.Windows.Window.ShowDialog%2A> waits until <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span> <span data-ttu-id="3855a-220">返<xref:System.Windows.Window.ShowDialog%2A>されるときに、呼び出したコードは、ユーザーが **[OK]** ボタンを押したか **、[キャンセル]** ボタンを押したかに基づいて、処理を続行するか停止するかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-220">When <xref:System.Windows.Window.ShowDialog%2A> returns, the code that called it needs to decide whether to continue processing or stop processing, based on whether the user pressed the **OK** button or the **Cancel** button.</span></span> <span data-ttu-id="3855a-221">この決定を容易にするために、ダイアログ ボックスは、メソッドから返される値としてユーザー<xref:System.Boolean>の選択を<xref:System.Windows.Window.ShowDialog%2A>返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-221">To facilitate this decision, the dialog box needs to return the user's choice as a <xref:System.Boolean> value that is returned from the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span>  

<span data-ttu-id="3855a-222">**[OK]** ボタンをクリックすると<xref:System.Windows.Window.ShowDialog%2A>、`true`が戻ります。</span><span class="sxs-lookup"><span data-stu-id="3855a-222">When the **OK** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `true`.</span></span> <span data-ttu-id="3855a-223">これは **、[OK]** ボタン<xref:System.Windows.Window.DialogResult%2A>をクリックしたときにダイアログ ボックスのプロパティを設定することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-223">This is achieved by setting the <xref:System.Windows.Window.DialogResult%2A> property of the dialog box when the **OK** button is clicked.</span></span>  

[!code-csharp[Responding to the OK button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,25-27,32-33,67-68)]
[!code-vb[Responding to the OK button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,27,31-33,61-62)]  

<span data-ttu-id="3855a-224">このプロパティを<xref:System.Windows.Window.DialogResult%2A>設定すると、ウィンドウが自動的に閉じ、明示的に呼び出す<xref:System.Windows.Window.Close%2A>必要が軽減されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3855a-224">Note that setting the <xref:System.Windows.Window.DialogResult%2A> property also causes the window to close automatically, which alleviates the need to explicitly call <xref:System.Windows.Window.Close%2A>.</span></span>  
  
<span data-ttu-id="3855a-225">**[キャンセル**] ボタンをクリックすると<xref:System.Windows.Window.ShowDialog%2A>、`false`が返されます<xref:System.Windows.Window.DialogResult%2A>。</span><span class="sxs-lookup"><span data-stu-id="3855a-225">When the **Cancel** button is clicked, <xref:System.Windows.Window.ShowDialog%2A> should return `false`, which also requires setting the <xref:System.Windows.Window.DialogResult%2A> property.</span></span>  
  
[!code-csharp[Responding to the Cancel button](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml.cs?range=1-8,19-24,67-68)]
[!code-vb[Responding to the Cancel button](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MarginsDialogBox.xaml.vb?range=1-8,22-25,61-62)]  

<span data-ttu-id="3855a-226">ボタン<xref:System.Windows.Controls.Button.IsCancel%2A>のプロパティが`true`に設定され、ユーザーが**キャンセル**ボタンまたは Esc キーを押すと、<xref:System.Windows.Window.DialogResult%2A>自動的に に`false`に 設定されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-226">When a button's <xref:System.Windows.Controls.Button.IsCancel%2A> property is set to `true` and the user presses either the **Cancel** button or the ESC key, <xref:System.Windows.Window.DialogResult%2A> is automatically set to `false`.</span></span> <span data-ttu-id="3855a-227">次のマークアップは、<xref:System.Windows.Controls.Primitives.ButtonBase.Click>前のコードと同じ結果になり、イベントを処理する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3855a-227">The following markup has the same effect as the preceding code, without the need to handle the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span>  
  
[!code-xaml[Markup instead of handling the Click event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MarginsDialogBox.xaml#L109-L109)]  

<span data-ttu-id="3855a-228">ユーザーがタイトル バー`false`の **[閉じる**] ボタンを押すか、[**システム**] メニューの [**閉じる**] メニュー項目をクリックすると、ダイアログ ボックスが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3855a-228">A dialog box automatically returns `false` when a user presses the **Close** button in the title bar or chooses the **Close** menu item from the **System** menu.</span></span>  

#### <a name="processing-data-returned-from-a-modal-dialog-box"></a><span data-ttu-id="3855a-229">モーダル ダイアログ ボックスから返されるデータの処理</span><span class="sxs-lookup"><span data-stu-id="3855a-229">Processing data returned from a modal dialog box</span></span>  

<span data-ttu-id="3855a-230">ダイアログ<xref:System.Windows.Window.DialogResult%2A>ボックスで設定すると、ダイアログ ボックスを開いた関数は、プロパティが返されたときに<xref:System.Windows.Window.DialogResult%2A><xref:System.Windows.Window.ShowDialog%2A>検査を行うことで、ダイアログ ボックスの結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="3855a-230">When <xref:System.Windows.Window.DialogResult%2A> is set by a dialog box, the function that opened it can get the dialog box result by inspecting the <xref:System.Windows.Window.DialogResult%2A> property when <xref:System.Windows.Window.ShowDialog%2A> returns.</span></span>  
  
[!code-csharp[Processing data returned from the modal dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,77-79,89-96,194-195)]
[!code-vb[Processing data returned from the modal dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,58,69-73,131-132)]

<span data-ttu-id="3855a-231">ダイアログの結果が`true`の場合、関数は、ユーザーが提供するデータを取得して処理するためのキューとしてそれを使用します。</span><span class="sxs-lookup"><span data-stu-id="3855a-231">If the dialog result is `true`, the function uses that as a cue to retrieve and process the data provided by the user.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3855a-232">戻<xref:System.Windows.Window.ShowDialog%2A>った後で、ダイアログ ボックスを再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="3855a-232">After <xref:System.Windows.Window.ShowDialog%2A> has returned, a dialog box cannot be reopened.</span></span> <span data-ttu-id="3855a-233">代わりに、新しいインスタンスを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-233">Instead, you need to create a new instance.</span></span>

<span data-ttu-id="3855a-234">ダイアログの結果が`false`の場合、関数は処理を適切に終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-234">If the dialog result is `false`, the function should end processing appropriately.</span></span>  
  
<a name="Creating_a_Modeless_Custom_Dialog_Box"></a>
### <a name="creating-a-modeless-custom-dialog-box"></a><span data-ttu-id="3855a-235">モードレスカスタム ダイアログ ボックスの作成</span><span class="sxs-lookup"><span data-stu-id="3855a-235">Creating a modeless custom dialog box</span></span>

<span data-ttu-id="3855a-236">次の図に示されている [検索] ダイアログ ボックスなどのモードレス ダイアログ ボックスは、基本的な外観はモーダル ダイアログ ボックスと同じです。</span><span class="sxs-lookup"><span data-stu-id="3855a-236">A modeless dialog box, such as the Find Dialog Box shown in the following figure, has the same fundamental appearance as the modal dialog box.</span></span>  

![[検索] ダイアログ ボックスを示すスクリーンショット。](./media/dialog-boxes-overview/find-modeless-dialog-box.png)  

<span data-ttu-id="3855a-238">しかし、次のセクションで説明するように、動作は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="3855a-238">However, the behavior is slightly different, as described in the following sections.</span></span>  
  
#### <a name="opening-a-modeless-dialog-box"></a><span data-ttu-id="3855a-239">モードレス ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="3855a-239">Opening a modeless dialog box</span></span>

<span data-ttu-id="3855a-240">メソッドを呼び出すと、モードレス<xref:System.Windows.Window.Show%2A>ダイアログ ボックスが開きます。</span><span class="sxs-lookup"><span data-stu-id="3855a-240">A modeless dialog box is opened by calling the <xref:System.Windows.Window.Show%2A> method.</span></span>  

[!code-xaml[XAML to define a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml#L21-L22)]  

[!code-csharp[Opening a modeless dialog box](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,65-76,194-195)]
[!code-vb[Openng a modeless dialog box](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,18-23,131,132)]  

<span data-ttu-id="3855a-241">と<xref:System.Windows.Window.ShowDialog%2A>は<xref:System.Windows.Window.Show%2A>異なり、 はすぐに戻ります。</span><span class="sxs-lookup"><span data-stu-id="3855a-241">Unlike <xref:System.Windows.Window.ShowDialog%2A>, <xref:System.Windows.Window.Show%2A> returns immediately.</span></span> <span data-ttu-id="3855a-242">その結果、呼び出し元のウィンドウは、モードレス ダイアログ ボックスが閉じられたことを知ることができず、したがって、ダイアログ ボックスの結果を確認するタイミングを判断したり、ダイアログ ボックスからデータを取得して、さらに処理したりすることができません。</span><span class="sxs-lookup"><span data-stu-id="3855a-242">Consequently, the calling window cannot tell when the modeless dialog box is closed and, therefore, does not know when to check for a dialog box result or get data from the dialog box for further processing.</span></span> <span data-ttu-id="3855a-243">代わりに、ダイアログ ボックスは、別の方法を作成して、呼び出し元のウィンドウに処理用のデータを返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-243">Instead, the dialog box needs to create an alternative way to return data to the calling window for processing.</span></span>  
  
#### <a name="processing-data-returned-from-a-modeless-dialog-box"></a><span data-ttu-id="3855a-244">モードレス ダイアログ ボックスから返されたデータの処理</span><span class="sxs-lookup"><span data-stu-id="3855a-244">Processing data returned from a modeless dialog box</span></span>  

<span data-ttu-id="3855a-245">この例では、`FindDialogBox`は、特定の頻度を指定せずに検索されるテキストに応じて、1 つ以上の検索結果をメイン ウィンドウに返します。</span><span class="sxs-lookup"><span data-stu-id="3855a-245">In this example, the `FindDialogBox` may return one or more find results to the main window, depending on the text being searched for without any specific frequency.</span></span> <span data-ttu-id="3855a-246">モーダル ダイアログ ボックスと同様、モードレス ダイアログ ボックスは、プロパティを使用して結果を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-246">As with a modal dialog box, a modeless dialog box can return results using properties.</span></span> <span data-ttu-id="3855a-247">ただし、ダイアログ ボックスを所有しているウィンドウは、それらのプロパティを確認するタイミングを知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-247">However, the window that owns the dialog box needs to know when to check those properties.</span></span> <span data-ttu-id="3855a-248">これを可能にする方法の 1 つは、ダイアログ ボックスで、テキストが見つかったときに発生するイベントを実装することです。</span><span class="sxs-lookup"><span data-stu-id="3855a-248">One way to enable this is for the dialog box to implement an event that is raised whenever text is found.</span></span> <span data-ttu-id="3855a-249">`FindDialogBox`は、この`TextFoundEvent`目的のために実装します。</span><span class="sxs-lookup"><span data-stu-id="3855a-249">`FindDialogBox` implements the `TextFoundEvent` for this purpose, which first requires a delegate.</span></span>  

[!code-csharp[The TextFoundEventHandler delegate](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/TextFoundEventHandler.cs)]
[!code-vb[The TextFoundEventHandler delegate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/TextFoundEventHandler.vb)]  

<span data-ttu-id="3855a-250">デリゲートを`TextFoundEventHandler`使用して`FindDialogBox`、 を`TextFoundEvent`実装します。</span><span class="sxs-lookup"><span data-stu-id="3855a-250">Using the `TextFoundEventHandler` delegate, `FindDialogBox` implements the `TextFoundEvent`.</span></span>
  
[!code-csharp[The TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-17,125-126)]
[!code-vb[The TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-15,102-103)]

<span data-ttu-id="3855a-251">結果として、`Find`検索結果が見つかったときにイベントを発生させることができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-251">Consequently, `Find` can raise the event when a search result is found.</span></span>  
  
[!code-csharp[Raising the TextFound event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,50-52,91-94,124-127)]
[!code-vb[Raising the TextFound event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,15,60-64,102-103)]  

<span data-ttu-id="3855a-252">そのとき、所有者ウィンドウは、このイベントを登録し、処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3855a-252">The owner window then needs to register with and handle this event.</span></span>

[!code-csharp[Registering and handling the event](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/MainWindow.xaml.cs?range=1-10,184-195)]
[!code-vb[Registering and handling the event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/MainWindow.xaml.vb?range=1-9,126-132)]  

#### <a name="closing-a-modeless-dialog-box"></a><span data-ttu-id="3855a-253">モードレス ダイアログ ボックスを閉じる</span><span class="sxs-lookup"><span data-stu-id="3855a-253">Closing a modeless dialog box</span></span>

<span data-ttu-id="3855a-254">設定<xref:System.Windows.Window.DialogResult%2A>する必要がないため、システム提供機構を使用してモードレスダイアログを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-254">Because <xref:System.Windows.Window.DialogResult%2A> does not need to be set, a modeless dialog can be closed using system provide mechanisms, including the following:</span></span>  
  
- <span data-ttu-id="3855a-255">タイトル バーの **[閉じる**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3855a-255">Clicking the **Close** button in the title bar.</span></span>  
  
- <span data-ttu-id="3855a-256">Alt キーを押しながら F4 キーを押す。</span><span class="sxs-lookup"><span data-stu-id="3855a-256">Pressing ALT+F4.</span></span>  
  
- <span data-ttu-id="3855a-257">[システム] メニューから **[閉じる**]**を選択**します。</span><span class="sxs-lookup"><span data-stu-id="3855a-257">Choosing **Close** from the **System** menu.</span></span>  
  
<span data-ttu-id="3855a-258">または、[**閉じる**] ボタン<xref:System.Windows.Window.Close%2A>がクリックされたときにコードを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="3855a-258">Alternatively, your code can call <xref:System.Windows.Window.Close%2A> when the **Close** button is clicked.</span></span>  

[!code-csharp[Calling the Close method](~/samples/snippets/csharp/VS_Snippets_Wpf/DialogBoxSample/CSharp/FindDialogBox.xaml.cs?range=1-9,119-126)]
[!code-vb[Calling the Close method](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DialogBoxSample/VisualBasic/FindDialogBox.xaml.vb?range=1-9,99-103)]  

## <a name="see-also"></a><span data-ttu-id="3855a-259">関連項目</span><span class="sxs-lookup"><span data-stu-id="3855a-259">See also</span></span>

- [<span data-ttu-id="3855a-260">ポップアップの概要</span><span class="sxs-lookup"><span data-stu-id="3855a-260">Popup Overview</span></span>](../controls/popup-overview.md)
- [<span data-ttu-id="3855a-261">ダイアログ ボックスのサンプル</span><span class="sxs-lookup"><span data-stu-id="3855a-261">Dialog Box Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Windows/DialogBox)
