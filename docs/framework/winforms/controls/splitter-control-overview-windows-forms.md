---
title: Splitter コントロールの概要
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742889"
---
# <a name="splitter-control-overview-windows-forms"></a><span data-ttu-id="ab1da-102">Splitter コントロールの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ab1da-102">Splitter Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="ab1da-103"><xref:System.Windows.Forms.SplitContainer> に置き換えられ、以前のバージョンの <xref:System.Windows.Forms.Splitter> コントロールに機能が追加されますが、<xref:System.Windows.Forms.Splitter> は下位互換性と将来の使用の両方のために保持されます。</span><span class="sxs-lookup"><span data-stu-id="ab1da-103">Although <xref:System.Windows.Forms.SplitContainer> replaces and adds functionality to the <xref:System.Windows.Forms.Splitter> control of previous versions, <xref:System.Windows.Forms.Splitter> is retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="ab1da-104">Windows フォーム <xref:System.Windows.Forms.Splitter> コントロールを使用して、ドッキングされたコントロールのサイズを実行時に変更します。</span><span class="sxs-lookup"><span data-stu-id="ab1da-104">Windows Forms <xref:System.Windows.Forms.Splitter> controls are used to resize docked controls at run time.</span></span> <span data-ttu-id="ab1da-105"><xref:System.Windows.Forms.Splitter> コントロールは、多くの場合、フォームで使用されます。 Windows エクスプローラーのように、データペインにはさまざまな時間の異なる幅の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ab1da-105">The <xref:System.Windows.Forms.Splitter> control is often used on forms with controls that have varying lengths of data to present, like Windows Explorer, whose data panes contain information of varying widths at different times.</span></span>  
  
## <a name="working-with-the-splitter-control"></a><span data-ttu-id="ab1da-106">スプリッターコントロールの操作</span><span class="sxs-lookup"><span data-stu-id="ab1da-106">Working with the Splitter Control</span></span>  
 <span data-ttu-id="ab1da-107">ユーザーが、スプリッターコントロールによってサイズ変更できるコントロールのドッキング解除された端でマウスポインターをポイントすると、ポインターの外観が変化して、コントロールのサイズを変更できることを示します。</span><span class="sxs-lookup"><span data-stu-id="ab1da-107">When the user points the mouse pointer at the undocked edge of a control that can be resized by a splitter control, the pointer changes its appearance to indicate that the control can be resized.</span></span> <span data-ttu-id="ab1da-108">スプリッターコントロールを使用すると、ドッキングされたコントロールのサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="ab1da-108">With the splitter control, the user can resize the docked control that is immediately before it.</span></span> <span data-ttu-id="ab1da-109">そのため、ユーザーがドッキングされたコントロールのサイズを実行時に変更できるようにするには、サイズを変更するコントロールをコンテナーの端にドッキングし、そのコンテナーの同じ側に分割コントロールをドッキングします。</span><span class="sxs-lookup"><span data-stu-id="ab1da-109">Therefore, to enable the user to resize a docked control at run time, dock the control to be resized to an edge of a container, and then dock a splitter control to the same side of that container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab1da-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab1da-110">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="ab1da-111">方法 : Windows フォーム上のコントロールをドッキングする</span><span class="sxs-lookup"><span data-stu-id="ab1da-111">How to: Dock Controls on Windows Forms</span></span>](how-to-dock-controls-on-windows-forms.md)
- [<span data-ttu-id="ab1da-112">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="ab1da-112">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
