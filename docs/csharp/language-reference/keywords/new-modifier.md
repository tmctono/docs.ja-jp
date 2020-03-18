---
title: new 修飾子 - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 6c4fedd469efb79f91780dff26da89b586de2d1c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713342"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="dc243-102">new 修飾子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dc243-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="dc243-103">`new` キーワードを宣言の修飾子として使用すると、基底クラスから継承されたメンバーを明示的に隠ぺいできます。</span><span class="sxs-lookup"><span data-stu-id="dc243-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="dc243-104">継承されたメンバーを隠ぺいすると、派生バージョンのメンバーで基底クラスのバージョンが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="dc243-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="dc243-105">`new` 修飾子を使わずにメンバーを隠ぺいすることもできますが、コンパイラ警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc243-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="dc243-106">メンバーを明示的に隠ぺいするために `new` を使用する場合は、この警告が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="dc243-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="dc243-107">`new` キーワードは、[型のインスタンスの作成](../operators/new-operator.md)に使用することも、または[ジェネリック型制約](./new-constraint.md)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc243-107">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [generic type constraint](./new-constraint.md).</span></span>

<span data-ttu-id="dc243-108">継承されたメンバーを隠ぺいするには、派生クラスで同じメンバー名を使用してメンバーを宣言し、`new` キーワードで修飾します。</span><span class="sxs-lookup"><span data-stu-id="dc243-108">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="dc243-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dc243-109">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="dc243-110">この例では、`BaseC.Invoke` は `DerivedC.Invoke` で隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc243-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="dc243-111">`x` フィールドは、似た名前によって隠ぺいされないため、影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="dc243-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="dc243-112">継承による名前の隠ぺいは、次のいずれかの形式で行われます。</span><span class="sxs-lookup"><span data-stu-id="dc243-112">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="dc243-113">一般的に、定数、フィールド、プロパティ、型をクラスまたは構造体で使用すると、同じ名前を共有するすべての基底クラス メンバーが隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc243-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span> <span data-ttu-id="dc243-114">次のような特殊な状況があります。</span><span class="sxs-lookup"><span data-stu-id="dc243-114">There are special cases.</span></span> <span data-ttu-id="dc243-115">たとえば、呼び出し可能ではない型を持つ `N` という名前の新しいフィールドを宣言し、基本型が `N` をメソッドとして宣言する場合は、新しいフィールドが呼び出し構文内で基本型の宣言を隠ぺいすることはありません。</span><span class="sxs-lookup"><span data-stu-id="dc243-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span> <span data-ttu-id="dc243-116">詳細については、[C# 言語仕様](~/_csharplang/spec/expressions.md#member-lookup)の「[メンバー ルックアップ](~/_csharplang/spec/introduction.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc243-116">For more information, see the [Member lookup](~/_csharplang/spec/expressions.md#member-lookup) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="dc243-117">メソッドをクラスまたは構造体で使用すると、基底クラスで同じ名前を共有するプロパティ、フィールド、型が隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc243-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="dc243-118">また、同じシグネチャを持つすべての基底クラス メソッドも隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc243-118">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="dc243-119">インデクサーをクラスまたは構造体で使用すると、同じシグネチャを持つすべての基底クラス インデクサーが隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc243-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="dc243-120">`new` と [override](override.md) には相反する意味があるため、同じメンバーにこの 2 つの修飾子を使用するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="dc243-120">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="dc243-121">`new` 修飾子は、同じ名前で新しいメンバーを作成し、元のメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="dc243-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="dc243-122">`override` 修飾子は、継承されたメンバーの実装を拡張します。</span><span class="sxs-lookup"><span data-stu-id="dc243-122">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="dc243-123">宣言で、継承されたメンバーを隠ぺいしない `new` 修飾子を使用すると、警告が出力されます。</span><span class="sxs-lookup"><span data-stu-id="dc243-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="dc243-124">例</span><span class="sxs-lookup"><span data-stu-id="dc243-124">Example</span></span>

<span data-ttu-id="dc243-125">この例では、基底クラス `BaseC` と派生クラス `DerivedC` が同じフィールド名 `x` を使用するため、継承されるフィールドの値が隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc243-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="dc243-126">この例では、`new` 修飾子の使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="dc243-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="dc243-127">また、基底クラスの隠ぺいされたメンバーに完全修飾名を使ってアクセスする方法も示します。</span><span class="sxs-lookup"><span data-stu-id="dc243-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="dc243-128">例</span><span class="sxs-lookup"><span data-stu-id="dc243-128">Example</span></span>

<span data-ttu-id="dc243-129">この例では、入れ子になったクラスが、基底クラスにある同名のクラスを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="dc243-129">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="dc243-130">この例では、`new` 修飾子を使って警告メッセージが表示されないようにする方法に加えて、完全修飾名を使用してクラスの隠ぺいされたメンバーにアクセスする方法も示します。</span><span class="sxs-lookup"><span data-stu-id="dc243-130">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="dc243-131">`new` 修飾子を削除すると、プログラムのコンパイルおよび実行は行われますが、次の警告が出力されます。</span><span class="sxs-lookup"><span data-stu-id="dc243-131">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="dc243-132">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="dc243-132">C# language specification</span></span>

<span data-ttu-id="dc243-133">詳細については、[C# 言語仕様](~/_csharplang/spec/classes.md#the-new-modifier)の「[new 修飾子](~/_csharplang/spec/introduction.md)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc243-133">For more information, see [The new modifier](~/_csharplang/spec/classes.md#the-new-modifier) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc243-134">参照</span><span class="sxs-lookup"><span data-stu-id="dc243-134">See also</span></span>

- [<span data-ttu-id="dc243-135">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="dc243-135">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="dc243-136">C# プログラミングガイド</span><span class="sxs-lookup"><span data-stu-id="dc243-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc243-137">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="dc243-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dc243-138">修飾子</span><span class="sxs-lookup"><span data-stu-id="dc243-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="dc243-139">Override キーワードと New キーワードによるバージョン管理</span><span class="sxs-lookup"><span data-stu-id="dc243-139">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="dc243-140">Override キーワードと New キーワードを使用する場合について</span><span class="sxs-lookup"><span data-stu-id="dc243-140">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
