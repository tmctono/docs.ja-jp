---
title: 入れ子になった制御構造
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: 290366d9d9428cefee108ac472fbe7c0eb66d82e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "91084165"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="69042-102">入れ子になった制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="69042-102">Nested Control Structures (Visual Basic)</span></span>

<span data-ttu-id="69042-103">`For...Next` ループ内の `If...Then...Else` ブロックなど、制御ステートメントを他の制御ステートメントに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="69042-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="69042-104">別の制御ステートメントに配置された制御ステートメントは、"*入れ子にされた*" ステートメントと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="69042-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="69042-105">入れ子のレベル</span><span class="sxs-lookup"><span data-stu-id="69042-105">Nesting Levels</span></span>  

 <span data-ttu-id="69042-106">Visual Basic の制御構造は、必要な数のレベルで入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="69042-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="69042-107">一般的には、入れ子構造を読みやすくするには、各本体をインデントします。</span><span class="sxs-lookup"><span data-stu-id="69042-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="69042-108">統合開発環境 (IDE) エディターでは、これが自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="69042-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="69042-109">次の例では、プロシージャ `sumRows` は、マトリックスの各行の正の要素をすべて加算します。</span><span class="sxs-lookup"><span data-stu-id="69042-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
```vb
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 <span data-ttu-id="69042-110">前の例では、最初の `Next` ステートメントが内側の `For` ループを閉じ、最後の `Next` ステートメントが外側の `For` ループを閉じます。</span><span class="sxs-lookup"><span data-stu-id="69042-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="69042-111">同様に、入れ子にされた `If` ステートメントでは、`End If` ステートメントは、最も近い前の `If` ステートメントに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="69042-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="69042-112">入れ子にされた `Do` ループも同じように機能し、最も内側の `Loop` ステートメントと最も内側の `Do` ステートメントが一致します。</span><span class="sxs-lookup"><span data-stu-id="69042-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69042-113">多くの制御構造で、キーワードの 1 つをクリックすると、構造内のすべてのキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="69042-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="69042-114">たとえば、`If...Then...Else` コンストラクションで `If` をクリックすると、コンストラクション内の `If`、`Then`、`ElseIf`、`Else`、および `End If` のすべてのインスタンスが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="69042-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="69042-115">次または前の強調表示されたキーワードに移動するには、Ctrl + Shift + ↓キーを押すか、Ctrl + Shift + ↑キーを押します。</span><span class="sxs-lookup"><span data-stu-id="69042-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="69042-116">入れ子にされたさまざまな種類の制御構造</span><span class="sxs-lookup"><span data-stu-id="69042-116">Nesting Different Kinds of Control Structures</span></span>  

 <span data-ttu-id="69042-117">ある種類の制御構造を、別の種類の制御構造の中で入れ子にできます。</span><span class="sxs-lookup"><span data-stu-id="69042-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="69042-118">次の例は、`For Each` ループ内の `With` ブロックと、`With` ブロック内の入れ子にされた `If` ブロックを使用しています。</span><span class="sxs-lookup"><span data-stu-id="69042-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
```vb
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="69042-119">制御構造のオーバーラップ</span><span class="sxs-lookup"><span data-stu-id="69042-119">Overlapping Control Structures</span></span>  

 <span data-ttu-id="69042-120">制御構造をオーバーラップさせることはできません。</span><span class="sxs-lookup"><span data-stu-id="69042-120">You cannot overlap control structures.</span></span> <span data-ttu-id="69042-121">つまり、入れ子構造は、次の最も内側にある構造に完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="69042-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="69042-122">たとえば、次の配置は、内側の `With` ブロックが終了する前に `For` ループが終了するため無効です。</span><span class="sxs-lookup"><span data-stu-id="69042-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![無効な入れ子の例を示す図。](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="69042-124">Visual Basic コンパイラは、このような制御構造の重なりを検出し、コンパイル時にエラーが発生したことを通知します。</span><span class="sxs-lookup"><span data-stu-id="69042-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69042-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="69042-125">See also</span></span>

- [<span data-ttu-id="69042-126">制御フロー</span><span class="sxs-lookup"><span data-stu-id="69042-126">Control Flow</span></span>](index.md)
- [<span data-ttu-id="69042-127">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="69042-127">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="69042-128">ループ構造</span><span class="sxs-lookup"><span data-stu-id="69042-128">Loop Structures</span></span>](loop-structures.md)
- [<span data-ttu-id="69042-129">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="69042-129">Other Control Structures</span></span>](other-control-structures.md)
