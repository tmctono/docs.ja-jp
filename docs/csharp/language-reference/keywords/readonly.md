---
title: readonly キーワード - C# リファレンス
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 03b0aa63eda3e7a9d8745baaa33479fd5e85b01b
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389058"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="6eccf-102">readonly (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="6eccf-102">readonly (C# Reference)</span></span>

<span data-ttu-id="6eccf-103">`readonly` キーワードは、次の 4 つのコンテキストで使用できる修飾子です。</span><span class="sxs-lookup"><span data-stu-id="6eccf-103">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="6eccf-104">[フィールドの宣言](#readonly-field-example)では、`readonly` は、フィールドへの割り当てが、宣言の一部として、または同じクラスのコンストラクター内でのみ可能であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-104">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="6eccf-105">readonly フィールドは、フィールドの宣言とコンストラクターで複数回割り当ておよび再割り当てを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-105">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="6eccf-106">`readonly` フィールドは、コンストラクターが終了した後で割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-106">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="6eccf-107">この規則は、値型と参照型では意味が異なります。</span><span class="sxs-lookup"><span data-stu-id="6eccf-107">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="6eccf-108">値型にはそのデータが直接含まれるため、`readonly` 値型のフィールドは変更できません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-108">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="6eccf-109">参照型にはそのデータへの参照が含まれるため、`readonly` 参照型のフィールドは、常に同じオブジェクトを参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6eccf-109">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="6eccf-110">そのオブジェクトは不変ではありません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-110">That object isn't immutable.</span></span> <span data-ttu-id="6eccf-111">`readonly` 修飾子があると、フィールドを参照型の別のインスタンスで置き換えることはできません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-111">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="6eccf-112">ただし、フィールドのインスタンス データを読み取り専用フィールドで変更することは禁止されません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-112">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="6eccf-113">変更可能な参照型である外部から参照できる読み取り専用フィールドを含む外部から参照できる型はセキュリティの脆弱性があり、警告 [CA2104](/visualstudio/code-quality/ca2104) がトリガーされる可能性があります: "読み取り専用の変更可能な参照型を宣言しません"。</span><span class="sxs-lookup"><span data-stu-id="6eccf-113">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="6eccf-114">`readonly struct` 型定義では、`readonly` は構造体型が変更不可であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-114">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="6eccf-115">詳細については、「[構造体型](../builtin-types/struct.md)」の記事の「[`readonly` 構造体](../builtin-types/struct.md#readonly-struct)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eccf-115">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="6eccf-116">構造体型内のインスタンス メンバー宣言では、`readonly` は、インスタンス メンバーによって構造体の状態が変更されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-116">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="6eccf-117">詳細については、[構造体型](../builtin-types/struct.md)に関する記事の「[`readonly` インスタンス メンバー](../builtin-types/struct.md#readonly-instance-members)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6eccf-117">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="6eccf-118">[`ref readonly` メソッドの戻り値](#ref-readonly-return-example)では、`readonly` 修飾子は、メソッドが参照を返し、その参照への書き込みが許可されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-118">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="6eccf-119">`readonly struct` と `ref readonly` のコンテキストは、C# 7.2 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="6eccf-119">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="6eccf-120">`readonly` 構造体メンバーは、C# 8.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="6eccf-120">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="6eccf-121">読み取り専用フィールドの例</span><span class="sxs-lookup"><span data-stu-id="6eccf-121">Readonly field example</span></span>

<span data-ttu-id="6eccf-122">この例では、`year` フィールドの値は、クラス コンストラクターで値が割り当てられていても `ChangeYear` メソッドでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-122">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="6eccf-123">`readonly` のフィールドに値を割り当てることができるのは、次のコンテキスト内に限られます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-123">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="6eccf-124">値が宣言で初期化される場合。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-124">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="6eccf-125">インスタンス フィールド宣言を含むクラスのインスタンス コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="6eccf-125">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="6eccf-126">静的フィールド宣言を含むクラスの静的コンストラクター内。</span><span class="sxs-lookup"><span data-stu-id="6eccf-126">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="6eccf-127">また、これらのコンストラクター コンテキスト内でのみ、`readonly` フィールドを [out](out-parameter-modifier.md) パラメーターまたは [ref](ref.md) パラメーターとして渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-127">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="6eccf-128">`readonly` キーワードは [const](const.md) キーワードとは異なります。</span><span class="sxs-lookup"><span data-stu-id="6eccf-128">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="6eccf-129">`const` フィールドは、フィールドの宣言でしか初期化できません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-129">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="6eccf-130">`readonly` フィールドは、フィールドの宣言と任意のコンストラクターで複数回割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-130">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="6eccf-131">このため、`readonly` フィールドは、使用するコンストラクターに応じて異なる値を持つことができます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-131">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="6eccf-132">また、次の例のように、`const` フィールドがコンパイル時定数であるのに対し、`readonly` フィールドは実行時定数として使用できます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-132">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="6eccf-133">上の例で、次の例のようなステートメントを使うものとします。</span><span class="sxs-lookup"><span data-stu-id="6eccf-133">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="6eccf-134">この場合、次のコンパイル エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-134">you'll get the compiler error message:</span></span>

<span data-ttu-id="6eccf-135">**読み取り専用フィールドに割り当てることはできません (コンストラクター、変数初期化子では可)**</span><span class="sxs-lookup"><span data-stu-id="6eccf-135">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="6eccf-136">ref readonly の戻り値の例</span><span class="sxs-lookup"><span data-stu-id="6eccf-136">Ref readonly return example</span></span>

<span data-ttu-id="6eccf-137">`ref return`での `readonly` 修飾子は、返される参照を変更できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-137">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="6eccf-138">次の例は、origin に参照を返します。</span><span class="sxs-lookup"><span data-stu-id="6eccf-138">The following example returns a reference to the origin.</span></span> <span data-ttu-id="6eccf-139">`readonly` 修飾子を使用して、呼び出し元が origin を変更できないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="6eccf-139">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="6eccf-140">返される型を `readonly struct` にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6eccf-140">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="6eccf-141">`ref` で返すことができる任意の型を、`ref readonly` で返すことができます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-141">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6eccf-142">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="6eccf-142">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="6eccf-143">言語仕様の提案を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="6eccf-143">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="6eccf-144">readonly ref と readonly struct</span><span class="sxs-lookup"><span data-stu-id="6eccf-144">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="6eccf-145">readonly 構造体メンバー</span><span class="sxs-lookup"><span data-stu-id="6eccf-145">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="6eccf-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="6eccf-146">See also</span></span>

- [<span data-ttu-id="6eccf-147">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="6eccf-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6eccf-148">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="6eccf-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6eccf-149">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="6eccf-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6eccf-150">修飾子</span><span class="sxs-lookup"><span data-stu-id="6eccf-150">Modifiers</span></span>](index.md)
- [<span data-ttu-id="6eccf-151">const</span><span class="sxs-lookup"><span data-stu-id="6eccf-151">const</span></span>](const.md)
- [<span data-ttu-id="6eccf-152">フィールド</span><span class="sxs-lookup"><span data-stu-id="6eccf-152">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
