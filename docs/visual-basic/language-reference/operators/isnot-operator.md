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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336074"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="8db38-102">IsNot 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8db38-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="8db38-103">2 つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="8db38-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="8db38-104">構文</span><span class="sxs-lookup"><span data-stu-id="8db38-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="8db38-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="8db38-105">Parts</span></span>
 <span data-ttu-id="8db38-106">`result` 必須。</span><span class="sxs-lookup"><span data-stu-id="8db38-106">`result` Required.</span></span> <span data-ttu-id="8db38-107">`Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="8db38-107">A `Boolean` value.</span></span>

 <span data-ttu-id="8db38-108">`object1` 必須。</span><span class="sxs-lookup"><span data-stu-id="8db38-108">`object1` Required.</span></span> <span data-ttu-id="8db38-109">任意の `Object` 変数または式。</span><span class="sxs-lookup"><span data-stu-id="8db38-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="8db38-110">`object2` 必須。</span><span class="sxs-lookup"><span data-stu-id="8db38-110">`object2` Required.</span></span> <span data-ttu-id="8db38-111">任意の `Object` 変数または式。</span><span class="sxs-lookup"><span data-stu-id="8db38-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="8db38-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="8db38-112">Remarks</span></span>
 <span data-ttu-id="8db38-113">`IsNot` 演算子は、2 つのオブジェクト参照が別のオブジェクトを参照しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8db38-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="8db38-114">ただし、値の比較は行われません。</span><span class="sxs-lookup"><span data-stu-id="8db38-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="8db38-115">`object1` と `object2` の両方がまったく同じオブジェクト インスタンスを参照している場合、`result` は `False` です。そうでない場合、`result` は `True` です。</span><span class="sxs-lookup"><span data-stu-id="8db38-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="8db38-116">`IsNot` は `Is` 演算子の逆です。</span><span class="sxs-lookup"><span data-stu-id="8db38-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="8db38-117">`IsNot` の利点は、`Not` と `Is` を使用することで読みにくくなる可能性がある洗練されていない構文を回避できることです。</span><span class="sxs-lookup"><span data-stu-id="8db38-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="8db38-118">`Is` と `IsNot` の演算子を使用すると、事前バインディング オブジェクトと遅延バインディング オブジェクトの両方をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8db38-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="8db38-119">例</span><span class="sxs-lookup"><span data-stu-id="8db38-119">Example</span></span>
 <span data-ttu-id="8db38-120">次のコード例では、`Is` 演算子と `IsNot` 演算子の両方を使用して、同じ比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="8db38-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="8db38-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="8db38-121">See also</span></span>

- [<span data-ttu-id="8db38-122">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="8db38-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="8db38-123">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="8db38-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="8db38-124">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="8db38-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="8db38-125">方法: 2 つのオブジェクトが等しいかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="8db38-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
