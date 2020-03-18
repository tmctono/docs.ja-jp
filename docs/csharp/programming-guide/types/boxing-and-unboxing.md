---
title: ボックス化とボックス化解除 - C# プログラミング ガイド
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 62df08bf4ae3580e9b8d5b3aab0697d396674ca1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "76745411"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="c3008-102">ボックス化とボックス化解除 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="c3008-102">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="c3008-103">ボックス化とは、[値型](../../language-reference/builtin-types/value-types.md)から `object` 型、またはその値型によって実装されている任意のインターフェイス型へ変換するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="c3008-103">Boxing is the process of converting a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="c3008-104">共通言語ランタイム (CLR) により値型がボックス化されるとき、値は <xref:System.Object?displayProperty=nameWithType> インスタンス内部にラップされ、マネージド ヒープに格納されます。</span><span class="sxs-lookup"><span data-stu-id="c3008-104">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="c3008-105">ボックス化解除すると、値型がオブジェクトから抽出されます。</span><span class="sxs-lookup"><span data-stu-id="c3008-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="c3008-106">ボックス化は暗黙的に行われ、ボックス化解除すると明示的になります。</span><span class="sxs-lookup"><span data-stu-id="c3008-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="c3008-107">ボックス化とボックス化解除の概念は、任意の型の値をオブジェクトとして扱うという C# の型システムの統一されたビューに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c3008-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="c3008-108">次の例では、整数の変数 `i` を "*ボックス化*" し、オブジェクト `o` に代入しています。</span><span class="sxs-lookup"><span data-stu-id="c3008-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="c3008-109">次に、オブジェクト `o` は、次のようにボックス化解除し、整数の変数 `i` に代入できます。</span><span class="sxs-lookup"><span data-stu-id="c3008-109">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="c3008-110">次のコードは、C# でのボックス化の使用例です。</span><span class="sxs-lookup"><span data-stu-id="c3008-110">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="c3008-111">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="c3008-111">Performance</span></span>

<span data-ttu-id="c3008-112">簡単な代入と比べて、ボックス化およびボックス化解除は負荷の大きいプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c3008-112">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="c3008-113">値型をボックス化するときは、新しいオブジェクトを割り当てて構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3008-113">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="c3008-114">ボックス化ほどではありませんが、ボックス化解除に必要なキャストも大きな負荷がかかります。</span><span class="sxs-lookup"><span data-stu-id="c3008-114">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="c3008-115">詳しくは、「[パフォーマンス](../../../framework/performance/performance-tips.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c3008-115">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="c3008-116">ボックス化</span><span class="sxs-lookup"><span data-stu-id="c3008-116">Boxing</span></span>

<span data-ttu-id="c3008-117">ボックス化は、値型をガベージ コレクション ヒープに格納するために使用します。</span><span class="sxs-lookup"><span data-stu-id="c3008-117">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="c3008-118">ボックス化とは、[値型](../../language-reference/builtin-types/value-types.md)から `object` 型、またはその値型によって実装されている任意のインターフェイス型への暗黙の変換のことです。</span><span class="sxs-lookup"><span data-stu-id="c3008-118">Boxing is an implicit conversion of a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="c3008-119">値型をボックス化すると、オブジェクト インスタンスがヒープに割り当てられ、値が新しいオブジェクトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="c3008-119">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="c3008-120">値型の変数の宣言例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="c3008-120">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="c3008-121">次のステートメントは、変数 `i` にボックス化を暗黙的に適用します。</span><span class="sxs-lookup"><span data-stu-id="c3008-121">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="c3008-122">このステートメントによって、ヒープ上にある `o` 型の値を参照するオブジェクト参照 `int` がスタック上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="c3008-122">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="c3008-123">この値は、変数 `i` に割り当てられた値型の値のコピーです。</span><span class="sxs-lookup"><span data-stu-id="c3008-123">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="c3008-124">2 つの変数 `i` と `o` の違いを次のボックス化変換の図に示します。</span><span class="sxs-lookup"><span data-stu-id="c3008-124">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![i 変数と o 変数の違いを示す図。](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="c3008-126">次の例に示すように、明示的にボックス化を実行することもできますが、明示的なボックス化は不要です。</span><span class="sxs-lookup"><span data-stu-id="c3008-126">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="c3008-127">[説明]</span><span class="sxs-lookup"><span data-stu-id="c3008-127">Description</span></span>

<span data-ttu-id="c3008-128">ここでは、ボックス化を使用して整数の変数 `i` をオブジェクト `o` に変換する例を示します。</span><span class="sxs-lookup"><span data-stu-id="c3008-128">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="c3008-129">変換後に、変数 `i` の値を `123` から `456` に変更します。</span><span class="sxs-lookup"><span data-stu-id="c3008-129">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="c3008-130">この例は、元の値型とボックス化されたオブジェクトが別個のメモリ位置を使用するため、それぞれ別々の値を格納できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="c3008-130">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="c3008-131">例</span><span class="sxs-lookup"><span data-stu-id="c3008-131">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="c3008-132">ボックス化解除</span><span class="sxs-lookup"><span data-stu-id="c3008-132">Unboxing</span></span>

<span data-ttu-id="c3008-133">ボックス化解除とは、`object` 型から[値型](../../language-reference/builtin-types/value-types.md)へ、またはインターフェイス型からそのインターフェイスを実装している値型への明示的な変換のことです。</span><span class="sxs-lookup"><span data-stu-id="c3008-133">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/builtin-types/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="c3008-134">ボックス化解除では、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="c3008-134">An unboxing operation consists of:</span></span>

- <span data-ttu-id="c3008-135">オブジェクト インスタンスが、指定された値型のボックス化された値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3008-135">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="c3008-136">インスタンスの値を値型の変数にコピーします。</span><span class="sxs-lookup"><span data-stu-id="c3008-136">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="c3008-137">次のステートメントに、ボックス化およびボックス化解除の両方を示します。</span><span class="sxs-lookup"><span data-stu-id="c3008-137">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="c3008-138">前のステートメントの結果は、次の図に示すとおりです。</span><span class="sxs-lookup"><span data-stu-id="c3008-138">The following figure demonstrates the result of the previous statements:</span></span>

![ボックス化解除変換を示す図。](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="c3008-140">実行時に値型のボックス化解除を成功させるには、ボックス化解除の対象項目が、同じ値型のインスタンスのボックス化によって既に作成済みのオブジェクトへの参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3008-140">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="c3008-141">`null` をボックス化解除しようとすると <xref:System.NullReferenceException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="c3008-141">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="c3008-142">互換性のない値型への参照をボックス化解除しようとすると、<xref:System.InvalidCastException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="c3008-142">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="c3008-143">例</span><span class="sxs-lookup"><span data-stu-id="c3008-143">Example</span></span>

<span data-ttu-id="c3008-144">次の例は、無効なボックス化解除の結果、`InvalidCastException` が発生する場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="c3008-144">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="c3008-145">`try` と `catch` を使用すると、エラーの発生時にエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c3008-145">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="c3008-146">このプログラムの出力を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c3008-146">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="c3008-147">エラーを修正するには、次のステートメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="c3008-147">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="c3008-148">この行を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="c3008-148">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="c3008-149">ステートメントを変更すると、変換が実行されて次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="c3008-149">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="c3008-150">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="c3008-150">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c3008-151">参照</span><span class="sxs-lookup"><span data-stu-id="c3008-151">See also</span></span>

- [<span data-ttu-id="c3008-152">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c3008-152">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c3008-153">参照型</span><span class="sxs-lookup"><span data-stu-id="c3008-153">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="c3008-154">値型</span><span class="sxs-lookup"><span data-stu-id="c3008-154">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
