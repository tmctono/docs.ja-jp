---
title: LinkLabel コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 541467b0f1285d372e5f6d502d9d8f28c8c6333e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012959"
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="1d0ac-102">LinkLabel コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="1d0ac-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="1d0ac-103">Windows フォーム<xref:System.Windows.Forms.LinkLabel>コントロールでは、Windows フォーム アプリケーションを Web スタイルのリンクを追加できます。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="1d0ac-104">使用することができます、<xref:System.Windows.Forms.LinkLabel>使用できるすべてのコントロール、<xref:System.Windows.Forms.Label>の制御も設定できるは、テキストの一部として、ファイル、フォルダー、または Web ページへのリンク。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you also can set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="1d0ac-105">LinkLabel コントロールで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="1d0ac-106">すべてのプロパティ、メソッド、およびのイベントだけでなく、<xref:System.Windows.Forms.Label>コントロール、<xref:System.Windows.Forms.LinkLabel>コントロールのハイパーリンクとリンクの色のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="1d0ac-107"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティは、リンクをアクティブにするテキストの領域を設定します。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="1d0ac-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>、および<xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A>プロパティは、リンクの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="1d0ac-109"><xref:System.Windows.Forms.LinkLabel.LinkClicked>イベントは、リンクのテキストが選択されているときの動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="1d0ac-110">最も簡単な使用、<xref:System.Windows.Forms.LinkLabel>コントロールを使用して、1 つのリンクを表示する、<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティがすることができますを使用して複数のハイパーリンクを表示も、<xref:System.Windows.Forms.LinkLabel.Links%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="1d0ac-111"><xref:System.Windows.Forms.LinkLabel.Links%2A>プロパティでは、リンクのコレクションにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="1d0ac-112">内のデータを指定することも、<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>プロパティをそれぞれ個別<xref:System.Windows.Forms.LinkLabel.Link>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="1d0ac-113">値、<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>プロパティを表示するファイルの場所または Web サイトのアドレスの格納に使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d0ac-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d0ac-114">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="1d0ac-115">Label コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="1d0ac-115">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="1d0ac-116">方法: オブジェクトへのリンクまたは Web ページと Windows フォーム LinkLabel コントロール</span><span class="sxs-lookup"><span data-stu-id="1d0ac-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="1d0ac-117">方法: Windows フォーム LinkLabel コントロールの外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="1d0ac-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
