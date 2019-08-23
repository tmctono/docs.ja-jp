---
title: StatusBar コントロール (Windows フォーム)
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 72a93fc32715596efc7fb0f8b941e62f7019d06c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964422"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="e472f-102">StatusBar コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="e472f-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="e472f-103"><xref:System.Windows.Forms.ToolStripStatusLabel> コントロールは、<xref:System.Windows.Forms.StatusBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.StatusBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="e472f-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="e472f-104">Windows フォームの <xref:System.Windows.Forms.StatusBar> コントロールは、フォーム上で領域として使用され、通常はウィンドウの下端に表示されます。アプリケーションは、このコントロールにさまざまな種類のステータス情報を表示できます</span><span class="sxs-lookup"><span data-stu-id="e472f-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="e472f-105"><xref:System.Windows.Forms.StatusBar>コントロールには、状態を示すアイコンを表示するステータスバーパネルや、プロセスが動作していることを示すアニメーションの一連のアイコンがあります。たとえば、Microsoft Word では、ドキュメントが保存されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="e472f-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e472f-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e472f-106">In This Section</span></span>  
 [<span data-ttu-id="e472f-107">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="e472f-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="e472f-108"><xref:System.Windows.Forms.StatusBar>コントロールの一般的な概念を紹介します。これにより、フォーカスのあるコントロールに関する関連情報をユーザーが表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e472f-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="e472f-109">方法: StatusBar コントロールにパネルを追加する</span><span class="sxs-lookup"><span data-stu-id="e472f-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="e472f-110"><xref:System.Windows.Forms.StatusBar>コントロールにプログラミング可能なパネルを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e472f-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="e472f-111">方法: Windows フォーム StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="e472f-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="e472f-112">コントロールから発生し<xref:System.Windows.Forms.Control.Click>た<xref:System.Windows.Forms.StatusBar>イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e472f-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="e472f-113">方法: ステータスバーパネルのサイズを設定する</span><span class="sxs-lookup"><span data-stu-id="e472f-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="e472f-114">実行時にステータスバーパネルの幅とサイズ変更の動作を制御するプロパティについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e472f-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="e472f-115">チュートリアル: 実行時のステータスバー情報の更新</span><span class="sxs-lookup"><span data-stu-id="e472f-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="e472f-116">ステータスバーパネル内のデータをプログラムで制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e472f-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e472f-117">参照</span><span class="sxs-lookup"><span data-stu-id="e472f-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="e472f-118">クラスとそのメンバーに関するリファレンス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="e472f-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="e472f-119">を置き換えて、 <xref:System.Windows.Forms.StatusBar>コントロールに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="e472f-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e472f-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e472f-120">Related Sections</span></span>  
 [<span data-ttu-id="e472f-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="e472f-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="e472f-122">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="e472f-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
