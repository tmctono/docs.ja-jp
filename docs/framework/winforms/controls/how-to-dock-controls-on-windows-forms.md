---
title: '方法: Windows フォーム上のコントロールをドッキングします。'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 4acda9149dd147a823eb42d3962a22b75df93802
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720269"
---
# <a name="how-to-dock-controls-on-windows-forms"></a><span data-ttu-id="2fc8c-102">方法: Windows フォーム上のコントロールをドッキングします。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-102">How to: Dock Controls on Windows Forms</span></span>
<span data-ttu-id="2fc8c-103">コントロールをフォームの端にドッキングまたはコントロールのコンテナー (フォームまたはコンテナー コントロールのいずれか) を入力することがあることができます。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-103">You can dock controls to the edges of your form or have them fill the control's container (either a form or a container control).</span></span> <span data-ttu-id="2fc8c-104">たとえば、Windows エクスプ ローラーをドッキングその<xref:System.Windows.Forms.TreeView>、ウィンドウの左側にあるコントロールとその<xref:System.Windows.Forms.ListView>ウィンドウの右側にあるコントロール。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-104">For example, Windows Explorer docks its <xref:System.Windows.Forms.TreeView> control to the left side of the window and its <xref:System.Windows.Forms.ListView> control to the right side of the window.</span></span> <span data-ttu-id="2fc8c-105">使用して、<xref:System.Windows.Forms.Control.Dock%2A>ドッキングのモードを定義する表示されているすべての Windows フォーム コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-105">Use the <xref:System.Windows.Forms.Control.Dock%2A> property for all visible Windows Forms controls to define the docking mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2fc8c-106">逆の z オーダーでコントロールがドッキングされます。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-106">Controls are docked in reverse z-order.</span></span>  
  
 <span data-ttu-id="2fc8c-107"><xref:System.Windows.Forms.Control.Dock%2A>プロパティの対話、<xref:System.Windows.Forms.Control.AutoSize%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-107">The <xref:System.Windows.Forms.Control.Dock%2A> property interacts with the <xref:System.Windows.Forms.Control.AutoSize%2A> property.</span></span> <span data-ttu-id="2fc8c-108">詳細については、[AutoSize プロパティの概要](autosize-property-overview.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-108">For more information, see [AutoSize Property Overview](autosize-property-overview.md).</span></span>  
  
### <a name="to-dock-a-control"></a><span data-ttu-id="2fc8c-109">コントロールをドッキングするには</span><span class="sxs-lookup"><span data-stu-id="2fc8c-109">To dock a control</span></span>  
  
1.  <span data-ttu-id="2fc8c-110">ドッキングするコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-110">Select the control that you want to dock.</span></span>  
  
2.  <span data-ttu-id="2fc8c-111">[プロパティ] ウィンドウの右側にある矢印をクリックします。、<xref:System.Windows.Forms.Control.Dock%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-111">In the Properties window, click the arrow to the right of the <xref:System.Windows.Forms.Control.Dock%2A> property.</span></span>  
  
     <span data-ttu-id="2fc8c-112">一連の端とフォームの中央を表すボックスを示しています。 エディターが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-112">An editor is displayed that shows a series of boxes representing the edges and the center of the form.</span></span>  
  
3.  <span data-ttu-id="2fc8c-113">コントロールをドッキングするフォームの端を表すボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-113">Click the button that represents the edge of the form where you want to dock the control.</span></span> <span data-ttu-id="2fc8c-114">コントロールのフォームまたはコンテナー コントロールの内容を入力するには、中央のボックスをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-114">To fill the contents of the control's form or container control, click the center box.</span></span> <span data-ttu-id="2fc8c-115">クリックして **(なし)** ドッキングを無効にします。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-115">Click **(none)** to disable docking.</span></span>  
  
     <span data-ttu-id="2fc8c-116">コントロールのドッキングのエッジの境界に合わせてサイズを自動的にします。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-116">The control is automatically resized to fit the boundaries of the docked edge.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2fc8c-117">継承されたコントロールである必要があります`Protected`ドッキングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-117">Inherited controls must be `Protected` to be able to be docked.</span></span> <span data-ttu-id="2fc8c-118">コントロールのアクセス レベルを変更するには、次のように設定します。 その**修飾子**プロパティ ウィンドウでプロパティ。</span><span class="sxs-lookup"><span data-stu-id="2fc8c-118">To change the access level of a control, set its **Modifier** property in the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc8c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fc8c-119">See also</span></span>
- [<span data-ttu-id="2fc8c-120">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="2fc8c-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="2fc8c-121">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="2fc8c-121">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="2fc8c-122">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="2fc8c-122">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="2fc8c-123">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="2fc8c-123">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="2fc8c-124">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="2fc8c-124">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- [<span data-ttu-id="2fc8c-125">方法: 固定およびドッキング FlowLayoutPanel コントロールで子コントロール</span><span class="sxs-lookup"><span data-stu-id="2fc8c-125">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="2fc8c-126">方法: 固定およびドッキング TableLayoutPanel コントロールで子コントロール</span><span class="sxs-lookup"><span data-stu-id="2fc8c-126">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="2fc8c-127">AutoSize プロパティの概要</span><span class="sxs-lookup"><span data-stu-id="2fc8c-127">AutoSize Property Overview</span></span>](autosize-property-overview.md)
- [<span data-ttu-id="2fc8c-128">方法: Windows フォームにコントロールを固定</span><span class="sxs-lookup"><span data-stu-id="2fc8c-128">How to: Anchor Controls on Windows Forms</span></span>](how-to-anchor-controls-on-windows-forms.md)
