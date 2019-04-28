---
title: 継承
description: "'Inherit' キーワードを使用して F# 継承リレーションシップを指定する方法について説明します。"
ms.date: 05/16/2016
ms.openlocfilehash: 775ee52039caf4c4ab65f82fa21d4e536135a12a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937463"
---
# <a name="inheritance"></a><span data-ttu-id="61ac5-103">継承</span><span class="sxs-lookup"><span data-stu-id="61ac5-103">Inheritance</span></span>

<span data-ttu-id="61ac5-104">継承の使用を「の」リレーションシップをモデル オブジェクト指向プログラミングでは、サブタイプまたはします。</span><span class="sxs-lookup"><span data-stu-id="61ac5-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="61ac5-105">継承リレーションシップの指定</span><span class="sxs-lookup"><span data-stu-id="61ac5-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="61ac5-106">使用して継承リレーションシップを指定する、`inherit`クラス宣言でキーワード。</span><span class="sxs-lookup"><span data-stu-id="61ac5-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="61ac5-107">基本的な構文形式は、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="61ac5-108">クラスは、最大で 1 つ直接基底クラスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="61ac5-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="61ac5-109">使用して基底クラスを指定しないかどうか、`inherit`キーワード、クラスから暗黙的に継承`System.Object`します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="61ac5-110">継承されたメンバー</span><span class="sxs-lookup"><span data-stu-id="61ac5-110">Inherited Members</span></span>

<span data-ttu-id="61ac5-111">クラスは、別のクラスから継承している場合、メソッドと基底クラスのメンバーは場合、派生クラスの直接のメンバーと同様に、派生クラスのユーザーに公開します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="61ac5-112">いずれかの let バインドとコンストラクターのパラメーターは、クラスに対してプライベートであるため、派生クラスからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="61ac5-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="61ac5-113">キーワード`base`は派生クラスで使用でき、基本クラスのインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="61ac5-114">これは、自己識別子のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="61ac5-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="61ac5-115">仮想メソッドとオーバーライド</span><span class="sxs-lookup"><span data-stu-id="61ac5-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="61ac5-116">仮想メソッド (およびプロパティ) 動作は少し異なります F# で他の .NET 言語と比較しています。</span><span class="sxs-lookup"><span data-stu-id="61ac5-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="61ac5-117">使用する新しい仮想メンバーを宣言する、`abstract`キーワード。</span><span class="sxs-lookup"><span data-stu-id="61ac5-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="61ac5-118">この操作は、そのメソッドの既定の実装を提供するかどうかに関係なく行います。</span><span class="sxs-lookup"><span data-stu-id="61ac5-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="61ac5-119">したがって、基底クラス仮想メソッドの完全な定義では、このパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="61ac5-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="61ac5-120">この仮想メソッドのオーバーライドを派生クラスでこのパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="61ac5-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="61ac5-121">基底クラスの既定の実装を省略した場合、基底クラスは抽象クラスになります。</span><span class="sxs-lookup"><span data-stu-id="61ac5-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="61ac5-122">次のコード例は、新しい仮想メソッドの宣言を示しています。`function1`で基底クラスと派生クラスでオーバーライドする方法。</span><span class="sxs-lookup"><span data-stu-id="61ac5-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="61ac5-123">コンストラクターと継承</span><span class="sxs-lookup"><span data-stu-id="61ac5-123">Constructors and Inheritance</span></span>

<span data-ttu-id="61ac5-124">派生クラスでは、基底クラスのコンス トラクターを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="61ac5-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="61ac5-125">基底クラスのコンス トラクターの引数、引数のリストに表示、`inherit`句。</span><span class="sxs-lookup"><span data-stu-id="61ac5-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="61ac5-126">使用される値は、派生クラスのコンス トラクターに指定された引数から決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61ac5-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="61ac5-127">次のコードは基底クラスと派生クラスでは、派生クラスが継承句の基本クラス コンス トラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="61ac5-128">複数のコンス トラクターの場合、次のコードを使用していることができます。</span><span class="sxs-lookup"><span data-stu-id="61ac5-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="61ac5-129">派生クラスのコンス トラクターの最初の行は、`inherit`句と、フィールドで宣言された明示的なフィールドとして表示されます、`val`キーワード。</span><span class="sxs-lookup"><span data-stu-id="61ac5-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="61ac5-130">詳細については、次を参照してください。[明示的なフィールド:`val`キーワード](members/explicit-fields-the-val-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-130">For more information, see [Explicit Fields: The `val` Keyword](members/explicit-fields-the-val-keyword.md).</span></span>

```fsharp
type BaseClass =
    val string1 : string
    new (str) = { string1 = str }
    new () = { string1 = "" }

type DerivedClass =
    inherit BaseClass

    val string2 : string
    new (str1, str2) = { inherit BaseClass(str1); string2 = str2 }
    new (str2) = { inherit BaseClass(); string2 = str2 }

let obj1 = DerivedClass("A", "B")
let obj2 = DerivedClass("A")
```

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="61ac5-131">継承の代替手段</span><span class="sxs-lookup"><span data-stu-id="61ac5-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="61ac5-132">型の若干の変更が必要な場合は、継承する代わりにオブジェクト式の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="61ac5-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="61ac5-133">次の例は、新しい派生型を作成する代わりにオブジェクト式の使用を示しています。</span><span class="sxs-lookup"><span data-stu-id="61ac5-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="61ac5-134">オブジェクトの式の詳細については、次を参照してください。[オブジェクト式](object-expressions.md)します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="61ac5-135">オブジェクト階層を作成するときは、継承ではなくの判別共用体の使用を検討します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="61ac5-136">判別共用体は、共通の全体的な型を共有する別のオブジェクトのさまざまなモデルの動作でこともできます。</span><span class="sxs-lookup"><span data-stu-id="61ac5-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="61ac5-137">1 つの判別共用体では、さまざまな派生クラスの他のわずかな違いをする必要がある多くの場合。</span><span class="sxs-lookup"><span data-stu-id="61ac5-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="61ac5-138">判別共用体の詳細については、次を参照してください。[判別共用体](discriminated-unions.md)します。</span><span class="sxs-lookup"><span data-stu-id="61ac5-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="61ac5-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="61ac5-139">See also</span></span>

- [<span data-ttu-id="61ac5-140">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="61ac5-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="61ac5-141">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="61ac5-141">F# Language Reference</span></span>](index.md)