---
title: PrintPreviewControl コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- PrintPreviewControl
helpviewer_keywords:
- print preview
- PrintPreviewControl control
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
ms.openlocfilehash: e9f1c2ae912b6beeba70c318b94a3052e2f99acb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012599"
---
# <a name="printpreviewcontrol-control-overview-windows-forms"></a><span data-ttu-id="bca7f-102">PrintPreviewControl コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="bca7f-102">PrintPreviewControl Control Overview (Windows Forms)</span></span>
<span data-ttu-id="bca7f-103">Windows フォーム<xref:System.Windows.Forms.PrintPreviewControl>を表示するために使用する[PrintDocument](printdocument-component-windows-forms.md)印刷時に表示されます。</span><span class="sxs-lookup"><span data-stu-id="bca7f-103">The Windows Forms <xref:System.Windows.Forms.PrintPreviewControl> is used to display a [PrintDocument](printdocument-component-windows-forms.md) as it will appear when printed.</span></span> <span data-ttu-id="bca7f-104">このコントロールには、ボタンやその他のユーザー インターフェイスの要素がないため、通常は、独自の印刷プレビューのユーザー インターフェイスを作成する場合にのみ <xref:System.Windows.Forms.PrintPreviewControl> を使用します。</span><span class="sxs-lookup"><span data-stu-id="bca7f-104">This control has no buttons or other user interface elements, so typically you use the <xref:System.Windows.Forms.PrintPreviewControl> only if you wish to write your own print-preview user interface.</span></span> <span data-ttu-id="bca7f-105">標準のユーザー インターフェイスを実行する場合に、使用、<xref:System.Windows.Forms.PrintPreviewDialog>制御; を参照してください[PrintPreviewDialog コントロールの概要](printpreviewdialog-control-overview-windows-forms.md)の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="bca7f-105">If you want the standard user interface, use a <xref:System.Windows.Forms.PrintPreviewDialog> control; see [PrintPreviewDialog Control Overview](printpreviewdialog-control-overview-windows-forms.md) for an overview.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="bca7f-106">キー プロパティ</span><span class="sxs-lookup"><span data-stu-id="bca7f-106">Key Properties</span></span>  
 <span data-ttu-id="bca7f-107">コントロールのキー プロパティは、<xref:System.Windows.Forms.PrintPreviewControl.Document%2A>をプレビューするドキュメントを設定します。</span><span class="sxs-lookup"><span data-stu-id="bca7f-107">The control's key property is <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>, which sets the document to be previewed.</span></span> <span data-ttu-id="bca7f-108">ドキュメントがある必要があります、<xref:System.Drawing.Printing.PrintDocument>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="bca7f-108">The document must be a <xref:System.Drawing.Printing.PrintDocument> object.</span></span> <span data-ttu-id="bca7f-109">印刷するドキュメントの作成の概要については、次を参照してください。 [PrintDocument コンポーネントの概要](printdocument-component-overview-windows-forms.md)と[Windows フォームにおける印刷のサポート](../advanced/windows-forms-print-support.md)します。</span><span class="sxs-lookup"><span data-stu-id="bca7f-109">For an overview of creating documents for printing, see [PrintDocument Component Overview](printdocument-component-overview-windows-forms.md) and [Windows Forms Print Support](../advanced/windows-forms-print-support.md).</span></span> <span data-ttu-id="bca7f-110"><xref:System.Windows.Forms.PrintPreviewControl.Columns%2A>と<xref:System.Windows.Forms.PrintPreviewControl.Rows%2A>プロパティは、コントロールの水平および垂直を表示するページの数を決定します。</span><span class="sxs-lookup"><span data-stu-id="bca7f-110">The <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> and <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> properties determine the number of pages displayed horizontally and vertically on the control.</span></span> <span data-ttu-id="bca7f-111">アンチエイリアシングをテキストが滑らかに使用するが、低速です。 表示することもできますが、これを使用する設定、<xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A>プロパティを`true`します。</span><span class="sxs-lookup"><span data-stu-id="bca7f-111">Antialiasing can make the text appear smoother, but it can also make the display slower; to use it, set the <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> property to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bca7f-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="bca7f-112">See also</span></span>

- <xref:System.Windows.Forms.PrintPreviewControl>
- [<span data-ttu-id="bca7f-113">PrintPreviewDialog コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="bca7f-113">PrintPreviewDialog Control Overview</span></span>](printpreviewdialog-control-overview-windows-forms.md)
- [<span data-ttu-id="bca7f-114">PrintPreviewControl コントロール</span><span class="sxs-lookup"><span data-stu-id="bca7f-114">PrintPreviewControl Control</span></span>](printpreviewcontrol-control-windows-forms.md)
- [<span data-ttu-id="bca7f-115">ダイアログ ボックス コントロールおよびコンポーネント</span><span class="sxs-lookup"><span data-stu-id="bca7f-115">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
