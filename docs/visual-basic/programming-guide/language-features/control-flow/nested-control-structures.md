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
ms.openlocfilehash: 5818b13661fb4415c6f531b741b8a963a80bd2b8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348151"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="16078-102">入れ子になった制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16078-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="16078-103">制御ステートメントは、`For...Next` ループ内の `If...Then...Else` ブロックなど、他のコントロールステートメント内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="16078-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="16078-104">別の control ステートメント内に配置された control ステートメントは、*入れ子になっ*ていると言います。</span><span class="sxs-lookup"><span data-stu-id="16078-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="16078-105">入れ子のレベル</span><span class="sxs-lookup"><span data-stu-id="16078-105">Nesting Levels</span></span>  
 <span data-ttu-id="16078-106">Visual Basic の制御構造は、必要な数のレベルに入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="16078-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="16078-107">入れ子構造体を読みやすくするには、それぞれの本文をインデントするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="16078-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="16078-108">これは、統合開発環境 (IDE) エディターによって自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="16078-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="16078-109">次の例では、プロシージャ `sumRows`、マトリックスの各行の正の要素を加算します。</span><span class="sxs-lookup"><span data-stu-id="16078-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="16078-110">前の例では、最初の `Next` ステートメントは内側の `For` ループを閉じ、最後の `Next` ステートメントは外側の `For` ループを閉じます。</span><span class="sxs-lookup"><span data-stu-id="16078-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="16078-111">同様に、入れ子になった `If` ステートメントでは、`End If` ステートメントが最も近い直前の `If` ステートメントに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="16078-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="16078-112">入れ子になった `Do` ループは同様の方法で動作し、最も内側の `Loop` ステートメントは最も内側の `Do` ステートメントと一致します。</span><span class="sxs-lookup"><span data-stu-id="16078-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16078-113">多くの制御構造では、キーワードをクリックすると、構造内のすべてのキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="16078-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="16078-114">たとえば、`If...Then...Else` の構築で [`If`] をクリックすると、構築内の `If`、`Then`、`ElseIf`、`Else`、および `End If` のすべてのインスタンスが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="16078-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="16078-115">次または前の強調表示されたキーワードに移動するには、CTRL + SHIFT + ↓キーを押すか、CTRL + SHIFT + 上方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="16078-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="16078-116">さまざまな種類の制御構造の入れ子</span><span class="sxs-lookup"><span data-stu-id="16078-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="16078-117">1つの種類のコントロール構造を別の種類に入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="16078-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="16078-118">次の例では、`With` ブロック内で `For Each` ループと入れ子になった `If` ブロック内の `With` ブロックを使用します。</span><span class="sxs-lookup"><span data-stu-id="16078-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="16078-119">重複する制御構造</span><span class="sxs-lookup"><span data-stu-id="16078-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="16078-120">制御構造を重ねることはできません。</span><span class="sxs-lookup"><span data-stu-id="16078-120">You cannot overlap control structures.</span></span> <span data-ttu-id="16078-121">つまり、入れ子構造は、次の最も内側の構造体内に完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="16078-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="16078-122">たとえば、次の配置は、内部 `With` ブロックが終了する前に `For` ループが終了するため無効です。</span><span class="sxs-lookup"><span data-stu-id="16078-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![無効な入れ子の例を示す図。](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="16078-124">Visual Basic コンパイラは、このような重複する制御構造を検出し、コンパイル時エラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="16078-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16078-125">参照</span><span class="sxs-lookup"><span data-stu-id="16078-125">See also</span></span>

- [<span data-ttu-id="16078-126">制御フロー</span><span class="sxs-lookup"><span data-stu-id="16078-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="16078-127">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="16078-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="16078-128">ループ構造</span><span class="sxs-lookup"><span data-stu-id="16078-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="16078-129">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="16078-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
