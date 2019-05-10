---
title: '方法: Windows フォーム上のコントロールを位置設定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211649"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="e5669-102">方法: Windows フォーム上のコントロールを位置設定する</span><span class="sxs-lookup"><span data-stu-id="e5669-102">How to: Position Controls on Windows Forms</span></span>

<span data-ttu-id="e5669-103">コントロールの位置、Visual Studio で、Windows フォーム デザイナーを使用するかを指定する、<xref:System.Windows.Forms.Control.Location%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5669-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="e5669-104">Windows フォーム デザイナーのデザイン サーフェイス上のコントロールを配置します。</span><span class="sxs-lookup"><span data-stu-id="e5669-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="e5669-105">Visual Studio では、マウスを使用して適切な場所にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="e5669-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="e5669-106">コントロールを選択しより正確に配置する矢印の付いたがキーに移動します。</span><span class="sxs-lookup"><span data-stu-id="e5669-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="e5669-107">また、*スナップ*コントロールをフォームに正確に配置できます。</span><span class="sxs-lookup"><span data-stu-id="e5669-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="e5669-108">詳細については、「[チュートリアル:フォームのスナップ線を使用して Windows 上のコントロール](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5669-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="e5669-109">[プロパティ] ウィンドウを使用して、コントロールを位置します。</span><span class="sxs-lookup"><span data-stu-id="e5669-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="e5669-110">Visual Studio に移動するコントロールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5669-110">In Visual Studio, click the control you want to position.</span></span>

2. <span data-ttu-id="e5669-111">**プロパティ**ウィンドウで、値を入力、<xref:System.Windows.Forms.Control.Location%2A>プロパティ、コントロール コンテナー内の位置をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="e5669-111">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

     <span data-ttu-id="e5669-112">最初の数値 (X) は、コンテナーの左端からの距離2 番目の数字 (Y) は、ピクセル単位で、コンテナーの領域の上端からの距離です。</span><span class="sxs-lookup"><span data-stu-id="e5669-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e5669-113">展開することができます、<xref:System.Windows.Forms.Control.Location%2A>プロパティを入力、 **X**と**Y**個別の値します。</span><span class="sxs-lookup"><span data-stu-id="e5669-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="e5669-114">プログラムでコントロールを位置します。</span><span class="sxs-lookup"><span data-stu-id="e5669-114">Position a control programmatically</span></span>

1. <span data-ttu-id="e5669-115">設定、<xref:System.Windows.Forms.Control.Location%2A>するコントロールのプロパティを<xref:System.Drawing.Point>します。</span><span class="sxs-lookup"><span data-stu-id="e5669-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="e5669-116">変更するコントロールの位置の X 座標を使用して、<xref:System.Windows.Forms.Control.Left%2A>サブプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5669-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="e5669-117">コントロールの位置をプログラムでインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="e5669-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="e5669-118">設定、<xref:System.Windows.Forms.Control.Left%2A>サブプロパティをコントロールの X 座標をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="e5669-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <span data-ttu-id="e5669-119">使用して、<xref:System.Windows.Forms.Control.Location%2A>コントロールの X と Y を設定するプロパティを同時に配置します。</span><span class="sxs-lookup"><span data-stu-id="e5669-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="e5669-120">位置を個別に設定するには、コントロールを使用して、 <xref:System.Windows.Forms.Control.Left%2A> (**X**) または<xref:System.Windows.Forms.Control.Top%2A>(**Y**) サブプロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5669-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="e5669-121">座標 X と Y 座標を暗黙的に設定しないで、<xref:System.Drawing.Point>この構造体には、ボタンの座標のコピーが含まれているため、ボタンの場所を表す構造体です。</span><span class="sxs-lookup"><span data-stu-id="e5669-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5669-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5669-122">See also</span></span>

- [<span data-ttu-id="e5669-123">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="e5669-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="e5669-124">チュートリアル: スナップ線を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="e5669-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="e5669-125">チュートリアル: TableLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="e5669-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="e5669-126">チュートリアル: FlowLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="e5669-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="e5669-127">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="e5669-127">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="e5669-128">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="e5669-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="e5669-129">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="e5669-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="e5669-130">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="e5669-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="e5669-131">[方法: Windows フォームの画面位置を設定します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e5669-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
