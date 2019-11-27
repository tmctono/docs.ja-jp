---
title: IsNot 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 616506f64d20e1f150b443433f1b69040136a5ba
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336074"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="9517e-102">IsNot 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9517e-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="9517e-103">2つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="9517e-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="9517e-104">構文</span><span class="sxs-lookup"><span data-stu-id="9517e-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="9517e-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="9517e-105">Parts</span></span>
 <span data-ttu-id="9517e-106">`result` 必須。</span><span class="sxs-lookup"><span data-stu-id="9517e-106">`result` Required.</span></span> <span data-ttu-id="9517e-107">`Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="9517e-107">A `Boolean` value.</span></span>

 <span data-ttu-id="9517e-108">`object1` 必須。</span><span class="sxs-lookup"><span data-stu-id="9517e-108">`object1` Required.</span></span> <span data-ttu-id="9517e-109">任意の `Object` 変数または式。</span><span class="sxs-lookup"><span data-stu-id="9517e-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="9517e-110">`object2` 必須。</span><span class="sxs-lookup"><span data-stu-id="9517e-110">`object2` Required.</span></span> <span data-ttu-id="9517e-111">任意の `Object` 変数または式。</span><span class="sxs-lookup"><span data-stu-id="9517e-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="9517e-112">コメント</span><span class="sxs-lookup"><span data-stu-id="9517e-112">Remarks</span></span>
 <span data-ttu-id="9517e-113">`IsNot` 演算子は、2つのオブジェクト参照が異なるオブジェクトを参照するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9517e-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="9517e-114">ただし、値の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="9517e-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="9517e-115">`object1` と `object2` 両方がまったく同じオブジェクトインスタンスを参照している場合、`result` は `False`です。そうでない場合は、`result` が `True`ます。</span><span class="sxs-lookup"><span data-stu-id="9517e-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="9517e-116">`IsNot` は、`Is` 演算子とは逆です。</span><span class="sxs-lookup"><span data-stu-id="9517e-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="9517e-117">`IsNot` の利点は、`Not` と `Is`での不適切な構文を避けることができることです。これは読みにくくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9517e-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="9517e-118">`Is` 演算子と `IsNot` 演算子を使用すると、事前バインディングオブジェクトと遅延バインディングオブジェクトの両方をテストできます。</span><span class="sxs-lookup"><span data-stu-id="9517e-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="9517e-119">例</span><span class="sxs-lookup"><span data-stu-id="9517e-119">Example</span></span>
 <span data-ttu-id="9517e-120">次のコード例では、`Is` 演算子と `IsNot` 演算子の両方を使用して、同じ比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="9517e-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="9517e-121">参照</span><span class="sxs-lookup"><span data-stu-id="9517e-121">See also</span></span>

- [<span data-ttu-id="9517e-122">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="9517e-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="9517e-123">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="9517e-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="9517e-124">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="9517e-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="9517e-125">方法: 2 つのオブジェクトが等しいかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="9517e-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
