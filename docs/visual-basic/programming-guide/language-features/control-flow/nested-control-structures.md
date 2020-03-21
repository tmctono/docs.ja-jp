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
ms.openlocfilehash: b696c79cd3cada4416b3f4b6cdf96f00b89a5a0a
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266925"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="e9d52-102">入れ子になった制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9d52-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="e9d52-103">制御ステートメントは、ループ内のブロックなど、他の`If...Then...Else`制御ステートメント内に`For...Next`配置できます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="e9d52-104">別の制御ステートメント内に置かれた制御ステートメントは *、 ネストされていると*言います。</span><span class="sxs-lookup"><span data-stu-id="e9d52-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="e9d52-105">ネストレベル</span><span class="sxs-lookup"><span data-stu-id="e9d52-105">Nesting Levels</span></span>  
 <span data-ttu-id="e9d52-106">Visual Basic のコントロール構造は、必要な数のレベルに入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="e9d52-107">ネストされた構造体を、それぞれの構造体の本文をインデントすることで、読みやすくするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="e9d52-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="e9d52-108">統合開発環境 (IDE) エディターは、自動的にこれを行います。</span><span class="sxs-lookup"><span data-stu-id="e9d52-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="e9d52-109">次の例では、行列の`sumRows`各行の正の要素を加算します。</span><span class="sxs-lookup"><span data-stu-id="e9d52-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="e9d52-110">前の例では、`Next`最初のステートメントが内部`For`ループを閉じ、最後`Next`のステートメントが外側`For`のループを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="e9d52-111">同様に、ネストされた`If`ステートメントでは、ステートメント`End If`は最も近い前`If`のステートメントに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="e9d52-112">入れ`Do`子になったループは、最も内側のステートメントと一`Loop`致するステートメントで、`Do`同様の方法で動作します。</span><span class="sxs-lookup"><span data-stu-id="e9d52-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9d52-113">多くの制御構造では、キーワードをクリックすると、その構造内のすべてのキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="e9d52-114">たとえば`If`、`If...Then...Else`建設中にクリックすると、建設中の`If`、 `Then`、、、`Else``End If``ElseIf`および のすべてのインスタンスが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="e9d52-115">次または前の強調表示されたキーワードに移動するには、Ctrl キーを押しながら Shift キーを押しながら下方向キーを押すか、Ctrl キーを押しながら Shift キーを押しながら上方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e9d52-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="e9d52-116">異なる種類の制御構造のネスト</span><span class="sxs-lookup"><span data-stu-id="e9d52-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="e9d52-117">ある種類の制御構造を別の種類の中に入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9d52-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="e9d52-118">次の例では、`With`ループ内の`For Each`ブロックとブロック内`If`のネストされた`With`ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="e9d52-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="e9d52-119">コントロール構造の重複</span><span class="sxs-lookup"><span data-stu-id="e9d52-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="e9d52-120">制御構造を重ねることはできません。</span><span class="sxs-lookup"><span data-stu-id="e9d52-120">You cannot overlap control structures.</span></span> <span data-ttu-id="e9d52-121">つまり、入れ子になった構造体は、次の最も内側の構造体内に完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9d52-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="e9d52-122">たとえば、内部`With`ブロックが終了する前にループ`For`が終了するため、次の配置は無効です。</span><span class="sxs-lookup"><span data-stu-id="e9d52-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![無効な入れ子の例を示す図。](./media/nested-control-structures/example-invalid-nesting.gif)
  
 <span data-ttu-id="e9d52-124">Visual Basic コンパイラは、このような重複する制御構造を検出し、コンパイル時エラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="e9d52-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d52-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e9d52-125">See also</span></span>

- [<span data-ttu-id="e9d52-126">制御フロー</span><span class="sxs-lookup"><span data-stu-id="e9d52-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="e9d52-127">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="e9d52-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="e9d52-128">ループ構造</span><span class="sxs-lookup"><span data-stu-id="e9d52-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="e9d52-129">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="e9d52-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
