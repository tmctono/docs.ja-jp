---
title: 入れ子になった制御構造 (Visual Basic)
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
ms.openlocfilehash: c016722332dafa3d3be91a1e9e98cc0ce9a49717
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907994"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="03efe-102">入れ子になった制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03efe-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="03efe-103">たとえば他のコントロール ステートメント内のコントロール ステートメントを配置することができます、`If...Then...Else`ブロック内で、`For...Next`ループします。</span><span class="sxs-lookup"><span data-stu-id="03efe-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="03efe-104">別のコントロール ステートメントの内側に配置する制御ステートメントはモード*入れ子になった*します。</span><span class="sxs-lookup"><span data-stu-id="03efe-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="03efe-105">入れ子のレベル</span><span class="sxs-lookup"><span data-stu-id="03efe-105">Nesting Levels</span></span>  
 <span data-ttu-id="03efe-106">Visual Basic での制御構造は、複数のレベルにネストできます。</span><span class="sxs-lookup"><span data-stu-id="03efe-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="03efe-107">一般的に、それぞれのインデントして入れ子になった構造体を読みやすくすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="03efe-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="03efe-108">統合開発環境 (IDE) のエディターを使用して、この自動的に行います。</span><span class="sxs-lookup"><span data-stu-id="03efe-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="03efe-109">次の例では、プロシージャ`sumRows`マトリックスの行ごとの正の要素をまとめて追加します。</span><span class="sxs-lookup"><span data-stu-id="03efe-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="03efe-110">前の例では、最初の`Next`ステートメント終了内部`For`ループし、最後`Next`外側のステートメントを閉じます`For`ループします。</span><span class="sxs-lookup"><span data-stu-id="03efe-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="03efe-111">同様に、入れ子になった`If`、ステートメント、`End If`ステートメントが自動的に適用する前に、最も近い`If`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="03efe-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="03efe-112">入れ子になった`Do`で同様に、最も内側のループが`Loop`ステートメントの内側に一致する`Do`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="03efe-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="03efe-113">多くの制御構造のキーワードをクリックすると、すべての構造のキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="03efe-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="03efe-114">クリックすると、`If`で、`If...Then...Else`構築のすべてのインスタンス`If`、 `Then`、 `ElseIf`、 `Else`、および`End If`構築では強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="03efe-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="03efe-115">次または前の強調表示されているキーワードに移動するには、CTRL と shift キーを押しながら下方向キーまたは CTRL + SHIFT キーを押しながら上方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="03efe-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="03efe-116">さまざまな種類の制御構造の入れ子</span><span class="sxs-lookup"><span data-stu-id="03efe-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="03efe-117">別の種類内のコントロール構造体の 1 つの種類を入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="03efe-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="03efe-118">次の例では、`With`ブロック内で、`For Each`ループを入れ子になった`If`ブロック内で、`With`ブロックします。</span><span class="sxs-lookup"><span data-stu-id="03efe-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="03efe-119">重複する制御構造</span><span class="sxs-lookup"><span data-stu-id="03efe-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="03efe-120">制御構造を重ねることはできません。</span><span class="sxs-lookup"><span data-stu-id="03efe-120">You cannot overlap control structures.</span></span> <span data-ttu-id="03efe-121">つまり、入れ子になった構造を完全に次の最も内側の構造内で含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="03efe-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="03efe-122">たとえば、次の配置が無効ですので、`For`内部の前にループが終了した`With`ブロックを終了します。</span><span class="sxs-lookup"><span data-stu-id="03efe-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![無効な入れ子の例を示す図。](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="03efe-124">Visual Basic コンパイラでは、このような重複する制御構造を検出し、コンパイル時エラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="03efe-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03efe-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="03efe-125">See also</span></span>

- [<span data-ttu-id="03efe-126">制御フロー</span><span class="sxs-lookup"><span data-stu-id="03efe-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="03efe-127">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="03efe-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="03efe-128">ループ構造</span><span class="sxs-lookup"><span data-stu-id="03efe-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="03efe-129">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="03efe-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
