---
title: '方法: プロシージャを別のプロシージャに渡す'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345247"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a><span data-ttu-id="c5bab-102">方法 : Visual Basic でプロシージャを別のプロシージャに渡す</span><span class="sxs-lookup"><span data-stu-id="c5bab-102">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>
<span data-ttu-id="c5bab-103">この例では、デリゲートを使用してプロシージャを別のプロシージャに渡す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-103">This example shows how to use delegates to pass a procedure to another procedure.</span></span>  
  
 <span data-ttu-id="c5bab-104">デリゲートは、Visual Basic の他の型と同様に使用できる型です。</span><span class="sxs-lookup"><span data-stu-id="c5bab-104">A delegate is a type that you can use like any other type in Visual Basic.</span></span> <span data-ttu-id="c5bab-105">`AddressOf` 演算子は、プロシージャ名に適用されるときにデリゲートオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-105">The `AddressOf` operator returns a delegate object when applied to a procedure name.</span></span>  
  
 <span data-ttu-id="c5bab-106">この例には、`AddressOf` 演算子で取得した別のプロシージャへの参照を受け取ることができるデリゲートパラメーターを持つプロシージャがあります。</span><span class="sxs-lookup"><span data-stu-id="c5bab-106">This example has a procedure with a delegate parameter that can take a reference to another procedure, obtained with the `AddressOf` operator.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="c5bab-107">デリゲートと一致するプロシージャを作成する</span><span class="sxs-lookup"><span data-stu-id="c5bab-107">Create the delegate and matching procedures</span></span>  
  
1. <span data-ttu-id="c5bab-108">`MathOperator`という名前のデリゲートを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-108">Create a delegate named `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. <span data-ttu-id="c5bab-109">シグネチャが一致するように、パラメーターと戻り値が `MathOperator`と一致する `AddNumbers` という名前のプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-109">Create a procedure named `AddNumbers` with parameters and return value that match those of `MathOperator`, so that the signatures match.</span></span>  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. <span data-ttu-id="c5bab-110">`MathOperator`に一致する署名を持つ `SubtractNumbers` という名前のプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-110">Create a procedure named `SubtractNumbers` with a signature that matches `MathOperator`.</span></span>  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. <span data-ttu-id="c5bab-111">デリゲートをパラメーターとして受け取る `DelegateTest` という名前のプロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-111">Create a procedure named `DelegateTest` that takes a delegate as a parameter.</span></span>  
  
     <span data-ttu-id="c5bab-112">署名が `MathOperator` シグネチャと一致するため、このプロシージャは `AddNumbers` または `SubtractNumbers`への参照を受け入れることができます。</span><span class="sxs-lookup"><span data-stu-id="c5bab-112">This procedure can accept a reference to `AddNumbers` or `SubtractNumbers`, because their signatures match the `MathOperator` signature.</span></span>  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. <span data-ttu-id="c5bab-113">パラメーターとして `AddNumbers` のデリゲートを使用して `DelegateTest` を1回呼び出す `Test` という名前のプロシージャを作成し、さらに、パラメーターとして `SubtractNumbers` のデリゲートを使用します。</span><span class="sxs-lookup"><span data-stu-id="c5bab-113">Create a procedure named `Test` that calls `DelegateTest` once with the delegate for `AddNumbers` as a parameter, and again with the delegate for `SubtractNumbers` as a parameter.</span></span>  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     <span data-ttu-id="c5bab-114">`Test` が呼び出されると、最初に `5` および `3`(8) で動作している `AddNumbers` の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c5bab-114">When `Test` is called, it first displays the result of `AddNumbers` acting on `5` and `3`, which is 8.</span></span> <span data-ttu-id="c5bab-115">次に、`9` と `3` に作用する `SubtractNumbers` の結果が表示されます。これは6です。</span><span class="sxs-lookup"><span data-stu-id="c5bab-115">Then the result of `SubtractNumbers` acting on `9` and `3` is displayed, which is 6.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bab-116">参照</span><span class="sxs-lookup"><span data-stu-id="c5bab-116">See also</span></span>

- [<span data-ttu-id="c5bab-117">デリゲート</span><span class="sxs-lookup"><span data-stu-id="c5bab-117">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="c5bab-118">AddressOf 演算子</span><span class="sxs-lookup"><span data-stu-id="c5bab-118">AddressOf Operator</span></span>](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="c5bab-119">Delegate ステートメント</span><span class="sxs-lookup"><span data-stu-id="c5bab-119">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="c5bab-120">方法: デリゲート メソッドを呼び出す</span><span class="sxs-lookup"><span data-stu-id="c5bab-120">How to: Invoke a Delegate Method</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
