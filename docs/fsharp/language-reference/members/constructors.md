---
title: コンストラクター
description: でF#コンストラクターを定義および使用して、クラスおよび構造体オブジェクトを作成および初期化する方法について説明します。
ms.date: 05/16/2016
ms.openlocfilehash: 6769ec7fc6768090d8ae68e21946a58829b6eea0
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736848"
---
# <a name="constructors"></a><span data-ttu-id="cf803-103">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="cf803-103">Constructors</span></span>

<span data-ttu-id="cf803-104">この記事では、コンストラクターを定義および使用して、クラスオブジェクトと構造体オブジェクトを作成および初期化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf803-104">This article describes how to define and use constructors to create and initialize class and structure objects.</span></span>

## <a name="construction-of-class-objects"></a><span data-ttu-id="cf803-105">クラスオブジェクトの構築</span><span class="sxs-lookup"><span data-stu-id="cf803-105">Construction of class objects</span></span>

<span data-ttu-id="cf803-106">クラス型のオブジェクトにはコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="cf803-106">Objects of class types have constructors.</span></span> <span data-ttu-id="cf803-107">コンストラクターには、次の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="cf803-107">There are two kinds of constructors.</span></span> <span data-ttu-id="cf803-108">1つはプライマリコンストラクターであり、パラメーターは型名の直後にかっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="cf803-108">One is the primary constructor, whose parameters appear in parentheses just after the type name.</span></span> <span data-ttu-id="cf803-109">`new`キーワードを使用して、その他のオプションの追加コンストラクターを指定します。</span><span class="sxs-lookup"><span data-stu-id="cf803-109">You specify other, optional additional constructors by using the `new` keyword.</span></span> <span data-ttu-id="cf803-110">このような追加のコンストラクターは、プライマリコンストラクターを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf803-110">Any such additional constructors must call the primary constructor.</span></span>

<span data-ttu-id="cf803-111">プライマリコンストラクターには`let` 、 `do`クラス定義の先頭に表示されるバインディングとバインドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf803-111">The primary constructor contains `let` and `do` bindings that appear at the start of the class definition.</span></span> <span data-ttu-id="cf803-112">バインディング`let`は、クラスのプライベートフィールドおよびメソッドを宣言し`do`ます。バインディングはコードを実行します。</span><span class="sxs-lookup"><span data-stu-id="cf803-112">A `let` binding declares private fields and methods of the class; a `do` binding executes code.</span></span> <span data-ttu-id="cf803-113">クラスコンストラクター内の`let`バインディングの詳細については、「 [ `let`クラスのバインディング](let-bindings-in-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf803-113">For more information about `let` bindings in class constructors, see [`let` Bindings in Classes](let-bindings-in-classes.md).</span></span> <span data-ttu-id="cf803-114">コンストラクターでの`do`バインディングの詳細については、「 [ `do`クラスのバインディング](do-bindings-in-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf803-114">For more information about `do` bindings in constructors, see [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

<span data-ttu-id="cf803-115">呼び出すコンストラクターがプライマリコンストラクターであるか、追加のコンストラクターであるかに関係なく、 `new`式を使用してオブジェクトを作成できます。これには、省略可能`new`なキーワードを指定するかどうかにかかわらず、式を使用します。</span><span class="sxs-lookup"><span data-stu-id="cf803-115">Regardless of whether the constructor you want to call is a primary constructor or an additional constructor, you can create objects by using a `new` expression, with or without the optional `new` keyword.</span></span> <span data-ttu-id="cf803-116">オブジェクトをコンストラクター引数と共に初期化するには、引数の順序を指定してコンマで区切り、かっこで囲むか、名前付き引数と値をかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="cf803-116">You initialize your objects together with constructor arguments, either by listing the arguments in order and separated by commas and enclosed in parentheses, or by using named arguments and values in parentheses.</span></span> <span data-ttu-id="cf803-117">また、プロパティ名を使用し、名前付きコンストラクター引数を使用するのと同じように値を割り当てることによって、オブジェクトの構築中にオブジェクトのプロパティを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf803-117">You can also set properties on an object during the construction of the object by using the property names and assigning values just as you use named constructor arguments.</span></span>

<span data-ttu-id="cf803-118">次のコードは、コンストラクターとオブジェクトを作成するさまざまな方法を持つクラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="cf803-118">The following code illustrates a class that has a constructor and various ways of creating objects:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3501.fs)]

<span data-ttu-id="cf803-119">出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cf803-119">The output is as follows:</span></span>

```console
Initialized object that has coordinates (1, 2, 3)
Initialized object that has coordinates (4, 5, 6)
Initialized object that has coordinates (7, 8, 9)
Initialized object that has coordinates (0, 0, 0)
```

## <a name="construction-of-structures"></a><span data-ttu-id="cf803-120">構造体の構築</span><span class="sxs-lookup"><span data-stu-id="cf803-120">Construction of structures</span></span>

<span data-ttu-id="cf803-121">構造体は、クラスのすべての規則に従います。</span><span class="sxs-lookup"><span data-stu-id="cf803-121">Structures follow all the rules of classes.</span></span> <span data-ttu-id="cf803-122">したがって、プライマリコンストラクターを持つことができます。また、を使用`new`して追加のコンストラクターを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf803-122">Therefore, you can have a primary constructor, and you can provide additional constructors by using `new`.</span></span> <span data-ttu-id="cf803-123">ただし、構造体とクラスには1つの重要な違いがあります。構造体には、プライマリコンストラクターが定義されていない場合でも、パラメーターなしのコンストラクター (つまり、引数なし) を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cf803-123">However, there is one important difference between structures and classes: structures can have a parameterless constructor (that is, one with no arguments) even if no primary constructor is defined.</span></span> <span data-ttu-id="cf803-124">パラメーターなしのコンストラクターは、すべてのフィールドをその型の既定値 (通常は0またはそれと等価) に初期化します。</span><span class="sxs-lookup"><span data-stu-id="cf803-124">The parameterless constructor initializes all the fields to the default value for that type, usually zero or its equivalent.</span></span> <span data-ttu-id="cf803-125">構造体に対して定義するコンストラクターには、パラメーターなしのコンストラクターと競合しないように、少なくとも1つの引数が必要です。</span><span class="sxs-lookup"><span data-stu-id="cf803-125">Any constructors that you define for structures must have at least one argument so that they do not conflict with the parameterless constructor.</span></span>

<span data-ttu-id="cf803-126">また、多くの場合、構造体には`val`キーワードを使用して作成されたフィールドがあります。クラスにはこれらのフィールドも含まれます。</span><span class="sxs-lookup"><span data-stu-id="cf803-126">Also, structures often have fields that are created by using the `val` keyword; classes can also have these fields.</span></span> <span data-ttu-id="cf803-127">`val`キーワードを使用して定義されたフィールドを持つ構造体とクラスは、次のコードに示すように、レコード式を使用して追加のコンストラクターで初期化することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf803-127">Structures and classes that have fields defined by using the `val` keyword can also be initialized in additional constructors by using record expressions, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3502.fs)]

<span data-ttu-id="cf803-128">詳細については、次を参照してください。[明示的なフィールド:`val`キーワード](explicit-fields-the-val-keyword.md)します。</span><span class="sxs-lookup"><span data-stu-id="cf803-128">For more information, see [Explicit Fields: The `val` Keyword](explicit-fields-the-val-keyword.md).</span></span>

## <a name="executing-side-effects-in-constructors"></a><span data-ttu-id="cf803-129">コンストラクターでの副作用の実行</span><span class="sxs-lookup"><span data-stu-id="cf803-129">Executing side effects in constructors</span></span>

<span data-ttu-id="cf803-130">クラスのプライマリコンストラクターは、 `do`バインディングでコードを実行できます。</span><span class="sxs-lookup"><span data-stu-id="cf803-130">A primary constructor in a class can execute code in a `do` binding.</span></span> <span data-ttu-id="cf803-131">ただし、 `do`バインドせずに、追加のコンストラクターでコードを実行する必要がある場合はどうすればよいでしょうか。</span><span class="sxs-lookup"><span data-stu-id="cf803-131">However, what if you have to execute code in an additional constructor, without a `do` binding?</span></span> <span data-ttu-id="cf803-132">これを行うには、 `then`キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf803-132">To do this, you use the `then` keyword.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3503.fs)]

<span data-ttu-id="cf803-133">プライマリコンストラクターの副作用は引き続き実行されます。</span><span class="sxs-lookup"><span data-stu-id="cf803-133">The side effects of the primary constructor still execute.</span></span> <span data-ttu-id="cf803-134">したがって、出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf803-134">Therefore, the output is as follows:</span></span>

```console
Created a person object.
Created a person object.
Created an invalid person object.
```

## <a name="self-identifiers-in-constructors"></a><span data-ttu-id="cf803-135">コンストラクター内の自己識別子</span><span class="sxs-lookup"><span data-stu-id="cf803-135">Self identifiers in constructors</span></span>

<span data-ttu-id="cf803-136">他のメンバーでは、各メンバーの定義で現在のオブジェクトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cf803-136">In other members, you provide a name for the current object in the definition of each member.</span></span> <span data-ttu-id="cf803-137">コンストラクターのパラメーターの直後に`as`キーワードを使用して、クラス定義の最初の行に自己識別子を配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf803-137">You can also put the self identifier on the first line of the class definition by using the `as` keyword immediately following the constructor parameters.</span></span> <span data-ttu-id="cf803-138">この構文の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cf803-138">The following example illustrates this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3504.fs)]

<span data-ttu-id="cf803-139">追加のコンストラクターでは、コンストラクターパラメーターの直後に`as`句を配置することで、自己識別子を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf803-139">In additional constructors, you can also define a self identifier by putting the `as` clause right after the constructor parameters.</span></span> <span data-ttu-id="cf803-140">この構文の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cf803-140">The following example illustrates this syntax:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3505.fs)]

<span data-ttu-id="cf803-141">オブジェクトを完全に定義する前に使用しようとすると、問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf803-141">Problems can occur when you try to use an object before it is fully defined.</span></span> <span data-ttu-id="cf803-142">したがって、自己識別子を使用すると、コンパイラが警告を出力し、追加のチェックを挿入して、オブジェクトが初期化される前にオブジェクトのメンバーにアクセスしないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf803-142">Therefore, uses of the self identifier can cause the compiler to emit a warning and insert additional checks to ensure the members of an object are not accessed before the object is initialized.</span></span> <span data-ttu-id="cf803-143">自己識別子は、プライマリコンストラクターのバインディング、 `do`または追加のコンストラクター内の`then`キーワードの後にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="cf803-143">You should only use the self identifier in the `do` bindings of the primary constructor, or after the `then` keyword in additional constructors.</span></span>

<span data-ttu-id="cf803-144">自己識別子の名前は、で`this`ある必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cf803-144">The name of the self identifier does not have to be `this`.</span></span> <span data-ttu-id="cf803-145">任意の有効な識別子を指定できます。</span><span class="sxs-lookup"><span data-stu-id="cf803-145">It can be any valid identifier.</span></span>

## <a name="assigning-values-to-properties-at-initialization"></a><span data-ttu-id="cf803-146">初期化時のプロパティへの値の割り当て</span><span class="sxs-lookup"><span data-stu-id="cf803-146">Assigning values to properties at initialization</span></span>

<span data-ttu-id="cf803-147">コンストラクターの引数リストにフォーム`property = value`の割り当ての一覧を追加することにより、初期化コードでクラスオブジェクトのプロパティに値を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cf803-147">You can assign values to the properties of a class object in the initialization code by appending a list of assignments of the form `property = value` to the argument list for a constructor.</span></span> <span data-ttu-id="cf803-148">これを次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="cf803-148">This is shown in the following code example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="cf803-149">次のバージョンの前のコードは、通常の引数、省略可能な引数、およびプロパティ設定を1つのコンストラクター呼び出しで組み合わせる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="cf803-149">The following version of the previous code illustrates the combination of ordinary arguments, optional arguments, and property settings in one constructor call:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3507.fs)]

## <a name="constructors-in-inherited-class"></a><span data-ttu-id="cf803-150">継承されたクラスのコンストラクター</span><span class="sxs-lookup"><span data-stu-id="cf803-150">Constructors in inherited class</span></span>

<span data-ttu-id="cf803-151">コンストラクターを持つ基底クラスから継承する場合は、inherit 句で引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf803-151">When inheriting from a base class that has a constructor, you must specify its arguments in the inherit clause.</span></span> <span data-ttu-id="cf803-152">詳細については、「[コンストラクターと継承](../inheritance.md#constructors-and-inheritance)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf803-152">For more information, see [Constructors and inheritance](../inheritance.md#constructors-and-inheritance).</span></span>

## <a name="static-constructors-or-type-constructors"></a><span data-ttu-id="cf803-153">静的コンストラクターまたは型コンストラクター</span><span class="sxs-lookup"><span data-stu-id="cf803-153">Static constructors or type constructors</span></span>

<span data-ttu-id="cf803-154">オブジェクトを作成するためのコードを指定する`let`だけ`do`でなく、型を最初に使用して型レベルで初期化を実行する前に実行されるクラス型で静的およびバインディングを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf803-154">In addition to specifying code for creating objects, static `let` and `do` bindings can be authored in class types that execute before the type is first used to perform initialization at the type level.</span></span> <span data-ttu-id="cf803-155">詳細については、「クラスと[ `do`バインド](do-bindings-in-classes.md) [ `let`のバインド](let-bindings-in-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf803-155">For more information, see [`let` Bindings in Classes](let-bindings-in-classes.md) and [`do` Bindings in Classes](do-bindings-in-classes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf803-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="cf803-156">See also</span></span>

- [<span data-ttu-id="cf803-157">メンバー</span><span class="sxs-lookup"><span data-stu-id="cf803-157">Members</span></span>](index.md)
