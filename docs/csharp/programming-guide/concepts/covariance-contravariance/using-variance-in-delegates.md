---
title: デリゲートの変性の使用 (C#)
description: 含まれている共変性と反変性のコード例を使用してデリゲートの変性を使用する方法について説明します。
ms.date: 07/20/2015
ms.assetid: 1638c95d-dc8b-40c1-972c-c2dcf84be55e
ms.openlocfilehash: 6704c3bf09dd854335f1e2719ccc8462cb7cde26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176319"
---
# <a name="using-variance-in-delegates-c"></a><span data-ttu-id="a1937-103">デリゲートの変性の使用 (C#)</span><span class="sxs-lookup"><span data-stu-id="a1937-103">Using Variance in Delegates (C#)</span></span>

<span data-ttu-id="a1937-104">メソッドをデリゲートに割り当てると、"*共変性*" と "*反変性*" により、デリゲート型をメソッドのシグネチャに柔軟に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="a1937-104">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="a1937-105">共変性により、メソッドの戻り値の型の派生を、デリゲートに定義されている型よりも強くできます。</span><span class="sxs-lookup"><span data-stu-id="a1937-105">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="a1937-106">また、反変性により、メソッドのパラメーター型の派生をデリゲート型よりも弱くできます。</span><span class="sxs-lookup"><span data-stu-id="a1937-106">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="a1937-107">例 1:共変性</span><span class="sxs-lookup"><span data-stu-id="a1937-107">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="a1937-108">説明</span><span class="sxs-lookup"><span data-stu-id="a1937-108">Description</span></span>  

 <span data-ttu-id="a1937-109">この例は、デリゲート シグネチャ内の戻り値の型から派生した戻り値の型を持つメソッドで、デリゲートをどのように使用できるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="a1937-109">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="a1937-110">`DogsHandler` が返すデータ型は `Dogs` です。これは、デリゲートに定義された `Mammals` 型の派生型です。</span><span class="sxs-lookup"><span data-stu-id="a1937-110">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a1937-111">コード</span><span class="sxs-lookup"><span data-stu-id="a1937-111">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="a1937-112">例 2:反変性</span><span class="sxs-lookup"><span data-stu-id="a1937-112">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="a1937-113">説明</span><span class="sxs-lookup"><span data-stu-id="a1937-113">Description</span></span>

<span data-ttu-id="a1937-114">この例は、型がデリゲート シグネチャ パラメーター型の基本データ型であるパラメーターを持つメソッドでデリゲートを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a1937-114">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="a1937-115">反変性により、複数のハンドラーの代わりに単一のイベント ハンドラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1937-115">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="a1937-116">次の例では、2 つのデリゲートを使用します。</span><span class="sxs-lookup"><span data-stu-id="a1937-116">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="a1937-117">[Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) イベントのシグネチャを定義する <xref:System.Windows.Forms.KeyEventHandler> デリゲート。</span><span class="sxs-lookup"><span data-stu-id="a1937-117">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="a1937-118">そのシグネチャ:</span><span class="sxs-lookup"><span data-stu-id="a1937-118">Its signature is:</span></span>

   ```csharp
   public delegate void KeyEventHandler(object sender, KeyEventArgs e)
   ```

- <span data-ttu-id="a1937-119">[Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) イベントのシグネチャを定義する <xref:System.Windows.Forms.MouseEventHandler> デリゲート。</span><span class="sxs-lookup"><span data-stu-id="a1937-119">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="a1937-120">そのシグネチャ:</span><span class="sxs-lookup"><span data-stu-id="a1937-120">Its signature is:</span></span>

   ```csharp
   public delegate void MouseEventHandler(object sender, MouseEventArgs e)
   ```

<span data-ttu-id="a1937-121">この例では、イベント ハンドラーと <xref:System.EventArgs> パラメーターが定義され、そのパラメーターを使用し、`Button.KeyDown` と `Button.MouseClick` の両方のイベントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="a1937-121">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="a1937-122">これが可能になるのは、<xref:System.EventArgs> は <xref:System.Windows.Forms.KeyEventArgs> と <xref:System.Windows.Forms.MouseEventArgs> の両方の基本データ型であるためです。</span><span class="sxs-lookup"><span data-stu-id="a1937-122">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>
  
### <a name="code"></a><span data-ttu-id="a1937-123">コード</span><span class="sxs-lookup"><span data-stu-id="a1937-123">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a1937-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1937-124">See also</span></span>

- [<span data-ttu-id="a1937-125">デリゲートの変性 (C#)</span><span class="sxs-lookup"><span data-stu-id="a1937-125">Variance in Delegates (C#)</span></span>](./variance-in-delegates.md)
- [<span data-ttu-id="a1937-126">Func および Action 汎用デリゲートでの変性の使用 (C#)</span><span class="sxs-lookup"><span data-stu-id="a1937-126">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
