---
title: Null 条件演算子 (Visual Basic)
ms.date: 10/19/2018
helpviewer_keywords:
- null-conditional operators [Visual Basic]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.openlocfilehash: b83435b8448b53eca63aac0519e9eed2f7dfa9f3
ms.sourcegitcommit: 344d82456f27d09a210671214a14cfd7daf1f97c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2019
ms.locfileid: "58348766"
---
# <a name="-and--null-conditional-operators-visual-basic"></a><span data-ttu-id="308fe-102">?.</span><span class="sxs-lookup"><span data-stu-id="308fe-102">?.</span></span> <span data-ttu-id="308fe-103">そして。() null 条件演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="308fe-103">and ?() null-conditional operators (Visual Basic)</span></span>

<span data-ttu-id="308fe-104">Null の左側のオペランドの値をテスト (`Nothing`) メンバー アクセスを実行する前に (`?.`) またはインデックス (`?()`); の操作を返します。`Nothing`に左側のオペランドが評価された場合`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="308fe-104">Tests the value of the left-hand operand for null (`Nothing`) before performing a member access (`?.`) or index (`?()`) operation; returns `Nothing` if the left-hand operand evaluates to `Nothing`.</span></span> <span data-ttu-id="308fe-105">通常の値の型を返す式、null 条件演算子が返されます、<xref:System.Nullable%601>します。</span><span class="sxs-lookup"><span data-stu-id="308fe-105">Note that in expressions that ordinarily return value types, the null-conditional operator returns a <xref:System.Nullable%601>.</span></span>

<span data-ttu-id="308fe-106">これらの演算子を使用して、データ構造を下って場合は特に、null のチェックを処理するには、少ないコードを記述するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="308fe-106">These operators help you write less code to handle null checks, especially when descending into data structures.</span></span> <span data-ttu-id="308fe-107">例:</span><span class="sxs-lookup"><span data-stu-id="308fe-107">For example:</span></span>

```vb
' Nothing if customers is Nothing  
Dim length As Integer? = customers?.Length  

' Nothing if customers is Nothing
Dim first As Customer = customers?(0)

' Nothing if customers, the first customer, or Orders is Nothing
Dim count As Integer? = customers?(0)?.Orders?.Count()   
```

<span data-ttu-id="308fe-108">比較については、null 条件演算子を使用せず、これらの式の最初の代替のコードは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="308fe-108">For comparison, the alternative code for the first of these expressions without a null-conditional operator is:</span></span>

```vb
Dim length As Integer
If customers IsNot Nothing Then
   length = customers.Length
End If
```

<span data-ttu-id="308fe-109">Null 条件演算子はショートサーキットです。</span><span class="sxs-lookup"><span data-stu-id="308fe-109">The null-conditional operators are short-circuiting.</span></span>  <span data-ttu-id="308fe-110">条件付きメンバー アクセスおよびインデックス操作のチェーン内の 1 つの操作を返す場合`Nothing`残りのチェーンの実行が停止します。</span><span class="sxs-lookup"><span data-stu-id="308fe-110">If one operation in a chain of conditional member access and index operations returns `Nothing`, the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="308fe-111">次の例では、`C(E)`場合は評価されません`A`、 `B`、または`C`に評価される`Nothing`します。</span><span class="sxs-lookup"><span data-stu-id="308fe-111">In the following example, `C(E)` isn't evaluated if `A`, `B`, or `C` evaluates to `Nothing`.</span></span>

```vb
A?.B?.C?(E);
```

<span data-ttu-id="308fe-112">Null 条件メンバー アクセスの別の用途では、はるかに少ないコードでスレッド セーフな方法でデリゲートを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="308fe-112">Another use for null-conditional member access is to invoke delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="308fe-113">次の例は、2 つの型を定義、`NewsBroadcaster`と`NewsReceiver`します。</span><span class="sxs-lookup"><span data-stu-id="308fe-113">The following example defines two types, a `NewsBroadcaster` and a `NewsReceiver`.</span></span> <span data-ttu-id="308fe-114">ニュース項目によって、受信側に送信されます、`NewsBroadcaster.SendNews`を委任します。</span><span class="sxs-lookup"><span data-stu-id="308fe-114">News items are sent to the receiver by the `NewsBroadcaster.SendNews` delegate.</span></span>

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

<span data-ttu-id="308fe-115">内の要素がない場合、`SendNews`呼び出しリスト、`SendNews`デリゲートがスローされます、<xref:System.NullReferenceException>します。</span><span class="sxs-lookup"><span data-stu-id="308fe-115">If there are no elements in the `SendNews` invocation list, the `SendNews` delegate throws a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="308fe-116">Null 条件演算子では、前にコードのデリゲートの呼び出しリストがありませんが、次のことを確認するよう`Nothing`:</span><span class="sxs-lookup"><span data-stu-id="308fe-116">Before null conditional operators, code like the following ensured that the delegate invocation list was not `Nothing`:</span></span>

```vb  
SendNews = SendNews.Combine({SendNews, client})  
If SendNews IsNot Nothing Then 
   SendNews("Just in...")
End If
```

<span data-ttu-id="308fe-117">新しい方法は格段に単純です。</span><span class="sxs-lookup"><span data-stu-id="308fe-117">The new way is much simpler:</span></span>  

```vb
SendNews = SendNews.Combine({SendNews, client})  
SendNews?.Invoke("Just in...")
```

<span data-ttu-id="308fe-118">コンパイラが `SendNews` を評価するためのコードを一度しか生成せず、一時変数に結果が保持されるため、新しい方法はスレッド セーフです。</span><span class="sxs-lookup"><span data-stu-id="308fe-118">The new way is thread-safe because the compiler generates code to evaluate `SendNews` one time only, keeping the result in a temporary variable.</span></span> <span data-ttu-id="308fe-119">null 条件デリゲート呼び出し構文 `SendNews?(String)` がないため、`Invoke` メソッドを明示的に呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="308fe-119">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `SendNews?(String)`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="308fe-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="308fe-120">See also</span></span>

- [<span data-ttu-id="308fe-121">演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="308fe-121">Operators (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="308fe-122">Visual Basic プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="308fe-122">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="308fe-123">Visual Basic の言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="308fe-123">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)
