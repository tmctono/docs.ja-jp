---
title: readonly キーワード - C# リファレンス
ms.date: 03/26/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 344d5e54fcd500e283c52fa7953c6366823f13f0
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345150"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="17b48-102">readonly (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="17b48-102">readonly (C# Reference)</span></span>

<span data-ttu-id="17b48-103">`readonly` キーワードは、次の 4 つのコンテキストで使用できる修飾子です。</span><span class="sxs-lookup"><span data-stu-id="17b48-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="17b48-104">[フィールドの宣言](#readonly-field-example)では、`readonly` は、フィールドへの割り当てが、宣言の一部として、または同じクラスのコンストラクター内でのみ可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="17b48-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="17b48-105">readonly フィールドは、フィールドの宣言とコンストラクターで複数回割り当ておよび再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="17b48-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="17b48-106">`readonly` フィールドは、コンストラクターが終了した後で割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="17b48-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="17b48-107">この規則は、値型と参照型では意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="17b48-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="17b48-108">値型にはそのデータが直接含まれるため、`readonly` 値型のフィールドは変更できません。</span><span class="sxs-lookup"><span data-stu-id="17b48-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="17b48-109">参照型にはそのデータへの参照が含まれるため、`readonly` 参照型のフィールドは、常に同じオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17b48-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="17b48-110">そのオブジェクトは不変ではありません。</span><span class="sxs-lookup"><span data-stu-id="17b48-110">That object isn't immutable.</span></span> <span data-ttu-id="17b48-111">`readonly` 修飾子があると、フィールドを参照型の別のインスタンスで置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="17b48-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="17b48-112">ただし、フィールドのインスタンス データを読み取り専用フィールドで変更することは禁止されません。</span><span class="sxs-lookup"><span data-stu-id="17b48-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="17b48-113">変更可能な参照型である外部から参照できる読み取り専用フィールドを含む外部から参照できる型はセキュリティの脆弱性があり、警告 [CA2104](/visualstudio/code-quality/ca2104) がトリガーされる可能性があります: "読み取り専用の変更可能な参照型を宣言しません"。</span><span class="sxs-lookup"><span data-stu-id="17b48-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="17b48-114">`readonly struct` 型定義では、`readonly` は構造体型が変更不可であることを示します。</span><span class="sxs-lookup"><span data-stu-id="17b48-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="17b48-115">詳細については、「[構造体型](../builtin-types/struct.md)」の記事の「[`readonly` 構造体](../builtin-types/struct.md#readonly-struct)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17b48-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="17b48-116">[`readonly` メンバー定義](#readonly-member-examples)では、`readonly`は、`struct` のメンバーが構造体の内部状態を変更しないことを示します。</span><span class="sxs-lookup"><span data-stu-id="17b48-116">In a [`readonly` member definition](#readonly-member-examples), `readonly` indicates that a member of a `struct` doesn't mutate the struct's internal state.</span></span>
- <span data-ttu-id="17b48-117">[`ref readonly` メソッドの戻り値](#ref-readonly-return-example)では、`readonly` 修飾子は、メソッドが参照を返し、その参照への書き込みが許可されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="17b48-117">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="17b48-118">`readonly struct` と `ref readonly` のコンテキストは、C# 7.2 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="17b48-118">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="17b48-119">`readonly` 構造体メンバーは、C# 8.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="17b48-119">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="17b48-120">読み取り専用フィールドの例</span><span class="sxs-lookup"><span data-stu-id="17b48-120">Readonly field example</span></span>

<span data-ttu-id="17b48-121">この例では、`year` フィールドの値は、クラス コンストラクターで値が割り当てられていても `ChangeYear` メソッドでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="17b48-121">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="17b48-122">`readonly` のフィールドに値を割り当てることができるのは、次のコンテキスト内に限られます。</span><span class="sxs-lookup"><span data-stu-id="17b48-122">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="17b48-123">値が宣言で初期化される場合。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="17b48-123">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="17b48-124">インスタンス フィールド宣言を含むクラスのインスタンス コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="17b48-124">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="17b48-125">静的フィールド宣言を含むクラスの静的コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="17b48-125">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="17b48-126">また、これらのコンストラクター コンテキスト内でのみ、`readonly` フィールドを [out](out-parameter-modifier.md) パラメーターまたは [ref](ref.md) パラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="17b48-126">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="17b48-127">`readonly` キーワードは [const](const.md) キーワードとは異なります。</span><span class="sxs-lookup"><span data-stu-id="17b48-127">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="17b48-128">`const` フィールドは、フィールドの宣言でしか初期化できません。</span><span class="sxs-lookup"><span data-stu-id="17b48-128">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="17b48-129">`readonly` フィールドは、フィールドの宣言と任意のコンストラクターで複数回割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="17b48-129">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="17b48-130">このため、`readonly` フィールドは、使用するコンストラクターに応じて異なる値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="17b48-130">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="17b48-131">また、次の例のように、`const` フィールドがコンパイル時定数であるのに対し、`readonly` フィールドは実行時定数として使用できます。</span><span class="sxs-lookup"><span data-stu-id="17b48-131">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="17b48-132">上の例で、次の例のようなステートメントを使うものとします。</span><span class="sxs-lookup"><span data-stu-id="17b48-132">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="17b48-133">この場合、次のコンパイル エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17b48-133">you'll get the compiler error message:</span></span>

<span data-ttu-id="17b48-134">**読み取り専用フィールドに割り当てることはできません (コンストラクター、変数初期化子では可)**</span><span class="sxs-lookup"><span data-stu-id="17b48-134">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="readonly-member-examples"></a><span data-ttu-id="17b48-135">読み取り専用メンバーの例</span><span class="sxs-lookup"><span data-stu-id="17b48-135">Readonly member examples</span></span>

<span data-ttu-id="17b48-136">また、変更をサポートする構造体を作成する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="17b48-136">Other times, you may create a struct that supports mutation.</span></span> <span data-ttu-id="17b48-137">このような場合、一部のインスタンス メンバーは、構造体の内部状態を変更しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17b48-137">In those cases, several of the instance members likely won't modify the internal state of the struct.</span></span> <span data-ttu-id="17b48-138">`readonly` を使用すると、これらのインスタンス メンバーを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="17b48-138">You can declare those instance members with the `readonly` modifier.</span></span> <span data-ttu-id="17b48-139">コンパイラによって意図が適用されます。</span><span class="sxs-lookup"><span data-stu-id="17b48-139">The compiler enforces your intent.</span></span> <span data-ttu-id="17b48-140">そのメンバーが状態を直接変更したり、`readonly` 修飾子で宣言されていないメンバーにもアクセスしたりすると、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="17b48-140">If that member modifies state directly or accesses a member that isn't also declared with the `readonly` modifier, the result is a compile-time error.</span></span> <span data-ttu-id="17b48-141">`readonly` 修飾子は、`class` メンバー宣言または `interface` メンバー宣言ではなく `struct` メンバーで有効です。</span><span class="sxs-lookup"><span data-stu-id="17b48-141">The `readonly` modifier is valid on `struct` members, not `class` or `interface` member declarations.</span></span>

<span data-ttu-id="17b48-142">`readonly` 修飾子を適用可能な `struct` メソッドに適用すると、2 つの利点が得られます。</span><span class="sxs-lookup"><span data-stu-id="17b48-142">You gain two advantages by applying the `readonly` modifier to applicable `struct` methods.</span></span> <span data-ttu-id="17b48-143">最も重要なのは、コンパイラによって意図が適用されることです。</span><span class="sxs-lookup"><span data-stu-id="17b48-143">Most importantly, the compiler enforces your intent.</span></span> <span data-ttu-id="17b48-144">状態を変更するコードは、`readonly` では有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="17b48-144">Code that modifies state isn't valid in a `readonly` method.</span></span> <span data-ttu-id="17b48-145">コンパイラは、`readonly` 修飾子を使用してパフォーマンスの最適化を有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="17b48-145">The compiler may also make use of the `readonly` modifier to enable performance optimizations.</span></span> <span data-ttu-id="17b48-146">大きな `struct` 型が `in` 参照によって渡された場合、構造体の状態が変更される可能性があれば、コンパイルは防御用のコピーを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17b48-146">When large `struct` types are passed by `in` reference, the compiler must generate a defensive copy if the state of the struct might be modified.</span></span> <span data-ttu-id="17b48-147">`readonly` メンバーのみがアクセスされる場合、コンパイラは防御用のコピーを作成しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17b48-147">If only `readonly` members are accessed, the compiler may not create the defensive copy.</span></span>

<span data-ttu-id="17b48-148">`readonly` 修飾子は、<xref:System.Object?displayProperty=nameWithType> で宣言されたメソッドをオーバーライドするメソッドを含めて、`struct` のほとんどのメンバーで有効です。</span><span class="sxs-lookup"><span data-stu-id="17b48-148">The `readonly` modifier is valid on most members of a `struct`, including methods that override methods declared in <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="17b48-149">いくつかの制限があります。</span><span class="sxs-lookup"><span data-stu-id="17b48-149">There are some restrictions:</span></span>

- <span data-ttu-id="17b48-150">`readonly` 静的メソッドまたはプロパティを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="17b48-150">You can't declare `readonly` static methods or properties.</span></span>
- <span data-ttu-id="17b48-151">`readonly` コンストラクターを宣言することはできません。</span><span class="sxs-lookup"><span data-stu-id="17b48-151">You can't declare `readonly` constructors.</span></span>

<span data-ttu-id="17b48-152">`readonly` をプロパティ宣言またはインデクサー宣言に追加できます。</span><span class="sxs-lookup"><span data-stu-id="17b48-152">You can add the `readonly` modifier to a property or indexer declaration:</span></span>

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

<span data-ttu-id="17b48-153">また、`readonly` 修飾子をプロパティまたはインデクサーの個々の `get` アクセサーまたは `set` アクセサーに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="17b48-153">You may also add the `readonly` modifier to individual `get` or `set` accessors of a property or indexer:</span></span>

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

<span data-ttu-id="17b48-154">`readonly` 修飾子をプロパティと、その同じプロパティの 1 つ以上のアクセサーの両方に追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="17b48-154">You may not add the `readonly` modifier to both a property and one or more of that same property's accessors.</span></span> <span data-ttu-id="17b48-155">同じ制限がインデクサーにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="17b48-155">That same restriction applies to indexers.</span></span>

<span data-ttu-id="17b48-156">コンパイラによって実装されたコードが状態を変更しない場合、コンパイラは `readonly` 修飾子を自動実装プロパティに暗黙的に適用します。</span><span class="sxs-lookup"><span data-stu-id="17b48-156">The compiler implicitly applies the `readonly` modifier to auto-implemented properties where the compiler implemented code doesn't modify state.</span></span> <span data-ttu-id="17b48-157">これは次の宣言と同等です。</span><span class="sxs-lookup"><span data-stu-id="17b48-157">It's equivalent to the following declarations:</span></span>

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

<span data-ttu-id="17b48-158">これらの場所に `readonly` 修飾子を追加できますが、有意義な効果はありません。</span><span class="sxs-lookup"><span data-stu-id="17b48-158">You may add the `readonly` modifier in those locations, but it will have no meaningful effect.</span></span> <span data-ttu-id="17b48-159">`readonly` 修飾子を自動実装プロパティのセッター、または読み取り/書き込み自動実装プロパティに追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="17b48-159">You may not add the `readonly` modifier to an auto-implemented property setter, or to a read/write auto-implemented property.</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="17b48-160">ref readonly の戻り値の例</span><span class="sxs-lookup"><span data-stu-id="17b48-160">Ref readonly return example</span></span>

<span data-ttu-id="17b48-161">`ref return`での `readonly` 修飾子は、返される参照を変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="17b48-161">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="17b48-162">次の例は、origin に参照を返します。</span><span class="sxs-lookup"><span data-stu-id="17b48-162">The following example returns a reference to the origin.</span></span> <span data-ttu-id="17b48-163">`readonly` 修飾子を使用して、呼び出し元が origin を変更できないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="17b48-163">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="17b48-164">返される型を `readonly struct` にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17b48-164">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="17b48-165">`ref` で返すことができる任意の型を、`ref readonly` で返すことができます。</span><span class="sxs-lookup"><span data-stu-id="17b48-165">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="17b48-166">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="17b48-166">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="17b48-167">言語仕様の提案を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="17b48-167">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="17b48-168">readonly ref と readonly struct</span><span class="sxs-lookup"><span data-stu-id="17b48-168">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="17b48-169">readonly 構造体メンバー</span><span class="sxs-lookup"><span data-stu-id="17b48-169">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="17b48-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="17b48-170">See also</span></span>

- [<span data-ttu-id="17b48-171">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="17b48-171">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="17b48-172">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="17b48-172">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="17b48-173">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="17b48-173">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="17b48-174">修飾子</span><span class="sxs-lookup"><span data-stu-id="17b48-174">Modifiers</span></span>](index.md)
- [<span data-ttu-id="17b48-175">const</span><span class="sxs-lookup"><span data-stu-id="17b48-175">const</span></span>](const.md)
- [<span data-ttu-id="17b48-176">フィールド</span><span class="sxs-lookup"><span data-stu-id="17b48-176">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
