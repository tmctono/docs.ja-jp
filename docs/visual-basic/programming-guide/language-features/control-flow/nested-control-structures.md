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
ms.openlocfilehash: f559bf603605873f1b9155e9a96cb367e5420343
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941686"
---
# <a name="nested-control-structures-visual-basic"></a><span data-ttu-id="a9df1-102">入れ子になった制御構造 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9df1-102">Nested Control Structures (Visual Basic)</span></span>
<span data-ttu-id="a9df1-103">制御ステートメントは、 `If...Then...Else` `For...Next`ループ内のブロックなど、他のコントロールステートメント内に配置できます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-103">You can place control statements inside other control statements, for example an `If...Then...Else` block within a `For...Next` loop.</span></span> <span data-ttu-id="a9df1-104">別の control ステートメント内に配置された control ステートメントは、*入れ子になっ*ていると言います。</span><span class="sxs-lookup"><span data-stu-id="a9df1-104">A control statement placed inside another control statement is said to be *nested*.</span></span>  
  
## <a name="nesting-levels"></a><span data-ttu-id="a9df1-105">入れ子のレベル</span><span class="sxs-lookup"><span data-stu-id="a9df1-105">Nesting Levels</span></span>  
 <span data-ttu-id="a9df1-106">Visual Basic の制御構造は、必要な数のレベルに入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-106">Control structures in Visual Basic can be nested to as many levels as you want.</span></span> <span data-ttu-id="a9df1-107">入れ子構造体を読みやすくするには、それぞれの本文をインデントするのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="a9df1-107">It is common practice to make nested structures more readable by indenting the body of each one.</span></span> <span data-ttu-id="a9df1-108">これは、統合開発環境 (IDE) エディターによって自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-108">The integrated development environment (IDE) editor automatically does this.</span></span>  
  
 <span data-ttu-id="a9df1-109">次の例では、プロシージャ`sumRows`によって、マトリックスの各行の正の要素が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-109">In the following example, the procedure `sumRows` adds together the positive elements of each row of the matrix.</span></span>  
  
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
  
 <span data-ttu-id="a9df1-110">前の例では、最初`Next`のステートメントは内側`For`のループを閉じ`Next` 、最後のステートメント`For`は外側のループを閉じます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-110">In the preceding example, the first `Next` statement closes the inner `For` loop and the last `Next` statement closes the outer `For` loop.</span></span>  
  
 <span data-ttu-id="a9df1-111">同様に、入れ子`If`になった`End If`ステートメントでは、ステートメントは最も`If`近い先行するステートメントに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-111">Likewise, in nested `If` statements, the `End If` statements automatically apply to the nearest prior `If` statement.</span></span> <span data-ttu-id="a9df1-112">入れ子`Do`になったループは同様の方法で動作`Loop`し、最も内側`Do`のステートメントが最も内側のステートメントに一致します。</span><span class="sxs-lookup"><span data-stu-id="a9df1-112">Nested `Do` loops work in a similar fashion, with the innermost `Loop` statement matching the innermost `Do` statement.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9df1-113">多くの制御構造では、キーワードをクリックすると、構造内のすべてのキーワードが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-113">For many control structures, when you click a keyword, all of the keywords in the structure are highlighted.</span></span> <span data-ttu-id="a9df1-114">たとえば、 `If...Then...Else`構築をクリック`If`すると、、 `Then` `ElseIf`、、 `Else`、および`If` `End If`のすべてのインスタンスが構築されます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-114">For instance, when you click `If` in an `If...Then...Else` construction, all instances of `If`, `Then`, `ElseIf`, `Else`, and `End If` in the construction are highlighted.</span></span> <span data-ttu-id="a9df1-115">次または前の強調表示されたキーワードに移動するには、CTRL + SHIFT + ↓キーを押すか、CTRL + SHIFT + 上方向キーを押します。</span><span class="sxs-lookup"><span data-stu-id="a9df1-115">To move to the next or previous highlighted keyword, press CTRL+SHIFT+DOWN ARROW or CTRL+SHIFT+UP ARROW.</span></span>  
  
## <a name="nesting-different-kinds-of-control-structures"></a><span data-ttu-id="a9df1-116">さまざまな種類の制御構造の入れ子</span><span class="sxs-lookup"><span data-stu-id="a9df1-116">Nesting Different Kinds of Control Structures</span></span>  
 <span data-ttu-id="a9df1-117">1つの種類のコントロール構造を別の種類に入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a9df1-117">You can nest one kind of control structure within another kind.</span></span> <span data-ttu-id="a9df1-118">次の例では`With` 、ブロック内`For Each`のブロックを`If`使用して`With` 、ループと入れ子になったブロックをブロック内に配置します。</span><span class="sxs-lookup"><span data-stu-id="a9df1-118">The following example uses a `With` block inside a `For Each` loop and nested `If` blocks inside the `With` block.</span></span>  
  
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
  
## <a name="overlapping-control-structures"></a><span data-ttu-id="a9df1-119">重複する制御構造</span><span class="sxs-lookup"><span data-stu-id="a9df1-119">Overlapping Control Structures</span></span>  
 <span data-ttu-id="a9df1-120">制御構造を重ねることはできません。</span><span class="sxs-lookup"><span data-stu-id="a9df1-120">You cannot overlap control structures.</span></span> <span data-ttu-id="a9df1-121">つまり、入れ子構造は、次の最も内側の構造体内に完全に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9df1-121">This means that any nested structure must be completely contained within the next innermost structure.</span></span> <span data-ttu-id="a9df1-122">たとえば、次の配置は無効です。これ`For`は、内部`With`ブロックが終了する前にループが終了するためです。</span><span class="sxs-lookup"><span data-stu-id="a9df1-122">For example, the following arrangement is invalid because the `For` loop terminates before the inner `With` block terminates.</span></span>  
  
 ![無効な入れ子の例を示す図。](./media/nested-control-structures/example-invalid-nesting.gif) 
  
 <span data-ttu-id="a9df1-124">Visual Basic コンパイラは、このような重複する制御構造を検出し、コンパイル時エラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="a9df1-124">The Visual Basic compiler detects such overlapping control structures and signals a compile-time error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9df1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a9df1-125">See also</span></span>

- [<span data-ttu-id="a9df1-126">制御フロー</span><span class="sxs-lookup"><span data-stu-id="a9df1-126">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="a9df1-127">条件判断構造</span><span class="sxs-lookup"><span data-stu-id="a9df1-127">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="a9df1-128">ループ構造</span><span class="sxs-lookup"><span data-stu-id="a9df1-128">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="a9df1-129">その他の制御構造</span><span class="sxs-lookup"><span data-stu-id="a9df1-129">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
