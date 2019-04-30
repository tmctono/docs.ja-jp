---
title: PrintDialog コンポーネントを表示する方法
ms.date: 03/30/2017
helpviewer_keywords:
- Print dialog box [Windows Forms], displaying
- PrintDialog component [Windows Forms], displaying
- printing [Windows Forms], displaying print dialog box
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
ms.openlocfilehash: 198ae75d407bd1837033a1cc186d84ff972fdc2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941571"
---
# <a name="how-to-display-the-printdialog-component"></a><span data-ttu-id="a66e8-102">PrintDialog コンポーネントを表示する方法</span><span class="sxs-lookup"><span data-stu-id="a66e8-102">How to display the PrintDialog component</span></span>

<span data-ttu-id="a66e8-103"><xref:System.Windows.Forms.PrintDialog>コンポーネントは、多くのユーザーは使い慣れている標準の Windows 印刷ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="a66e8-103">The <xref:System.Windows.Forms.PrintDialog> component is the standard Windows print dialog box that many of your users will be familiar with.</span></span> <span data-ttu-id="a66e8-104">なので、ユーザーはすぐに慣れてを使用するには有益なります、<xref:System.Windows.Forms.PrintDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="a66e8-104">Because your users will be immediately comfortable with it, it would be beneficial for you to use the <xref:System.Windows.Forms.PrintDialog> component.</span></span>

## <a name="to-display-the-printdialog-component"></a><span data-ttu-id="a66e8-105">PrintDialog コンポーネントを表示するには</span><span class="sxs-lookup"><span data-stu-id="a66e8-105">To display the PrintDialog component</span></span>

- <span data-ttu-id="a66e8-106">呼び出す、<xref:System.Windows.Forms.Form.ShowDialog%2A>アプリケーションのコード内からメソッド。</span><span class="sxs-lookup"><span data-stu-id="a66e8-106">Call the <xref:System.Windows.Forms.Form.ShowDialog%2A> method from within the code of your application.</span></span>

     <span data-ttu-id="a66e8-107">コンポーネントが表示されると、ユーザーはそれを使用して印刷ジョブのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="a66e8-107">Once the component is shown, users will interact with it, setting the properties of the print job.</span></span> <span data-ttu-id="a66e8-108">保存されます、<xref:System.Drawing.Printing.PrinterSettings>クラス (および<xref:System.Drawing.Printing.PageSettings>クラス、ユーザーがアクセスする場合、 [PageSetupDialog コンポーネント](pagesetupdialog-component-windows-forms.md)を通じて、<xref:System.Windows.Forms.PrintDialog>コンポーネント) 印刷ジョブに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="a66e8-108">These are saved in the  <xref:System.Drawing.Printing.PrinterSettings> class (and the <xref:System.Drawing.Printing.PageSettings> class, if the user accesses the [PageSetupDialog Component](pagesetupdialog-component-windows-forms.md) through the <xref:System.Windows.Forms.PrintDialog> component) associated with that print job.</span></span> <span data-ttu-id="a66e8-109">その後で、設定されたプロパティを呼び出して印刷ジョブの詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="a66e8-109">You can then make calls to the properties they set to determine the specifics of the print job.</span></span>

## <a name="see-also"></a><span data-ttu-id="a66e8-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="a66e8-110">See also</span></span>

- [<span data-ttu-id="a66e8-111">方法: 標準の Windows フォーム印刷ジョブを作成します。</span><span class="sxs-lookup"><span data-stu-id="a66e8-111">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="a66e8-112">方法: 実行時に PrintDialog のユーザー入力をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="a66e8-112">How to: Capture User Input from a PrintDialog at Run Time</span></span>](../advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)
- [<span data-ttu-id="a66e8-113">PrintPreviewDialog コントロール</span><span class="sxs-lookup"><span data-stu-id="a66e8-113">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="a66e8-114">PrintDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a66e8-114">PrintDialog Component</span></span>](printdialog-component-windows-forms.md)
- [<span data-ttu-id="a66e8-115">Windows フォームにおける印刷のサポート</span><span class="sxs-lookup"><span data-stu-id="a66e8-115">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="a66e8-116">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="a66e8-116">Windows Forms Controls</span></span>](index.md)