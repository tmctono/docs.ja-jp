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
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182006"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="ecc02-102">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="ecc02-102">User-Drawn Controls</span></span>
<span data-ttu-id="ecc02-103">.NET Framework では、独自のコントロールを簡単に開発できます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="ecc02-104">コードによってバインドされた一連の標準コントロールであるユーザー コントロールを作成することも、独自のコントロールを一からデザインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="ecc02-105">継承を使用して、既存のコントロールから継承するコントロールを作成し、その固有の機能を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="ecc02-106">どのような方法を使用しても、.NET Framework には、作成するコントロールのカスタム グラフィカル インターフェイスを描画する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ecc02-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="ecc02-107">コントロールの描画は、コントロールの<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドでコードを実行することによって行われます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ecc02-108"><xref:System.Windows.Forms.Control.OnPaint%2A>メソッドの単一の引数は、<xref:System.Windows.Forms.PaintEventArgs>コントロールのレンダリングに必要なすべての情報と機能を提供するオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="ecc02-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="ecc02-109">では<xref:System.Windows.Forms.PaintEventArgs>、コントロールのレンダリングで使用される 2 つの主要なオブジェクトをプロパティとして提供します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="ecc02-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>object : 描画されるコントロールの一部を表す四角形。</span><span class="sxs-lookup"><span data-stu-id="ecc02-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="ecc02-111">これは、コントロール全体、またはコントロールの描画方法に応じてコントロールの一部にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="ecc02-112"><xref:System.Drawing.Graphics>object - コントロールの描画に必要な機能を提供する、いくつかのグラフィックス指向のオブジェクトとメソッドをカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="ecc02-113">オブジェクトの<xref:System.Drawing.Graphics>詳細と使用方法については、「[方法: 図面用のグラフィックス オブジェクトを作成する](../advanced/how-to-create-graphics-objects-for-drawing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ecc02-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="ecc02-114">この<xref:System.Windows.Forms.Control.OnPaint%2A>イベントは、コントロールが画面に描画または更新され、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>オブジェクトが描画が行われる四角形を表すたびに発生します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="ecc02-115">コントロール全体を更新する必要がある場合は<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>、 はコントロール全体のサイズを表します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="ecc02-116">ただし、コントロールの一部だけを更新する必要がある場合、<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>オブジェクトは再描画が必要な領域のみを表します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="ecc02-117">このような場合の例としては、ユーザー インターフェイスの別のコントロールまたはフォームによってコントロールが部分的に隠されていた場合があります。</span><span class="sxs-lookup"><span data-stu-id="ecc02-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="ecc02-118"><xref:System.Windows.Forms.Control>クラスから継承する場合は、メソッドをオーバーライドし<xref:System.Windows.Forms.Control.OnPaint%2A>、グラフィックス レンダリング コードを内部に提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecc02-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="ecc02-119">ユーザー コントロールまたは継承されたコントロールにカスタム グラフィカル インターフェイスを提供する場合は、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドをオーバーライドして提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="ecc02-120">例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="ecc02-121">前の例では、非常に単純なグラフィカル表現でコントロールをレンダリングする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="ecc02-122">このメソッドは<xref:System.Windows.Forms.Control.OnPaint%2A>、基本クラスのメソッドを呼び出<xref:System.Drawing.Pen>し、描画に使用するオブジェクトを作成し、最後に<xref:System.Windows.Forms.Control.Location%2A>、コントロールの で<xref:System.Windows.Forms.Control.Size%2A>決定された四角形に楕円を描画します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="ecc02-123">ほとんどのレンダリング コードはこれよりかなり複雑になりますが、この例では、オブジェクト内に含まれる<xref:System.Drawing.Graphics>オブジェクトの使用方法を<xref:System.Windows.Forms.PaintEventArgs>示します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="ecc02-124">または<xref:System.Windows.Forms.UserControl><xref:System.Windows.Forms.Button>などのグラフィカル表現を既に持っているクラスから継承していて、その表現をレンダリングに組み込まない場合は、基本クラスの<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドを呼び出すべきではありません。</span><span class="sxs-lookup"><span data-stu-id="ecc02-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="ecc02-125">コントロールの<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドのコードは、コントロールが最初に描画されたとき、および更新されるたびに実行されます。</span><span class="sxs-lookup"><span data-stu-id="ecc02-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="ecc02-126">コントロールのサイズを変更するたびにコントロールが再描画されるようにするには、コントロールのコンストラクターに次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="ecc02-127">プロパティを<xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>使用して、四角形以外のコントロールを実装します。</span><span class="sxs-lookup"><span data-stu-id="ecc02-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc02-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecc02-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="ecc02-129">方法 : 描画する Graphics オブジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="ecc02-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="ecc02-130">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="ecc02-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="ecc02-131">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="ecc02-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
