---
title: '方法: Windows フォーム上のオブジェクトをレイヤー化する'
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
ms.openlocfilehash: 818f36633575b248d92da475c462cc0f211fe969
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966539"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="f2009-102">方法: Windows フォーム上のオブジェクトをレイヤー化する</span><span class="sxs-lookup"><span data-stu-id="f2009-102">How to: Layer Objects on Windows Forms</span></span>
<span data-ttu-id="f2009-103">複雑なユーザーインターフェイスを作成する場合や、マルチドキュメントインターフェイス (MDI) フォームを使用する場合は、多くの場合、コントロールと子フォームの両方をレイヤー化することで、より複雑なユーザーインターフェイス (UI) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2009-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="f2009-104">グループのコンテキスト内でコントロールとウィンドウを移動して追跡するには、z オーダーを操作します。</span><span class="sxs-lookup"><span data-stu-id="f2009-104">To move and keep track of controls and windows within the context of a group, you manipulate their z-order.</span></span> <span data-ttu-id="f2009-105">*Z オーダー*は、フォームの z 軸 (深度) に沿ってフォーム上のコントロールを視覚的に重ねたものです。</span><span class="sxs-lookup"><span data-stu-id="f2009-105">*Z-order* is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="f2009-106">Z オーダーの最上部にあるウィンドウは、他のすべてのウィンドウと重なっています。</span><span class="sxs-lookup"><span data-stu-id="f2009-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="f2009-107">他のすべてのウィンドウは、z オーダーの下部にあるウィンドウと重なっています。</span><span class="sxs-lookup"><span data-stu-id="f2009-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="f2009-108">デザイン時にコントロールをレイヤー化するには</span><span class="sxs-lookup"><span data-stu-id="f2009-108">To layer controls at design time</span></span>

1. <span data-ttu-id="f2009-109">レイヤー化するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2009-109">Select a control that you want to layer.</span></span>

2. <span data-ttu-id="f2009-110">**[書式]** メニューの **[順序]** をポイントし、 **[前面へ移動]** または **[背面へ]** 移動 をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2009-110">On the **Format** menu, point to **Order**, and then click **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="f2009-111">プログラムによってコントロールをレイヤー化するには</span><span class="sxs-lookup"><span data-stu-id="f2009-111">To layer controls programmatically</span></span>

- <span data-ttu-id="f2009-112">コントロールの z <xref:System.Windows.Forms.Control.SendToBack%2A>オーダーを操作するには、メソッドとメソッドを使用します。<xref:System.Windows.Forms.Control.BringToFront%2A></span><span class="sxs-lookup"><span data-stu-id="f2009-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

     <span data-ttu-id="f2009-113">たとえば、 <xref:System.Windows.Forms.TextBox> `txtFirstName`コントロールが別のコントロールの下にあり、そのコントロールを上に表示する場合は、次のコードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2009-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
> <span data-ttu-id="f2009-114">Windows フォームは*コントロールの含有*をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2009-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="f2009-115">コントロールのコンテインメントでは、 <xref:System.Windows.Forms.RadioButton> <xref:System.Windows.Forms.GroupBox>コントロール内のコントロールの数など、コントロールを含むコントロール内に多数のコントロールを配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2009-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="f2009-116">次に、それを含んでいるコントロール内のコントロールをレイヤー化できます。</span><span class="sxs-lookup"><span data-stu-id="f2009-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="f2009-117">グループボックスを移動すると、コントロールがその中に含まれているため、コントロールも移動します。</span><span class="sxs-lookup"><span data-stu-id="f2009-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2009-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2009-118">See also</span></span>

- [<span data-ttu-id="f2009-119">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="f2009-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f2009-120">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="f2009-120">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="f2009-121">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="f2009-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f2009-122">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="f2009-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f2009-123">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="f2009-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
