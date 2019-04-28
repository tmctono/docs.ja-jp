---
title: '方法: 2 つのオブジェクトが同じです (Visual Basic) であるかどうかを確認します。'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: aae053ae0473ed6ced0f28da3d5e5afc0be629df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769084"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a><span data-ttu-id="1ca80-102">方法: 2 つのオブジェクトが同じです (Visual Basic) であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-102">How to: Determine Whether Two Objects Are Identical (Visual Basic)</span></span>
<span data-ttu-id="1ca80-103">Visual basic で 2 つの変数参照は同一と見なされます、ポインターが同じ場合、つまり、両方の変数がメモリ内と同じクラスのインスタンスを指している場合。</span><span class="sxs-lookup"><span data-stu-id="1ca80-103">In Visual Basic, two variable references are considered identical if their pointers are the same, that is, if both variables point to the same class instance in memory.</span></span> <span data-ttu-id="1ca80-104">たとえば、Windows フォーム アプリケーションでたい判断する比較を行うことかどうか、現在のインスタンス (`Me`) など、特定のインスタンスと同じ`Form2`します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-104">For example, in a Windows Forms application, you might want to make a comparison to determine whether the current instance (`Me`) is the same as a particular instance, such as `Form2`.</span></span>  
  
 <span data-ttu-id="1ca80-105">Visual Basic では、ポインターを比較する 2 つの演算子を提供します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-105">Visual Basic provides two operators to compare pointers.</span></span> <span data-ttu-id="1ca80-106">[Is 演算子](../../../../visual-basic/language-reference/operators/is-operator.md)返します`True`オブジェクトが同じですが場合、 [IsNot 演算子](../../../../visual-basic/language-reference/operators/isnot-operator.md)返します`True`それ以外の場合。</span><span class="sxs-lookup"><span data-stu-id="1ca80-106">The [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) returns `True` if the objects are identical, and the [IsNot Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) returns `True` if they are not.</span></span>  
  
## <a name="determining-if-two-objects-are-identical"></a><span data-ttu-id="1ca80-107">2 つのオブジェクトが同じかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-107">Determining if Two Objects Are Identical</span></span>  
  
#### <a name="to-determine-if-two-objects-are-identical"></a><span data-ttu-id="1ca80-108">2 つのオブジェクトが同じかどうかを判断するには</span><span class="sxs-lookup"><span data-stu-id="1ca80-108">To determine if two objects are identical</span></span>  
  
1. <span data-ttu-id="1ca80-109">セットアップ、 `Boolean` 2 つのオブジェクトをテストする式。</span><span class="sxs-lookup"><span data-stu-id="1ca80-109">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="1ca80-110">テスト式で使用して、`Is`演算子のオペランドとして 2 つのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ca80-110">In your testing expression, use the `Is` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="1ca80-111">`Is` 返します`True`場合は、オブジェクトが、同じクラスのインスタンスをポイントします。</span><span class="sxs-lookup"><span data-stu-id="1ca80-111">`Is` returns `True` if the objects point to the same class instance.</span></span>  
  
## <a name="determining-if-two-objects-are-not-identical"></a><span data-ttu-id="1ca80-112">2 つのオブジェクトが同一でないかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-112">Determining if Two Objects Are Not Identical</span></span>  
 <span data-ttu-id="1ca80-113">2 つのオブジェクトが異なると、結合にくいことができる場合、操作を実行する場合があります`Not`と`Is`、たとえば`If Not obj1 Is obj2`します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-113">Sometimes you want to perform an action if the two objects are not identical, and it can be awkward to combine `Not` and `Is`, for example `If Not obj1 Is obj2`.</span></span> <span data-ttu-id="1ca80-114">このような場合に使用することができます、`IsNot`演算子。</span><span class="sxs-lookup"><span data-stu-id="1ca80-114">In such a case you can use the `IsNot` operator.</span></span>  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a><span data-ttu-id="1ca80-115">2 つのオブジェクトが同一でないかどうかを判断するには</span><span class="sxs-lookup"><span data-stu-id="1ca80-115">To determine if two objects are not identical</span></span>  
  
1. <span data-ttu-id="1ca80-116">セットアップ、 `Boolean` 2 つのオブジェクトをテストする式。</span><span class="sxs-lookup"><span data-stu-id="1ca80-116">Set up a `Boolean` expression to test the two objects.</span></span>  
  
2. <span data-ttu-id="1ca80-117">テスト式で使用して、`IsNot`演算子のオペランドとして 2 つのオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="1ca80-117">In your testing expression, use the `IsNot` operator with the two objects as operands.</span></span>  
  
     <span data-ttu-id="1ca80-118">`IsNot` 返します`True`場合は、オブジェクトが同じクラスのインスタンスを指していません。</span><span class="sxs-lookup"><span data-stu-id="1ca80-118">`IsNot` returns `True` if the objects do not point to the same class instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ca80-119">例</span><span class="sxs-lookup"><span data-stu-id="1ca80-119">Example</span></span>  
 <span data-ttu-id="1ca80-120">次の例では、テストのペア`Object`変数を同じクラスのインスタンスを指しているかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1ca80-120">The following example tests pairs of `Object` variables to see if they point to the same class instance.</span></span>  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 <span data-ttu-id="1ca80-121">前の例では、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1ca80-121">The preceding example displays the following output.</span></span>  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a><span data-ttu-id="1ca80-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="1ca80-122">See also</span></span>

- [<span data-ttu-id="1ca80-123">Object 型</span><span class="sxs-lookup"><span data-stu-id="1ca80-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="1ca80-124">オブジェクト変数</span><span class="sxs-lookup"><span data-stu-id="1ca80-124">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="1ca80-125">オブジェクト変数の値</span><span class="sxs-lookup"><span data-stu-id="1ca80-125">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="1ca80-126">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="1ca80-126">Is Operator</span></span>](../../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="1ca80-127">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="1ca80-127">IsNot Operator</span></span>](../../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="1ca80-128">方法: 2 つのオブジェクトが関連するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="1ca80-128">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="1ca80-129">Me、My、MyBase、および MyClass</span><span class="sxs-lookup"><span data-stu-id="1ca80-129">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
