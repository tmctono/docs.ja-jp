---
title: Windows フォームにおける印刷のサポート
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- forms [Windows Forms], printing (using designer)
- printing [Windows Forms], Windows Forms, support
- printing [Windows Forms], print support
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
ms.openlocfilehash: 8e008f2cb4b2f32cdba676e68d9fd790530e2b06
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708133"
---
# <a name="windows-forms-print-support"></a><span data-ttu-id="be0af-102">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="be0af-102">Windows Forms Print Support</span></span>
<span data-ttu-id="be0af-103">Windows フォームでの印刷を使用して主に構成、 [PrintDocument コンポーネント](../controls/printdocument-component-windows-forms.md)を印刷するユーザーを有効にするコンポーネントと[PrintPreviewDialog コントロール](../controls/printpreviewdialog-control-windows-forms.md)コントロール、 [PrintDialogコンポーネント](../controls/printdialog-component-windows-forms.md)と[PageSetupDialog コンポーネント](../controls/pagesetupdialog-component-windows-forms.md)Windows オペレーティング システムに慣れているユーザーに使い慣れたグラフィカル インターフェイスを提供するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-103">Printing in Windows Forms consists primarily of using the [PrintDocument Component](../controls/printdocument-component-windows-forms.md) component to enable the user to print, and the [PrintPreviewDialog Control](../controls/printpreviewdialog-control-windows-forms.md) control, [PrintDialog Component](../controls/printdialog-component-windows-forms.md) and [PageSetupDialog Component](../controls/pagesetupdialog-component-windows-forms.md) components to provide a familiar graphical interface to users accustomed to the Windows operating system.</span></span>  
  
 <span data-ttu-id="be0af-104">通常の新しいインスタンスを作成、<xref:System.Drawing.Printing.PrintDocument>コンポーネントを使用して印刷する対象を記述するプロパティを設定する、<xref:System.Drawing.Printing.PrinterSettings>と<xref:System.Drawing.Printing.PageSettings>クラス、および呼び出し、<xref:System.Drawing.Printing.PrintDocument.Print%2A>実際には、ドキュメントを印刷する方法。</span><span class="sxs-lookup"><span data-stu-id="be0af-104">Typically, you create a new instance of the <xref:System.Drawing.Printing.PrintDocument> component, set the properties that describe what to print using the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to actually print the document.</span></span>  
  
 <span data-ttu-id="be0af-105">Windows ベースのアプリケーションから印刷の実行中に、<xref:System.Drawing.Printing.PrintDocument>コンポーネントをユーザーに警告印刷が発生しているという事実と印刷ジョブをキャンセルできる中止の印刷 ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="be0af-105">During the course of printing from a Windows-based application, the <xref:System.Drawing.Printing.PrintDocument> component will show an abort print dialog box to alert users to the fact that printing is occurring and to allow the print job to be canceled.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be0af-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="be0af-106">In This Section</span></span>  
 [<span data-ttu-id="be0af-107">方法: 標準の Windows フォーム印刷ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="be0af-107">How to: Create Standard Windows Forms Print Jobs</span></span>](how-to-create-standard-windows-forms-print-jobs.md)  
 <span data-ttu-id="be0af-108">使用する方法について説明します、<xref:System.Drawing.Printing.PrintDocument>から Windows フォームを印刷するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-108">Explains how to use the <xref:System.Drawing.Printing.PrintDocument> component to print from a Windows Form.</span></span>  
  
 [<span data-ttu-id="be0af-109">方法: 実行時に PrintDialog のユーザー入力をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="be0af-109">How to: Capture User Input from a PrintDialog at Run Time</span></span>](how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <span data-ttu-id="be0af-110">選択した印刷オプションを使用してプログラムで変更する方法について説明します、<xref:System.Windows.Forms.PrintDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-110">Explains how to modify selected print options programmatically using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="be0af-111">方法: Windows フォームでユーザーのコンピューターに接続されているプリンターを選択します。</span><span class="sxs-lookup"><span data-stu-id="be0af-111">How to: Choose the Printers Attached to a User's Computer in Windows Forms</span></span>](how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 <span data-ttu-id="be0af-112">印刷を使用するプリンターの変更について説明します、<xref:System.Windows.Forms.PrintDialog>実行時にコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-112">Describes changing the printer to print to using the <xref:System.Windows.Forms.PrintDialog> component at run time.</span></span>  
  
 [<span data-ttu-id="be0af-113">方法: Windows フォームでグラフィックスを印刷します。</span><span class="sxs-lookup"><span data-stu-id="be0af-113">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)  
 <span data-ttu-id="be0af-114">プリンターに送信側のグラフィックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="be0af-114">Describes sending graphics to the printer.</span></span>  
  
 [<span data-ttu-id="be0af-115">方法: Windows フォームで複数ページのテキスト ファイルを印刷します。</span><span class="sxs-lookup"><span data-stu-id="be0af-115">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 <span data-ttu-id="be0af-116">プリンターに送信するテキストをについて説明します。</span><span class="sxs-lookup"><span data-stu-id="be0af-116">Describes sending text to the printer.</span></span>  
  
 [<span data-ttu-id="be0af-117">方法: 完全な Windows フォームの印刷ジョブ</span><span class="sxs-lookup"><span data-stu-id="be0af-117">How to: Complete Windows Forms Print Jobs</span></span>](how-to-complete-windows-forms-print-jobs.md)  
 <span data-ttu-id="be0af-118">印刷ジョブの完了をユーザーに警告する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="be0af-118">Explains how to alert users to the completion of a print job.</span></span>  
  
 [<span data-ttu-id="be0af-119">方法: Windows フォームを印刷します。</span><span class="sxs-lookup"><span data-stu-id="be0af-119">How to: Print a Windows Form</span></span>](how-to-print-a-windows-form.md)  
 <span data-ttu-id="be0af-120">現在のフォームのコピーを印刷する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="be0af-120">Shows how to print a copy of the current form.</span></span>  
  
 [<span data-ttu-id="be0af-121">方法: 印刷プレビューを使用して Windows フォームで印刷します。</span><span class="sxs-lookup"><span data-stu-id="be0af-121">How to: Print in Windows Forms Using Print Preview</span></span>](how-to-print-in-windows-forms-using-print-preview.md)  
 <span data-ttu-id="be0af-122">使用する方法を示しています、<xref:System.Windows.Forms.PrintPreviewDialog>のドキュメントを印刷します。</span><span class="sxs-lookup"><span data-stu-id="be0af-122">Shows how to use a <xref:System.Windows.Forms.PrintPreviewDialog> for printing a document.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="be0af-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="be0af-123">Related Sections</span></span>  
 [<span data-ttu-id="be0af-124">PrintDocument コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be0af-124">PrintDocument Component</span></span>](../controls/printdocument-component-windows-forms.md)  
 <span data-ttu-id="be0af-125">使用方法について説明します、<xref:System.Drawing.Printing.PrintDocument>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-125">Explains usage of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 [<span data-ttu-id="be0af-126">PrintDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be0af-126">PrintDialog Component</span></span>](../controls/printdialog-component-windows-forms.md)  
 <span data-ttu-id="be0af-127">使用方法について説明します、<xref:System.Windows.Forms.PrintDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-127">Explains usage of the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
 [<span data-ttu-id="be0af-128">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="be0af-128">PrintPreviewDialog Control</span></span>](../controls/printpreviewdialog-control-windows-forms.md)  
 <span data-ttu-id="be0af-129">使用方法について説明します、<xref:System.Windows.Forms.PrintPreviewDialog>コントロール。</span><span class="sxs-lookup"><span data-stu-id="be0af-129">Explains usage of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
 [<span data-ttu-id="be0af-130">PageSetupDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="be0af-130">PageSetupDialog Component</span></span>](../controls/pagesetupdialog-component-windows-forms.md)  
 <span data-ttu-id="be0af-131">使用方法について説明します、<xref:System.Windows.Forms.PageSetupDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="be0af-131">Explains usage of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
 <xref:System.Drawing.Printing>  
 <span data-ttu-id="be0af-132">クラスについて説明します、<xref:System.Drawing.Printing>名前空間。</span><span class="sxs-lookup"><span data-stu-id="be0af-132">Describes the classes in the <xref:System.Drawing.Printing> namespace.</span></span>
