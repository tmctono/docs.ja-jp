---
title: Splitter コントロールの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 0477f68aaf67d4b29c491052999ff7784e736669
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009709"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="0b87e-102">Splitter コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="0b87e-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="0b87e-103"><xref:System.Windows.Forms.SplitContainer>が置換および追加する機能、 <xref:System.Windows.Forms.Splitter> 、以前のバージョン コントロール<xref:System.Windows.Forms.Splitter>を選択した場合に、旧バージョンとの互換性と将来の使用のため保持されます。</span><span class="sxs-lookup"><span data-stu-id="0b87e-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="0b87e-104">Windows フォーム<xref:System.Windows.Forms.Splitter>コントロールを使用すると、実行時にドッキングされたコントロールのサイズを変更します。</span><span class="sxs-lookup"><span data-stu-id="0b87e-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="0b87e-105"><xref:System.Windows.Forms.Splitter>コントロールはフォーム上でのデータ ペインには、異なる時刻でさまざまな幅の情報が含まれて、Windows エクスプ ローラーのように、提示するデータのさまざまな長さを持つコントロールによく使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b87e-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="0b87e-106">Splitter コントロールの操作</span><span class="sxs-lookup"><span data-stu-id="0b87e-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="0b87e-107">ユーザーは、分割線コントロールでサイズを変更できるコントロールのドッキングされていないエッジにマウス ポインターをポイント、ポインターは、コントロールのサイズを変更できることを示すには、その外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="0b87e-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="0b87e-108">分割線コントロールをユーザーはすぐにする前に、ドッキングされたコントロールをサイズ変更できます。</span><span class="sxs-lookup"><span data-stu-id="0b87e-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="0b87e-109">そのため、実行時にドッキングされたコントロールのサイズを変更するユーザーを有効にするコンテナーの端にサイズを変更するコントロールをドッキングし、その後の分割線コントロールをそのコンテナーの同じ側にドッキングします。</span><span class="sxs-lookup"><span data-stu-id="0b87e-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b87e-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0b87e-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="0b87e-111">方法: Windows フォーム上のコントロールをドッキングします。</span><span class="sxs-lookup"><span data-stu-id="0b87e-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="0b87e-112">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="0b87e-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
