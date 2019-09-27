---
title: IsNot 演算子 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 7e1ac1004e671f592c03bd44ee7ec2e8cc572933
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71331632"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="5e1fc-102">IsNot 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e1fc-102">IsNot Operator (Visual Basic)</span></span>
<span data-ttu-id="5e1fc-103">2つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e1fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e1fc-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="5e1fc-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="5e1fc-105">Parts</span></span>
 <span data-ttu-id="5e1fc-106">`result` 必須。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-106">`result` Required.</span></span> <span data-ttu-id="5e1fc-107">`Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-107">A `Boolean` value.</span></span>

 <span data-ttu-id="5e1fc-108">`object1` 必須。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-108">`object1` Required.</span></span> <span data-ttu-id="5e1fc-109">@No__t 0 の変数または式。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-109">Any `Object` variable or expression.</span></span>

 <span data-ttu-id="5e1fc-110">`object2` 必須。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-110">`object2` Required.</span></span> <span data-ttu-id="5e1fc-111">@No__t 0 の変数または式。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e1fc-112">コメント</span><span class="sxs-lookup"><span data-stu-id="5e1fc-112">Remarks</span></span>
 <span data-ttu-id="5e1fc-113">@No__t-0 演算子は、2つのオブジェクト参照が異なるオブジェクトを参照するかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="5e1fc-114">ただし、値の比較は実行されません。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="5e1fc-115">@No__t-0 および `object2` がまったく同じオブジェクトインスタンスを参照している場合、`result` は `False` です。そうでない場合、`result` は `True` になります。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they do not, `result` is `True`.</span></span>

 <span data-ttu-id="5e1fc-116">`IsNot` は、`Is` 演算子の逆です。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="5e1fc-117">@No__t-0 の利点は、`Not` と `Is` を使用して、読みにくい構文を避けることができることです。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="5e1fc-118">@No__t-0 および `IsNot` 演算子を使用すると、事前バインディングオブジェクトと遅延バインディングオブジェクトの両方をテストできます。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="5e1fc-119">例</span><span class="sxs-lookup"><span data-stu-id="5e1fc-119">Example</span></span>
 <span data-ttu-id="5e1fc-120">次のコード例では、`Is` 演算子と `IsNot` 演算子の両方を使用して、同じ比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e1fc-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="see-also"></a><span data-ttu-id="5e1fc-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e1fc-121">See also</span></span>

- [<span data-ttu-id="5e1fc-122">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="5e1fc-122">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="5e1fc-123">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="5e1fc-123">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="5e1fc-124">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="5e1fc-124">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="5e1fc-125">2 つのオブジェクトが等しいかどうかをテストする方法</span><span class="sxs-lookup"><span data-stu-id="5e1fc-125">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
