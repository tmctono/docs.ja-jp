---
title: StatusBar コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964431"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="63e01-102">StatusBar コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="63e01-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="63e01-103"><xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar>コントロール<xref:System.Windows.Forms.StatusStrip>と<xref:System.Windows.Forms.ToolStripStatusLabel>コントロールは、および<xref:System.Windows.Forms.StatusBarPanel>コントロールに対して、機能の置き換えと追加を行います。ただし、コントロールとコントロールは、下位互換性と将来の使用の両方のために保持されます。し.</span><span class="sxs-lookup"><span data-stu-id="63e01-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="63e01-104">Windows フォーム[StatusBar コントロール](statusbar-control-windows-forms.md)は、フォーム上で通常はウィンドウの下部に表示される領域として使用されます。この領域では、アプリケーションはさまざまな種類の状態情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="63e01-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="63e01-105"><xref:System.Windows.Forms.StatusBar>コントロールには、状態を示すためにテキストまたはアイコンを表示するステータスバーパネル、またはプロセスが動作していることを示すアニメーション内の一連のアイコンがあります。たとえば、Microsoft Word では、ドキュメントが保存されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="63e01-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="63e01-106">StatusBar コントロールの使用</span><span class="sxs-lookup"><span data-stu-id="63e01-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="63e01-107">Internet Explorer は、ハイパーリンク上でマウスがロールオーバーしたときに、ステータスバーを使用してページの URL を示します。Microsoft Word では、ページの場所、セクションの場所、および上書きやリビジョンの追跡などの編集モードに関する情報が提供されます。また、Visual Studio はステータスバーを使用して、ドッキングされたウィンドウをドッキングまたはフローティングとして操作する方法を示すなど、状況に応じた情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="63e01-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="63e01-108">ステータスバーに1つのメッセージを表示するには、 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>プロパティを`false` ( <xref:System.Windows.Forms.StatusBar.Text%2A>既定値) に設定し、ステータスバーのプロパティをステータスバーに表示するテキストに設定します。</span><span class="sxs-lookup"><span data-stu-id="63e01-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="63e01-109">ステータスバーをパネルに分割して複数の種類の情報を表示するには、 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A>プロパティを`true`に設定し<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> 、の<xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="63e01-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63e01-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="63e01-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="63e01-111">方法: Windows フォーム StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="63e01-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
