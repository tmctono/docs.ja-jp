---
title: オブジェクトを階層化する
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736342"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="c9881-102">方法: Windows フォーム上のオブジェクトをレイヤー化する</span><span class="sxs-lookup"><span data-stu-id="c9881-102">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="c9881-103">複雑なユーザーインターフェイスを作成する場合や、マルチドキュメントインターフェイス (MDI) フォームを使用する場合は、多くの場合、コントロールと子フォームの両方をレイヤー化することで、より複雑なユーザーインターフェイス (UI) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="c9881-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="c9881-104">グループのコンテキスト内でコントロールとウィンドウを移動して追跡するには、 *z オーダー*を操作します。</span><span class="sxs-lookup"><span data-stu-id="c9881-104">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="c9881-105">Z オーダーは、フォームの z 軸 (深度) に沿ってフォーム上のコントロールを視覚的に重ねたものです。</span><span class="sxs-lookup"><span data-stu-id="c9881-105">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="c9881-106">Z オーダーの最上部にあるウィンドウは、他のすべてのウィンドウと重なっています。</span><span class="sxs-lookup"><span data-stu-id="c9881-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="c9881-107">他のすべてのウィンドウは、z オーダーの下部にあるウィンドウと重なっています。</span><span class="sxs-lookup"><span data-stu-id="c9881-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="c9881-108">デザイン時にコントロールをレイヤー化するには</span><span class="sxs-lookup"><span data-stu-id="c9881-108">To layer controls at design time</span></span>

1. <span data-ttu-id="c9881-109">Visual Studio で、レイヤー化するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="c9881-109">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="c9881-110">**[書式]** メニューの **[順序]** をクリックし、 **[前面へ移動]** または **[背面へ]** 移動 を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9881-110">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="c9881-111">プログラムによってコントロールをレイヤー化するには</span><span class="sxs-lookup"><span data-stu-id="c9881-111">To layer controls programmatically</span></span>

<span data-ttu-id="c9881-112"><xref:System.Windows.Forms.Control.BringToFront%2A> および <xref:System.Windows.Forms.Control.SendToBack%2A> メソッドを使用して、コントロールの z オーダーを操作します。</span><span class="sxs-lookup"><span data-stu-id="c9881-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="c9881-113">たとえば、<xref:System.Windows.Forms.TextBox> コントロール、`txtFirstName`が別のコントロールの下にあり、そのコントロールを上に表示する場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="c9881-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="c9881-114">Windows フォームは*コントロールの含有*をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c9881-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="c9881-115">コントロールの含有では、<xref:System.Windows.Forms.GroupBox> コントロール内の <xref:System.Windows.Forms.RadioButton> コントロールの数など、多数のコントロールを含んでいるコントロール内に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9881-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="c9881-116">次に、それを含んでいるコントロール内のコントロールをレイヤー化できます。</span><span class="sxs-lookup"><span data-stu-id="c9881-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="c9881-117">グループボックスを移動すると、コントロールがその中に含まれているため、コントロールも移動します。</span><span class="sxs-lookup"><span data-stu-id="c9881-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="c9881-118">参照</span><span class="sxs-lookup"><span data-stu-id="c9881-118">See also</span></span>

- [<span data-ttu-id="c9881-119">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="c9881-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="c9881-120">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="c9881-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="c9881-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="c9881-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="c9881-122">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="c9881-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
