---
title: readonly キーワード - C# リファレンス
ms.custom: seodec18
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: c3d18a52068b17b4a4259200754819dd43e28a03
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267647"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="1426a-102">readonly (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="1426a-102">readonly (C# Reference)</span></span>

<span data-ttu-id="1426a-103">`readonly` キーワードは、3 つのコンテキストで使用できる修飾子です。</span><span class="sxs-lookup"><span data-stu-id="1426a-103">The `readonly` keyword is a modifier that can be used in three contexts:</span></span>

- <span data-ttu-id="1426a-104">[フィールドの宣言](#readonly-field-example)では、`readonly` は、フィールドへの割り当てが、宣言の一部として、または同じクラスのコンストラクター内でのみ可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1426a-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="1426a-105">readonly フィールドは、フィールドの宣言とコンストラクターで複数回割り当ておよび再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="1426a-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span> <span data-ttu-id="1426a-106">`readonly` フィールドは、コンストラクターが終了した後で割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="1426a-106">A `readonly` field cannot be assigned after the constructor exits.</span></span> <span data-ttu-id="1426a-107">値型と参照型では意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="1426a-107">That has different implications for value types and reference types:</span></span>
- <span data-ttu-id="1426a-108">値型にはそのデータが直接含まれるため、`readonly` 値型のフィールドは変更できません。</span><span class="sxs-lookup"><span data-stu-id="1426a-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span> 
- <span data-ttu-id="1426a-109">参照型にはそのデータへの参照が含まれるため、`readonly` 参照型のフィールドは、常に同じオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1426a-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="1426a-110">そのオブジェクトは不変ではありません。</span><span class="sxs-lookup"><span data-stu-id="1426a-110">That object is not immutable.</span></span> <span data-ttu-id="1426a-111">`readonly` 修飾子があると、フィールドを参照型の別のインスタンスで置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="1426a-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="1426a-112">ただし、フィールドのインスタンス データを読み取り専用フィールドで変更することは禁止されません。</span><span class="sxs-lookup"><span data-stu-id="1426a-112">However, the modifier does not prevent the instance data of the field from being modified through the read-only field.</span></span>

> [!WARNING]
> <span data-ttu-id="1426a-113">変更可能な参照型である外部から参照できる読み取り専用フィールドを含む外部から参照できる型はセキュリティの脆弱性があり、警告 [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) がトリガーされる可能性があります: "読み取り専用の変更可能な参照型を宣言しません"。</span><span class="sxs-lookup"><span data-stu-id="1426a-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="1426a-114">[`readonly struct` の定義](#readonly-struct-example)では、`readonly` は `struct` が変更不可であることを示します。</span><span class="sxs-lookup"><span data-stu-id="1426a-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="1426a-115">[`ref readonly` メソッドの戻り値](#ref-readonly-return-example)では、`readonly` 修飾子は、メソッドが参照を返し、その参照への書き込みが許可されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1426a-115">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes are not allowed to that reference.</span></span>

<span data-ttu-id="1426a-116">最後の 2 つのコンテキストは、C# 7.2 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="1426a-116">The final two contexts were added in C# 7.2.</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="1426a-117">読み取り専用フィールドの例</span><span class="sxs-lookup"><span data-stu-id="1426a-117">Readonly field example</span></span>

<span data-ttu-id="1426a-118">この例では、`year` フィールドの値は、クラス コンストラクターで値が割り当てられていても `ChangeYear` メソッドでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="1426a-118">In this example, the value of the field `year` cannot be changed in the method `ChangeYear`, even though it is assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="1426a-119">`readonly` のフィールドに値を割り当てることができるのは、次のコンテキスト内に限られます。</span><span class="sxs-lookup"><span data-stu-id="1426a-119">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="1426a-120">値が宣言で初期化される場合。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="1426a-120">When the variable is initialized in the declaration, for example:</span></span>

```csharp
public readonly int y = 5;
```

- <span data-ttu-id="1426a-121">インスタンス フィールド宣言を含むクラスのインスタンス コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="1426a-121">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="1426a-122">静的フィールド宣言を含むクラスの静的コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="1426a-122">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="1426a-123">また、これらのコンストラクター コンテキスト内でのみ、`readonly` フィールドを [out](out-parameter-modifier.md) パラメーターまたは [ref](ref.md) パラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="1426a-123">These constructor contexts are also the only contexts in which it is valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="1426a-124">`readonly` キーワードは [const](const.md) キーワードとは異なります。</span><span class="sxs-lookup"><span data-stu-id="1426a-124">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="1426a-125">`const` フィールドは、フィールドの宣言でしか初期化できません。</span><span class="sxs-lookup"><span data-stu-id="1426a-125">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="1426a-126">`readonly` フィールドは、フィールドの宣言と任意のコンストラクターで複数回割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="1426a-126">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="1426a-127">このため、`readonly` フィールドは、使用するコンストラクターに応じて異なる値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="1426a-127">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="1426a-128">また、次の例のように、`const` フィールドがコンパイル時定数であるのに対し、`readonly` フィールドは実行時定数として使用できます。</span><span class="sxs-lookup"><span data-stu-id="1426a-128">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for runtime constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="1426a-129">上の例で、次の例のようなステートメントを使うものとします。</span><span class="sxs-lookup"><span data-stu-id="1426a-129">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="1426a-130">この場合、次のコンパイル エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1426a-130">you will get the compiler error message:</span></span>

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a><span data-ttu-id="1426a-131">読み取り専用の構造体の例</span><span class="sxs-lookup"><span data-stu-id="1426a-131">Readonly struct example</span></span>

<span data-ttu-id="1426a-132">`struct` 定義での `readonly` 修飾子は、構造体が**変更不可**であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="1426a-132">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="1426a-133">次の例のように、`struct` のすべてのインスタンス フィールドを `readonly` とマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1426a-133">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="1426a-134">前の例では、[読み取り専用の自動プロパティ](../../properties.md#read-only)を使ってその記憶域を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="1426a-134">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="1426a-135">これは、これらのプロパティに対して `readonly` バッキング フィールドを作成するようコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="1426a-135">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="1426a-136">`readonly` フィールドを直接宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="1426a-136">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="1426a-137">`readonly` に指定されていないフィールドを追加すると、コンパイラ エラー `CS8340`:"読み取り専用の構造体のインスタンス フィールドは、読み取り専用である必要があります" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="1426a-137">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="1426a-138">ref readonly の戻り値の例</span><span class="sxs-lookup"><span data-stu-id="1426a-138">Ref readonly return example</span></span>

<span data-ttu-id="1426a-139">`ref return` での `readonly` 修飾子は、返される参照を変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1426a-139">The `readonly` modifier on a `ref return` indicates that the returned reference cannot be modified.</span></span> <span data-ttu-id="1426a-140">次の例は、origin に参照を返します。</span><span class="sxs-lookup"><span data-stu-id="1426a-140">The following example returns a reference to the origin.</span></span> <span data-ttu-id="1426a-141">`readonly` 修飾子を使用して、呼び出し元が origin を変更できないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="1426a-141">It uses the `readonly` modifier to indicate that callers cannot modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="1426a-142">返される型を `readonly struct` にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1426a-142">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="1426a-143">`ref` で返すことができる任意の型を、`ref readonly` で返すことができます。</span><span class="sxs-lookup"><span data-stu-id="1426a-143">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1426a-144">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="1426a-144">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1426a-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="1426a-145">See also</span></span>

- [<span data-ttu-id="1426a-146">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="1426a-146">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1426a-147">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="1426a-147">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1426a-148">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="1426a-148">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1426a-149">修飾子</span><span class="sxs-lookup"><span data-stu-id="1426a-149">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="1426a-150">const</span><span class="sxs-lookup"><span data-stu-id="1426a-150">const</span></span>](const.md)
- [<span data-ttu-id="1426a-151">フィールド</span><span class="sxs-lookup"><span data-stu-id="1426a-151">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
