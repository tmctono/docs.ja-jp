---
title: '方法: Visual Basic での別のプロシージャに渡す'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 312c0e0f100e85256ad4ca856ccf7f35dbaa36dc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305248"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="a8dd1-102">方法: Visual Basic での別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="a8dd1-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="a8dd1-103">この例では、プロシージャを別のプロシージャに渡すデリゲートを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="a8dd1-104">デリゲートは、Visual Basic での他の種類のように使用できる型です。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="a8dd1-105">`AddressOf`演算子プロシージャ名に適用する場合は、デリゲート オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="a8dd1-106">この例では、プロシージャを別のプロシージャを使用して取得への参照を受け取ることができます delegate パラメーターを持つ、`AddressOf`演算子。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="a8dd1-107">デリゲートと一致するプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="a8dd1-108">という名前のデリゲートを作成する`MathOperator`します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="a8dd1-109">という名前のプロシージャを作成する`AddNumbers`パラメーターと戻り値のものと一致する`MathOperator`署名が一致するようにします。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="a8dd1-110">という名前のプロシージャを作成する`SubtractNumbers`と一致するシグネチャを持つ`MathOperator`します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="a8dd1-111">という名前のプロシージャを作成`DelegateTest`をパラメーターとしてデリゲートを取得します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="a8dd1-112">この手順への参照を受け入れることができる`AddNumbers`または`SubtractNumbers`、署名が一致しているため、`MathOperator`署名します。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="a8dd1-113">という名前のプロシージャを作成する`Test`を呼び出す`DelegateTest`のデリゲートが 1 回`AddNumbers`をパラメーターとして、もう一度のデリゲートと`SubtractNumbers`をパラメーターとして。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="a8dd1-114">ときに`Test`が呼び出されると、その最初の結果を表示`AddNumbers`に機能している`5`と`3`8 であります。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="a8dd1-115">結果、`SubtractNumbers`に作用する`9`と`3`が表示されたら、6 であります。</span><span class="sxs-lookup"><span data-stu-id="a8dd1-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8dd1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8dd1-116">See also</span></span>

- [<span data-ttu-id="a8dd1-117">デリゲート</span><span class="sxs-lookup"><span data-stu-id="a8dd1-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="a8dd1-118">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="a8dd1-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="a8dd1-119">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="a8dd1-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="a8dd1-120">方法: デリゲート メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="a8dd1-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
