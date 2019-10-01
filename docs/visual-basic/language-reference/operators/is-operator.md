---
title: Is 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 0351d224d9bf08a8f3ca74090de7b9c51c2c61bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701362"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="501e5-102">Is 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="501e5-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="501e5-103">2つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="501e5-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="501e5-104">構文</span><span class="sxs-lookup"><span data-stu-id="501e5-104">Syntax</span></span>  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="501e5-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="501e5-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="501e5-106">必須。</span><span class="sxs-lookup"><span data-stu-id="501e5-106">Required.</span></span> <span data-ttu-id="501e5-107">@No__t 0 の値。</span><span class="sxs-lookup"><span data-stu-id="501e5-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="501e5-108">必須。</span><span class="sxs-lookup"><span data-stu-id="501e5-108">Required.</span></span> <span data-ttu-id="501e5-109">任意の `Object` の名前。</span><span class="sxs-lookup"><span data-stu-id="501e5-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="501e5-110">必須。</span><span class="sxs-lookup"><span data-stu-id="501e5-110">Required.</span></span> <span data-ttu-id="501e5-111">任意の `Object` の名前。</span><span class="sxs-lookup"><span data-stu-id="501e5-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="501e5-112">コメント</span><span class="sxs-lookup"><span data-stu-id="501e5-112">Remarks</span></span>  
 <span data-ttu-id="501e5-113">@No__t-0 演算子は、2つのオブジェクト参照が同じオブジェクトを参照するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="501e5-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="501e5-114">ただし、値の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="501e5-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="501e5-115">@No__t-0 および `object2` がまったく同じオブジェクトインスタンスを参照している場合、`result` は `True` です。そうでない場合、`result` は `False` になります。</span><span class="sxs-lookup"><span data-stu-id="501e5-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="501e5-116">`Is` は、`TypeOf` キーワードと共に使用して `TypeOf`... `Is` 式を作成することもできます。これにより、オブジェクト変数がデータ型と互換性があるかどうかがテストされます。</span><span class="sxs-lookup"><span data-stu-id="501e5-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="501e5-117">`Is`キーワードは[Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="501e5-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="501e5-118">例</span><span class="sxs-lookup"><span data-stu-id="501e5-118">Example</span></span>  
 <span data-ttu-id="501e5-119">次の例では、`Is` 演算子を使用して、オブジェクト参照のペアを比較します。</span><span class="sxs-lookup"><span data-stu-id="501e5-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="501e5-120">結果は、2つのオブジェクトが同一かどうかを表す @no__t 0 の値に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="501e5-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="501e5-121">前の例で示したように、`Is` 演算子を使用して、事前バインディングオブジェクトと遅延バインディングオブジェクトの両方をテストできます。</span><span class="sxs-lookup"><span data-stu-id="501e5-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="501e5-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="501e5-122">See also</span></span>

- [<span data-ttu-id="501e5-123">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="501e5-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="501e5-124">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="501e5-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="501e5-125">Visual Basic の比較演算子</span><span class="sxs-lookup"><span data-stu-id="501e5-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="501e5-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="501e5-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="501e5-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="501e5-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="501e5-128">演算子および式</span><span class="sxs-lookup"><span data-stu-id="501e5-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
