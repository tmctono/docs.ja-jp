---
title: LinkLabel コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739521"
---
# <a name="linklabel-control-overview-windows-forms"></a><span data-ttu-id="1bcda-102">LinkLabel コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="1bcda-102">LinkLabel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="1bcda-103">Windows フォーム<xref:System.Windows.Forms.LinkLabel>コントロールを使用すると、Web スタイルのリンクを Windows フォーム アプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="1bcda-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to add Web-style links to Windows Forms applications.</span></span> <span data-ttu-id="1bcda-104">コントロールを<xref:System.Windows.Forms.LinkLabel>使用できるすべてのものに対してコントロールを<xref:System.Windows.Forms.Label>使用できます。テキストの一部をファイル、フォルダ、または Web ページへのリンクとして設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bcda-104">You can use the <xref:System.Windows.Forms.LinkLabel> control for everything that you can use the <xref:System.Windows.Forms.Label> control for; you can also set part of the text as a link to a file, folder, or Web page.</span></span>  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a><span data-ttu-id="1bcda-105">リンクラベル コントロールで実行できる操作</span><span class="sxs-lookup"><span data-stu-id="1bcda-105">What You Can Do with the LinkLabel Control</span></span>  
 <span data-ttu-id="1bcda-106">コントロールには、コントロールのすべてのプロパティ、メソッド、およびイベントのほかに<xref:System.Windows.Forms.Label>、ハイパーリンクとリンクの色のプロパティがあります。 <xref:System.Windows.Forms.LinkLabel></span><span class="sxs-lookup"><span data-stu-id="1bcda-106">In addition to all the properties, methods, and events of the <xref:System.Windows.Forms.Label> control, the <xref:System.Windows.Forms.LinkLabel> control has properties for hyperlinks and link colors.</span></span> <span data-ttu-id="1bcda-107">この<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>プロパティは、リンクをアクティブにするテキストの領域を設定します。</span><span class="sxs-lookup"><span data-stu-id="1bcda-107">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property sets the area of the text that activates the link.</span></span> <span data-ttu-id="1bcda-108"><xref:System.Windows.Forms.LinkLabel.LinkColor%2A>、、<xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>および<xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A>プロパティはリンクの色を設定します。</span><span class="sxs-lookup"><span data-stu-id="1bcda-108">The <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, and <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> properties set the colors of the link.</span></span> <span data-ttu-id="1bcda-109">イベント<xref:System.Windows.Forms.LinkLabel.LinkClicked>は、リンク テキストが選択されたときに何が起こるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1bcda-109">The <xref:System.Windows.Forms.LinkLabel.LinkClicked> event determines what happens when the link text is selected.</span></span>  
  
 <span data-ttu-id="1bcda-110">コントロールの<xref:System.Windows.Forms.LinkLabel>最も簡単な使用方法は、 プロパティを使用して<xref:System.Windows.Forms.LinkLabel.LinkArea%2A>1 つのリンクを表示することですが、 プロパティを<xref:System.Windows.Forms.LinkLabel.Links%2A>使用して複数のハイパーリンクを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bcda-110">The simplest use of the <xref:System.Windows.Forms.LinkLabel> control is to display a single link using the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property, but you can also display multiple hyperlinks using the <xref:System.Windows.Forms.LinkLabel.Links%2A> property.</span></span> <span data-ttu-id="1bcda-111">この<xref:System.Windows.Forms.LinkLabel.Links%2A>プロパティを使用すると、リンクのコレクションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1bcda-111">The <xref:System.Windows.Forms.LinkLabel.Links%2A> property enables you to access a collection of links.</span></span> <span data-ttu-id="1bcda-112">個々の<xref:System.Windows.Forms.LinkLabel.Link>オブジェクトのプロパティでデータ<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bcda-112">You can also specify data in the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property of each individual <xref:System.Windows.Forms.LinkLabel.Link> object.</span></span> <span data-ttu-id="1bcda-113">プロパティの<xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A>値は、表示するファイルの場所や Web サイトのアドレスを格納するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="1bcda-113">The value of the <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> property can be used to store the location of a file to display or the address of a Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcda-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="1bcda-114">See also</span></span>

- <xref:System.Windows.Forms.LinkLabel>
- [<span data-ttu-id="1bcda-115">Label コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="1bcda-115">Label Control Overview</span></span>](label-control-overview-windows-forms.md)
- [<span data-ttu-id="1bcda-116">方法: Windows フォーム LinkLabel コントロールでオブジェクトまたは Web ページにリンクする</span><span class="sxs-lookup"><span data-stu-id="1bcda-116">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [<span data-ttu-id="1bcda-117">方法: Windows フォーム LinkLabel コントロールの表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="1bcda-117">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
