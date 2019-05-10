---
title: ユーザー描画コントロール
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: bd7ce150e4dc0ecfe53f92ec8b557459f1e14e3a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651566"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="5e8e0-102">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="5e8e0-102">User-Drawn Controls</span></span>
<span data-ttu-id="5e8e0-103">.NET Framework では、独自のコントロールを簡単に開発する機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="5e8e0-104">コードによって結合されて標準のコントロールのセットである、ユーザー コントロールを作成することもをゼロから独自のコントロールをデザインすることができます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="5e8e0-105">既存のコントロールから継承するコントロールを作成し、本来の機能を追加する継承を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="5e8e0-106">どのようなアプローチを使用すると、.NET Framework は、任意のコントロールを作成するためのカスタムのグラフィカル インターフェイスを描画するために機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="5e8e0-107">コントロールの描画には、コントロールのコードの実行、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5e8e0-108">1 つの引数、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドは、<xref:System.Windows.Forms.PaintEventArgs>すべての情報と、コントロールのレンダリングに必要な機能を提供するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="5e8e0-109"><xref:System.Windows.Forms.PaintEventArgs>プロパティとして、コントロールの描画に使用される 2 つのプリンシパル オブジェクトを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="5e8e0-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> オブジェクトの描画されるコントロールの一部を表す四角形。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="5e8e0-111">これには、全体をコントロール、またはコントロールの描画方法に応じたコントロールの一部です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="5e8e0-112"><xref:System.Drawing.Graphics> オブジェクト - いくつかのグラフィック指向オブジェクトとコントロールを描画するために必要な機能を提供するメソッドをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="5e8e0-113">詳細については、<xref:System.Drawing.Graphics>オブジェクトとそれを使用して、参照してください方法[方法。描画の Graphics オブジェクトを作成](../advanced/how-to-create-graphics-objects-for-drawing.md)です。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="5e8e0-114"><xref:System.Windows.Forms.Control.OnPaint%2A>コントロールの描画または画面で、更新されるたびにイベントが発生し、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>オブジェクトが描画を実行、四角形を表します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="5e8e0-115">コントロール全体を更新する必要がある場合、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>コントロール全体のサイズを表します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="5e8e0-116">コントロールの一部がただし、更新、する必要があるあれば、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>オブジェクトが再描画する必要があるリージョンのみを表します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="5e8e0-117">このようなケースの例は、別のコントロールまたはユーザー インターフェイスでのフォーム コントロールの一部が見えない場合になります。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="5e8e0-118">継承する場合、<xref:System.Windows.Forms.Control>クラスがオーバーライドする必要があります、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド内でのグラフィックス レンダリング コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="5e8e0-119">ユーザー コントロールまたは継承されたコントロールにカスタムのグラフィカル インターフェイスを提供する場合もこれを行うオーバーライドすることで、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="5e8e0-120">例は、以下に示します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-120">An example is shown below:</span></span>  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 <span data-ttu-id="5e8e0-121">前の例では、非常にシンプルなグラフィカル表示コントロールを描画する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="5e8e0-122">呼び出す、<xref:System.Windows.Forms.Control.OnPaint%2A>基底クラスのメソッドを作成、<xref:System.Drawing.Pen>を描画する対象のオブジェクトし、最後に、四角形に楕円を描画しますが定め、<xref:System.Windows.Forms.Control.Location%2A>と<xref:System.Windows.Forms.Control.Size%2A>コントロールの。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="5e8e0-123">この例での使用を示しますが、ほとんどのレンダリング コードは、これよりも大幅に複雑になります、<xref:System.Drawing.Graphics>オブジェクト内に含まれる、<xref:System.Windows.Forms.PaintEventArgs>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="5e8e0-124">既にグラフィカル表現をなどが含まれるクラスから継承している場合<xref:System.Windows.Forms.UserControl>または<xref:System.Windows.Forms.Button>、その表現をレンダリングに組み込むしたくない、基本クラスを呼び出す必要はありません、 <xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="5e8e0-125">内のコード、<xref:System.Windows.Forms.Control.OnPaint%2A>および更新は、コントロールが最初に描画されるときに、コントロールのメソッドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="5e8e0-126">サイズを変更するたびに、コントロールが再描画されることを確認するには、コントロールのコンス トラクターに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="5e8e0-127">使用して、<xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>四角形以外のコントロールを実装するプロパティ。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8e0-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e8e0-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="5e8e0-129">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="5e8e0-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="5e8e0-130">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="5e8e0-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="5e8e0-131">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="5e8e0-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
