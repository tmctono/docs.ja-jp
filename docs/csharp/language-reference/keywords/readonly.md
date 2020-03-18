---
title: readonly キーワード - C# リファレンス
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 165b6287e1610e013b289601e1535a08fdd3b5c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398125"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="b4645-102">readonly (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b4645-102">readonly (C# Reference)</span></span>

<span data-ttu-id="b4645-103">`readonly` キーワードは、次の 4 つのコンテキストで使用できる修飾子です。</span><span class="sxs-lookup"><span data-stu-id="b4645-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="b4645-104">[フィールドの宣言](#readonly-field-example)では、`readonly` は、フィールドへの割り当てが、宣言の一部として、または同じクラスのコンストラクター内でのみ可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="b4645-105">readonly フィールドは、フィールドの宣言とコンストラクターで複数回割り当ておよび再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b4645-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="b4645-106">`readonly` フィールドは、コンストラクターが終了した後で割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b4645-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="b4645-107">この規則は、値型と参照型では意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="b4645-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="b4645-108">値型にはそのデータが直接含まれるため、`readonly` 値型のフィールドは変更できません。</span><span class="sxs-lookup"><span data-stu-id="b4645-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="b4645-109">参照型にはそのデータへの参照が含まれるため、`readonly` 参照型のフィールドは、常に同じオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4645-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="b4645-110">そのオブジェクトは不変ではありません。</span><span class="sxs-lookup"><span data-stu-id="b4645-110">That object isn't immutable.</span></span> <span data-ttu-id="b4645-111">`readonly` 修飾子があると、フィールドを参照型の別のインスタンスで置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="b4645-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="b4645-112">ただし、フィールドのインスタンス データを読み取り専用フィールドで変更することは禁止されません。</span><span class="sxs-lookup"><span data-stu-id="b4645-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="b4645-113">変更可能な参照型である外部から参照できる読み取り専用フィールドを含む外部から参照できる型はセキュリティの脆弱性があり、警告 [CA2104](/visualstudio/code-quality/ca2104) がトリガーされる可能性があります: "読み取り専用の変更可能な参照型を宣言しません"。</span><span class="sxs-lookup"><span data-stu-id="b4645-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="b4645-114">[`readonly struct` の定義](#readonly-struct-example)では、`readonly` は `struct` が変更不可であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-114">In a [`readonly struct` definition](#readonly-struct-example), `readonly` indicates that the `struct` is immutable.</span></span>
- <span data-ttu-id="b4645-115">[`readonly` メンバー定義](#readonly-member-examples)では、`readonly`は、`struct` のメンバーが構造体の内部状態を変更しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-115">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="b4645-116">[`ref readonly` メソッドの戻り値](#ref-readonly-return-example)では、`readonly` 修飾子は、メソッドが参照を返し、その参照への書き込みが許可されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-116">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="b4645-117">`readonly struct` と `ref readonly` のコンテキストは、C# 7.2 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="b4645-117">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="b4645-118">`readonly` 構造体メンバーは、C# 8.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="b4645-118">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="b4645-119">読み取り専用フィールドの例</span><span class="sxs-lookup"><span data-stu-id="b4645-119">Readonly field example</span></span>

<span data-ttu-id="b4645-120">この例では、`year` フィールドの値は、クラス コンストラクターで値が割り当てられていても `ChangeYear` メソッドでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="b4645-120">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="b4645-121">`readonly` のフィールドに値を割り当てることができるのは、次のコンテキスト内に限られます。</span><span class="sxs-lookup"><span data-stu-id="b4645-121">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="b4645-122">値が宣言で初期化される場合。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-122">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="b4645-123">インスタンス フィールド宣言を含むクラスのインスタンス コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="b4645-123">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="b4645-124">静的フィールド宣言を含むクラスの静的コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="b4645-124">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="b4645-125">また、これらのコンストラクター コンテキスト内でのみ、`readonly` フィールドを [out](out-parameter-modifier.md) パラメーターまたは [ref](ref.md) パラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b4645-125">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="b4645-126">`readonly` キーワードは [const](const.md) キーワードとは異なります。</span><span class="sxs-lookup"><span data-stu-id="b4645-126">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="b4645-127">`const` フィールドは、フィールドの宣言でしか初期化できません。</span><span class="sxs-lookup"><span data-stu-id="b4645-127">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="b4645-128">`readonly` フィールドは、フィールドの宣言と任意のコンストラクターで複数回割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b4645-128">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="b4645-129">このため、`readonly` フィールドは、使用するコンストラクターに応じて異なる値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="b4645-129">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="b4645-130">また、次の例のように、`const` フィールドがコンパイル時定数であるのに対し、`readonly` フィールドは実行時定数として使用できます。</span><span class="sxs-lookup"><span data-stu-id="b4645-130">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="b4645-131">上の例で、次の例のようなステートメントを使うものとします。</span><span class="sxs-lookup"><span data-stu-id="b4645-131">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="b4645-132">この場合、次のコンパイル エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4645-132">you'll get the compiler error message:</span></span>

<span data-ttu-id="b4645-133">**読み取り専用フィールドに割り当てることはできません (コンストラクター、変数初期化子では可)**</span><span class="sxs-lookup"><span data-stu-id="b4645-133">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-struct-example"></a><span data-ttu-id="b4645-134">読み取り専用の構造体の例</span><span class="sxs-lookup"><span data-stu-id="b4645-134">Readonly struct example</span></span>

<span data-ttu-id="b4645-135">`struct` 定義での `readonly` 修飾子は、構造体が**変更不可**であることを宣言します。</span><span class="sxs-lookup"><span data-stu-id="b4645-135">The `readonly` modifier on a `struct` definition declares that the struct is **immutable**.</span></span> <span data-ttu-id="b4645-136">次の例のように、`struct` のすべてのインスタンス フィールドを `readonly` とマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4645-136">Every instance field of the `struct` must be marked `readonly`, as shown in the following example:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

<span data-ttu-id="b4645-137">前の例では、[読み取り専用の自動プロパティ](../../properties.md#read-only)を使ってその記憶域を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="b4645-137">The preceding example uses [readonly auto properties](../../properties.md#read-only) to declare its storage.</span></span> <span data-ttu-id="b4645-138">これは、これらのプロパティに対して `readonly` バッキング フィールドを作成するようコンパイラに指示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-138">That instructs the compiler to create `readonly` backing fields for those properties.</span></span> <span data-ttu-id="b4645-139">`readonly` フィールドを直接宣言することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4645-139">You could also declare `readonly` fields directly:</span></span>

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

<span data-ttu-id="b4645-140">`readonly` に指定されていないフィールドを追加すると、コンパイラ エラー `CS8340`:"読み取り専用の構造体のインスタンス フィールドは、読み取り専用である必要があります" が生成されます。</span><span class="sxs-lookup"><span data-stu-id="b4645-140">Adding a field not marked `readonly` generates compiler error `CS8340`: "Instance fields of readonly structs must be readonly."</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="b4645-141">読み取り専用メンバーの例</span><span class="sxs-lookup"><span data-stu-id="b4645-141">Readonly member examples</span></span>

<span data-ttu-id="b4645-142">また、変更をサポートする構造体を作成する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b4645-142">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="b4645-143">このような場合、一部のインスタンス メンバーは、構造体の内部状態を変更しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4645-143">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="b4645-144">`readonly` を使用すると、これらのインスタンス メンバーを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="b4645-144">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="b4645-145">コンパイラによって意図が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4645-145">The compiler enforces your intent.</span></span> <span data-ttu-id="b4645-146">そのメンバーが状態を直接変更したり、`readonly` 修飾子で宣言されていないメンバーにもアクセスしたりすると、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="b4645-146">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="b4645-147">`readonly` 修飾子は、`class` メンバー宣言または `interface` メンバー宣言ではなく `struct` メンバーで有効です。</span><span class="sxs-lookup"><span data-stu-id="b4645-147">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="b4645-148">`readonly` 修飾子を適用可能な `struct` メソッドに適用すると、2 つの利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="b4645-148">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="b4645-149">最も重要なのは、コンパイラによって意図が適用されることです。</span><span class="sxs-lookup"><span data-stu-id="b4645-149">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="b4645-150">状態を変更するコードは、`readonly` では有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="b4645-150">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="b4645-151">コンパイラは、`readonly` 修飾子を使用してパフォーマンスの最適化を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b4645-151">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="b4645-152">大きな `struct` 型が `in` 参照によって渡された場合、構造体の状態が変更される可能性があれば、コンパイルは防御用のコピーを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4645-152">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="b4645-153">`readonly` メンバーのみがアクセスされる場合、コンパイラは防御用のコピーを作成しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4645-153">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="b4645-154">`readonly` 修飾子は、<xref:System.Object?displayProperty=nameWithType> で宣言されたメソッドをオーバーライドするメソッドを含めて、`struct` のほとんどのメンバーで有効です。</span><span class="sxs-lookup"><span data-stu-id="b4645-154">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4645-155">いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="b4645-155">There are some restrictions:</span></span>

- <span data-ttu-id="b4645-156">`readonly` 静的メソッドまたはプロパティを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4645-156">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="b4645-157">`readonly` コンストラクターを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4645-157">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="b4645-158">`readonly` をプロパティ宣言またはインデクサー宣言に追加できます。</span><span class="sxs-lookup"><span data-stu-id="b4645-158">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="b4645-159">また、`readonly` 修飾子をプロパティまたはインデクサーの個々の `get` アクセサーまたは `set` アクセサーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4645-159">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="b4645-160">`readonly` 修飾子をプロパティと、その同じプロパティの 1 つ以上のアクセサーの両方に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4645-160">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="b4645-161">同じ制限がインデクサーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4645-161">That same restriction applies to indexers.</span></span>

<span data-ttu-id="b4645-162">コンパイラによって実装されたコードが状態を変更しない場合、コンパイラは `readonly` 修飾子を自動実装プロパティに暗黙的に適用します。</span><span class="sxs-lookup"><span data-stu-id="b4645-162">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="b4645-163">これは次の宣言と同等です。</span><span class="sxs-lookup"><span data-stu-id="b4645-163">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

<span data-ttu-id="b4645-164">これらの場所に `readonly` 修飾子を追加できますが、有意義な効果はありません。</span><span class="sxs-lookup"><span data-stu-id="b4645-164">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="b4645-165">`readonly` 修飾子を自動実装プロパティのセッター、または読み取り/書き込み自動実装プロパティに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="b4645-165">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="b4645-166">ref readonly の戻り値の例</span><span class="sxs-lookup"><span data-stu-id="b4645-166">Ref readonly return example</span></span>

<span data-ttu-id="b4645-167">`ref return`での `readonly` 修飾子は、返される参照を変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b4645-167">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="b4645-168">次の例は、origin に参照を返します。</span><span class="sxs-lookup"><span data-stu-id="b4645-168">The following example returns a reference to the origin.</span></span> <span data-ttu-id="b4645-169">`readonly` 修飾子を使用して、呼び出し元が origin を変更できないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4645-169">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
<span data-ttu-id="b4645-170">返される型を `readonly struct` にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b4645-170">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="b4645-171">`ref` で返すことができる任意の型を、`ref readonly` で返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b4645-171">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b4645-172">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b4645-172">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="b4645-173">言語仕様の提案を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4645-173">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="b4645-174">readonly ref と readonly struct</span><span class="sxs-lookup"><span data-stu-id="b4645-174">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="b4645-175">readonly 構造体メンバー</span><span class="sxs-lookup"><span data-stu-id="b4645-175">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="b4645-176">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4645-176">See also</span></span>

- [<span data-ttu-id="b4645-177">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b4645-177">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b4645-178">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b4645-178">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b4645-179">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b4645-179">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b4645-180">修飾子</span><span class="sxs-lookup"><span data-stu-id="b4645-180">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b4645-181">const</span><span class="sxs-lookup"><span data-stu-id="b4645-181">const</span></span>](const.md)
- [<span data-ttu-id="b4645-182">フィールド</span><span class="sxs-lookup"><span data-stu-id="b4645-182">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
