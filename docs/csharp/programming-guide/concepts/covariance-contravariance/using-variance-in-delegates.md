---
title: デリゲートの変性の使用 (C#)
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 83e86e760edb17f6d9ae61864c154062d41416e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169767"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="b1214-102">デリゲートの変性の使用 (C#)</span><span class="sxs-lookup"><span data-stu-id="b1214-102">Using Variance in Delegates (C#)</span></span>
<span data-ttu-id="b1214-103">メソッドをデリゲートに割り当てると、"*共変性*" と "*反変性*" により、デリゲート型をメソッドのシグネチャに柔軟に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="b1214-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="b1214-104">共変性により、メソッドの戻り値の型の派生を、デリゲートに定義されている型よりも強くできます。</span><span class="sxs-lookup"><span data-stu-id="b1214-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="b1214-105">また、反変性により、メソッドのパラメーター型の派生をデリゲート型よりも弱くできます。</span><span class="sxs-lookup"><span data-stu-id="b1214-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="b1214-106">例 1: 共変性</span><span class="sxs-lookup"><span data-stu-id="b1214-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1214-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="b1214-107">Description</span></span>  
 <span data-ttu-id="b1214-108">この例は、デリゲート シグネチャ内の戻り値の型から派生した戻り値の型を持つメソッドで、デリゲートをどのように使用できるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="b1214-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="b1214-109">`DogsHandler` が返すデータ型は `Dogs` です。これは、デリゲートに定義された `Mammals` 型の派生型です。</span><span class="sxs-lookup"><span data-stu-id="b1214-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b1214-110">コード</span><span class="sxs-lookup"><span data-stu-id="b1214-110">Code</span></span>  
  
```csharp  
class Mammals {}  
class Dogs : Mammals {}  
  
class Program  
{  
    // Define the delegate.  
    public delegate Mammals HandlerMethod();  
  
    public static Mammals MammalsHandler()  
    {  
        return null;  
    }  
  
    public static Dogs DogsHandler()  
    {  
        return null;  
    }  
  
    static void Test()  
    {  
        HandlerMethod handlerMammals = MammalsHandler;  
  
        // Covariance enables this assignment.  
        HandlerMethod handlerDogs = DogsHandler;  
    }  
}  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="b1214-111">例 2: 反変性</span><span class="sxs-lookup"><span data-stu-id="b1214-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="b1214-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="b1214-112">Description</span></span>

<span data-ttu-id="b1214-113">この例は、型がデリゲート シグネチャ パラメーター型の基本データ型であるパラメーターを持つメソッドでデリゲートを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b1214-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="b1214-114">反変性により、複数のハンドラーの代わりに単一のイベント ハンドラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b1214-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="b1214-115">次の例では、2 つのデリゲートを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1214-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="b1214-116"><xref:System.Windows.Forms.KeyEventHandler>Button.KeyDown[ イベントのシグネチャを定義する ](xref:System.Windows.Forms.Control.KeyDown) デリゲート。</span><span class="sxs-lookup"><span data-stu-id="b1214-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="b1214-117">そのシグネチャ:</span><span class="sxs-lookup"><span data-stu-id="b1214-117">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="b1214-118"><xref:System.Windows.Forms.MouseEventHandler>Button.MouseClick[ イベントのシグネチャを定義する ](xref:System.Windows.Forms.Control.MouseDown) デリゲート。</span><span class="sxs-lookup"><span data-stu-id="b1214-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="b1214-119">そのシグネチャ:</span><span class="sxs-lookup"><span data-stu-id="b1214-119">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="b1214-120">この例では、イベント ハンドラーと <xref:System.EventArgs> パラメーターが定義され、そのパラメーターを使用し、`Button.KeyDown` と `Button.MouseClick` の両方のイベントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="b1214-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="b1214-121">これが可能になるのは、<xref:System.EventArgs> は <xref:System.Windows.Forms.KeyEventArgs> と <xref:System.Windows.Forms.MouseEventArgs> の両方の基本データ型であるためです。</span><span class="sxs-lookup"><span data-stu-id="b1214-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="b1214-122">コード</span><span class="sxs-lookup"><span data-stu-id="b1214-122">Code</span></span>  
  
```csharp  
// Event handler that accepts a parameter of the EventArgs type.  
private void MultiHandler(object sender, System.EventArgs e)  
{  
    label1.Text = System.DateTime.Now.ToString();  
}  
  
public Form1()  
{  
    InitializeComponent();  
  
    // You can use a method that has an EventArgs parameter,  
    // although the event expects the KeyEventArgs parameter.  
    this.button1.KeyDown += this.MultiHandler;  
  
    // You can use the same method
    // for an event that expects the MouseEventArgs parameter.  
    this.button1.MouseClick += this.MultiHandler;  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1214-123">参照</span><span class="sxs-lookup"><span data-stu-id="b1214-123">See also</span></span>

- [<span data-ttu-id="b1214-124">デリゲートの変性 (C#)</span><span class="sxs-lookup"><span data-stu-id="b1214-124">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="b1214-125">Func および Action 汎用デリゲートでの分散の使用 (C#)</span><span class="sxs-lookup"><span data-stu-id="b1214-125">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
