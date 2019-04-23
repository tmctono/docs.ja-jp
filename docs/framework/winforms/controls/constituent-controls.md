---
title: 内在コントロール
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], constituent controls
- constituent controls [Windows Forms]
- user controls [Windows Forms], constituent controls
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
ms.openlocfilehash: 76a5a4f9b02a71616d247a1bb0f03cc0aec1d70d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224878"
---
# <a name="constituent-controls"></a><span data-ttu-id="57f37-102">内在コントロール</span><span class="sxs-lookup"><span data-stu-id="57f37-102">Constituent Controls</span></span>
<span data-ttu-id="57f37-103">ユーザー コントロールを構成するコントロール ("*内在コントロール*" と呼ばれます) は、カスタム グラフィックスのレンダリングに関してはそれほど柔軟ではありません。</span><span class="sxs-lookup"><span data-stu-id="57f37-103">The controls that make up a user control, or *constituent controls* as they are termed, are relatively inflexible when it comes to custom graphics rendering.</span></span> <span data-ttu-id="57f37-104">すべての Windows フォーム コントロールの処理が自分で独自のレンダリング<xref:System.Windows.Forms.Control.OnPaint%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="57f37-104">All Windows Forms controls handle their own rendering through their own <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="57f37-105">このメソッドは保護されているため、開発者はアクセスできず、したがってコントロールが描画されるときに実行を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="57f37-105">Because this method is protected, it is not accessible to the developer, and thus cannot be prevented from executing when the control is painted.</span></span> <span data-ttu-id="57f37-106">ただし、これは、内在コントロールの外観に影響を与えるコードを追加できないという意味ではありません。</span><span class="sxs-lookup"><span data-stu-id="57f37-106">This does not mean, however, that you cannot add code to affect the appearance of constituent controls.</span></span> <span data-ttu-id="57f37-107">イベント ハンドラーを追加することで、追加のレンダリングを実現できます。</span><span class="sxs-lookup"><span data-stu-id="57f37-107">Additional rendering can be accomplished by adding an event handler.</span></span> <span data-ttu-id="57f37-108">たとえば、作成された、<xref:System.Windows.Forms.UserControl>という名前のボタンで`MyButton`します。</span><span class="sxs-lookup"><span data-stu-id="57f37-108">For example, suppose you were authoring a <xref:System.Windows.Forms.UserControl> with a button named `MyButton`.</span></span> <span data-ttu-id="57f37-109">によって提供されたどのようなレンダリングを追加するさせたいかどうかは、<xref:System.Web.UI.WebControls.Button>コードを次のようなユーザー コントロールを追加するは。</span><span class="sxs-lookup"><span data-stu-id="57f37-109">If you wished to have additional rendering beyond what was provided by the <xref:System.Web.UI.WebControls.Button>, you would add code to your user control similar to the following:</span></span>  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="57f37-110">などの一部の Windows フォーム コントロール<xref:System.Windows.Forms.TextBox>、Windows によって直接描画されます。</span><span class="sxs-lookup"><span data-stu-id="57f37-110">Some Windows Forms controls, such as <xref:System.Windows.Forms.TextBox>, are painted directly by Windows.</span></span> <span data-ttu-id="57f37-111">これらのインスタンスで、<xref:System.Windows.Forms.Control.OnPaint%2A>メソッドが呼び出されないと、そのため、上記の例では呼び出されない。</span><span class="sxs-lookup"><span data-stu-id="57f37-111">In these instances, the <xref:System.Windows.Forms.Control.OnPaint%2A> method is never called, and thus the above example will never be called.</span></span>  
  
 <span data-ttu-id="57f37-112">この例は、`MyButton.Paint` イベントが実行されるたびに実行するメソッドを作成し、それによって追加のグラフィカル表示をコントロールに追加します。</span><span class="sxs-lookup"><span data-stu-id="57f37-112">This creates a method that executes every time the `MyButton.Paint` event executes, thereby adding additional graphical representation to your control.</span></span> <span data-ttu-id="57f37-113">これにより `MyButton.OnPaint` の実行は妨げられないので、カスタム描画に加えて、ボタンによって通常実行されるすべての描画が実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57f37-113">Note that this does not prevent the execution of `MyButton.OnPaint`, and thus all of the painting usually performed by a button will still be performed in addition to your custom painting.</span></span> <span data-ttu-id="57f37-114">GDI+ テクノロジとカスタム レンダリングについて詳しくは、「[Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md)」 (GDI+ でのグラフィカル イメージの作成) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57f37-114">For details about GDI+ technology and custom rendering, see the [Creating Graphical Images with GDI+](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="57f37-115">コントロールの表示を独自のものにしたい場合の最善の方法は、継承コントロールを作成し、カスタム レンダリング コードをそこに記述するというものです。</span><span class="sxs-lookup"><span data-stu-id="57f37-115">If you wish to have a unique representation of your control, your best course of action is to create an inherited control, and to write custom rendering code for it.</span></span> <span data-ttu-id="57f37-116">詳しくは、「[ユーザー描画コントロール](user-drawn-controls.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="57f37-116">For details, see [User-Drawn Controls](user-drawn-controls.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57f37-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="57f37-117">See also</span></span>

- <xref:System.Windows.Forms.UserControl>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="57f37-118">ユーザー描画コントロール</span><span class="sxs-lookup"><span data-stu-id="57f37-118">User-Drawn Controls</span></span>](user-drawn-controls.md)
- [<span data-ttu-id="57f37-119">方法: 描画の Graphics オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="57f37-119">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="57f37-120">さまざまなカスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="57f37-120">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
