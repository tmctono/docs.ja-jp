---
title: ボックス化とボックス化解除 - C# プログラミング ガイド
description: C# プログラミングにおけるボックス化とボックス化解除について説明します。 コード例を参照し、使用可能なその他のリソースを確認してください。
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 5a5bfcc79de8ba3ff66ca8aab9d86d69d89f9221
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380697"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="b2d26-104">ボックス化とボックス化解除 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="b2d26-104">Boxing and Unboxing (C# Programming Guide)</span></span>

<span data-ttu-id="b2d26-105">ボックス化とは、[値型](../../language-reference/builtin-types/value-types.md)から `object` 型、またはその値型によって実装されている任意のインターフェイス型へ変換するプロセスのことです。</span><span class="sxs-lookup"><span data-stu-id="b2d26-105">Boxing is the process of converting a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="b2d26-106">共通言語ランタイム (CLR) により値型がボックス化されるとき、値は <xref:System.Object?displayProperty=nameWithType> インスタンス内部にラップされ、マネージド ヒープに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-106">When the common language runtime (CLR) boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="b2d26-107">ボックス化解除すると、値型がオブジェクトから抽出されます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-107">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="b2d26-108">ボックス化は暗黙的に行われ、ボックス化解除すると明示的になります。</span><span class="sxs-lookup"><span data-stu-id="b2d26-108">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="b2d26-109">ボックス化とボックス化解除の概念は、任意の型の値をオブジェクトとして扱うという C# の型システムの統一されたビューに基づいています。</span><span class="sxs-lookup"><span data-stu-id="b2d26-109">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>

<span data-ttu-id="b2d26-110">次の例では、整数の変数 `i` を "*ボックス化*" し、オブジェクト `o` に代入しています。</span><span class="sxs-lookup"><span data-stu-id="b2d26-110">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

<span data-ttu-id="b2d26-111">次に、オブジェクト `o` は、次のようにボックス化解除し、整数の変数 `i` に代入できます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-111">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

<span data-ttu-id="b2d26-112">次のコードは、C# でのボックス化の使用例です。</span><span class="sxs-lookup"><span data-stu-id="b2d26-112">The following examples illustrate how boxing is used in C#.</span></span>

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a><span data-ttu-id="b2d26-113">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="b2d26-113">Performance</span></span>

<span data-ttu-id="b2d26-114">簡単な代入と比べて、ボックス化およびボックス化解除は負荷の大きいプロセスです。</span><span class="sxs-lookup"><span data-stu-id="b2d26-114">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="b2d26-115">値型をボックス化するときは、新しいオブジェクトを割り当てて構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d26-115">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="b2d26-116">ボックス化ほどではありませんが、ボックス化解除に必要なキャストも大きな負荷がかかります。</span><span class="sxs-lookup"><span data-stu-id="b2d26-116">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="b2d26-117">詳しくは、「[パフォーマンス](../../../framework/performance/performance-tips.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b2d26-117">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>

## <a name="boxing"></a><span data-ttu-id="b2d26-118">ボックス化</span><span class="sxs-lookup"><span data-stu-id="b2d26-118">Boxing</span></span>

<span data-ttu-id="b2d26-119">ボックス化は、値型をガベージ コレクション ヒープに格納するために使用します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-119">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="b2d26-120">ボックス化とは、[値型](../../language-reference/builtin-types/value-types.md)から `object` 型、またはその値型によって実装されている任意のインターフェイス型への暗黙の変換のことです。</span><span class="sxs-lookup"><span data-stu-id="b2d26-120">Boxing is an implicit conversion of a [value type](../../language-reference/builtin-types/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="b2d26-121">値型をボックス化すると、オブジェクト インスタンスがヒープに割り当てられ、値が新しいオブジェクトにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-121">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>

<span data-ttu-id="b2d26-122">値型の変数の宣言例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-122">Consider the following declaration of a value-type variable:</span></span>

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

<span data-ttu-id="b2d26-123">次のステートメントは、変数 `i` にボックス化を暗黙的に適用します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-123">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

<span data-ttu-id="b2d26-124">このステートメントによって、ヒープ上にある `o` 型の値を参照するオブジェクト参照 `int` がスタック上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-124">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="b2d26-125">この値は、変数 `i` に割り当てられた値型の値のコピーです。</span><span class="sxs-lookup"><span data-stu-id="b2d26-125">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="b2d26-126">2 つの変数 `i` と `o` の違いを次のボックス化変換の図に示します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-126">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>

![i 変数と o 変数の違いを示す図。](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

<span data-ttu-id="b2d26-128">次の例に示すように、明示的にボックス化を実行することもできますが、明示的なボックス化は不要です。</span><span class="sxs-lookup"><span data-stu-id="b2d26-128">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a><span data-ttu-id="b2d26-129">説明</span><span class="sxs-lookup"><span data-stu-id="b2d26-129">Description</span></span>

<span data-ttu-id="b2d26-130">ここでは、ボックス化を使用して整数の変数 `i` をオブジェクト `o` に変換する例を示します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-130">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="b2d26-131">変換後に、変数 `i` の値を `123` から `456` に変更します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-131">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="b2d26-132">この例は、元の値型とボックス化されたオブジェクトが別個のメモリ位置を使用するため、それぞれ別々の値を格納できることを示しています。</span><span class="sxs-lookup"><span data-stu-id="b2d26-132">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>

## <a name="example"></a><span data-ttu-id="b2d26-133">例</span><span class="sxs-lookup"><span data-stu-id="b2d26-133">Example</span></span>

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a><span data-ttu-id="b2d26-134">ボックス化解除</span><span class="sxs-lookup"><span data-stu-id="b2d26-134">Unboxing</span></span>

<span data-ttu-id="b2d26-135">ボックス化解除とは、`object` 型から[値型](../../language-reference/builtin-types/value-types.md)へ、またはインターフェイス型からそのインターフェイスを実装している値型への明示的な変換のことです。</span><span class="sxs-lookup"><span data-stu-id="b2d26-135">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/builtin-types/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="b2d26-136">ボックス化解除では、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-136">An unboxing operation consists of:</span></span>

- <span data-ttu-id="b2d26-137">オブジェクト インスタンスが、指定された値型のボックス化された値であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-137">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>

- <span data-ttu-id="b2d26-138">インスタンスの値を値型の変数にコピーします。</span><span class="sxs-lookup"><span data-stu-id="b2d26-138">Copying the value from the instance into the value-type variable.</span></span>

<span data-ttu-id="b2d26-139">次のステートメントに、ボックス化およびボックス化解除の両方を示します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-139">The following statements demonstrate both boxing and unboxing operations:</span></span>

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

<span data-ttu-id="b2d26-140">前のステートメントの結果は、次の図に示すとおりです。</span><span class="sxs-lookup"><span data-stu-id="b2d26-140">The following figure demonstrates the result of the previous statements:</span></span>

![ボックス化解除変換を示す図。](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

<span data-ttu-id="b2d26-142">実行時に値型のボックス化解除を成功させるには、ボックス化解除の対象項目が、同じ値型のインスタンスのボックス化によって既に作成済みのオブジェクトへの参照である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2d26-142">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="b2d26-143">`null` をボックス化解除しようとすると <xref:System.NullReferenceException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-143">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="b2d26-144">互換性のない値型への参照をボックス化解除しようとすると、<xref:System.InvalidCastException> が発生します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-144">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>

## <a name="example"></a><span data-ttu-id="b2d26-145">例</span><span class="sxs-lookup"><span data-stu-id="b2d26-145">Example</span></span>

<span data-ttu-id="b2d26-146">次の例は、無効なボックス化解除の結果、`InvalidCastException` が発生する場合を示しています。</span><span class="sxs-lookup"><span data-stu-id="b2d26-146">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="b2d26-147">`try` と `catch` を使用すると、エラーの発生時にエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-147">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

<span data-ttu-id="b2d26-148">このプログラムの出力を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-148">This program outputs:</span></span>

`Specified cast is not valid. Error: Incorrect unboxing.`

<span data-ttu-id="b2d26-149">エラーを修正するには、次のステートメントを変更します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-149">If you change the statement:</span></span>

```csharp
int j = (short) o;
```

<span data-ttu-id="b2d26-150">この行を次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="b2d26-150">to:</span></span>

```csharp
int j = (int) o;
```

<span data-ttu-id="b2d26-151">ステートメントを変更すると、変換が実行されて次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="b2d26-151">the conversion will be performed, and you will get the output:</span></span>

`Unboxing OK.`

## <a name="c-language-specification"></a><span data-ttu-id="b2d26-152">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b2d26-152">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b2d26-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2d26-153">See also</span></span>

- [<span data-ttu-id="b2d26-154">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b2d26-154">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b2d26-155">参照型</span><span class="sxs-lookup"><span data-stu-id="b2d26-155">Reference types</span></span>](../../language-reference/keywords/reference-types.md)
- [<span data-ttu-id="b2d26-156">値型</span><span class="sxs-lookup"><span data-stu-id="b2d26-156">Value types</span></span>](../../language-reference/builtin-types/value-types.md)
