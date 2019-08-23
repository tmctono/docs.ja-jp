---
title: '方法: Windows フォーム上のコントロールをドッキングする'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: dc514fd8b9b7a17bf07a878e42729db4187d2b82
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963627"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="d48a5-102">方法: Windows フォーム上のコントロールをドッキングする</span><span class="sxs-lookup"><span data-stu-id="d48a5-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="d48a5-103">コントロールをフォームの端にドッキングしたり、コントロールのコンテナー (フォームまたはコンテナーコントロールのいずれか) に入力したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="d48a5-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="d48a5-104">たとえば、Windows エクスプローラーでは、 <xref:System.Windows.Forms.TreeView>ウィンドウの左側<xref:System.Windows.Forms.ListView>にコントロールがドッキングされ、コントロールはウィンドウの右側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48a5-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="d48a5-105">ドッキングモード<xref:System.Windows.Forms.Control.Dock%2A>を定義するには、表示されているすべての Windows フォームコントロールに対してプロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="d48a5-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d48a5-106">コントロールは、逆 z オーダーでドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="d48a5-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="d48a5-107">プロパティ<xref:System.Windows.Forms.Control.Dock%2A>は、 <xref:System.Windows.Forms.Control.AutoSize%2A>プロパティと対話します。</span><span class="sxs-lookup"><span data-stu-id="d48a5-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="d48a5-108">詳細については、「 [AutoSize プロパティの概要](autosize-property-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d48a5-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="d48a5-109">コントロールをドッキングするには</span><span class="sxs-lookup"><span data-stu-id="d48a5-109">To dock a control</span></span>  
  
1. <span data-ttu-id="d48a5-110">ドッキングするコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="d48a5-110">Select the control that you want to dock.</span></span>  
  
2. <span data-ttu-id="d48a5-111">プロパティウィンドウで、 <xref:System.Windows.Forms.Control.Dock%2A>プロパティの右側にある矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d48a5-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="d48a5-112">フォームの端と中央を表す一連のボックスを示すエディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d48a5-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3. <span data-ttu-id="d48a5-113">コントロールをドッキングするフォームの端を表すボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d48a5-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="d48a5-114">コントロールのフォームまたはコンテナーコントロールの内容を塗りつぶすには、中央のボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="d48a5-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="d48a5-115">**[(なし)]** をクリックして、ドッキングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d48a5-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="d48a5-116">ドッキングされた端の境界に合わせてコントロールのサイズが自動的に変更されます。</span><span class="sxs-lookup"><span data-stu-id="d48a5-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d48a5-117">継承された`Protected`コントロールは、ドッキングできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d48a5-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="d48a5-118">コントロールのアクセスレベルを変更するには、プロパティウィンドウの **[修飾子]** プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="d48a5-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48a5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="d48a5-119">See also</span></span>

- [<span data-ttu-id="d48a5-120">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="d48a5-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="d48a5-121">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="d48a5-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="d48a5-122">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="d48a5-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="d48a5-123">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="d48a5-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="d48a5-124">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="d48a5-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="d48a5-125">方法: FlowLayoutPanel コントロールに子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="d48a5-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="d48a5-126">方法: TableLayoutPanel コントロールに子コントロールを固定およびドッキングする</span><span class="sxs-lookup"><span data-stu-id="d48a5-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="d48a5-127">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="d48a5-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="d48a5-128">方法: Windows フォームのアンカーコントロール</span><span class="sxs-lookup"><span data-stu-id="d48a5-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
