---
title: IsNot 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966935"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="acc91-102">IsNot 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="acc91-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="acc91-103">2つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="acc91-103">Compares two object reference variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc91-104">構文</span><span class="sxs-lookup"><span data-stu-id="acc91-104">Syntax</span></span>  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a><span data-ttu-id="acc91-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="acc91-105">Parts</span></span>  
 `result`  
 <span data-ttu-id="acc91-106">必須。</span><span class="sxs-lookup"><span data-stu-id="acc91-106">Required.</span></span> <span data-ttu-id="acc91-107">`Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="acc91-107">A `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="acc91-108">必須。</span><span class="sxs-lookup"><span data-stu-id="acc91-108">Required.</span></span> <span data-ttu-id="acc91-109">任意`Object`の変数または式。</span><span class="sxs-lookup"><span data-stu-id="acc91-109">Any `Object` variable or expression.</span></span>  
  
 `object2`  
 <span data-ttu-id="acc91-110">必須。</span><span class="sxs-lookup"><span data-stu-id="acc91-110">Required.</span></span> <span data-ttu-id="acc91-111">任意`Object`の変数または式。</span><span class="sxs-lookup"><span data-stu-id="acc91-111">Any `Object` variable or expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acc91-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="acc91-112">Remarks</span></span>  
 <span data-ttu-id="acc91-113">演算子`IsNot`は、2つのオブジェクト参照が異なるオブジェクトを参照するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="acc91-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="acc91-114">ただし、値の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="acc91-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="acc91-115">と`object1` `False`の両方`True`がまったく同じオブジェクトインスタンスを参照する`result`場合、はです。それ以外`result`の場合、はになります。 `object2`</span><span class="sxs-lookup"><span data-stu-id="acc91-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>  
  
 <span data-ttu-id="acc91-116">`IsNot`は、 `Is`演算子の反対側です。</span><span class="sxs-lookup"><span data-stu-id="acc91-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="acc91-117">の`IsNot`利点は、とを使用`Not`すると`Is`、読みにくくなることがある、厄介な構文を避けることができることです。</span><span class="sxs-lookup"><span data-stu-id="acc91-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>  
  
 <span data-ttu-id="acc91-118">`Is` および`IsNot`演算子を使用すると、事前バインディングオブジェクトと遅延バインディングオブジェクトの両方をテストできます。</span><span class="sxs-lookup"><span data-stu-id="acc91-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="acc91-119">演算子を使用して、 `TypeOf`演算子から返された式を比較することはできません。 `IsNot`</span><span class="sxs-lookup"><span data-stu-id="acc91-119">The `IsNot` operator cannot be used to compare expressions returned from the `TypeOf` operator.</span></span> <span data-ttu-id="acc91-120">代わりに、演算子`Not`と`Is`演算子を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="acc91-120">Instead, you must use the `Not` and `Is` operators.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acc91-121">例</span><span class="sxs-lookup"><span data-stu-id="acc91-121">Example</span></span>  
 <span data-ttu-id="acc91-122">次のコード例では、 `Is`演算子`IsNot`と演算子の両方を使用して、同じ比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="acc91-122">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a><span data-ttu-id="acc91-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="acc91-123">See also</span></span>

- [<span data-ttu-id="acc91-124">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="acc91-124">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="acc91-125">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="acc91-125">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="acc91-126">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="acc91-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="acc91-127">2 つのオブジェクトが等しいかどうかをテストする方法</span><span class="sxs-lookup"><span data-stu-id="acc91-127">How to: Test Whether Two Objects Are the Same</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
