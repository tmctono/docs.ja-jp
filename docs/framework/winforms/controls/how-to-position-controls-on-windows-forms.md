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
ms.openlocfilehash: a0b97073b2f9363a64bfc4a4ede7ffa69e2bce42
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334004"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="bcb5a-102">方法: Windows フォーム上のコントロールを位置設定する</span><span class="sxs-lookup"><span data-stu-id="bcb5a-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="bcb5a-103">コントロールの位置、Windows フォーム デザイナーを使用するかを指定する、<xref:System.Windows.Forms.Control.Location%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcb5a-104">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bcb5a-105">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bcb5a-106">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-106">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="bcb5a-107">Windows フォーム デザイナーのデザイン サーフェイス上のコントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="bcb5a-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="bcb5a-108">マウスを使用して適切な場所にコントロールをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcb5a-109">コントロールを選択しより正確に配置する矢印の付いたがキーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="bcb5a-110">また、*スナップ*コントロールをフォームに正確に配置できます。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="bcb5a-111">詳細については、「[チュートリアル:フォームのスナップ線を使用して Windows 上のコントロール](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)します。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="bcb5a-112">[プロパティ] ウィンドウを使用してコントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="bcb5a-112">To position a control using the Properties window</span></span>  
  
1. <span data-ttu-id="bcb5a-113">移動するコントロールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-113">Click the control you want to position.</span></span>  
  
2. <span data-ttu-id="bcb5a-114">**プロパティ**ウィンドウで、値を入力、<xref:System.Windows.Forms.Control.Location%2A>プロパティ、コントロール コンテナー内の位置をコンマで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="bcb5a-115">最初の数値 (X) は、コンテナーの左端からの距離2 番目の数字 (Y) は、ピクセル単位で、コンテナーの領域の上端からの距離です。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bcb5a-116">展開することができます、<xref:System.Windows.Forms.Control.Location%2A>プロパティを入力、 **X**と**Y**個別の値します。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="bcb5a-117">プログラムでコントロールを配置するには</span><span class="sxs-lookup"><span data-stu-id="bcb5a-117">To position a control programmatically</span></span>  
  
1. <span data-ttu-id="bcb5a-118">設定、<xref:System.Windows.Forms.Control.Location%2A>するコントロールのプロパティを<xref:System.Drawing.Point>します。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2. <span data-ttu-id="bcb5a-119">変更するコントロールの位置の X 座標を使用して、<xref:System.Windows.Forms.Control.Left%2A>サブプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="bcb5a-120">コントロールの位置をプログラムでインクリメントするには</span><span class="sxs-lookup"><span data-stu-id="bcb5a-120">To increment a control's location programmatically</span></span>  
  
1. <span data-ttu-id="bcb5a-121">設定、<xref:System.Windows.Forms.Control.Left%2A>サブプロパティをコントロールの X 座標をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
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
    >  <span data-ttu-id="bcb5a-122">使用して、<xref:System.Windows.Forms.Control.Location%2A>コントロールの X と Y を設定するプロパティを同時に配置します。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="bcb5a-123">位置を個別に設定するには、コントロールを使用して、 <xref:System.Windows.Forms.Control.Left%2A> (**X**) または<xref:System.Windows.Forms.Control.Top%2A>(**Y**) サブプロパティ。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="bcb5a-124">座標 X と Y 座標を暗黙的に設定しないで、<xref:System.Drawing.Point>この構造体には、ボタンの座標のコピーが含まれているため、ボタンの場所を表す構造体です。</span><span class="sxs-lookup"><span data-stu-id="bcb5a-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcb5a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcb5a-125">See also</span></span>

- [<span data-ttu-id="bcb5a-126">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="bcb5a-126">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="bcb5a-127">チュートリアル: スナップ線を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bcb5a-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="bcb5a-128">チュートリアル: TableLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bcb5a-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="bcb5a-129">チュートリアル: FlowLayoutPanel を使用して Windows フォーム コントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bcb5a-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="bcb5a-130">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="bcb5a-130">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="bcb5a-131">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="bcb5a-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="bcb5a-132">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="bcb5a-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="bcb5a-133">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="bcb5a-133">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="bcb5a-134">[方法: Windows フォームの画面位置を設定します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bcb5a-134">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
