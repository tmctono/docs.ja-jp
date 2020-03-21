---
title: '方法 : 描画する Graphics オブジェクトを作成する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142434"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="c40cf-102">方法 : 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="c40cf-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="c40cf-103">線や図形の描画、テキストのレンダリング、GDI+ を使用したイメージの表示と操作を行うには、<xref:System.Drawing.Graphics>オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c40cf-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c40cf-104">オブジェクト<xref:System.Drawing.Graphics>は GDI+ 描画サーフェイスを表し、グラフィック イメージの作成に使用されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="c40cf-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="c40cf-105">グラフィックスを操作するには、次の 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="c40cf-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="c40cf-106">オブジェクトを<xref:System.Drawing.Graphics>作成する。</span><span class="sxs-lookup"><span data-stu-id="c40cf-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c40cf-107">オブジェクトを<xref:System.Drawing.Graphics>使用して、線や図形の描画、テキストのレンダリング、またはイメージの表示と操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c40cf-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="c40cf-108">グラフィックス オブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="c40cf-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="c40cf-109">グラフィックス オブジェクトは、さまざまな方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="c40cf-110">グラフィックス オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c40cf-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="c40cf-111">フォームまたはコントロールの<xref:System.Windows.Forms.PaintEventArgs><xref:System.Windows.Forms.Control.Paint>イベントの一部として、グラフィックス オブジェクトへの参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c40cf-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="c40cf-112">これは通常、コントロールの描画コードを作成するときに、グラフィックス オブジェクトへの参照を取得する方法です。</span><span class="sxs-lookup"><span data-stu-id="c40cf-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="c40cf-113">同様に、イベントを処理<xref:System.Drawing.Printing.PrintPageEventArgs>するときに、グラフィックス オブジェクトを<xref:System.Drawing.Printing.PrintDocument.PrintPage>プロパティとして取得することもできます。 <xref:System.Drawing.Printing.PrintDocument></span><span class="sxs-lookup"><span data-stu-id="c40cf-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="c40cf-114">または</span><span class="sxs-lookup"><span data-stu-id="c40cf-114">-or-</span></span>  
  
- <span data-ttu-id="c40cf-115">コントロールまたは<xref:System.Windows.Forms.Control.CreateGraphics%2A>フォームの描画サーフェイスを表すオブジェクトへの参照を<xref:System.Drawing.Graphics>取得するには、コントロールまたはフォームのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="c40cf-116">このメソッドは、既に存在するフォームまたはコントロールに描画する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="c40cf-117">または</span><span class="sxs-lookup"><span data-stu-id="c40cf-117">-or-</span></span>  
  
- <span data-ttu-id="c40cf-118">から<xref:System.Drawing.Image>継承<xref:System.Drawing.Graphics>するオブジェクトからオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="c40cf-119">この方法は、既存のイメージを変更する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="c40cf-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="c40cf-120">以下のセクションでは、これらの各プロセスについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="c40cf-121">ペイント イベント ハンドラーのペイント イベント引数</span><span class="sxs-lookup"><span data-stu-id="c40cf-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="c40cf-122">for コントロールまたは<xref:System.Windows.Forms.PaintEventHandler><xref:System.Drawing.Printing.PrintDocument.PrintPage>の をプログラミングする<xref:System.Drawing.Printing.PrintDocument>場合は、 または のプロパティ<xref:System.Windows.Forms.PaintEventArgs>の 1 つとして<xref:System.Drawing.Printing.PrintPageEventArgs>グラフィックス オブジェクトが提供されます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="c40cf-123">ペイント イベントのペイント イベント引数からグラフィックス オブジェクトへの参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="c40cf-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="c40cf-124">オブジェクトを<xref:System.Drawing.Graphics>宣言します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c40cf-125">の一部として渡される<xref:System.Drawing.Graphics>オブジェクトを参照する変数を<xref:System.Windows.Forms.PaintEventArgs>割り当てます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="c40cf-126">フォームまたはコントロールを描画するコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="c40cf-127">次の例は、イベント<xref:System.Drawing.Graphics><xref:System.Windows.Forms.PaintEventArgs>内の オブジェクトを参照する<xref:System.Windows.Forms.Control.Paint>方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c40cf-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="c40cf-128">グラフィックス メソッドの作成</span><span class="sxs-lookup"><span data-stu-id="c40cf-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="c40cf-129">コントロールまたはフォームのメソッド<xref:System.Windows.Forms.Control.CreateGraphics%2A>を使用して、そのコントロールまたはフォームの描画サーフェイス<xref:System.Drawing.Graphics>を表すオブジェクトへの参照を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="c40cf-130">CreateGraphics メソッドを使用してグラフィックス オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c40cf-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="c40cf-131">グラフィックスを<xref:System.Windows.Forms.Control.CreateGraphics%2A>レンダリングするフォームまたはコントロールのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="c40cf-132">イメージ オブジェクトから作成</span><span class="sxs-lookup"><span data-stu-id="c40cf-132">Create from an Image Object</span></span>  
 <span data-ttu-id="c40cf-133">また、クラスから派生する任意のオブジェクトからグラフィックス オブジェクトを<xref:System.Drawing.Image>作成できます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="c40cf-134">イメージからグラフィックス オブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c40cf-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="c40cf-135">オブジェクトを<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>作成する Image 変数の名前を指定して、メソッドを<xref:System.Drawing.Graphics>呼び出します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="c40cf-136">次の例は、オブジェクトの使用方法<xref:System.Drawing.Bitmap>を示しています。</span><span class="sxs-lookup"><span data-stu-id="c40cf-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> <span data-ttu-id="c40cf-137">16 ビット<xref:System.Drawing.Graphics>、24 ビット、32 ビットの .bmp ファイルなど、インデックスを作成していない .bmp ファイルからのみオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="c40cf-138">インデックスが作成されていない .bmp ファイルの各ピクセルは、カラー テーブルへのインデックスを保持するインデックス付きの .bmp ファイルのピクセルとは対照的に、色を保持します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="c40cf-139">図形とイメージの描画と操作</span><span class="sxs-lookup"><span data-stu-id="c40cf-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="c40cf-140">作成後、オブジェクトを<xref:System.Drawing.Graphics>使用して、線やシェイプの描画、テキストのレンダリング、イメージの表示と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="c40cf-141"><xref:System.Drawing.Graphics>オブジェクトで使用される主なオブジェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c40cf-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="c40cf-142">クラス<xref:System.Drawing.Pen>- 線の描画、シェイプのアウトライン表示、その他のジオメトリ表現のレンダリングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c40cf-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="c40cf-143">クラス<xref:System.Drawing.Brush>- 塗りつぶされた図形、イメージ、テキストなどのグラフィックス領域を塗りつぶす場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="c40cf-144">クラス<xref:System.Drawing.Font>- テキストをレンダリングするときに使用する図形の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="c40cf-145">構造<xref:System.Drawing.Color>- 表示するさまざまな色を表します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="c40cf-146">作成した Graphics オブジェクトを使用するには</span><span class="sxs-lookup"><span data-stu-id="c40cf-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="c40cf-147">上記の適切なオブジェクトを使用して、必要なものを描画します。</span><span class="sxs-lookup"><span data-stu-id="c40cf-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="c40cf-148">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c40cf-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="c40cf-149">レンダリングするには</span><span class="sxs-lookup"><span data-stu-id="c40cf-149">To render</span></span>|<span data-ttu-id="c40cf-150">参照先</span><span class="sxs-lookup"><span data-stu-id="c40cf-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="c40cf-151">路線</span><span class="sxs-lookup"><span data-stu-id="c40cf-151">Lines</span></span>|[<span data-ttu-id="c40cf-152">方法 : Windows フォームに直線を描画する</span><span class="sxs-lookup"><span data-stu-id="c40cf-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="c40cf-153">図形</span><span class="sxs-lookup"><span data-stu-id="c40cf-153">Shapes</span></span>|[<span data-ttu-id="c40cf-154">方法 : 形状のアウトラインを描画する</span><span class="sxs-lookup"><span data-stu-id="c40cf-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="c40cf-155">Text</span><span class="sxs-lookup"><span data-stu-id="c40cf-155">Text</span></span>|[<span data-ttu-id="c40cf-156">方法 : Windows フォームにテキストを描画する</span><span class="sxs-lookup"><span data-stu-id="c40cf-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="c40cf-157">イメージ</span><span class="sxs-lookup"><span data-stu-id="c40cf-157">Images</span></span>|[<span data-ttu-id="c40cf-158">方法 : GDI+ を使用してイメージをレンダリングする</span><span class="sxs-lookup"><span data-stu-id="c40cf-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c40cf-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="c40cf-159">See also</span></span>

- [<span data-ttu-id="c40cf-160">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="c40cf-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c40cf-161">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="c40cf-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c40cf-162">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="c40cf-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="c40cf-163">方法 : GDI+ を使用してイメージをレンダリングする</span><span class="sxs-lookup"><span data-stu-id="c40cf-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
