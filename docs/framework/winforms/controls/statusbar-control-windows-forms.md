---
title: StatusBar コントロール
ms.date: 03/30/2017
helpviewer_keywords:
- StatusBar control [Windows Forms]
- status bars [Windows Forms], creating
ms.assetid: 6f543e27-cf78-4b7f-b4d0-6a8030155d48
ms.openlocfilehash: 4d48cf497eeedcff6290dfa8ddecf38ce8ff7c63
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742851"
---
# <a name="statusbar-control-windows-forms"></a><span data-ttu-id="77f96-102">StatusBar コントロール (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="77f96-102">StatusBar Control (Windows Forms)</span></span>
> [!NOTE]
> <span data-ttu-id="77f96-103"><xref:System.Windows.Forms.ToolStripStatusLabel> コントロールは、<xref:System.Windows.Forms.StatusBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.StatusBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="77f96-103">The <xref:System.Windows.Forms.ToolStripStatusLabel> control replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control; however, the <xref:System.Windows.Forms.StatusBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="77f96-104">Windows フォームの <xref:System.Windows.Forms.StatusBar> コントロールは、フォーム上で領域として使用され、通常はウィンドウの下端に表示されます。アプリケーションは、このコントロールにさまざまな種類のステータス情報を表示できます</span><span class="sxs-lookup"><span data-stu-id="77f96-104">The Windows Forms <xref:System.Windows.Forms.StatusBar> control is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="77f96-105"><xref:System.Windows.Forms.StatusBar> コントロールには、状態を示すアイコンを表示するステータスバーパネルや、プロセスが動作していることを示す一連のアイコンがアニメーションに表示されることがあります。たとえば、Microsoft Word では、ドキュメントが保存されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="77f96-105"><xref:System.Windows.Forms.StatusBar> controls can have status-bar panels on them that display icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77f96-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="77f96-106">In This Section</span></span>  
 [<span data-ttu-id="77f96-107">StatusBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="77f96-107">StatusBar Control Overview</span></span>](statusbar-control-overview-windows-forms.md)  
 <span data-ttu-id="77f96-108"><xref:System.Windows.Forms.StatusBar> コントロールの一般的な概念について説明します。これにより、フォーカスのあるコントロールに関する関連情報をユーザーが表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="77f96-108">Introduces the general concepts of the <xref:System.Windows.Forms.StatusBar> control, which enables users to see relevant information for the control that has focus.</span></span>  
  
 [<span data-ttu-id="77f96-109">方法: StatusBar コントロールにパネルを追加する</span><span class="sxs-lookup"><span data-stu-id="77f96-109">How to: Add Panels to a StatusBar Control</span></span>](how-to-add-panels-to-a-statusbar-control.md)  
 <span data-ttu-id="77f96-110"><xref:System.Windows.Forms.StatusBar> コントロールにプログラミング可能なパネルを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77f96-110">Explains how to add programmable panels to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="77f96-111">方法: Windows フォームの StatusBar コントロールでクリックされたパネルを確認する</span><span class="sxs-lookup"><span data-stu-id="77f96-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)  
 <span data-ttu-id="77f96-112"><xref:System.Windows.Forms.StatusBar> コントロールから発生した <xref:System.Windows.Forms.Control.Click> イベントを処理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77f96-112">Explains how to handle <xref:System.Windows.Forms.Control.Click> events raised from the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
 [<span data-ttu-id="77f96-113">方法: ステータス バー パネルのサイズを設定する</span><span class="sxs-lookup"><span data-stu-id="77f96-113">How to: Set the Size of Status-Bar Panels</span></span>](how-to-set-the-size-of-status-bar-panels.md)  
 <span data-ttu-id="77f96-114">実行時にステータスバーパネルの幅とサイズ変更の動作を制御するプロパティについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="77f96-114">Gives details on the properties that control the width and resize behavior of status-bar panels at run time.</span></span>  
  
 [<span data-ttu-id="77f96-115">チュートリアル: ステータス バー情報の実行時更新</span><span class="sxs-lookup"><span data-stu-id="77f96-115">Walkthrough: Updating Status Bar Information at Run Time</span></span>](walkthrough-updating-status-bar-information-at-run-time.md)  
 <span data-ttu-id="77f96-116">ステータスバーパネル内のデータをプログラムで制御する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="77f96-116">Explains how to programmatically control the data within status-bar panels.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="77f96-117">参照先</span><span class="sxs-lookup"><span data-stu-id="77f96-117">Reference</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <span data-ttu-id="77f96-118">クラスとそのメンバーに関するリファレンス情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="77f96-118">Provides reference information on the class and its members.</span></span>  
  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <span data-ttu-id="77f96-119"><xref:System.Windows.Forms.StatusBar> コントロールに置き換えて機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="77f96-119">Replaces and adds functionality to the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="77f96-120">関連セクション</span><span class="sxs-lookup"><span data-stu-id="77f96-120">Related Sections</span></span>  
 [<span data-ttu-id="77f96-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="77f96-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="77f96-122">Windows フォーム コントロールの完全な一覧を、使用に関する情報リンクと共に提供します。</span><span class="sxs-lookup"><span data-stu-id="77f96-122">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
