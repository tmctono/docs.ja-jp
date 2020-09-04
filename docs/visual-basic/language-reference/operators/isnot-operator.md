---
title: IsNot 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811042"
---
# <a name="isnot-operator-visual-basic"></a><span data-ttu-id="c59f9-102">IsNot 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c59f9-102">IsNot Operator (Visual Basic)</span></span>

<span data-ttu-id="c59f9-103">2 つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="c59f9-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="c59f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="c59f9-104">Syntax</span></span>

```vb
result = object1 IsNot object2
```

## <a name="parts"></a><span data-ttu-id="c59f9-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="c59f9-105">Parts</span></span>

- `result`

  <span data-ttu-id="c59f9-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="c59f9-106">Required.</span></span> <span data-ttu-id="c59f9-107">`Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="c59f9-107">A `Boolean` value.</span></span>

- `object1`

  <span data-ttu-id="c59f9-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="c59f9-108">Required.</span></span> <span data-ttu-id="c59f9-109">任意の `Object` 変数または式。</span><span class="sxs-lookup"><span data-stu-id="c59f9-109">Any `Object` variable or expression.</span></span>

- `object2`

  <span data-ttu-id="c59f9-110">必須。</span><span class="sxs-lookup"><span data-stu-id="c59f9-110">Required.</span></span> <span data-ttu-id="c59f9-111">任意の `Object` 変数または式。</span><span class="sxs-lookup"><span data-stu-id="c59f9-111">Any `Object` variable or expression.</span></span>

## <a name="remarks"></a><span data-ttu-id="c59f9-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="c59f9-112">Remarks</span></span>

<span data-ttu-id="c59f9-113">`IsNot` 演算子は、2 つのオブジェクト参照が別のオブジェクトを参照しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="c59f9-113">The `IsNot` operator determines if two object references refer to different objects.</span></span> <span data-ttu-id="c59f9-114">ただし、値は比較されません。</span><span class="sxs-lookup"><span data-stu-id="c59f9-114">However, it doesn't perform value comparisons.</span></span> <span data-ttu-id="c59f9-115">`object1` と `object2` の両方がまったく同じオブジェクト インスタンスを参照している場合、`result` は `False` です。そうでない場合、`result` は `True` です。</span><span class="sxs-lookup"><span data-stu-id="c59f9-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `False`; if they don't, `result` is `True`.</span></span>

<span data-ttu-id="c59f9-116">`IsNot` は `Is` 演算子の逆です。</span><span class="sxs-lookup"><span data-stu-id="c59f9-116">`IsNot` is the opposite of the `Is` operator.</span></span> <span data-ttu-id="c59f9-117">`IsNot` の利点は、`Not` と `Is` を使用することで読みにくくなる可能性がある洗練されていない構文を回避できることです。</span><span class="sxs-lookup"><span data-stu-id="c59f9-117">The advantage of `IsNot` is that you can avoid awkward syntax with `Not` and `Is`, which can be difficult to read.</span></span>

 <span data-ttu-id="c59f9-118">`Is` と `IsNot` の演算子を使用すると、事前バインディング オブジェクトと遅延バインディング オブジェクトの両方をテストできます。</span><span class="sxs-lookup"><span data-stu-id="c59f9-118">You can use the `Is` and `IsNot` operators to test both early-bound and late-bound objects.</span></span>

## <a name="example"></a><span data-ttu-id="c59f9-119">例</span><span class="sxs-lookup"><span data-stu-id="c59f9-119">Example</span></span>

<span data-ttu-id="c59f9-120">次のコード例では、`Is` 演算子と `IsNot` 演算子の両方を使用して、同じ比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="c59f9-120">The following code example uses both the `Is` operator and the `IsNot` operator to accomplish the same comparison.</span></span>

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a><span data-ttu-id="c59f9-121">TypeOf 演算子と IsNot 演算子を使用する</span><span class="sxs-lookup"><span data-stu-id="c59f9-121">Use TypeOf operator with IsNot operator</span></span>

<span data-ttu-id="c59f9-122">Visual Basic 14 以降、`TypeOf` 演算子と `IsNot` 演算子を一緒に使用し、オブジェクトとデータ型の間に互換性が "*ない*" かどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="c59f9-122">Starting with Visual Basic 14, you can use the `TypeOf` operator with the `IsNot` operator to test whether an object is *not* compatible with a data type.</span></span> <span data-ttu-id="c59f9-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c59f9-123">For example:</span></span>

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a><span data-ttu-id="c59f9-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="c59f9-124">See also</span></span>

- [<span data-ttu-id="c59f9-125">Is 演算子</span><span class="sxs-lookup"><span data-stu-id="c59f9-125">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="c59f9-126">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="c59f9-126">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="c59f9-127">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="c59f9-127">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="c59f9-128">方法: 2 つのオブジェクトが等しいかどうかをテストする</span><span class="sxs-lookup"><span data-stu-id="c59f9-128">How to: Test Whether Two Objects Are the Same</span></span>](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
