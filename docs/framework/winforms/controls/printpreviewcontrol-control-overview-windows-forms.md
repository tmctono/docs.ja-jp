---
title: PrintPreviewControl コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: 8dfe5802a24d5ec85ed908fd04c5550e1fbec012
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741444"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="57498-102">PrintPreviewControl コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="57498-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="57498-103">Windows フォーム <xref:System.Windows.Forms.PrintPreviewControl> は、印刷時に表示される[PrintDocument](printdocument-component-windows-forms.md)を表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="57498-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="57498-104">このコントロールには、ボタンやその他のユーザー インターフェイスの要素がないため、通常は、独自の印刷プレビューのユーザー インターフェイスを作成する場合にのみ <xref:System.Windows.Forms.PrintPreviewControl> を使用します。</span><span class="sxs-lookup"><span data-stu-id="57498-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="57498-105">標準ユーザーインターフェイスが必要な場合は、<xref:System.Windows.Forms.PrintPreviewDialog> コントロールを使用します。概要については、「 [Printプレビューダイアログコントロールの概要](printpreviewdialog-control-overview-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57498-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="57498-106">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="57498-106">Key Properties</span></span>  
 <span data-ttu-id="57498-107">コントロールのキープロパティは <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>であり、プレビューするドキュメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="57498-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="57498-108">ドキュメントは <xref:System.Drawing.Printing.PrintDocument> オブジェクトである必要があります。</span><span class="sxs-lookup"><span data-stu-id="57498-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="57498-109">印刷用のドキュメントの作成の概要については、「 [PrintDocument Component の概要](printdocument-component-overview-windows-forms.md)」および「[印刷サポートの Windows フォーム](../advanced/windows-forms-print-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57498-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="57498-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> プロパティと <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> プロパティによって、コントロールの水平方向および垂直方向に表示されるページ数が決まります。</span><span class="sxs-lookup"><span data-stu-id="57498-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="57498-111">アンチエイリアシングを使用すると、テキストが滑らかに見えるようになりますが、表示速度が低下する可能性があります。これを使用するには、<xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> プロパティを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="57498-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57498-112">参照</span><span class="sxs-lookup"><span data-stu-id="57498-112">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewControl>
- [<span data-ttu-id="57498-113">PrintPreviewDialog コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="57498-113">PrintPreviewDialog Control Overview</span></span>](printpreviewdialog-control-overview-windows-forms.md)
- [<span data-ttu-id="57498-114">PrintPreviewControl コントロール</span><span class="sxs-lookup"><span data-stu-id="57498-114">PrintPreviewControl Control</span></span>](printpreviewcontrol-control-windows-forms.md)
- [<span data-ttu-id="57498-115">ダイアログ ボックス コントロールおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="57498-115">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
