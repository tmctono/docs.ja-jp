---
title: StatusBar コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 4e1816ef221641f5ad54fb429442ed43289b592a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505428"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="fe5be-102">StatusBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="fe5be-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="fe5be-103"><xref:System.Windows.Forms.StatusStrip>と<xref:System.Windows.Forms.ToolStripStatusLabel>コントロールの置換し、する機能を追加、<xref:System.Windows.Forms.StatusBar>と<xref:System.Windows.Forms.StatusBarPanel>を制御しますただし、、<xref:System.Windows.Forms.StatusBar>と<xref:System.Windows.Forms.StatusBarPanel>場合、下位互換性と将来の使用の両方のコントロールが保持されますします。選択します。</span><span class="sxs-lookup"><span data-stu-id="fe5be-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="fe5be-104">Windows フォーム[StatusBar コントロール](statusbar-control-windows-forms.md)はフォームの領域で、通常、アプリケーションがさまざまな種類のステータス情報を表示できるウィンドウの下部に表示として使用します。</span><span class="sxs-lookup"><span data-stu-id="fe5be-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="fe5be-105"><xref:System.Windows.Forms.StatusBar> コントロールがテキストまたは状態、または一連のプロセスが動作してを示すアニメーションのアイコンを示すアイコンを表示してステータス バー パネルを持つことができます。たとえば、Microsoft Word があることを示すドキュメント保存されます。</span><span class="sxs-lookup"><span data-stu-id="fe5be-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="fe5be-106">ステータス バー コントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="fe5be-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="fe5be-107">Internet Explorer は、マウスを取り消さない限り、ハイパーリンクときに、ページの URL を示すためにステータス バーを使用します。Microsoft Word での情報がページの場所、セクションの場所、および上書きや変更の追跡などの編集モードVisual Studio を使用してステータス バーをドッキングまたはフローティング、ドッキング可能なウィンドウを操作する方法を示すなどの状況に応じた情報します。</span><span class="sxs-lookup"><span data-stu-id="fe5be-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="fe5be-108">ステータス バーに設定して、1 つのメッセージを表示することができます、<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>プロパティを`false`(既定値) と設定、<xref:System.Windows.Forms.StatusBar.Text%2A>ステータス バーに表示するテキストをステータス バーのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="fe5be-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="fe5be-109">ステータス バーを設定して、情報の 1 つ以上の種類を表示するパネルに分割することができます、<xref:System.Windows.Forms.StatusBar.ShowPanels%2A>プロパティを`true`を使用して、<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A>メソッドの<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>します。</span><span class="sxs-lookup"><span data-stu-id="fe5be-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5be-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe5be-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="fe5be-111">方法: Windows フォームの StatusBar コントロール パネルのクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe5be-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
