---
description: readonly キーワード - C# リファレンス
title: readonly キーワード - C# リファレンス
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: b1bab5af18216fcef2162179493dbbb59e3470cf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137176"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="b0dda-103">readonly (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b0dda-103">readonly (C# Reference)</span></span>

<span data-ttu-id="b0dda-104">`readonly` キーワードは、次の 4 つのコンテキストで使用できる修飾子です。</span><span class="sxs-lookup"><span data-stu-id="b0dda-104">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="b0dda-105">[フィールドの宣言](#readonly-field-example)では、`readonly` は、フィールドへの割り当てが、宣言の一部として、または同じクラスのコンストラクター内でのみ可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-105">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="b0dda-106">readonly フィールドは、フィールドの宣言とコンストラクターで複数回割り当ておよび再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-106">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="b0dda-107">`readonly` フィールドは、コンストラクターが終了した後で割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-107">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="b0dda-108">この規則は、値型と参照型では意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="b0dda-108">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="b0dda-109">値型にはそのデータが直接含まれるため、`readonly` 値型のフィールドは変更できません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-109">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="b0dda-110">参照型にはそのデータへの参照が含まれるため、`readonly` 参照型のフィールドは、常に同じオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b0dda-110">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="b0dda-111">そのオブジェクトは不変ではありません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-111">That object isn't immutable.</span></span> <span data-ttu-id="b0dda-112">`readonly` 修飾子があると、フィールドを参照型の別のインスタンスで置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-112">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="b0dda-113">ただし、フィールドのインスタンス データを読み取り専用フィールドで変更することは禁止されません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-113">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="b0dda-114">変更可能な参照型である外部から参照できる読み取り専用フィールドを含む外部から参照できる型はセキュリティの脆弱性があり、警告 [CA2104](/visualstudio/code-quality/ca2104) がトリガーされる可能性があります: "読み取り専用の変更可能な参照型を宣言しません"。</span><span class="sxs-lookup"><span data-stu-id="b0dda-114">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="b0dda-115">`readonly struct` 型定義では、`readonly` は構造体型が変更不可であることを示します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-115">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="b0dda-116">詳細については、「[構造体型](../builtin-types/struct.md)」の記事の「[`readonly` 構造体](../builtin-types/struct.md#readonly-struct)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0dda-116">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="b0dda-117">構造体型内のインスタンス メンバー宣言では、`readonly` は、インスタンス メンバーによって構造体の状態が変更されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-117">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="b0dda-118">詳細については、[構造体型](../builtin-types/struct.md)に関する記事の「[`readonly` インスタンス メンバー](../builtin-types/struct.md#readonly-instance-members)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0dda-118">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="b0dda-119">[`ref readonly` メソッドの戻り値](#ref-readonly-return-example)では、`readonly` 修飾子は、メソッドが参照を返し、その参照への書き込みが許可されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-119">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="b0dda-120">`readonly struct` と `ref readonly` のコンテキストは、C# 7.2 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="b0dda-120">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="b0dda-121">`readonly` 構造体メンバーは、C# 8.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="b0dda-121">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="b0dda-122">読み取り専用フィールドの例</span><span class="sxs-lookup"><span data-stu-id="b0dda-122">Readonly field example</span></span>

<span data-ttu-id="b0dda-123">この例では、`year` フィールドの値は、クラス コンストラクターで値が割り当てられていても `ChangeYear` メソッドでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-123">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="b0dda-124">`readonly` のフィールドに値を割り当てることができるのは、次のコンテキスト内に限られます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-124">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="b0dda-125">値が宣言で初期化される場合。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-125">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="b0dda-126">インスタンス フィールド宣言を含むクラスのインスタンス コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="b0dda-126">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="b0dda-127">静的フィールド宣言を含むクラスの静的コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="b0dda-127">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="b0dda-128">また、これらのコンストラクター コンテキスト内でのみ、`readonly` フィールドを [out](out-parameter-modifier.md) パラメーターまたは [ref](ref.md) パラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-128">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="b0dda-129">`readonly` キーワードは [const](const.md) キーワードとは異なります。</span><span class="sxs-lookup"><span data-stu-id="b0dda-129">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="b0dda-130">`const` フィールドは、フィールドの宣言でしか初期化できません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-130">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="b0dda-131">`readonly` フィールドは、フィールドの宣言と任意のコンストラクターで複数回割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-131">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="b0dda-132">このため、`readonly` フィールドは、使用するコンストラクターに応じて異なる値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-132">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="b0dda-133">また、次の例のように、`const` フィールドがコンパイル時定数であるのに対し、`readonly` フィールドは実行時定数として使用できます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-133">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="b0dda-134">上の例で、次の例のようなステートメントを使うものとします。</span><span class="sxs-lookup"><span data-stu-id="b0dda-134">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="b0dda-135">この場合、次のコンパイル エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-135">you'll get the compiler error message:</span></span>

<span data-ttu-id="b0dda-136">**読み取り専用フィールドに割り当てることはできません (コンストラクター、変数初期化子では可)**</span><span class="sxs-lookup"><span data-stu-id="b0dda-136">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="b0dda-137">ref readonly の戻り値の例</span><span class="sxs-lookup"><span data-stu-id="b0dda-137">Ref readonly return example</span></span>

<span data-ttu-id="b0dda-138">`ref return`での `readonly` 修飾子は、返される参照を変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-138">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="b0dda-139">次の例は、origin に参照を返します。</span><span class="sxs-lookup"><span data-stu-id="b0dda-139">The following example returns a reference to the origin.</span></span> <span data-ttu-id="b0dda-140">`readonly` 修飾子を使用して、呼び出し元が origin を変更できないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="b0dda-140">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="b0dda-141">返される型を `readonly struct` にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b0dda-141">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="b0dda-142">`ref` で返すことができる任意の型を、`ref readonly` で返すことができます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-142">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b0dda-143">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="b0dda-143">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="b0dda-144">言語仕様の提案を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="b0dda-144">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="b0dda-145">readonly ref と readonly struct</span><span class="sxs-lookup"><span data-stu-id="b0dda-145">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="b0dda-146">readonly 構造体メンバー</span><span class="sxs-lookup"><span data-stu-id="b0dda-146">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="b0dda-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="b0dda-147">See also</span></span>

- [<span data-ttu-id="b0dda-148">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="b0dda-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b0dda-149">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="b0dda-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b0dda-150">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="b0dda-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b0dda-151">修飾子</span><span class="sxs-lookup"><span data-stu-id="b0dda-151">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b0dda-152">const</span><span class="sxs-lookup"><span data-stu-id="b0dda-152">const</span></span>](const.md)
- [<span data-ttu-id="b0dda-153">フィールド</span><span class="sxs-lookup"><span data-stu-id="b0dda-153">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
