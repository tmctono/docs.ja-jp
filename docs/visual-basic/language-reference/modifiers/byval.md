---
title: ByVal (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 1fa4c1fa0a2def02dd56fa3728a8df4b5ff16b7f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666859"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="e83b3-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e83b3-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="e83b3-103">引数が[値によって](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)渡されることを指定します。これにより、呼び出されたプロシージャまたはプロパティが、呼び出し元のコードの引数の基になる変数の値を変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="e83b3-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="e83b3-104">修飾子が指定されていない場合、ByVal が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="e83b3-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="e83b3-105">これは既定であるため、メソッドシグネチャで`ByVal`キーワードを明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e83b3-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="e83b3-106">ノイズの多いコードが生成される傾向があり、多くの`ByRef`場合、既定以外のキーワードが見落とされてしまいます。</span><span class="sxs-lookup"><span data-stu-id="e83b3-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="e83b3-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="e83b3-107">Remarks</span></span>
 <span data-ttu-id="e83b3-108">`ByVal` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e83b3-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="e83b3-109">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="e83b3-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

 [<span data-ttu-id="e83b3-110">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="e83b3-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [<span data-ttu-id="e83b3-111">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="e83b3-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [<span data-ttu-id="e83b3-112">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="e83b3-112">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [<span data-ttu-id="e83b3-113">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="e83b3-113">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="e83b3-114">例</span><span class="sxs-lookup"><span data-stu-id="e83b3-114">Example</span></span>
 <span data-ttu-id="e83b3-115">次の例では、参照型`ByVal`の引数を指定してパラメーター渡し機構を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e83b3-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="e83b3-116">この例では、引数は`c1`クラス`Class1`のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="e83b3-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="e83b3-117">`ByVal`プロシージャ内のコードが参照引数`c1`の基になる値を変更できないようにします。ただし、のアクセス可能な`c1`フィールドとプロパティは保護されません。</span><span class="sxs-lookup"><span data-stu-id="e83b3-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="e83b3-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e83b3-118">See also</span></span>

- [<span data-ttu-id="e83b3-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="e83b3-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="e83b3-120">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="e83b3-120">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
