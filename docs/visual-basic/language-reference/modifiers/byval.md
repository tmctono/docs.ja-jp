---
title: ByVal
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: a96f871c6ce119f65ebbec54fdb1471ae105d504
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351595"
---
# <a name="byval-visual-basic"></a><span data-ttu-id="7eea4-102">ByVal (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7eea4-102">ByVal (Visual Basic)</span></span>
<span data-ttu-id="7eea4-103">呼び出されたプロシージャまたはプロパティによって、呼び出し元のコードの引数の基になる変数の値を変更できないように、引数を[値渡し](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)で渡すことを指定します。</span><span class="sxs-lookup"><span data-stu-id="7eea4-103">Specifies that an argument is passed [by value](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md), so that the called procedure or property cannot change the value of a variable underlying the argument in the calling code.</span></span> <span data-ttu-id="7eea4-104">修飾子が指定されない場合、ByVal が既定になります。</span><span class="sxs-lookup"><span data-stu-id="7eea4-104">If no modifier is specified, ByVal is the default.</span></span>

> [!NOTE]
> <span data-ttu-id="7eea4-105">それは既定であるため、メソッド シグネチャに `ByVal` キーワードを明示的に指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7eea4-105">Because it is the default, you do not have to explicitly specify the `ByVal` keyword in method signatures.</span></span> <span data-ttu-id="7eea4-106">それにより、ノイズが多いコードが生成される傾向があるため、既定でない `ByRef` キーワードが見落とされることが多くなります。</span><span class="sxs-lookup"><span data-stu-id="7eea4-106">It tends to produce noisy code and often leads to the non-default `ByRef` keyword being overlooked.</span></span>

## <a name="remarks"></a><span data-ttu-id="7eea4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7eea4-107">Remarks</span></span>
 <span data-ttu-id="7eea4-108">`ByVal` 修飾子は、次のコンテキストで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7eea4-108">The `ByVal` modifier can be used in these contexts:</span></span>

 [<span data-ttu-id="7eea4-109">Declare ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eea4-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

 [<span data-ttu-id="7eea4-110">Function ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eea4-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
  
 [<span data-ttu-id="7eea4-111">Operator ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eea4-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
  
 [<span data-ttu-id="7eea4-112">Property ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eea4-112">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
  
 [<span data-ttu-id="7eea4-113">Sub ステートメント</span><span class="sxs-lookup"><span data-stu-id="7eea4-113">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="example"></a><span data-ttu-id="7eea4-114">例</span><span class="sxs-lookup"><span data-stu-id="7eea4-114">Example</span></span>
 <span data-ttu-id="7eea4-115">次の例では、参照型の引数を指定して `ByVal` パラメーターの引き渡し方法の使用を示します。</span><span class="sxs-lookup"><span data-stu-id="7eea4-115">The following example demonstrates the use of the `ByVal` parameter passing mechanism with a reference type argument.</span></span> <span data-ttu-id="7eea4-116">この例では、引数は、クラス `Class1` のインスタンスである `c1` です。</span><span class="sxs-lookup"><span data-stu-id="7eea4-116">In the example, the argument is `c1`, an instance of class `Class1`.</span></span> <span data-ttu-id="7eea4-117">`ByVal` によって、プロシージャ内のコードが参照引数 `c1` の基になる値を変更しないようになりますが、`c1` のアクセス可能なフィールドとプロパティは保護されません。</span><span class="sxs-lookup"><span data-stu-id="7eea4-117">`ByVal` prevents the code in the procedures from changing the underlying value of the reference argument, `c1`, but does not protect the accessible fields and properties of `c1`.</span></span>

 [!code-vb[VbVbalrKeywords#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class5.vb#10)]

## <a name="see-also"></a><span data-ttu-id="7eea4-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="7eea4-118">See also</span></span>

- [<span data-ttu-id="7eea4-119">キーワード</span><span class="sxs-lookup"><span data-stu-id="7eea4-119">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="7eea4-120">引数の値渡しと参照渡し</span><span class="sxs-lookup"><span data-stu-id="7eea4-120">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
