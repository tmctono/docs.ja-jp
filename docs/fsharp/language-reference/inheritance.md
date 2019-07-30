---
title: 継承
description: "'Inherit' キーワードを使用して F# 継承リレーションシップを指定する方法について説明します。"
ms.date: 05/16/2016
ms.openlocfilehash: 5ab891a93528427a66e4eb8f7bfeccbf6e4d2c7e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627667"
---
# <a name="inheritance"></a><span data-ttu-id="dc474-103">継承</span><span class="sxs-lookup"><span data-stu-id="dc474-103">Inheritance</span></span>

<span data-ttu-id="dc474-104">継承は、オブジェクト指向プログラミングの "the a" リレーションシップ (サブタイプ) をモデル化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc474-104">Inheritance is used to model the "is-a" relationship, or subtyping, in object-oriented programming.</span></span>

## <a name="specifying-inheritance-relationships"></a><span data-ttu-id="dc474-105">継承関係の指定</span><span class="sxs-lookup"><span data-stu-id="dc474-105">Specifying Inheritance Relationships</span></span>

<span data-ttu-id="dc474-106">継承関係を指定するには`inherit` 、クラス宣言でキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc474-106">You specify inheritance relationships by using the `inherit` keyword in a class declaration.</span></span> <span data-ttu-id="dc474-107">基本的な構文形式を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="dc474-107">The basic syntactical form is shown in the following example.</span></span>

```fsharp
type MyDerived(...) =
    inherit MyBase(...)
```

<span data-ttu-id="dc474-108">クラスは、最大で1つの直接基底クラスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="dc474-108">A class can have at most one direct base class.</span></span> <span data-ttu-id="dc474-109">`inherit`キーワードを使用して基底クラスを指定しない場合、クラスはから`System.Object`暗黙的に継承されます。</span><span class="sxs-lookup"><span data-stu-id="dc474-109">If you do not specify a base class by using the `inherit` keyword, the class implicitly inherits from `System.Object`.</span></span>

## <a name="inherited-members"></a><span data-ttu-id="dc474-110">継承されたメンバー</span><span class="sxs-lookup"><span data-stu-id="dc474-110">Inherited Members</span></span>

<span data-ttu-id="dc474-111">クラスが別のクラスから継承する場合、派生クラスのユーザーは、派生クラスの直接のメンバーであるかのように、基底クラスのメソッドとメンバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="dc474-111">If a class inherits from another class, the methods and members of the base class are available to users of the derived class as if they were direct members of the derived class.</span></span>

<span data-ttu-id="dc474-112">いずれかの let バインドとコンストラクターのパラメーターは、クラスに対してプライベートであるため、派生クラスからアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dc474-112">Any let bindings and constructor parameters are private to a class and, therefore, cannot be accessed from derived classes.</span></span>

<span data-ttu-id="dc474-113">キーワード`base`は、派生クラスで使用でき、基底クラスのインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="dc474-113">The keyword `base` is available in derived classes and refers to the base class instance.</span></span> <span data-ttu-id="dc474-114">これは、自己識別子のように使用されます。</span><span class="sxs-lookup"><span data-stu-id="dc474-114">It is used like the self-identifier.</span></span>

## <a name="virtual-methods-and-overrides"></a><span data-ttu-id="dc474-115">仮想メソッドとオーバーライド</span><span class="sxs-lookup"><span data-stu-id="dc474-115">Virtual Methods and Overrides</span></span>

<span data-ttu-id="dc474-116">仮想メソッド (およびプロパティ) 動作は少し異なります F# で他の .NET 言語と比較しています。</span><span class="sxs-lookup"><span data-stu-id="dc474-116">Virtual methods (and properties) work somewhat differently in F# as compared to other .NET languages.</span></span> <span data-ttu-id="dc474-117">新しい仮想メンバーを宣言するには、 `abstract`キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="dc474-117">To declare a new virtual member, you use the `abstract` keyword.</span></span> <span data-ttu-id="dc474-118">この操作は、そのメソッドの既定の実装を提供するかどうかに関係なく行います。</span><span class="sxs-lookup"><span data-stu-id="dc474-118">You do this regardless of whether you provide a default implementation for that method.</span></span> <span data-ttu-id="dc474-119">したがって、基本クラスの仮想メソッドの完全な定義は、次のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="dc474-119">Thus a complete definition of a virtual method in a base class follows this pattern:</span></span>

```fsharp
abstract member [method-name] : [type]

default [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="dc474-120">派生クラスでは、この仮想メソッドのオーバーライドは次のパターンに従います。</span><span class="sxs-lookup"><span data-stu-id="dc474-120">And in a derived class, an override of this virtual method follows this pattern:</span></span>

```fsharp
override [self-identifier].[method-name] [argument-list] = [method-body]
```

<span data-ttu-id="dc474-121">基本クラスで既定の実装を省略した場合、基本クラスは抽象クラスになります。</span><span class="sxs-lookup"><span data-stu-id="dc474-121">If you omit the default implementation in the base class, the base class becomes an abstract class.</span></span>

<span data-ttu-id="dc474-122">基底クラスでの新しい仮想メソッド`function1`の宣言と、派生クラスでオーバーライドする方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="dc474-122">The following code example illustrates the declaration of a new virtual method `function1` in a base class and how to override it in a derived class.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2601.fs)]

## <a name="constructors-and-inheritance"></a><span data-ttu-id="dc474-123">コンストラクターと継承</span><span class="sxs-lookup"><span data-stu-id="dc474-123">Constructors and Inheritance</span></span>

<span data-ttu-id="dc474-124">基底クラスのコンストラクターは、派生クラスで呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc474-124">The constructor for the base class must be called in the derived class.</span></span> <span data-ttu-id="dc474-125">基底クラスのコンストラクターの引数は、 `inherit`句の引数リストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc474-125">The arguments for the base class constructor appear in the argument list in the `inherit` clause.</span></span> <span data-ttu-id="dc474-126">使用される値は、派生クラスのコンストラクターに渡される引数から決定される必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc474-126">The values that are used must be determined from the arguments supplied to the derived class constructor.</span></span>

<span data-ttu-id="dc474-127">次のコードは、基底クラスと派生クラスを示しています。派生クラスは、継承句で基底クラスのコンストラクターを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dc474-127">The following code shows a base class and a derived class, where the derived class calls the base class constructor in the inherit clause:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2602.fs)]

<span data-ttu-id="dc474-128">複数のコンストラクターの場合、次のコードを使用していることができます。</span><span class="sxs-lookup"><span data-stu-id="dc474-128">In the case of multiple constructors, the following code can be used.</span></span> <span data-ttu-id="dc474-129">派生クラスのコンストラクターの最初の行は、`inherit`句と、フィールドで宣言された明示的なフィールドとして表示されます、`val`キーワード。</span><span class="sxs-lookup"><span data-stu-id="dc474-129">The first line of the derived class constructors is the `inherit` clause, and the fields appear as explicit fields that are declared with the `val` keyword.</span></span> <span data-ttu-id="dc474-130">詳細については、次を参照してください。[明示的なフィールド:`val`キーワード](./members/explicit-fields-the-val-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="dc474-130">For more information, see [Explicit Fields: The `val` Keyword](./members/explicit-fields-the-val-keyword.md).</span></span>

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

## <a name="alternatives-to-inheritance"></a><span data-ttu-id="dc474-131">継承の代替手段</span><span class="sxs-lookup"><span data-stu-id="dc474-131">Alternatives to Inheritance</span></span>

<span data-ttu-id="dc474-132">型の軽微な変更が必要な場合は、継承の代わりにオブジェクト式を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dc474-132">In cases where a minor modification of a type is required, consider using an object expression as an alternative to inheritance.</span></span> <span data-ttu-id="dc474-133">次の例は、新しい派生型を作成する代わりに、オブジェクト式を使用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc474-133">The following example illustrates the use of an object expression as an alternative to creating a new derived type:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2603.fs)]

<span data-ttu-id="dc474-134">オブジェクト式の詳細については、「[オブジェクト式](object-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc474-134">For more information about object expressions, see [Object Expressions](object-expressions.md).</span></span>

<span data-ttu-id="dc474-135">オブジェクト階層を作成する場合は、継承の代わりに判別共用体を使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dc474-135">When you are creating object hierarchies, consider using a discriminated union instead of inheritance.</span></span> <span data-ttu-id="dc474-136">判別共用体は、一般的な全体の種類を共有するさまざまなオブジェクトのさまざまな動作をモデル化することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc474-136">Discriminated unions can also model varied behavior of different objects that share a common overall type.</span></span> <span data-ttu-id="dc474-137">単一の判別共用体を使用すると、多くの場合、相互に軽微なバリエーションを持つ多数の派生クラスが不要になります。</span><span class="sxs-lookup"><span data-stu-id="dc474-137">A single discriminated union can often eliminate the need for a number of derived classes that are minor variations of each other.</span></span> <span data-ttu-id="dc474-138">判別共用体の詳細については、「[判別共用体](discriminated-unions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc474-138">For information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dc474-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc474-139">See also</span></span>

- [<span data-ttu-id="dc474-140">オブジェクト式</span><span class="sxs-lookup"><span data-stu-id="dc474-140">Object Expressions</span></span>](object-expressions.md)
- [<span data-ttu-id="dc474-141">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="dc474-141">F# Language Reference</span></span>](index.md)
