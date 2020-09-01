---
description: new 修飾子 - C# リファレンス
title: new 修飾子 - C# リファレンス
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 2da0a360868250169fb16380c80bf32c4b335d7a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139412"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="dc64e-103">new 修飾子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="dc64e-103">new modifier (C# Reference)</span></span>

<span data-ttu-id="dc64e-104">`new` キーワードを宣言の修飾子として使用すると、基底クラスから継承されたメンバーを明示的に隠ぺいできます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-104">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="dc64e-105">継承されたメンバーを隠ぺいすると、派生バージョンのメンバーで基底クラスのバージョンが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-105">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="dc64e-106">`new` 修飾子を使わずにメンバーを隠ぺいすることもできますが、コンパイラ警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-106">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="dc64e-107">メンバーを明示的に隠ぺいするために `new` を使用する場合は、この警告が抑制されます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-107">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="dc64e-108">`new` キーワードは、[型のインスタンスの作成](../operators/new-operator.md)に使用することも、または[ジェネリック型制約](./new-constraint.md)として使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-108">You can also use the `new` keyword to [create an instance of a type](../operators/new-operator.md) or as a [generic type constraint](./new-constraint.md).</span></span>

<span data-ttu-id="dc64e-109">継承されたメンバーを隠ぺいするには、派生クラスで同じメンバー名を使用してメンバーを宣言し、`new` キーワードで修飾します。</span><span class="sxs-lookup"><span data-stu-id="dc64e-109">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="dc64e-110">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dc64e-110">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="dc64e-111">この例では、`BaseC.Invoke` は `DerivedC.Invoke` で隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-111">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="dc64e-112">`x` フィールドは、似た名前によって隠ぺいされないため、影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="dc64e-112">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="dc64e-113">継承による名前の隠ぺいは、次のいずれかの形式で行われます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-113">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="dc64e-114">一般的に、定数、フィールド、プロパティ、型をクラスまたは構造体で使用すると、同じ名前を共有するすべての基底クラス メンバーが隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-114">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span> <span data-ttu-id="dc64e-115">次のような特殊な状況があります。</span><span class="sxs-lookup"><span data-stu-id="dc64e-115">There are special cases.</span></span> <span data-ttu-id="dc64e-116">たとえば、呼び出し可能ではない型を持つ `N` という名前の新しいフィールドを宣言し、基本型が `N` をメソッドとして宣言する場合は、新しいフィールドが呼び出し構文内で基本型の宣言を隠ぺいすることはありません。</span><span class="sxs-lookup"><span data-stu-id="dc64e-116">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span> <span data-ttu-id="dc64e-117">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[メンバー ルックアップ](~/_csharplang/spec/expressions.md#member-lookup)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc64e-117">For more information, see the [Member lookup](~/_csharplang/spec/expressions.md#member-lookup) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

- <span data-ttu-id="dc64e-118">メソッドをクラスまたは構造体で使用すると、基底クラスで同じ名前を共有するプロパティ、フィールド、型が隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-118">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="dc64e-119">また、同じシグネチャを持つすべての基底クラス メソッドも隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-119">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="dc64e-120">インデクサーをクラスまたは構造体で使用すると、同じシグネチャを持つすべての基底クラス インデクサーが隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-120">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="dc64e-121">`new` と [override](override.md) には相反する意味があるため、同じメンバーにこの 2 つの修飾子を使用するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="dc64e-121">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="dc64e-122">`new` 修飾子は、同じ名前で新しいメンバーを作成し、元のメンバーを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="dc64e-122">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="dc64e-123">`override` 修飾子は、継承されたメンバーの実装を拡張します。</span><span class="sxs-lookup"><span data-stu-id="dc64e-123">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="dc64e-124">宣言で、継承されたメンバーを隠ぺいしない `new` 修飾子を使用すると、警告が出力されます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-124">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="dc64e-125">例</span><span class="sxs-lookup"><span data-stu-id="dc64e-125">Example</span></span>

<span data-ttu-id="dc64e-126">この例では、基底クラス `BaseC` と派生クラス `DerivedC` が同じフィールド名 `x` を使用するため、継承されるフィールドの値が隠ぺいされます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-126">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="dc64e-127">この例では、`new` 修飾子の使い方を示します。</span><span class="sxs-lookup"><span data-stu-id="dc64e-127">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="dc64e-128">また、基底クラスの隠ぺいされたメンバーに完全修飾名を使ってアクセスする方法も示します。</span><span class="sxs-lookup"><span data-stu-id="dc64e-128">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="dc64e-129">例</span><span class="sxs-lookup"><span data-stu-id="dc64e-129">Example</span></span>

<span data-ttu-id="dc64e-130">この例では、入れ子になったクラスが、基底クラスにある同名のクラスを隠ぺいします。</span><span class="sxs-lookup"><span data-stu-id="dc64e-130">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="dc64e-131">この例では、`new` 修飾子を使って警告メッセージが表示されないようにする方法に加えて、完全修飾名を使用してクラスの隠ぺいされたメンバーにアクセスする方法も示します。</span><span class="sxs-lookup"><span data-stu-id="dc64e-131">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="dc64e-132">`new` 修飾子を削除すると、プログラムのコンパイルおよび実行は行われますが、次の警告が出力されます。</span><span class="sxs-lookup"><span data-stu-id="dc64e-132">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```text
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="dc64e-133">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="dc64e-133">C# language specification</span></span>

<span data-ttu-id="dc64e-134">詳細については、[C# 言語仕様](~/_csharplang/spec/introduction.md)の「[new 修飾子](~/_csharplang/spec/classes.md#the-new-modifier)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc64e-134">For more information, see [The new modifier](~/_csharplang/spec/classes.md#the-new-modifier) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc64e-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc64e-135">See also</span></span>

- [<span data-ttu-id="dc64e-136">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="dc64e-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dc64e-137">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="dc64e-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc64e-138">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="dc64e-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dc64e-139">修飾子</span><span class="sxs-lookup"><span data-stu-id="dc64e-139">Modifiers</span></span>](index.md)
- [<span data-ttu-id="dc64e-140">Override キーワードと New キーワードによるバージョン管理</span><span class="sxs-lookup"><span data-stu-id="dc64e-140">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="dc64e-141">Override キーワードと New キーワードを使用する場合について</span><span class="sxs-lookup"><span data-stu-id="dc64e-141">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
