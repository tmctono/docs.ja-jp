---
title: Windows フォーム コントロールのレンダリング
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968275"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="8b321-102">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="8b321-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="8b321-103">レンダリングとは、ユーザーの画面で視覚的表現を作成するプロセスを指します。</span><span class="sxs-lookup"><span data-stu-id="8b321-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="8b321-104">Windows フォームは、GDI (新しい Windows グラフィックスライブラリ) を使用してレンダリングを行います。</span><span class="sxs-lookup"><span data-stu-id="8b321-104">Windows Forms uses GDI (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="8b321-105">GDI へのアクセスを提供するマネージクラスは、 <xref:System.Drawing?displayProperty=nameWithType>名前空間とその副名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="8b321-105">The managed classes that provide access to GDI are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="8b321-106">コントロールのレンダリングには、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b321-106">The following elements are involved in control rendering:</span></span>  
  
- <span data-ttu-id="8b321-107">基本クラス<xref:System.Windows.Forms.Control?displayProperty=nameWithType>によって提供される描画機能。</span><span class="sxs-lookup"><span data-stu-id="8b321-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="8b321-108">GDI グラフィックスライブラリの重要な要素。</span><span class="sxs-lookup"><span data-stu-id="8b321-108">The essential elements of the GDI graphics library.</span></span>  
  
- <span data-ttu-id="8b321-109">描画領域のジオメトリ。</span><span class="sxs-lookup"><span data-stu-id="8b321-109">The geometry of the drawing region.</span></span>  
  
- <span data-ttu-id="8b321-110">グラフィックスリソースを解放する手順。</span><span class="sxs-lookup"><span data-stu-id="8b321-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="8b321-111">コントロールによって提供される描画機能</span><span class="sxs-lookup"><span data-stu-id="8b321-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="8b321-112">基底クラス<xref:System.Windows.Forms.Control>は、 <xref:System.Windows.Forms.Control.Paint>イベントを通じて描画機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="8b321-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8b321-113">コントロールは、表示<xref:System.Windows.Forms.Control.Paint>を更新する必要があるときに常にイベントを発生させます。</span><span class="sxs-lookup"><span data-stu-id="8b321-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="8b321-114">.NET Framework のイベントの詳細については、「[イベントの処理と発生](../../../standard/events/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b321-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="8b321-115"><xref:System.Windows.Forms.Control.Paint>イベントのイベントデータクラスは、コントロールを描画するために必要なデータ (グラフィックスオブジェクトへのハンドル、および描画する領域を表す四角形オブジェクトを保持します) を保持します。 <xref:System.Windows.Forms.PaintEventArgs></span><span class="sxs-lookup"><span data-stu-id="8b321-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="8b321-116">これらのオブジェクトは、次のコードフラグメントに太字で示されています。</span><span class="sxs-lookup"><span data-stu-id="8b321-116">These objects are shown in bold in the following code fragment.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <span data-ttu-id="8b321-117"><xref:System.Drawing.Graphics>は、このトピックの後半の「GDI の説明」で説明されているように、描画機能をカプセル化するマネージクラスです。</span><span class="sxs-lookup"><span data-stu-id="8b321-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this topic.</span></span> <span data-ttu-id="8b321-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>は<xref:System.Drawing.Rectangle>構造体のインスタンスであり、コントロールが描画できる領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b321-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="8b321-119">コントロール開発者は、この<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>トピックで<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>後述する「ジオメトリの説明」で説明されているように、コントロールのプロパティを使用してを計算できます。</span><span class="sxs-lookup"><span data-stu-id="8b321-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="8b321-120">コントロールは、継承元<xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control>のメソッドをオーバーライドすることにより、レンダリングロジックを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b321-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="8b321-121"><xref:System.Windows.Forms.Control.OnPaint%2A>グラフィックスオブジェクトと、 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>に渡される<xref:System.Windows.Forms.PaintEventArgs>インスタンスのプロパティを通じて描画する四角形へのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="8b321-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="8b321-122">基底<xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control.Paint>クラスのメソッドは描画機能を実装しませんが、イベントに登録されているイベントデリゲートを呼び出すだけです。 <xref:System.Windows.Forms.Control></span><span class="sxs-lookup"><span data-stu-id="8b321-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8b321-123">をオーバーライド<xref:System.Windows.Forms.Control.OnPaint%2A>する場合は、通常、基本<xref:System.Windows.Forms.Control.OnPaint%2A>クラスのメソッドを呼び出して、登録されて<xref:System.Windows.Forms.Control.Paint>いるデリゲートがイベントを受け取るようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b321-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="8b321-124">ただし、画面全体を描画するコントロールでは、基本クラスの<xref:System.Windows.Forms.Control.OnPaint%2A>を呼び出さないでください。これにより、ちらつきが発生します。</span><span class="sxs-lookup"><span data-stu-id="8b321-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="8b321-125"><xref:System.Windows.Forms.Control.OnPaint%2A>イベントをオーバーライドする例につい[ては、「方法:進行状況](how-to-create-a-windows-forms-control-that-shows-progress.md)を表示する Windows フォームコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b321-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b321-126">コントロールから直接<xref:System.Windows.Forms.Control.OnPaint%2A>呼び出すのではなく、(から<xref:System.Windows.Forms.Control>継承<xref:System.Windows.Forms.Control.Invalidate%2A>された) メソッドまたはを呼び出す<xref:System.Windows.Forms.Control.Invalidate%2A>他のメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8b321-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="8b321-127">メソッド<xref:System.Windows.Forms.Control.Invalidate%2A>が呼び出さ<xref:System.Windows.Forms.Control.OnPaint%2A>れます。</span><span class="sxs-lookup"><span data-stu-id="8b321-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="8b321-128">メソッドはオーバーロードされており、に<xref:System.Windows.Forms.Control.Invalidate%2A> `e`指定された引数によっては、コントロールが画面領域の一部またはすべてを再描画します。 <xref:System.Windows.Forms.Control.Invalidate%2A></span><span class="sxs-lookup"><span data-stu-id="8b321-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="8b321-129">基底<xref:System.Windows.Forms.Control>クラスは、描画に便利な別のメソッド<xref:System.Windows.Forms.Control.OnPaintBackground%2A> (メソッド) を定義します。</span><span class="sxs-lookup"><span data-stu-id="8b321-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="8b321-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A>ウィンドウの背景 (およびその図形) を描画し<xref:System.Windows.Forms.Control.OnPaint%2A>ます。また、個々の描画要求が1つ<xref:System.Windows.Forms.Control.Paint>のイベントに結合され、その結果、すべての領域を対象とするすべての領域をカバーします。描画.</span><span class="sxs-lookup"><span data-stu-id="8b321-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="8b321-131">たとえば、コントロールのグラデーションカラー <xref:System.Windows.Forms.Control.OnPaintBackground%2A>の背景を描画する必要がある場合は、を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="8b321-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="8b321-132">に<xref:System.Windows.Forms.Control.OnPaintBackground%2A>はイベントのような用語があり、 `OnPaint`メソッドと同じ引数を取り<xref:System.Windows.Forms.Control.OnPaintBackground%2A>ますが、は true のイベントメソッドではありません。</span><span class="sxs-lookup"><span data-stu-id="8b321-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="8b321-133">イベントは存在`PaintBackground`せず<xref:System.Windows.Forms.Control.OnPaintBackground%2A> 、イベントデリゲートを呼び出しません。</span><span class="sxs-lookup"><span data-stu-id="8b321-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="8b321-134"><xref:System.Windows.Forms.Control.OnPaintBackground%2A>メソッドをオーバーライドする場合、派生クラスは基底クラスの<xref:System.Windows.Forms.Control.OnPaintBackground%2A>メソッドを呼び出す必要がありません。</span><span class="sxs-lookup"><span data-stu-id="8b321-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="8b321-135">GDI + の基礎</span><span class="sxs-lookup"><span data-stu-id="8b321-135">GDI+ Basics</span></span>  
 <span data-ttu-id="8b321-136">クラス<xref:System.Drawing.Graphics>には、円、三角形、円弧、楕円などのさまざまな図形を描画するためのメソッドと、テキストを表示するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8b321-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="8b321-137">名前<xref:System.Drawing?displayProperty=nameWithType>空間とその副名前空間には、図形 (円、四角形、円弧など)、色、フォント、ブラシなどのグラフィックス要素をカプセル化するクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8b321-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="8b321-138">GDI の詳細については、「[マネージグラフィックスクラスの使用](../advanced/using-managed-graphics-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b321-138">For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="8b321-139">GDI の基本事項については、 [「方法:進行状況](how-to-create-a-windows-forms-control-that-shows-progress.md)を表示する Windows フォームコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b321-139">The essentials of GDI are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="8b321-140">描画領域のジオメトリ</span><span class="sxs-lookup"><span data-stu-id="8b321-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="8b321-141">コントロール<xref:System.Windows.Forms.Control.ClientRectangle%2A>のプロパティは、ユーザーの画面上のコントロールで使用できる四角形の領域を指定します<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 。また<xref:System.Windows.Forms.PaintEventArgs> 、のプロパティは、実際に描画される領域を指定します。</span><span class="sxs-lookup"><span data-stu-id="8b321-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="8b321-142">(描画は、引数として<xref:System.Windows.Forms.Control.Paint>インスタンスを<xref:System.Windows.Forms.PaintEventArgs>受け取るイベントメソッドで行われることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="8b321-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="8b321-143">コントロールは、コントロールの表示の小さいセクションが変更された場合のように、使用可能な領域の一部だけを描画する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b321-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="8b321-144">このような状況では、コントロール開発者は、描画する実際の四角形を計算<xref:System.Windows.Forms.Control.Invalidate%2A>してに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b321-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="8b321-145">引数として<xref:System.Windows.Forms.Control.Invalidate%2A>または<xref:System.Drawing.Region>を<xref:System.Drawing.Rectangle>受け取るのオーバーロードされたバージョンは、その<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>引数を<xref:System.Windows.Forms.PaintEventArgs>使用してプロパティを生成します。</span><span class="sxs-lookup"><span data-stu-id="8b321-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="8b321-146">次のコードフラグメントは、カスタム`FlashTrackBar`コントロールが四角形の領域を計算して描画する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b321-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="8b321-147">変数`client`は、プロパティ<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>を表します。</span><span class="sxs-lookup"><span data-stu-id="8b321-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="8b321-148">完全なサンプルについて[は、「方法:進行状況](how-to-create-a-windows-forms-control-that-shows-progress.md)を表示する Windows フォームコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b321-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="8b321-149">グラフィックスリソースの解放</span><span class="sxs-lookup"><span data-stu-id="8b321-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="8b321-150">グラフィックスオブジェクトは、システムリソースを使用するため、コストが高くなります。</span><span class="sxs-lookup"><span data-stu-id="8b321-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="8b321-151">このようなオブジェクトには<xref:System.Drawing.Graphics?displayProperty=nameWithType> 、クラスのインスタンスだけで<xref:System.Drawing.Brush?displayProperty=nameWithType>なく<xref:System.Drawing.Pen?displayProperty=nameWithType>、、、およびその他のグラフィックスクラスのインスタンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8b321-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="8b321-152">グラフィックスリソースは、必要なときにのみ作成し、使用が終了したらすぐにリリースすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="8b321-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="8b321-153"><xref:System.IDisposable>インターフェイスを実装する型を作成する場合は、リソース<xref:System.IDisposable.Dispose%2A>を解放するために、メソッドの使用が終了したときにメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8b321-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="8b321-154">次のコードフラグメントは、カスタム`FlashTrackBar`コントロールがリソースを<xref:System.Drawing.Brush>作成および解放する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8b321-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="8b321-155">完全なソースコードについて[は、「方法:進行状況](how-to-create-a-windows-forms-control-that-shows-progress.md)を表示する Windows フォームコントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b321-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8b321-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b321-156">See also</span></span>

- [<span data-ttu-id="8b321-157">方法: 進行状況を表示する Windows フォームコントロールを作成する</span><span class="sxs-lookup"><span data-stu-id="8b321-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
