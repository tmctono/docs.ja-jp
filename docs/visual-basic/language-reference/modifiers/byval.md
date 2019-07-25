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
ms.openlocfilehash: abfe1489cb7e0d06b03c308e0704ce6f69ee55da
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433799"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="1d9b1-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d9b1-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="1d9b1-103">引数が[値によって](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)渡されることを指定します。これにより、呼び出されたプロシージャまたはプロパティが、呼び出し元のコードの引数の基になる変数の値を変更できなくなります。</span><span class="sxs-lookup"><span data-stu-id="1d9b1-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="1d9b1-104">修飾子が指定されていない場合、ByVal が既定値になります。</span><span class="sxs-lookup"><span data-stu-id="1d9b1-104">If no modifier is specified, ByVal is the default.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1d9b1-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1d9b1-105">Remarks</span></span>  
 <span data-ttu-id="1d9b1-106">`ByVal` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="1d9b1-106">The `ByVal` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="1d9b1-107">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="1d9b1-107">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="1d9b1-108">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="1d9b1-108">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="1d9b1-109">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="1d9b1-109">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="1d9b1-110">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="1d9b1-110">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="1d9b1-111">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="1d9b1-111">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a><span data-ttu-id="1d9b1-112">例</span><span class="sxs-lookup"><span data-stu-id="1d9b1-112">Example</span></span>  
 <span data-ttu-id="1d9b1-113">次の例では、参照型`ByVal`の引数を指定してパラメーター渡し機構を使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1d9b1-113">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="1d9b1-114">この例では、引数は`c1`クラス`Class1`のインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="1d9b1-114">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="1d9b1-115">`ByVal`プロシージャ内のコードが参照引数`c1`の基になる値を変更できないようにします。ただし、のアクセス可能な`c1`フィールドとプロパティは保護されません。</span><span class="sxs-lookup"><span data-stu-id="1d9b1-115">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="1d9b1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="1d9b1-116">See also</span></span>

- [<span data-ttu-id="1d9b1-117">キーワード</span><span class="sxs-lookup"><span data-stu-id="1d9b1-117">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="1d9b1-118">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="1d9b1-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
