---
title: '* 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977345"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f336e-102">\* 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="f336e-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="f336e-103">`*` 演算子は 2 つの形式でサポートされています。単項ポインター間接参照演算子、または二項乗算演算子です。</span><span class="sxs-lookup"><span data-stu-id="f336e-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="f336e-104">ポインター間接参照演算子</span><span class="sxs-lookup"><span data-stu-id="f336e-104">Pointer indirection operator</span></span>

<span data-ttu-id="f336e-105">単項 `*` 演算子を使って、ポインター型のオペランドが指す変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="f336e-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="f336e-106">詳細については、[ポインター変数の値を取得する方法](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f336e-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="f336e-107">ポインター間接参照演算子 `*` には [unsafe](../keywords/unsafe.md) コンテキストが必要です。</span><span class="sxs-lookup"><span data-stu-id="f336e-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="f336e-108">乗算演算子</span><span class="sxs-lookup"><span data-stu-id="f336e-108">Multiplication operator</span></span>

<span data-ttu-id="f336e-109">数値型の場合、`*` 演算子によってそのオペランドの積が計算されます。</span><span class="sxs-lookup"><span data-stu-id="f336e-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="f336e-110">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="f336e-110">Operator overloadability</span></span>

<span data-ttu-id="f336e-111">ユーザー定義型は二項 `*` 演算子を[オーバーロード](../keywords/operator.md)できます。</span><span class="sxs-lookup"><span data-stu-id="f336e-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="f336e-112">二項 `*` 演算子をオーバーロードすると、[乗算代入演算子](multiplication-assignment-operator.md) `*=` も暗黙的にオーバーロードされます。</span><span class="sxs-lookup"><span data-stu-id="f336e-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f336e-113">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f336e-113">C# language specification</span></span>

<span data-ttu-id="f336e-114">詳細については、[C# 言語仕様](../language-specification/index.md)の「[Pointer indirection (ポインターの間接参照)](~/_csharplang/spec/unsafe-code.md#pointer-indirection)」と「[Multiplication operator (乗算演算子)](~/_csharplang/spec/expressions.md#multiplication-operator)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f336e-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f336e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f336e-115">See also</span></span>

- [<span data-ttu-id="f336e-116">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="f336e-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f336e-117">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="f336e-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f336e-118">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="f336e-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="f336e-119">ポインター型</span><span class="sxs-lookup"><span data-stu-id="f336e-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)