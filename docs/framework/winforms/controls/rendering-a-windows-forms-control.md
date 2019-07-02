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
ms.openlocfilehash: 76506e504fdaca83fee502111dbadab5cb41d9b9
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2019
ms.locfileid: "67506180"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="232b7-102">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="232b7-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="232b7-103">レンダリングは、ユーザーの画面にビジュアル表現を作成するプロセスを指します。</span><span class="sxs-lookup"><span data-stu-id="232b7-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="232b7-104">Windows フォームでは、レンダリングの GDI (新しい Windows グラフィックス ライブラリ) を使用します。</span><span class="sxs-lookup"><span data-stu-id="232b7-104">Windows Forms uses GDI (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="232b7-105">GDI へのアクセスを提供するマネージ クラスは、<xref:System.Drawing?displayProperty=nameWithType>名前空間とその下位の名前空間。</span><span class="sxs-lookup"><span data-stu-id="232b7-105">The managed classes that provide access to GDI are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="232b7-106">コントロールのレンダリングで、次の要素が含まれます。</span><span class="sxs-lookup"><span data-stu-id="232b7-106">The following elements are involved in control rendering:</span></span>  
  
- <span data-ttu-id="232b7-107">基本クラスによって提供される描画機能<xref:System.Windows.Forms.Control?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="232b7-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="232b7-108">GDI グラフィックス ライブラリの重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="232b7-108">The essential elements of the GDI graphics library.</span></span>  
  
- <span data-ttu-id="232b7-109">描画領域のジオメトリ。</span><span class="sxs-lookup"><span data-stu-id="232b7-109">The geometry of the drawing region.</span></span>  
  
- <span data-ttu-id="232b7-110">グラフィックス リソースを解放するプロシージャです。</span><span class="sxs-lookup"><span data-stu-id="232b7-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="232b7-111">描画コントロールによって提供される機能</span><span class="sxs-lookup"><span data-stu-id="232b7-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="232b7-112">基本クラス<xref:System.Windows.Forms.Control>を通じて描画機能を提供します。 その<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="232b7-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="232b7-113">コントロールを有効に、<xref:System.Windows.Forms.Control.Paint>イベントの表示を更新する必要があるたびにします。</span><span class="sxs-lookup"><span data-stu-id="232b7-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="232b7-114">.NET Framework のイベントの詳細については、次を参照してください。[処理とイベントの発生](../../../standard/events/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="232b7-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="232b7-115">イベント データ クラスに対する、<xref:System.Windows.Forms.Control.Paint>イベント、<xref:System.Windows.Forms.PaintEventArgs>コントロールを描画するために必要なデータを保持する — グラフィック オブジェクト、および描画する領域を表す四角形オブジェクトを識別するハンドル。</span><span class="sxs-lookup"><span data-stu-id="232b7-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="232b7-116">これらのオブジェクトが示すように、次のコード フラグメントでは太字です。</span><span class="sxs-lookup"><span data-stu-id="232b7-116">These objects are shown in bold in the following code fragment.</span></span>  
  
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
  
 <span data-ttu-id="232b7-117"><xref:System.Drawing.Graphics> このトピックの「GDI の説明」の説明に従って、描画機能をカプセル化するマネージ クラスは、します。</span><span class="sxs-lookup"><span data-stu-id="232b7-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this topic.</span></span> <span data-ttu-id="232b7-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>のインスタンスである、<xref:System.Drawing.Rectangle>構造体であり、コントロールの描画に使用できる使用可能な領域を定義します。</span><span class="sxs-lookup"><span data-stu-id="232b7-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="232b7-119">コントロールの開発者が計算できる、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>を使用して、 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> geometry このトピックの後半の説明」の説明に従って、コントロールのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="232b7-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="232b7-120">コントロールは、オーバーライドすることでレンダリング ロジックを提供する必要があります、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドから継承した<xref:System.Windows.Forms.Control>します。</span><span class="sxs-lookup"><span data-stu-id="232b7-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="232b7-121"><xref:System.Windows.Forms.Control.OnPaint%2A> グラフィックス オブジェクトと経由描画する四角形へのアクセスを取得、<xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A>と<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>のプロパティ、<xref:System.Windows.Forms.PaintEventArgs>にインスタンスが渡されます。</span><span class="sxs-lookup"><span data-stu-id="232b7-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="232b7-122"><xref:System.Windows.Forms.Control.OnPaint%2A>メソッド ベースの<xref:System.Windows.Forms.Control>クラスは、描画機能を実装していませんが、単に登録されているイベントのデリゲートを呼び出す、<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="232b7-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="232b7-123">オーバーライドする場合<xref:System.Windows.Forms.Control.OnPaint%2A>、通常、呼び出す必要があります、<xref:System.Windows.Forms.Control.OnPaint%2A>デリゲートを登録するための基本クラスのメソッドの受信、<xref:System.Windows.Forms.Control.Paint>イベント。</span><span class="sxs-lookup"><span data-stu-id="232b7-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="232b7-124">ただし、コントロールの表面全体を描画するには、基本クラスが呼び出す必要がない<xref:System.Windows.Forms.Control.OnPaint%2A>ちらつきが導入されます。</span><span class="sxs-lookup"><span data-stu-id="232b7-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="232b7-125">オーバーライドする例については、<xref:System.Windows.Forms.Control.OnPaint%2A>イベントを参照してください、[方法。進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)します。</span><span class="sxs-lookup"><span data-stu-id="232b7-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="232b7-126">呼び出さないでください<xref:System.Windows.Forms.Control.OnPaint%2A>を直接コントロールの代わりに、起動、<xref:System.Windows.Forms.Control.Invalidate%2A>メソッド (から継承された<xref:System.Windows.Forms.Control>) または他の方法を呼び出す<xref:System.Windows.Forms.Control.Invalidate%2A>します。</span><span class="sxs-lookup"><span data-stu-id="232b7-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="232b7-127"><xref:System.Windows.Forms.Control.Invalidate%2A>メソッドが呼び出されます<xref:System.Windows.Forms.Control.OnPaint%2A>します。</span><span class="sxs-lookup"><span data-stu-id="232b7-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="232b7-128"><xref:System.Windows.Forms.Control.Invalidate%2A>メソッドをオーバー ロードしてに渡される引数に応じて<xref:System.Windows.Forms.Control.Invalidate%2A> `e`、一部またはすべての画面領域のコントロールを再描画します。</span><span class="sxs-lookup"><span data-stu-id="232b7-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="232b7-129">基本<xref:System.Windows.Forms.Control>クラス描画のために役立つもう 1 つのメソッドを定義する —、<xref:System.Windows.Forms.Control.OnPaintBackground%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="232b7-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="232b7-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 背景を描画 (これにより、図形) ウィンドウの中に、高速にすることが保証されます<xref:System.Windows.Forms.Control.OnPaint%2A>詳細を描画し、個々 の描画要求が 1 つに結合されますので、遅い場合があります<xref:System.Windows.Forms.Control.Paint>に必要なすべての領域をカバーするイベント再描画されます。</span><span class="sxs-lookup"><span data-stu-id="232b7-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="232b7-131">呼び出したい場合があります、<xref:System.Windows.Forms.Control.OnPaintBackground%2A>コントロールのグラデーションの色の背景を描画する場合。</span><span class="sxs-lookup"><span data-stu-id="232b7-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="232b7-132">中に<xref:System.Windows.Forms.Control.OnPaintBackground%2A>、イベントのような命名規則がありと同じ引数を受け取り、`OnPaint`メソッド、 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> true イベント メソッドではありません。</span><span class="sxs-lookup"><span data-stu-id="232b7-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="232b7-133">ない`PaintBackground`イベントと<xref:System.Windows.Forms.Control.OnPaintBackground%2A>イベント デリゲートは呼び出されません。</span><span class="sxs-lookup"><span data-stu-id="232b7-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="232b7-134">オーバーライドする場合、<xref:System.Windows.Forms.Control.OnPaintBackground%2A>メソッドでは、派生クラスに呼び出す必要はありません、<xref:System.Windows.Forms.Control.OnPaintBackground%2A>基底クラスのメソッド。</span><span class="sxs-lookup"><span data-stu-id="232b7-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="232b7-135">GDI + の基本</span><span class="sxs-lookup"><span data-stu-id="232b7-135">GDI+ Basics</span></span>  
 <span data-ttu-id="232b7-136"><xref:System.Drawing.Graphics>クラスには、円、三角形、弧、および楕円などのさまざまな図形を描画するためのメソッドとテキストを表示するためのメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="232b7-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="232b7-137"><xref:System.Drawing?displayProperty=nameWithType>名前空間とそのサブ図形 (円、四角形、弧、および他のユーザー)、色、フォント、ブラシなどのグラフィックス要素をカプセル化するクラスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="232b7-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="232b7-138">GDI の詳細については、次を参照してください。[マネージ グラフィックス クラスを使用して](../advanced/using-managed-graphics-classes.md)します。</span><span class="sxs-lookup"><span data-stu-id="232b7-138">For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="232b7-139">GDI の要点が記載されても、[方法。進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)します。</span><span class="sxs-lookup"><span data-stu-id="232b7-139">The essentials of GDI are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="232b7-140">描画領域のジオメトリ</span><span class="sxs-lookup"><span data-stu-id="232b7-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="232b7-141"><xref:System.Windows.Forms.Control.ClientRectangle%2A>コントロールのプロパティは、ユーザーの画面で、コントロールで使用できる四角形の領域を指定します中に、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>プロパティの<xref:System.Windows.Forms.PaintEventArgs>が実際に描画される領域を指定します。</span><span class="sxs-lookup"><span data-stu-id="232b7-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="232b7-142">(で描画を行うことに注意してください、<xref:System.Windows.Forms.Control.Paint>を受け取るイベント メソッドを<xref:System.Windows.Forms.PaintEventArgs>インスタンスの引数として)。</span><span class="sxs-lookup"><span data-stu-id="232b7-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="232b7-143">コントロールは、コントロールの表示の変更の場合と小さいセクションと同様、使用可能な領域では、一部だけを描画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="232b7-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="232b7-144">これらの状況では、コントロールの開発者が実際の四角形を描画しに渡さを計算する必要があります<xref:System.Windows.Forms.Control.Invalidate%2A>します。</span><span class="sxs-lookup"><span data-stu-id="232b7-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="232b7-145">オーバー ロードされたバージョンの<xref:System.Windows.Forms.Control.Invalidate%2A>を受け取る、<xref:System.Drawing.Rectangle>または<xref:System.Drawing.Region>を引数としてその引数を使用して生成する、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>プロパティの<xref:System.Windows.Forms.PaintEventArgs>します。</span><span class="sxs-lookup"><span data-stu-id="232b7-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="232b7-146">次のコード フラグメントを示していますが、どのように`FlashTrackBar`カスタム コントロールを描画する四角形の領域を計算します。</span><span class="sxs-lookup"><span data-stu-id="232b7-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="232b7-147">`client`変数を表します、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="232b7-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="232b7-148">完全なサンプルを参照してください。[方法。進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)します。</span><span class="sxs-lookup"><span data-stu-id="232b7-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="232b7-149">グラフィックス リソースの解放</span><span class="sxs-lookup"><span data-stu-id="232b7-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="232b7-150">グラフィックス オブジェクトは、システム リソースを使用するために高価です。</span><span class="sxs-lookup"><span data-stu-id="232b7-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="232b7-151">このようなオブジェクトのインスタンスを含む、<xref:System.Drawing.Graphics?displayProperty=nameWithType>クラスのインスタンスと<xref:System.Drawing.Brush?displayProperty=nameWithType>、 <xref:System.Drawing.Pen?displayProperty=nameWithType>、およびその他のグラフィックス クラス。</span><span class="sxs-lookup"><span data-stu-id="232b7-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="232b7-152">必要がありますが、リリースする場合にのみ、グラフィックス リソースを作成することが重要になりますがそれを使用して終了するとすぐにします。</span><span class="sxs-lookup"><span data-stu-id="232b7-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="232b7-153">実装する型を作成する場合、<xref:System.IDisposable>インターフェイスを呼び出してその<xref:System.IDisposable.Dispose%2A>リソースを解放するために操作を終了したらメソッド。</span><span class="sxs-lookup"><span data-stu-id="232b7-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="232b7-154">次のコード フラグメントを示しています、`FlashTrackBar`カスタム コントロールを作成して、解放、<xref:System.Drawing.Brush>リソース。</span><span class="sxs-lookup"><span data-stu-id="232b7-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="232b7-155">完全なソース コードでは、次を参照してください。[方法。進行状況を示す Windows フォーム コントロールを作成する](how-to-create-a-windows-forms-control-that-shows-progress.md)します。</span><span class="sxs-lookup"><span data-stu-id="232b7-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="232b7-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="232b7-156">See also</span></span>

- [<span data-ttu-id="232b7-157">方法: 進行状況を示す Windows フォーム コントロールを作成します。</span><span class="sxs-lookup"><span data-stu-id="232b7-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
