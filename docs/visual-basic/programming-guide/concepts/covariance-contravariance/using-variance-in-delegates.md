---
title: デリゲートの分散の使用
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: 842392a1342f7d3689d4d1f2a2adb7470eeda05e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375785"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="b7582-102">デリゲートの変性の使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7582-102">Using Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="b7582-103">メソッドをデリゲートに割り当てると、"*共変性*" と "*反変性*" により、デリゲート型をメソッドのシグネチャに柔軟に一致させることができます。</span><span class="sxs-lookup"><span data-stu-id="b7582-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="b7582-104">共変性により、メソッドの戻り値の型の派生を、デリゲートに定義されている型よりも強くできます。</span><span class="sxs-lookup"><span data-stu-id="b7582-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="b7582-105">また、反変性により、メソッドのパラメーター型の派生をデリゲート型よりも弱くできます。</span><span class="sxs-lookup"><span data-stu-id="b7582-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>

## <a name="example-1-covariance"></a><span data-ttu-id="b7582-106">例 1: 共変性</span><span class="sxs-lookup"><span data-stu-id="b7582-106">Example 1: Covariance</span></span>

### <a name="description"></a><span data-ttu-id="b7582-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="b7582-107">Description</span></span>

<span data-ttu-id="b7582-108">この例は、デリゲート シグネチャ内の戻り値の型から派生した戻り値の型を持つメソッドで、デリゲートをどのように使用できるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="b7582-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="b7582-109">`DogsHandler` が返すデータ型は `Dogs` です。これは、デリゲートに定義された `Mammals` 型の派生型です。</span><span class="sxs-lookup"><span data-stu-id="b7582-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>

### <a name="code"></a><span data-ttu-id="b7582-110">コード</span><span class="sxs-lookup"><span data-stu-id="b7582-110">Code</span></span>

```vb
Class Mammals
End Class

Class Dogs
    Inherits Mammals
End Class
Class Test
    Public Delegate Function HandlerMethod() As Mammals
    Public Shared Function MammalsHandler() As Mammals
        Return Nothing
    End Function
    Public Shared Function DogsHandler() As Dogs
        Return Nothing
    End Function
    Sub Test()
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler
        ' Covariance enables this assignment.
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler
    End Sub
End Class
```

## <a name="example-2-contravariance"></a><span data-ttu-id="b7582-111">例 2: 反変性</span><span class="sxs-lookup"><span data-stu-id="b7582-111">Example 2: Contravariance</span></span>

### <a name="description"></a><span data-ttu-id="b7582-112">[説明]</span><span class="sxs-lookup"><span data-stu-id="b7582-112">Description</span></span>

<span data-ttu-id="b7582-113">この例は、型がデリゲート シグネチャ パラメーター型の基本データ型であるパラメーターを持つメソッドでデリゲートを使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b7582-113">This example demonstrates how delegates can be used with methods that have parameters whose types are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="b7582-114">反変性により、複数のハンドラーの代わりに単一のイベント ハンドラーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b7582-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="b7582-115">次の例では、2 つのデリゲートを使用します。</span><span class="sxs-lookup"><span data-stu-id="b7582-115">The following example makes use of two delegates:</span></span>

- <span data-ttu-id="b7582-116">[Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) イベントのシグネチャを定義する <xref:System.Windows.Forms.KeyEventHandler> デリゲート。</span><span class="sxs-lookup"><span data-stu-id="b7582-116">A <xref:System.Windows.Forms.KeyEventHandler> delegate that defines the signature of the [Button.KeyDown](xref:System.Windows.Forms.Control.KeyDown) event.</span></span> <span data-ttu-id="b7582-117">そのシグネチャ:</span><span class="sxs-lookup"><span data-stu-id="b7582-117">Its signature is:</span></span>

   ```vb
   Public Delegate Sub KeyEventHandler(sender As Object, e As KeyEventArgs)
   ```

- <span data-ttu-id="b7582-118">[Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) イベントのシグネチャを定義する <xref:System.Windows.Forms.MouseEventHandler> デリゲート。</span><span class="sxs-lookup"><span data-stu-id="b7582-118">A <xref:System.Windows.Forms.MouseEventHandler> delegate that defines the signature of the [Button.MouseClick](xref:System.Windows.Forms.Control.MouseDown) event.</span></span> <span data-ttu-id="b7582-119">そのシグネチャ:</span><span class="sxs-lookup"><span data-stu-id="b7582-119">Its signature is:</span></span>

   ```vb
   Public Delegate Sub MouseEventHandler(sender As Object, e As MouseEventArgs)
   ```

<span data-ttu-id="b7582-120">この例では、イベント ハンドラーと <xref:System.EventArgs> パラメーターが定義され、そのパラメーターを使用し、`Button.KeyDown` と `Button.MouseClick` の両方のイベントが処理されます。</span><span class="sxs-lookup"><span data-stu-id="b7582-120">The example defines an event handler with an <xref:System.EventArgs> parameter and uses it to handle both the `Button.KeyDown` and `Button.MouseClick` events.</span></span> <span data-ttu-id="b7582-121">これが可能になるのは、<xref:System.EventArgs> は <xref:System.Windows.Forms.KeyEventArgs> と <xref:System.Windows.Forms.MouseEventArgs> の両方の基本データ型であるためです。</span><span class="sxs-lookup"><span data-stu-id="b7582-121">It can do this because <xref:System.EventArgs> is a base type of both <xref:System.Windows.Forms.KeyEventArgs>  and <xref:System.Windows.Forms.MouseEventArgs>.</span></span>

### <a name="code"></a><span data-ttu-id="b7582-122">コード</span><span class="sxs-lookup"><span data-stu-id="b7582-122">Code</span></span>

```vb
' Event handler that accepts a parameter of the EventArgs type.
Private Sub MultiHandler(ByVal sender As Object,
                         ByVal e As System.EventArgs)
    Label1.Text = DateTime.Now
End Sub

Private Sub Form1_Load(ByVal sender As System.Object,
    ByVal e As System.EventArgs) Handles MyBase.Load

    ' You can use a method that has an EventArgs parameter,
    ' although the event expects the KeyEventArgs parameter.
    AddHandler Button1.KeyDown, AddressOf MultiHandler

    ' You can use the same method
    ' for the event that expects the MouseEventArgs parameter.
    AddHandler Button1.MouseClick, AddressOf MultiHandler
End Sub
```

## <a name="see-also"></a><span data-ttu-id="b7582-123">参照</span><span class="sxs-lookup"><span data-stu-id="b7582-123">See also</span></span>

- [<span data-ttu-id="b7582-124">デリゲートの変性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7582-124">Variance in Delegates (Visual Basic)</span></span>](variance-in-delegates.md)
- [<span data-ttu-id="b7582-125">Func および Action 汎用デリゲートでの分散の使用 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7582-125">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](using-variance-for-func-and-action-generic-delegates.md)
