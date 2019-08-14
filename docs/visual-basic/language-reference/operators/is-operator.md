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
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054959"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="98b16-102">Is 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="98b16-102">Is Operator (Visual Basic)</span></span>
<span data-ttu-id="98b16-103">2 つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="98b16-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b16-104">構文</span><span class="sxs-lookup"><span data-stu-id="98b16-104">Syntax</span></span>  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a><span data-ttu-id="98b16-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="98b16-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="98b16-106">必須。</span><span class="sxs-lookup"><span data-stu-id="98b16-106">Required.</span></span> <span data-ttu-id="98b16-107">すべて`Boolean`値。</span><span class="sxs-lookup"><span data-stu-id="98b16-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="98b16-108">必須。</span><span class="sxs-lookup"><span data-stu-id="98b16-108">Required.</span></span> <span data-ttu-id="98b16-109">すべて`Object`名。</span><span class="sxs-lookup"><span data-stu-id="98b16-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="98b16-110">必須。</span><span class="sxs-lookup"><span data-stu-id="98b16-110">Required.</span></span> <span data-ttu-id="98b16-111">すべて`Object`名。</span><span class="sxs-lookup"><span data-stu-id="98b16-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98b16-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="98b16-112">Remarks</span></span>  
 <span data-ttu-id="98b16-113">`Is`演算子が 2 つのオブジェクト参照が同じオブジェクトを参照してかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="98b16-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="98b16-114">ただし、値の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="98b16-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="98b16-115">場合`object1`と`object2`両方には、まったく同じオブジェクト インスタンスを参照してください`result`は`True`; が存在しない場合、`result`は`False`します。</span><span class="sxs-lookup"><span data-stu-id="98b16-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>  
  
 <span data-ttu-id="98b16-116">`Is` 使用することができますも、`TypeOf`キーワードを`TypeOf`.`Is`オブジェクト変数のデータ型と互換性があるかどうかをテストする式。</span><span class="sxs-lookup"><span data-stu-id="98b16-116">`Is` can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98b16-117">`Is`キーワードは[Select...Case ステートメント](../../../visual-basic/language-reference/statements/select-case-statement.md)でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="98b16-117">The `Is` keyword is also used in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="98b16-118">例</span><span class="sxs-lookup"><span data-stu-id="98b16-118">Example</span></span>  
 <span data-ttu-id="98b16-119">次の例では、`Is`オブジェクト参照のペアを比較する演算子。</span><span class="sxs-lookup"><span data-stu-id="98b16-119">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="98b16-120">割り当てられている結果を`Boolean`2 つのオブジェクトが同一であるかどうかを表す値。</span><span class="sxs-lookup"><span data-stu-id="98b16-120">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 <span data-ttu-id="98b16-121">使用することができます、前の例に示すよう、`Is`両方をテストする演算子が事前バインディングし、遅延バインドされたオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="98b16-121">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b16-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="98b16-122">See also</span></span>

- [<span data-ttu-id="98b16-123">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="98b16-123">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="98b16-124">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="98b16-124">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="98b16-125">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="98b16-125">Comparison Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="98b16-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="98b16-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="98b16-127">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="98b16-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="98b16-128">演算子および式</span><span class="sxs-lookup"><span data-stu-id="98b16-128">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
