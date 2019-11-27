---
title: Null 条件演算子
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: 003f579a7128bbe2462b7fbe7057de03e61bfbe6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348289"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="1c252-102">?.</span><span class="sxs-lookup"><span data-stu-id="1c252-102">?.</span></span> <span data-ttu-id="1c252-103">そして。() null 条件演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c252-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="1c252-104">メンバーアクセス (`?.`) 操作またはインデックス (`?()`) 操作を実行する前に、左側のオペランドの値を null (`Nothing`) に対してテストします。左側のオペランドが `Nothing`に評価された場合に `Nothing` を返します。</span><span class="sxs-lookup"><span data-stu-id="1c252-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="1c252-105">通常、値型を返す式では、null 条件演算子は <xref:System.Nullable%601>を返します。</span><span class="sxs-lookup"><span data-stu-id="1c252-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="1c252-106">これらの演算子を使用すると、特にデータ構造への降順で、null チェックを処理するコードを記述しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1c252-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="1c252-107">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1c252-107">For example:</span></span>

```vb
' Nothing if customers is Nothing
Dim length As Integer? = customers?.Length

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()
```

<span data-ttu-id="1c252-108">比較のために、null 条件演算子を使用しない最初の式の代替コードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1c252-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="1c252-109">場合によっては、オブジェクトのブール型の値に基づいて、null である可能性のあるオブジェクトに対してアクションを実行する必要があります (次の例で `IsAllowedFreeShipping` ブール型プロパティと同様)。</span><span class="sxs-lookup"><span data-stu-id="1c252-109">Sometimes you need to take an action on an object that may be null, based on the value of a Boolean member on that object (like the Boolean property `IsAllowedFreeShipping` in the following example):</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer IsNot Nothing AndAlso customer.IsAllowedFreeShipping Then
  ApplyFreeShippingToOrders(customer)
End If
```

<span data-ttu-id="1c252-110">次のように、null 条件演算子を使用すると、コードを短くして、null を手動でチェックすることを回避できます。</span><span class="sxs-lookup"><span data-stu-id="1c252-110">You can shorten your code and avoid manually checking for null by using the null-conditional operator as follows:</span></span>

```vb
Dim customer = FindCustomerByID(123) 'customer will be Nothing if not found.

If customer?.IsAllowedFreeShipping Then ApplyFreeShippingToOrders(customer)
```

<span data-ttu-id="1c252-111">Null 条件演算子はショートサーキットです。</span><span class="sxs-lookup"><span data-stu-id="1c252-111">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="1c252-112">条件付きメンバーアクセスとインデックス操作のチェーンの1つの操作が `Nothing`を返す場合、チェーンの残りの実行は停止します。</span><span class="sxs-lookup"><span data-stu-id="1c252-112">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="1c252-113">次の例では、`A`、`B`、または `C` が `Nothing`に評価される場合、`C(E)` は評価されません。</span><span class="sxs-lookup"><span data-stu-id="1c252-113">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E)
```

<span data-ttu-id="1c252-114">Null 条件メンバーアクセスのもう1つの用途は、はるかに少ないコードでスレッドセーフな方法でデリゲートを呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="1c252-114">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="1c252-115">次の例では、`NewsBroadcaster` と `NewsReceiver`の2つの型を定義しています。</span><span class="sxs-lookup"><span data-stu-id="1c252-115">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="1c252-116">ニュース項目は `NewsBroadcaster.SendNews` デリゲートによって受信者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1c252-116">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

```vb
Public Module NewsBroadcaster
   Dim SendNews As Action(Of String)

   Public Sub Main()
      Dim rec As New NewsReceiver()
      Dim rec2 As New NewsReceiver()
      SendNews?.Invoke("Just in: A newsworthy item...")
   End Sub

   Public Sub Register(client As Action(Of String))
      SendNews = SendNews.Combine({SendNews, client})
   End Sub
End Module

Public Class NewsReceiver
   Public Sub New()
      NewsBroadcaster.Register(AddressOf Me.DisplayNews)
   End Sub

   Public Sub DisplayNews(newsItem As String)
      Console.WriteLine(newsItem)
   End Sub
End Class
```

<span data-ttu-id="1c252-117">`SendNews` の呼び出しリストに要素がない場合、`SendNews` デリゲートは <xref:System.NullReferenceException>をスローします。</span><span class="sxs-lookup"><span data-stu-id="1c252-117">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="1c252-118">Null 条件演算子の前に、次のようなコードは、デリゲート呼び出しリストが `Nothing`されていないことを保証しています。</span><span class="sxs-lookup"><span data-stu-id="1c252-118">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
If SendNews IsNot Nothing Then
   SendNews("Just in...")
End If
```

<span data-ttu-id="1c252-119">新しい方法は格段に単純です。</span><span class="sxs-lookup"><span data-stu-id="1c252-119">The new way is much simpler:</span></span>

```vb
SendNews = SendNews.Combine({SendNews, client})
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="1c252-120">コンパイラが `SendNews` を評価するためのコードを一度しか生成せず、一時変数に結果が保持されるため、新しい方法はスレッド セーフです。</span><span class="sxs-lookup"><span data-stu-id="1c252-120">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="1c252-121">null 条件デリゲート呼び出し構文 `Invoke` がないため、`SendNews?(String)` メソッドを明示的に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c252-121">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c252-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c252-122">See also</span></span>

- [<span data-ttu-id="1c252-123">演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c252-123">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="1c252-124">Visual Basic のプログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1c252-124">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="1c252-125">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="1c252-125">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
