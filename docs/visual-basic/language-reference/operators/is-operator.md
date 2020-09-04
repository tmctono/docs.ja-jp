---
title: Is 演算子
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 1c2d87ef0a8202332c87af552f488d652c400213
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812264"
---
# <a name="is-operator-visual-basic"></a><span data-ttu-id="02f7b-102">Is 演算子 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02f7b-102">Is operator (Visual Basic)</span></span>

<span data-ttu-id="02f7b-103">2 つのオブジェクト参照変数を比較します。</span><span class="sxs-lookup"><span data-stu-id="02f7b-103">Compares two object reference variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="02f7b-104">構文</span><span class="sxs-lookup"><span data-stu-id="02f7b-104">Syntax</span></span>

```vb
result = object1 Is object2
```

## <a name="parts"></a><span data-ttu-id="02f7b-105">指定項目</span><span class="sxs-lookup"><span data-stu-id="02f7b-105">Parts</span></span>

 `result`  
 <span data-ttu-id="02f7b-106">必須です。</span><span class="sxs-lookup"><span data-stu-id="02f7b-106">Required.</span></span> <span data-ttu-id="02f7b-107">任意の `Boolean` 値。</span><span class="sxs-lookup"><span data-stu-id="02f7b-107">Any `Boolean` value.</span></span>  
  
 `object1`  
 <span data-ttu-id="02f7b-108">必須です。</span><span class="sxs-lookup"><span data-stu-id="02f7b-108">Required.</span></span> <span data-ttu-id="02f7b-109">任意の `Object` 名。</span><span class="sxs-lookup"><span data-stu-id="02f7b-109">Any `Object` name.</span></span>  
  
 `object2`  
 <span data-ttu-id="02f7b-110">必須です。</span><span class="sxs-lookup"><span data-stu-id="02f7b-110">Required.</span></span> <span data-ttu-id="02f7b-111">任意の `Object` 名。</span><span class="sxs-lookup"><span data-stu-id="02f7b-111">Any `Object` name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02f7b-112">Remarks</span><span class="sxs-lookup"><span data-stu-id="02f7b-112">Remarks</span></span>

<span data-ttu-id="02f7b-113">`Is` 演算子では、2 つのオブジェクト参照が同じオブジェクトを参照しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="02f7b-113">The `Is` operator determines if two object references refer to the same object.</span></span> <span data-ttu-id="02f7b-114">ただし、値の比較は行われません。</span><span class="sxs-lookup"><span data-stu-id="02f7b-114">However, it does not perform value comparisons.</span></span> <span data-ttu-id="02f7b-115">`object1` と `object2` の両方がまったく同じオブジェクト インスタンスを参照している場合、`result` は `True` です。そうでない場合、`result` は `False` です。</span><span class="sxs-lookup"><span data-stu-id="02f7b-115">If `object1` and `object2` both refer to the exact same object instance, `result` is `True`; if they do not, `result` is `False`.</span></span>

> [!NOTE]
> <span data-ttu-id="02f7b-116">`Is` キーワードは、[Select...Case ステートメント](../statements/select-case-statement.md)でも使用されます。</span><span class="sxs-lookup"><span data-stu-id="02f7b-116">The `Is` keyword is also used in the [Select...Case Statement](../statements/select-case-statement.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="02f7b-117">例</span><span class="sxs-lookup"><span data-stu-id="02f7b-117">Example</span></span>

<span data-ttu-id="02f7b-118">次の例では、`Is` 演算子を使用してオブジェクト参照のペアを比較します。</span><span class="sxs-lookup"><span data-stu-id="02f7b-118">The following example uses the `Is` operator to compare pairs of object references.</span></span> <span data-ttu-id="02f7b-119">結果は、2 つのオブジェクトが同一かどうかを表す `Boolean` 値に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="02f7b-119">The results are assigned to a `Boolean` value representing whether the two objects are identical.</span></span>

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

<span data-ttu-id="02f7b-120">前の例で示したように、`Is` 演算子を使用して、事前バインディングと遅延バインディングの両方のオブジェクトをテストできます。</span><span class="sxs-lookup"><span data-stu-id="02f7b-120">As the preceding example demonstrates, you can use the `Is` operator to test both early bound and late bound objects.</span></span>

## <a name="use-typeof-operator-with-is-operator"></a><span data-ttu-id="02f7b-121">TypeOf 演算子と Is 演算子を使用する</span><span class="sxs-lookup"><span data-stu-id="02f7b-121">Use TypeOf operator with Is operator</span></span>

<span data-ttu-id="02f7b-122">`Is` 演算子を `TypeOf` キーワードと共に使用して `TypeOf`...`Is` 式を作成することもできます。これにより、オブジェクト変数がデータ型に対応しているかどうかがテストされます。</span><span class="sxs-lookup"><span data-stu-id="02f7b-122">`Is` operator can also be used with the `TypeOf` keyword to make a `TypeOf`...`Is` expression, which tests whether an object variable is compatible with a data type.</span></span> <span data-ttu-id="02f7b-123">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="02f7b-123">For example:</span></span>

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a><span data-ttu-id="02f7b-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="02f7b-124">See also</span></span>

- [<span data-ttu-id="02f7b-125">TypeOf 演算子</span><span class="sxs-lookup"><span data-stu-id="02f7b-125">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="02f7b-126">IsNot 演算子</span><span class="sxs-lookup"><span data-stu-id="02f7b-126">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="02f7b-127">Visual Basic における比較演算子</span><span class="sxs-lookup"><span data-stu-id="02f7b-127">Comparison Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [<span data-ttu-id="02f7b-128">Visual Basic における演算子の優先順位</span><span class="sxs-lookup"><span data-stu-id="02f7b-128">Operator Precedence in Visual Basic</span></span>](operator-precedence.md)
- [<span data-ttu-id="02f7b-129">機能別の演算子一覧</span><span class="sxs-lookup"><span data-stu-id="02f7b-129">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="02f7b-130">演算子および式</span><span class="sxs-lookup"><span data-stu-id="02f7b-130">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
