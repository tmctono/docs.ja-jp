---
title: '[] 演算子 - C# リファレンス'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 9088393f61d300ee76e56e320bec17b4a79bfebb
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835591"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fb9d9-102">[] 演算子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="fb9d9-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="fb9d9-103">通常、角かっこ `[]` は、配列、インデクサー、またはポインター要素へのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="fb9d9-104">ポインター要素へのアクセスの詳細については、「[ポインターを使用して配列要素にアクセスする方法](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="fb9d9-105">角かっこは、[属性](../../programming-guide/concepts/attributes/index.md)を指定するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="fb9d9-106">配列へのアクセス</span><span class="sxs-lookup"><span data-stu-id="fb9d9-106">Array access</span></span>

<span data-ttu-id="fb9d9-107">次の例は、配列要素へのアクセス方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="fb9d9-108">配列インデックスが配列の対応するディメンションの範囲に含まれない場合、<xref:System.IndexOutOfRangeException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="fb9d9-109">前述の例が示すように、配列型の宣言と配列インスタンスのインスタンス化にも角かっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="fb9d9-110">配列の詳細については、「[配列](../../programming-guide/arrays/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="fb9d9-111">インデクサーへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fb9d9-111">Indexer access</span></span>

<span data-ttu-id="fb9d9-112">次の例では、インデクサーへのアクセスを示すために .NET <xref:System.Collections.Generic.Dictionary%602> 型を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="fb9d9-113">インデクサーを使用すると、配列のインデックス作成と同様の方法でユーザー定義型のインスタンスのインデックスを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="fb9d9-114">整数である必要がある配列インデックスとは異なり、任意の型を持つインデクサー引数を宣言できます。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="fb9d9-115">インデクサーの詳細については、「[インデクサー](../../programming-guide/indexers/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="fb9d9-116">演算子のオーバーロード可/不可</span><span class="sxs-lookup"><span data-stu-id="fb9d9-116">Operator overloadability</span></span>

<span data-ttu-id="fb9d9-117">要素へのアクセス `[]` はオーバーロード可能な演算子とは見なされていません。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="fb9d9-118">ユーザー定義型を使用したインデックス作成をサポートするには、[インデクサー](../../programming-guide/indexers/index.md)を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fb9d9-119">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="fb9d9-119">C# language specification</span></span>

<span data-ttu-id="fb9d9-120">詳細については、「[C# 言語仕様](../language-specification/index.md)」の「[要素へのアクセス](~/_csharplang/spec/expressions.md#element-access)」と「[ポインターの要素へのアクセス](~/_csharplang/spec/unsafe-code.md#pointer-element-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb9d9-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb9d9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb9d9-121">See also</span></span>

- [<span data-ttu-id="fb9d9-122">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="fb9d9-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fb9d9-123">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="fb9d9-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fb9d9-124">C# 演算子</span><span class="sxs-lookup"><span data-stu-id="fb9d9-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="fb9d9-125">配列</span><span class="sxs-lookup"><span data-stu-id="fb9d9-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="fb9d9-126">インデクサー</span><span class="sxs-lookup"><span data-stu-id="fb9d9-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="fb9d9-127">ポインター型</span><span class="sxs-lookup"><span data-stu-id="fb9d9-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="fb9d9-128">属性</span><span class="sxs-lookup"><span data-stu-id="fb9d9-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)
- <span data-ttu-id="fb9d9-129">[?. および ?[] 演算子](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="fb9d9-129">[?. and ?[] operators](null-conditional-operators.md)</span></span>