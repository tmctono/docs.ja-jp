---
title: '方法: 描画する Graphics オブジェクトを作成する'
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
ms.openlocfilehash: 3d3ab62896f6b799cd38a8180b90f33125a9929b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964340"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="f0712-102">方法: 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="f0712-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="f0712-103">Gdi + を使用して、線や形状の描画、テキストのレンダリング、イメージの表示と操作を行う<xref:System.Drawing.Graphics>には、オブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0712-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f0712-104">オブジェクト<xref:System.Drawing.Graphics>は gdi + の描画サーフェイスを表し、はグラフィックイメージを作成するために使用されるオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f0712-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="f0712-105">グラフィックスを操作するには、次の2つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f0712-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="f0712-106">オブジェクトを<xref:System.Drawing.Graphics>作成しています。</span><span class="sxs-lookup"><span data-stu-id="f0712-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="f0712-107"><xref:System.Drawing.Graphics>オブジェクトを使用して、線と形状を描画したり、テキストを表示したり、イメージを表示および操作したりします。</span><span class="sxs-lookup"><span data-stu-id="f0712-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="f0712-108">グラフィックスオブジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="f0712-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="f0712-109">グラフィックスオブジェクトは、さまざまな方法で作成できます。</span><span class="sxs-lookup"><span data-stu-id="f0712-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="f0712-110">グラフィックスオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f0712-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="f0712-111">フォームまたはコントロールの<xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint>イベントで、の一部としてグラフィックスオブジェクトへの参照を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f0712-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="f0712-112">これは、通常、コントロールの描画コードを作成するときに、グラフィックスオブジェクトへの参照を取得する方法です。</span><span class="sxs-lookup"><span data-stu-id="f0712-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="f0712-113">同様に、の<xref:System.Drawing.Printing.PrintPageEventArgs> <xref:System.Drawing.Printing.PrintDocument.PrintPage>イベント<xref:System.Drawing.Printing.PrintDocument>を処理するときに、グラフィックスオブジェクトをのプロパティとして取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0712-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="f0712-114">\- または -</span><span class="sxs-lookup"><span data-stu-id="f0712-114">-or-</span></span>  
  
- <span data-ttu-id="f0712-115">コントロールまたはフォームの<xref:System.Drawing.Graphics> メソッドを呼び出して、そのコントロールまたはフォームの描画サーフェイスを表すオブジェクトへの参照を取得します。<xref:System.Windows.Forms.Control.CreateGraphics%2A></span><span class="sxs-lookup"><span data-stu-id="f0712-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="f0712-116">既に存在するフォームまたはコントロールに描画する場合は、このメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0712-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="f0712-117">\- または -</span><span class="sxs-lookup"><span data-stu-id="f0712-117">-or-</span></span>  
  
- <span data-ttu-id="f0712-118"><xref:System.Drawing.Graphics> を<xref:System.Drawing.Image>継承する任意のオブジェクトからオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0712-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="f0712-119">この方法は、既存のイメージを変更する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f0712-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="f0712-120">次のセクションでは、これらの各プロセスについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="f0712-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="f0712-121">描画イベントハンドラーの PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="f0712-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="f0712-122">コントロール<xref:System.Windows.Forms.PaintEventHandler> <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs>またはのをプログラミングする場合、グラフィックスオブジェクトはまたはのプロパティの1つとして提供されます。 <xref:System.Drawing.Printing.PrintDocument.PrintPage> <xref:System.Drawing.Printing.PrintDocument></span><span class="sxs-lookup"><span data-stu-id="f0712-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="f0712-123">描画イベントの PaintEventArgs からグラフィックスオブジェクトへの参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="f0712-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="f0712-124">オブジェクトを<xref:System.Drawing.Graphics>宣言します。</span><span class="sxs-lookup"><span data-stu-id="f0712-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="f0712-125">変数を割り当てて、 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs>の一部として渡されたオブジェクトを参照します。</span><span class="sxs-lookup"><span data-stu-id="f0712-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="f0712-126">フォームまたはコントロールを描画するためのコードを挿入します。</span><span class="sxs-lookup"><span data-stu-id="f0712-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="f0712-127">次の例は、 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.Control.Paint>イベント<xref:System.Windows.Forms.PaintEventArgs>でからオブジェクトを参照する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0712-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="f0712-128">CreateGraphics メソッド</span><span class="sxs-lookup"><span data-stu-id="f0712-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="f0712-129">また、コントロールまたは<xref:System.Windows.Forms.Control.CreateGraphics%2A>フォームのメソッドを使用して、そのコントロールまたは<xref:System.Drawing.Graphics>フォームの描画サーフェイスを表すオブジェクトへの参照を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0712-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="f0712-130">CreateGraphics メソッドを使用してグラフィックスオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f0712-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="f0712-131">グラフィックスを<xref:System.Windows.Forms.Control.CreateGraphics%2A>レンダリングするフォームまたはコントロールのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0712-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="f0712-132">イメージオブジェクトから作成する</span><span class="sxs-lookup"><span data-stu-id="f0712-132">Create from an Image Object</span></span>  
 <span data-ttu-id="f0712-133">さらに、 <xref:System.Drawing.Image>クラスから派生した任意のオブジェクトからグラフィックスオブジェクトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0712-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="f0712-134">イメージからグラフィックスオブジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="f0712-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="f0712-135">オブジェクト<xref:System.Drawing.Graphics>を<xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType>作成するイメージ変数の名前を指定して、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0712-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="f0712-136">次の例は、オブジェクトの<xref:System.Drawing.Bitmap>使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f0712-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="f0712-137">オブジェクトを作成<xref:System.Drawing.Graphics>できるのは、16ビット、24ビット、32ビットの .bmp ファイルなど、インデックスのない .bmp ファイルのオブジェクトだけです。</span><span class="sxs-lookup"><span data-stu-id="f0712-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="f0712-138">インデックス付けされていない .bmp ファイルの各ピクセルには、カラーテーブルのインデックスを保持するインデックス付き .bmp ファイルのピクセルとは対照的に、色が保持されます。</span><span class="sxs-lookup"><span data-stu-id="f0712-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="f0712-139">図形とイメージの描画と操作</span><span class="sxs-lookup"><span data-stu-id="f0712-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="f0712-140">オブジェクトを作成した後<xref:System.Drawing.Graphics> 、オブジェクトを使用して、線や図形の描画、テキストの表示、画像の表示と操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0712-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="f0712-141"><xref:System.Drawing.Graphics>オブジェクトで使用されるプリンシパルオブジェクトは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f0712-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="f0712-142"><xref:System.Drawing.Pen>クラス。線の描画、図形のアウトライン表示、またはその他の幾何学的表現のレンダリングに使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0712-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="f0712-143">塗り<xref:System.Drawing.Brush>つぶされた図形、画像、テキストなど、グラフィックスの領域を塗りつぶすために使用されるクラス。</span><span class="sxs-lookup"><span data-stu-id="f0712-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="f0712-144"><xref:System.Drawing.Font>クラス: テキストを表示するときに使用する図形の説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="f0712-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="f0712-145">構造<xref:System.Drawing.Color>体は、表示するさまざまな色を表します。</span><span class="sxs-lookup"><span data-stu-id="f0712-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="f0712-146">作成したグラフィックスオブジェクトを使用するには</span><span class="sxs-lookup"><span data-stu-id="f0712-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="f0712-147">上記の適切なオブジェクトを使用して、必要なものを描画します。</span><span class="sxs-lookup"><span data-stu-id="f0712-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="f0712-148">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0712-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="f0712-149">レンダリングするには</span><span class="sxs-lookup"><span data-stu-id="f0712-149">To render</span></span>|<span data-ttu-id="f0712-150">解決方法</span><span class="sxs-lookup"><span data-stu-id="f0712-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="f0712-151">線</span><span class="sxs-lookup"><span data-stu-id="f0712-151">Lines</span></span>|[<span data-ttu-id="f0712-152">方法: Windows フォーム上に線を描画する</span><span class="sxs-lookup"><span data-stu-id="f0712-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="f0712-153">図形</span><span class="sxs-lookup"><span data-stu-id="f0712-153">Shapes</span></span>|[<span data-ttu-id="f0712-154">方法: 輪郭付きの図形を描画する</span><span class="sxs-lookup"><span data-stu-id="f0712-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="f0712-155">テキスト</span><span class="sxs-lookup"><span data-stu-id="f0712-155">Text</span></span>|[<span data-ttu-id="f0712-156">方法: Windows フォームでのテキストの描画</span><span class="sxs-lookup"><span data-stu-id="f0712-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="f0712-157">画像</span><span class="sxs-lookup"><span data-stu-id="f0712-157">Images</span></span>|[<span data-ttu-id="f0712-158">方法: GDI + を使用したイメージのレンダリング</span><span class="sxs-lookup"><span data-stu-id="f0712-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f0712-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0712-159">See also</span></span>

- [<span data-ttu-id="f0712-160">グラフィックス プログラミングについて</span><span class="sxs-lookup"><span data-stu-id="f0712-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="f0712-161">Windows フォームにおけるグラフィックスと描画</span><span class="sxs-lookup"><span data-stu-id="f0712-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f0712-162">直線、曲線、および図形</span><span class="sxs-lookup"><span data-stu-id="f0712-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f0712-163">方法: GDI + を使用したイメージのレンダリング</span><span class="sxs-lookup"><span data-stu-id="f0712-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
