---
title: '方法: 既存のコントロールを別の親に再配置する'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
ms.openlocfilehash: a65b3c2b596a2d88ce4236aeadd86993bb268aa6
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039789"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="a0369-102">方法: 既存のコントロールを別の親に再配置する</span><span class="sxs-lookup"><span data-stu-id="a0369-102">How to: Reassign Existing Controls to a Different Parent</span></span>
<span data-ttu-id="a0369-103">フォームに存在するコントロールを新しいコンテナー コントロールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a0369-103">You can assign controls that exist on your form to a new container control.</span></span>

## <a name="to-reassign-existing-controls-to-a-different-parent"></a><span data-ttu-id="a0369-104">既存のコントロールを別の親に再配置するには</span><span class="sxs-lookup"><span data-stu-id="a0369-104">To reassign existing controls to a different parent</span></span>

1. <span data-ttu-id="a0369-105"><xref:System.Windows.Forms.Button> [ツールボックス] **から 3 つの** コントロールをフォームにドラッグします。</span><span class="sxs-lookup"><span data-stu-id="a0369-105">Drag three <xref:System.Windows.Forms.Button> controls from the **Toolbox** onto the form.</span></span>

     <span data-ttu-id="a0369-106">これらを互いに近づけて配置しますが、整列はさせません。</span><span class="sxs-lookup"><span data-stu-id="a0369-106">Position them near to each other, but leave them unaligned.</span></span>

2. <span data-ttu-id="a0369-107">**[ツールボックス]** で <xref:System.Windows.Forms.FlowLayoutPanel> コントロール アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0369-107">In the **Toolbox**, click the <xref:System.Windows.Forms.FlowLayoutPanel> control icon.</span></span>

     <span data-ttu-id="a0369-108">アイコンはフォームにドラッグしないでください。</span><span class="sxs-lookup"><span data-stu-id="a0369-108">Do not drag the icon onto the form.</span></span>

3. <span data-ttu-id="a0369-109">マウス ポインターを 3 つの <xref:System.Windows.Forms.Button> コントロールに近づけます。</span><span class="sxs-lookup"><span data-stu-id="a0369-109">Move the mouse pointer close to the three <xref:System.Windows.Forms.Button> controls.</span></span>

     <span data-ttu-id="a0369-110">ポインターが <xref:System.Windows.Forms.FlowLayoutPanel> コントロール アイコンが付いた十字カーソルに変わります。</span><span class="sxs-lookup"><span data-stu-id="a0369-110">The pointer changes to a crosshair with the <xref:System.Windows.Forms.FlowLayoutPanel> control icon attached.</span></span>

4. <span data-ttu-id="a0369-111">マウス ボタンを押したままにします。</span><span class="sxs-lookup"><span data-stu-id="a0369-111">Click and hold the mouse button.</span></span>

5. <span data-ttu-id="a0369-112">マウス ポインターをドラッグして、 <xref:System.Windows.Forms.FlowLayoutPanel> コントロールのアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="a0369-112">Drag the mouse pointer to draw the outline of the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

6. <span data-ttu-id="a0369-113">3 つの <xref:System.Windows.Forms.Button> コントロールを囲むようにアウトラインを描画します。</span><span class="sxs-lookup"><span data-stu-id="a0369-113">Draw the outline around the three <xref:System.Windows.Forms.Button> controls.</span></span>

7. <span data-ttu-id="a0369-114">マウスのボタンを離します。</span><span class="sxs-lookup"><span data-stu-id="a0369-114">Release the mouse button.</span></span>

     <span data-ttu-id="a0369-115">これで、3 つの <xref:System.Windows.Forms.Button> コントロールが <xref:System.Windows.Forms.FlowLayoutPanel> コントロールに挿入されました。</span><span class="sxs-lookup"><span data-stu-id="a0369-115">The three <xref:System.Windows.Forms.Button> controls are now inserted into the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0369-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0369-116">See also</span></span>

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="a0369-117">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="a0369-117">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="a0369-118">チュートリアル: TableLayoutPanel を使用した Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="a0369-118">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="a0369-119">チュートリアル: スナップ線を使用した Windows フォーム上のコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="a0369-119">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
