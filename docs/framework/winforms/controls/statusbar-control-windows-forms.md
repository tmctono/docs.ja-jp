---
title: StatusBar コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 9ef6bc125a641538e7fd2da4c17c5f25dfc62709
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009657"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="834d3-102">StatusBar コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="834d3-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="834d3-103"><xref:System.Windows.Forms.ToolStripStatusLabel> コントロールは、<xref:System.Windows.Forms.StatusBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.StatusBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="834d3-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="834d3-104">Windows フォームの <xref:System.Windows.Forms.StatusBar> コントロールは、フォーム上で領域として使用され、通常はウィンドウの下端に表示されます。アプリケーションは、このコントロールにさまざまな種類のステータス情報を表示できます</span><span class="sxs-lookup"><span data-stu-id="834d3-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="834d3-105"><xref:System.Windows.Forms.StatusBar> コントロールが状態、または一連のプロセスが動作してを示すアニメーションのアイコンを示すアイコンを表示することでステータス バー パネルを持つことができます。たとえば、Microsoft Word があることを示すドキュメント保存されます。</span><span class="sxs-lookup"><span data-stu-id="834d3-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="834d3-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="834d3-106">In This Section</span></span>  
 [<span data-ttu-id="834d3-107">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="834d3-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="834d3-108">一般的な概念が導入されています、<xref:System.Windows.Forms.StatusBar>コントロールで、フォーカスのあるコントロールの関連する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="834d3-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="834d3-109">方法: StatusBar コントロールにパネルを追加します。</span><span class="sxs-lookup"><span data-stu-id="834d3-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="834d3-110">プログラミング可能なパネルを追加する方法について説明します、<xref:System.Windows.Forms.StatusBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="834d3-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="834d3-111">方法: Windows フォームの StatusBar コントロール パネルのクリックを確認します。</span><span class="sxs-lookup"><span data-stu-id="834d3-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="834d3-112">処理する方法について説明します<xref:System.Windows.Forms.Control.Click>からイベントが発生した、<xref:System.Windows.Forms.StatusBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="834d3-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="834d3-113">方法: ステータス バー パネルのサイズを設定します。</span><span class="sxs-lookup"><span data-stu-id="834d3-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="834d3-114">幅を制御し、実行時の動作のステータス バー パネルのサイズを変更するプロパティの詳細がわかります。</span><span class="sxs-lookup"><span data-stu-id="834d3-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="834d3-115">チュートリアル: 実行時にステータス バー情報の更新</span><span class="sxs-lookup"><span data-stu-id="834d3-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="834d3-116">ステータス バー パネル内のデータをプログラムで制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="834d3-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="834d3-117">参照</span><span class="sxs-lookup"><span data-stu-id="834d3-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="834d3-118">クラスとそのメンバーに関するリファレンス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="834d3-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="834d3-119">置換および追加する機能、<xref:System.Windows.Forms.StatusBar>コントロール。</span><span class="sxs-lookup"><span data-stu-id="834d3-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="834d3-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="834d3-120">Related Sections</span></span>  
 [<span data-ttu-id="834d3-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="834d3-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="834d3-122">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="834d3-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
