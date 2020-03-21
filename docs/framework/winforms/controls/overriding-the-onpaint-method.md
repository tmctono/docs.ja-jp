---
title: OnPaint メソッドのオーバーライド
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182042"
---
# <a name="overriding-the-onpaint-method"></a><span data-ttu-id="eab9b-102">OnPaint メソッドのオーバーライド</span><span class="sxs-lookup"><span data-stu-id="eab9b-102">Overriding the OnPaint Method</span></span>
<span data-ttu-id="eab9b-103">.NET Framework で定義されているイベントをオーバーライドするための基本的な手順は同じです。</span><span class="sxs-lookup"><span data-stu-id="eab9b-103">The basic steps for overriding any event defined in the .NET Framework are identical and are summarized in the following list.</span></span>  
  
#### <a name="to-override-an-inherited-event"></a><span data-ttu-id="eab9b-104">継承されたイベントをオーバーライドするには</span><span class="sxs-lookup"><span data-stu-id="eab9b-104">To override an inherited event</span></span>  
  
1. <span data-ttu-id="eab9b-105">保護された`On` *EventName*メソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="eab9b-105">Override the protected `On`*EventName* method.</span></span>  
  
2. <span data-ttu-id="eab9b-106">`On`オーバーライドされた`On` *EventName*メソッドから基本クラスの*EventName*メソッドを呼び出して、登録されたデリゲートがイベントを受け取るようにします。</span><span class="sxs-lookup"><span data-stu-id="eab9b-106">Call the `On`*EventName* method of the base class from the overridden `On`*EventName* method, so that registered delegates receive the event.</span></span>  
  
 <span data-ttu-id="eab9b-107">イベント<xref:System.Windows.Forms.Control.Paint>の詳細については、各 Windows フォーム コントロールが継承するイベント<xref:System.Windows.Forms.Control.Paint>をオーバーライドする必要があるためです<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="eab9b-107">The <xref:System.Windows.Forms.Control.Paint> event is discussed in detail here because every Windows Forms control must override the <xref:System.Windows.Forms.Control.Paint> event that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="eab9b-108">基本<xref:System.Windows.Forms.Control>クラスは、派生コントロールの描画方法を認識せず、メソッドに描画ロジックを<xref:System.Windows.Forms.Control.OnPaint%2A>提供しません。</span><span class="sxs-lookup"><span data-stu-id="eab9b-108">The base <xref:System.Windows.Forms.Control> class does not know how a derived control needs to be drawn and does not provide any painting logic in the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="eab9b-109">登録されたイベント レシーバーにイベント<xref:System.Windows.Forms.Control.Paint>をディスパッチするメソッド。 <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control></span><span class="sxs-lookup"><span data-stu-id="eab9b-109">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of <xref:System.Windows.Forms.Control> simply dispatches the <xref:System.Windows.Forms.Control.Paint> event to registered event receivers.</span></span>  
  
 <span data-ttu-id="eab9b-110">[「方法: 単純な Windows フォーム コントロールを開発する](how-to-develop-a-simple-windows-forms-control.md)」のサンプルを使用している場合は、メソッドを<xref:System.Windows.Forms.Control.OnPaint%2A>オーバーライドする例を見てきました。</span><span class="sxs-lookup"><span data-stu-id="eab9b-110">If you worked through the sample in [How to: Develop a Simple Windows Forms Control](how-to-develop-a-simple-windows-forms-control.md), you have seen an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="eab9b-111">次のコードは、そのサンプルから取得されます。</span><span class="sxs-lookup"><span data-stu-id="eab9b-111">The following code fragment is taken from that sample.</span></span>  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class
```  
  
```csharp  
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 <span data-ttu-id="eab9b-112">クラス<xref:System.Windows.Forms.PaintEventArgs>には、イベントのデータ<xref:System.Windows.Forms.Control.Paint>が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eab9b-112">The <xref:System.Windows.Forms.PaintEventArgs> class contains data for the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="eab9b-113">次のコードに示すように、2 つのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="eab9b-113">It has two properties, as shown in the following code.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <span data-ttu-id="eab9b-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>は描画される四角形で、<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>プロパティはオブジェクトを<xref:System.Drawing.Graphics>参照します。</span><span class="sxs-lookup"><span data-stu-id="eab9b-114"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is the rectangle to be painted, and the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property refers to a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="eab9b-115">名前空間内の<xref:System.Drawing?displayProperty=nameWithType>クラスは、GDI+ の新しい Windows グラフィックス ライブラリの機能へのアクセスを提供するマネージ クラスです。</span><span class="sxs-lookup"><span data-stu-id="eab9b-115">The classes in the <xref:System.Drawing?displayProperty=nameWithType> namespace are managed classes that provide access to the functionality of GDI+, the new Windows graphics library.</span></span> <span data-ttu-id="eab9b-116">オブジェクト<xref:System.Drawing.Graphics>には、点、文字列、線、円弧、楕円、およびその他の多くの図形を描画するメソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="eab9b-116">The <xref:System.Drawing.Graphics> object has methods to draw points, strings, lines, arcs, ellipses, and many other shapes.</span></span>  
  
 <span data-ttu-id="eab9b-117">コントロールは、そのビジュアル<xref:System.Windows.Forms.Control.OnPaint%2A>表示を変更する必要がある場合に、そのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="eab9b-117">A control invokes its <xref:System.Windows.Forms.Control.OnPaint%2A> method whenever it needs to change its visual display.</span></span> <span data-ttu-id="eab9b-118">このメソッドは、イベントを<xref:System.Windows.Forms.Control.Paint>発生させます。</span><span class="sxs-lookup"><span data-stu-id="eab9b-118">This method in turn raises the <xref:System.Windows.Forms.Control.Paint> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eab9b-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="eab9b-119">See also</span></span>

- [<span data-ttu-id="eab9b-120">Events</span><span class="sxs-lookup"><span data-stu-id="eab9b-120">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="eab9b-121">Windows フォーム コントロールのレンダリング</span><span class="sxs-lookup"><span data-stu-id="eab9b-121">Rendering a Windows Forms Control</span></span>](rendering-a-windows-forms-control.md)
- [<span data-ttu-id="eab9b-122">イベントの定義</span><span class="sxs-lookup"><span data-stu-id="eab9b-122">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
