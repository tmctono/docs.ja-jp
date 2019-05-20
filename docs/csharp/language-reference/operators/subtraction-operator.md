---
title: '- 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -_CSharpKeyword
helpviewer_keywords:
- '- operator [C#]'
- subtraction operator (-) [C#]
ms.assetid: 4de7a4fa-c69d-48e6-aff1-3130af970b2d
ms.openlocfilehash: 920981addd5c779c9ad1c666ef45e1de5cd23408
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633003"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="3285c-102">- 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="3285c-102">- operator (C# Reference)</span></span>

<span data-ttu-id="3285c-103">`-` 演算子には、単項演算子としての働きと 2 項演算子としての働きとがあります。</span><span class="sxs-lookup"><span data-stu-id="3285c-103">The `-` operator can function as either a unary or a binary operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="3285c-104">解説</span><span class="sxs-lookup"><span data-stu-id="3285c-104">Remarks</span></span>

<span data-ttu-id="3285c-105">すべての数値型には、単項 `-` 演算子が事前定義されています。</span><span class="sxs-lookup"><span data-stu-id="3285c-105">Unary `-` operators are predefined for all numeric types.</span></span> <span data-ttu-id="3285c-106">数値型に対する単項 `-` 演算の結果は、オペランドの反転の数値となります。</span><span class="sxs-lookup"><span data-stu-id="3285c-106">The result of a unary `-` operation on a numeric type is the numeric negation of the operand.</span></span>

<span data-ttu-id="3285c-107">最初のオペランドから 2 番目のオペランドを減算するために、すべての数値型と列挙型に 2 項 `-` 演算子が事前定義されています。</span><span class="sxs-lookup"><span data-stu-id="3285c-107">Binary `-` operators are predefined for all numeric and enumeration types to subtract the second operand from the first.</span></span>

<span data-ttu-id="3285c-108">2 項 `-` 演算子はデリゲート型にも備わっており、その場合、デリゲートの削除が実行されます。</span><span class="sxs-lookup"><span data-stu-id="3285c-108">Delegate types also provide a binary `-` operator, which performs delegate removal.</span></span>

<span data-ttu-id="3285c-109">単項 `-` 演算子と 2 項 `-` 演算子は、ユーザー定義型でオーバーロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="3285c-109">User-defined types can overload the unary `-` and binary `-` operators.</span></span> <span data-ttu-id="3285c-110">詳細については、「[operator キーワード](../keywords/operator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3285c-110">For more information, see [operator keyword](../keywords/operator.md).</span></span>

## <a name="example"></a><span data-ttu-id="3285c-111">例</span><span class="sxs-lookup"><span data-stu-id="3285c-111">Example</span></span>

[!code-csharp[csRefOperators#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#40)]

## <a name="see-also"></a><span data-ttu-id="3285c-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="3285c-112">See also</span></span>

- [<span data-ttu-id="3285c-113">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="3285c-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3285c-114">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="3285c-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3285c-115">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="3285c-115">C# operators</span></span>](index.md)
