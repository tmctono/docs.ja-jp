---
title: クラス
description: 学習方法F#クラスは、プロパティ、メソッド、およびイベントを保持できるオブジェクトを表す型。
ms.date: 05/16/2016
ms.openlocfilehash: a233fea538274216db3c6751f6fbabbf70cc2841
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645531"
---
# <a name="classes"></a><span data-ttu-id="bba8b-103">クラス</span><span class="sxs-lookup"><span data-stu-id="bba8b-103">Classes</span></span>

<span data-ttu-id="bba8b-104">*クラス*プロパティ、メソッド、およびイベントを保持できるオブジェクトを表す型。</span><span class="sxs-lookup"><span data-stu-id="bba8b-104">*Classes* are types that represent objects that can have properties, methods, and events.</span></span>

## <a name="syntax"></a><span data-ttu-id="bba8b-105">構文</span><span class="sxs-lookup"><span data-stu-id="bba8b-105">Syntax</span></span>

```fsharp
// Class definition:
type [access-modifier] type-name [type-params] [access-modifier] ( parameter-list ) [ as identifier ] =
[ class ]
[ inherit base-type-name(base-constructor-args) ]
[ let-bindings ]
[ do-bindings ]
member-list
...
[ end ]
// Mutually recursive class definitions:
type [access-modifier] type-name1 ...
and [access-modifier] type-name2 ...
...
```

## <a name="remarks"></a><span data-ttu-id="bba8b-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="bba8b-106">Remarks</span></span>

<span data-ttu-id="bba8b-107">クラスは、.NET オブジェクト型の基本的な記述を表します。クラスは、F# オブジェクト指向プログラミングをサポートする型の主な概念です。</span><span class="sxs-lookup"><span data-stu-id="bba8b-107">Classes represent the fundamental description of .NET object types; the class is the primary type concept that supports object-oriented programming in F#.</span></span>

<span data-ttu-id="bba8b-108">上記の構文、`type-name`は任意の有効な識別子です。</span><span class="sxs-lookup"><span data-stu-id="bba8b-108">In the preceding syntax, the `type-name` is any valid identifier.</span></span> <span data-ttu-id="bba8b-109">`type-params`省略可能なジェネリック型パラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-109">The `type-params` describes optional generic type parameters.</span></span> <span data-ttu-id="bba8b-110">型パラメーター名と山かっこで囲まれた制約で構成されます (`<`と`>`)。</span><span class="sxs-lookup"><span data-stu-id="bba8b-110">It consists of type parameter names and constraints enclosed in angle brackets (`<` and `>`).</span></span> <span data-ttu-id="bba8b-111">詳細については、次を参照してください。[ジェネリック](generics/index.md)と[制約](generics/constraints.md)します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-111">For more information, see [Generics](generics/index.md) and [Constraints](generics/constraints.md).</span></span> <span data-ttu-id="bba8b-112">`parameter-list`コンス トラクターのパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-112">The `parameter-list` describes constructor parameters.</span></span> <span data-ttu-id="bba8b-113">最初のアクセス修飾子に関連する型。2 つ目は、プライマリ コンス トラクターに関するものです。</span><span class="sxs-lookup"><span data-stu-id="bba8b-113">The first access modifier pertains to the type; the second pertains to the primary constructor.</span></span> <span data-ttu-id="bba8b-114">どちらの場合、既定値は`public`します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-114">In both cases, the default is `public`.</span></span>

<span data-ttu-id="bba8b-115">クラスの基本クラスを使用して指定する、`inherit`キーワード。</span><span class="sxs-lookup"><span data-stu-id="bba8b-115">You specify the base class for a class by using the `inherit` keyword.</span></span> <span data-ttu-id="bba8b-116">基底クラスのコンス トラクターをかっこ内の引数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-116">You must supply arguments, in parentheses, for the base class constructor.</span></span>

<span data-ttu-id="bba8b-117">`let`バインドを使用してクラスに対してローカルなフィールドまたは関数値を宣言します。また、`let`バインドの一般的な規則に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-117">You declare fields or function values that are local to the class by using `let` bindings, and you must follow the general rules for `let` bindings.</span></span> <span data-ttu-id="bba8b-118">`do-bindings`バインド セクションには、オブジェクト構築時に実行されるコードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bba8b-118">The `do-bindings` section includes code to be executed upon object construction.</span></span>

<span data-ttu-id="bba8b-119">`member-list`の追加のコンス トラクター、インスタンスと静的メソッドの宣言、インターフェイス宣言、抽象バインドは、プロパティとイベントの宣言で構成されています。</span><span class="sxs-lookup"><span data-stu-id="bba8b-119">The `member-list` consists of additional constructors, instance and static method declarations, interface declarations, abstract bindings, and property and event declarations.</span></span> <span data-ttu-id="bba8b-120">後述[メンバー](members/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-120">These are described in [Members](members/index.md).</span></span>

<span data-ttu-id="bba8b-121">`identifier`オプションで使用されている`as`キーワードは、インスタンス変数、または型のインスタンスを参照する種類の定義で使用できる、自己識別子に名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-121">The `identifier` that is used with the optional `as` keyword gives a name to the instance variable, or self identifier, which can be used in the type definition to refer to the instance of the type.</span></span> <span data-ttu-id="bba8b-122">詳細については、このトピックで後述する「自己識別子を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba8b-122">For more information, see the section Self Identifiers later in this topic.</span></span>

<span data-ttu-id="bba8b-123">キーワード`class`と`end`開始をマークして、定義の最後は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="bba8b-123">The keywords `class` and `end` that mark the start and end of the definition are optional.</span></span>

<span data-ttu-id="bba8b-124">組み合わせて相互に参照型であり、再帰型が相互に参加している、`and`相互再帰関数と同じようにキーワード。</span><span class="sxs-lookup"><span data-stu-id="bba8b-124">Mutually recursive types, which are types that reference each other, are joined together with the `and` keyword just as mutually recursive functions are.</span></span> <span data-ttu-id="bba8b-125">例については、「相互再帰型」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba8b-125">For an example, see the section Mutually Recursive Types.</span></span>

## <a name="constructors"></a><span data-ttu-id="bba8b-126">コンストラクター</span><span class="sxs-lookup"><span data-stu-id="bba8b-126">Constructors</span></span>

<span data-ttu-id="bba8b-127">コンス トラクターは、クラス型のインスタンスを作成するコードを示します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-127">The constructor is code that creates an instance of the class type.</span></span> <span data-ttu-id="bba8b-128">これは、他の .NET 言語で、クラスのコンストラクターは F# のやや異なる方法で機能します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-128">Constructors for classes work somewhat differently in F# than they do in other .NET languages.</span></span> <span data-ttu-id="bba8b-129">F#クラスは、常にプライマリ コンス トラクターの引数が記載されて、`parameter-list`続く型の名前、および本文で構成されます、 `let` (と`let rec`)、クラス宣言の先頭にバインドし、`do`に従ってバインドします。</span><span class="sxs-lookup"><span data-stu-id="bba8b-129">In an F# class, there is always a primary constructor whose arguments are described in the `parameter-list` that follows the type name, and whose body consists of the `let` (and `let rec`) bindings at the start of the class declaration and the `do` bindings that follow.</span></span> <span data-ttu-id="bba8b-130">プライマリ コンス トラクターの引数は、クラス宣言全体のスコープになります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-130">The arguments of the primary constructor are in scope throughout the class declaration.</span></span>

<span data-ttu-id="bba8b-131">使用して追加のコンス トラクターを追加することができます、`new`キーワードを次のように、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-131">You can add additional constructors by using the `new` keyword to add a member, as follows:</span></span>

<span data-ttu-id="bba8b-132">`new`(`argument-list`) = `constructor-body`</span><span class="sxs-lookup"><span data-stu-id="bba8b-132">`new`(`argument-list`) = `constructor-body`</span></span>

<span data-ttu-id="bba8b-133">新しいコンス トラクターの本文には、クラス宣言の上部にある指定されたプライマリ コンス トラクターを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-133">The body of the new constructor must invoke the primary constructor that is specified at the top of the class declaration.</span></span>

<span data-ttu-id="bba8b-134">次の例では、この概念を示します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-134">The following example illustrates this concept.</span></span> <span data-ttu-id="bba8b-135">次のコードで`MyClass`2 つのコンス トラクターを持つ、2 つの引数と別のコンス トラクターを取得するプライマリ コンス トラクターは引数を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="bba8b-135">In the following code, `MyClass` has two constructors, a primary constructor that takes two arguments and another constructor that takes no arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2401.fs)]

## <a name="let-and-do-bindings"></a><span data-ttu-id="bba8b-136">`let`と`do`バインド</span><span class="sxs-lookup"><span data-stu-id="bba8b-136">let and do Bindings</span></span>

<span data-ttu-id="bba8b-137">`let`と`do`クラス定義内のバインディングは、主要なクラスのコンス トラクターの本体を形成し、したがって実行クラスのインスタンスが作成されるたびにします。</span><span class="sxs-lookup"><span data-stu-id="bba8b-137">The `let` and `do` bindings in a class definition form the body of the primary class constructor, and therefore they run whenever a class instance is created.</span></span> <span data-ttu-id="bba8b-138">場合、`let`バインドが関数の場合、そのメンバーにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-138">If a `let` binding is a function, then it is compiled into a member.</span></span> <span data-ttu-id="bba8b-139">場合、`let`バインド関数またはメンバーで使用されていない値は、そのコンス トラクターにローカル変数にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-139">If the `let` binding is a value that is not used in any function or member, then it is compiled into a variable that is local to the constructor.</span></span> <span data-ttu-id="bba8b-140">それ以外の場合、クラスのフィールドにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-140">Otherwise, it is compiled into a field of the class.</span></span> <span data-ttu-id="bba8b-141">`do`次の式は、プライマリ コンス トラクターにコンパイルされ、すべてのインスタンスの初期化コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-141">The `do` expressions that follow are compiled into the primary constructor and execute initialization code for every instance.</span></span> <span data-ttu-id="bba8b-142">追加のコンス トラクターは常に、プライマリ コンス トラクターを呼び出すので、`let`バインドと`do`コンス トラクターの呼び出しに関係なくバインドが常に実行します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-142">Because any additional constructors always call the primary constructor, the `let` bindings and `do` bindings always execute regardless of which constructor is called.</span></span>

<span data-ttu-id="bba8b-143">によって作成されるフィールド`let`バインド メソッドとクラスのプロパティを通じてアクセスできます。 ただし、アクセスできない、静的メソッドから静的メソッドがパラメーターとしてインスタンス変数を受け取る場合でもです。</span><span class="sxs-lookup"><span data-stu-id="bba8b-143">Fields that are created by `let` bindings can be accessed throughout the methods and properties of the class; however, they cannot be accessed from static methods, even if the static methods take an instance variable as a parameter.</span></span> <span data-ttu-id="bba8b-144">1 つが存在する場合、自己識別子を使用してアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="bba8b-144">They cannot be accessed by using the self identifier, if one exists.</span></span>

## <a name="self-identifiers"></a><span data-ttu-id="bba8b-145">自己識別子</span><span class="sxs-lookup"><span data-stu-id="bba8b-145">Self Identifiers</span></span>

<span data-ttu-id="bba8b-146">A*自己識別子*は現在のインスタンスを表す名前です。</span><span class="sxs-lookup"><span data-stu-id="bba8b-146">A *self identifier* is a name that represents the current instance.</span></span> <span data-ttu-id="bba8b-147">自己識別子のように、 `this` c# または C++ でキーワードまたは`Me`Visual Basic でします。</span><span class="sxs-lookup"><span data-stu-id="bba8b-147">Self identifiers resemble the `this` keyword in C# or C++ or `Me` in Visual Basic.</span></span> <span data-ttu-id="bba8b-148">クラス定義全体または個々 のメソッドのためだけにスコープ内にある自己識別子にするかどうかに応じて、2 つの異なる方法では、自己識別子を定義できます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-148">You can define a self identifier in two different ways, depending on whether you want the self identifier to be in scope for the whole class definition or just for an individual method.</span></span>

<span data-ttu-id="bba8b-149">クラス全体に対して自己識別子を定義するには、使用、`as`キーワードのコンス トラクターのパラメーターの閉じかっこの後に一覧表示、および識別子の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-149">To define a self identifier for the whole class, use the `as` keyword after the closing parentheses of the constructor parameter list, and specify the identifier name.</span></span>

<span data-ttu-id="bba8b-150">1 つのメソッドの個人識別子を定義するには、メソッド名と、区切り記号としてピリオド (.) の直前に、メンバーの宣言で個人識別子を指定します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-150">To define a self identifier for just one method, provide the self identifier in the member declaration, just before the method name and a period (.) as a separator.</span></span>

<span data-ttu-id="bba8b-151">次のコード例は、自己識別子を作成する 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="bba8b-151">The following code example illustrates the two ways to create a self identifier.</span></span> <span data-ttu-id="bba8b-152">最初の行で、`as`キーワードの使用を自己識別子を定義します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-152">In the first line, the `as` keyword is used to define the self identifier.</span></span> <span data-ttu-id="bba8b-153">5 番目の行識別子で`this`スコープをメソッドに制限は、自己識別子を定義するために使用`PrintMessage`します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-153">In the fifth line, the identifier `this` is used to define a self identifier whose scope is restricted to the method `PrintMessage`.</span></span>

```fsharp
type MyClass2(dataIn) as self =
    let data = dataIn
    do
        self.PrintMessage()
    member this.PrintMessage() =
        printf "Creating MyClass2 with Data %d" data
```

<span data-ttu-id="bba8b-154">異なり、他の .NET 言語で名前を指定できます、自己識別子; たいです。だけではない名前になど`self`、 `Me`、または`this`します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-154">Unlike in other .NET languages, you can name the self identifier however you want; you are not restricted to names such as `self`, `Me`, or `this`.</span></span>

<span data-ttu-id="bba8b-155">宣言されている自己識別子、`as`までキーワードが初期化されていない後、`let`バインドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-155">The self identifier that is declared with the `as` keyword is not initialized until after the `let` bindings are executed.</span></span> <span data-ttu-id="bba8b-156">したがってで使用できませんが、`let`バインドします。</span><span class="sxs-lookup"><span data-stu-id="bba8b-156">Therefore, it cannot be used in the `let` bindings.</span></span> <span data-ttu-id="bba8b-157">自己識別子を使用することができます、 `do` bindings セクション。</span><span class="sxs-lookup"><span data-stu-id="bba8b-157">You can use the self identifier in the `do` bindings section.</span></span>

## <a name="generic-type-parameters"></a><span data-ttu-id="bba8b-158">ジェネリック型の型パラメーター</span><span class="sxs-lookup"><span data-stu-id="bba8b-158">Generic Type Parameters</span></span>

<span data-ttu-id="bba8b-159">ジェネリック型パラメーターは山かっこで指定 (`<`と`>`)、単一引用符の後に、識別子の形式でします。</span><span class="sxs-lookup"><span data-stu-id="bba8b-159">Generic type parameters are specified in angle brackets (`<` and `>`), in the form of a single quotation mark followed by an identifier.</span></span> <span data-ttu-id="bba8b-160">複数のジェネリック型パラメーターは、コンマで区切られます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-160">Multiple generic type parameters are separated by commas.</span></span> <span data-ttu-id="bba8b-161">ジェネリック型パラメーターは、宣言全体のスコープ内です。</span><span class="sxs-lookup"><span data-stu-id="bba8b-161">The generic type parameter is in scope throughout the declaration.</span></span> <span data-ttu-id="bba8b-162">次のコード例では、ジェネリック型パラメーターを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-162">The following code example shows how to specify generic type parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2403.fs)]

<span data-ttu-id="bba8b-163">型を使用する場合、型引数が推論されます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-163">Type arguments are inferred when the type is used.</span></span> <span data-ttu-id="bba8b-164">次のコードでは、推定された型は、タプルのシーケンスが。</span><span class="sxs-lookup"><span data-stu-id="bba8b-164">In the following code, the inferred type is a sequence of tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet24031.fs)]

## <a name="specifying-inheritance"></a><span data-ttu-id="bba8b-165">継承を指定します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-165">Specifying Inheritance</span></span>

<span data-ttu-id="bba8b-166">`inherit`句が 1 つを使用する必要がある場合、直接の基本クラスを識別します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-166">The `inherit` clause identifies the direct base class, if there is one.</span></span> <span data-ttu-id="bba8b-167">F#1 つだけで、直接基底クラスを許可します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-167">In F#, only one direct base class is allowed.</span></span> <span data-ttu-id="bba8b-168">クラスが実装するインターフェイスでは、基底クラスは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="bba8b-168">Interfaces that a class implements are not considered base classes.</span></span> <span data-ttu-id="bba8b-169">インターフェイスは、後ほど、[インターフェイス](Interfaces.md)トピック。</span><span class="sxs-lookup"><span data-stu-id="bba8b-169">Interfaces are discussed in the [Interfaces](Interfaces.md) topic.</span></span>

<span data-ttu-id="bba8b-170">アクセスできますメソッドとプロパティの基本クラスの派生クラスから言語キーワードを使用して`base`、識別子としての後にピリオド (.) とメンバーの名前。</span><span class="sxs-lookup"><span data-stu-id="bba8b-170">You can access the methods and properties of the base class from the derived class by using the language keyword `base` as an identifier, followed by a period (.) and the name of the member.</span></span>

<span data-ttu-id="bba8b-171">詳細については、「[継承](inheritance.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba8b-171">For more information, see [Inheritance](inheritance.md).</span></span>

## <a name="members-section"></a><span data-ttu-id="bba8b-172">メンバー セクション</span><span class="sxs-lookup"><span data-stu-id="bba8b-172">Members Section</span></span>

<span data-ttu-id="bba8b-173">このセクションでは、静的またはインスタンス メソッド、プロパティ、インターフェイスの実装、抽象メンバー、イベント宣言、および追加のコンス トラクターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-173">You can define static or instance methods, properties, interface implementations, abstract members, event declarations, and additional constructors in this section.</span></span> <span data-ttu-id="bba8b-174">使用して、バインドはこのセクションでは表示できません。</span><span class="sxs-lookup"><span data-stu-id="bba8b-174">Let and do bindings cannot appear in this section.</span></span> <span data-ttu-id="bba8b-175">別のトピックで説明されている、メンバーは、さまざまなクラスのほか、F# の型に追加することができます、ため[メンバー](members/index.md)します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-175">Because members can be added to a variety of F# types in addition to classes, they are discussed in a separate topic, [Members](members/index.md).</span></span>

## <a name="mutually-recursive-types"></a><span data-ttu-id="bba8b-176">相互再帰型</span><span class="sxs-lookup"><span data-stu-id="bba8b-176">Mutually Recursive Types</span></span>

<span data-ttu-id="bba8b-177">相互に循環的に参照型を定義するときにつなぎ合わせる種類の定義を使用して、`and`キーワード。</span><span class="sxs-lookup"><span data-stu-id="bba8b-177">When you define types that reference each other in a circular way, you string together the type definitions by using the `and` keyword.</span></span> <span data-ttu-id="bba8b-178">`and`キーワードに置き換えられます、`type`を次のように、最初の定義を除くすべてのキーワード。</span><span class="sxs-lookup"><span data-stu-id="bba8b-178">The `and` keyword replaces the `type` keyword on all except the first definition, as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2404.fs)]

<span data-ttu-id="bba8b-179">出力は、現在のディレクトリ内のすべてのファイルの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-179">The output is a list of all the files in the current directory.</span></span>

## <a name="when-to-use-classes-unions-records-and-structures"></a><span data-ttu-id="bba8b-180">クラス、共用体、レコード、および構造体を使用する場合</span><span class="sxs-lookup"><span data-stu-id="bba8b-180">When to Use Classes, Unions, Records, and Structures</span></span>

<span data-ttu-id="bba8b-181">さまざまな種類から選択を指定するには、どのような各型の使用目的を特定の状況に適切な型を選択するをよく理解できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-181">Given the variety of types to choose from, you need to have a good understanding of what each type is designed for to select the appropriate type for a particular situation.</span></span> <span data-ttu-id="bba8b-182">クラスはオブジェクト指向プログラミングのコンテキストで使用するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="bba8b-182">Classes are designed for use in object-oriented programming contexts.</span></span> <span data-ttu-id="bba8b-183">オブジェクト指向プログラミングとは、.NET Framework 向けに作成されたアプリケーションで使用される主要なパラダイムです。</span><span class="sxs-lookup"><span data-stu-id="bba8b-183">Object-oriented programming is the dominant paradigm used in applications that are written for the .NET Framework.</span></span> <span data-ttu-id="bba8b-184">場合、 F# 、.NET Framework または別のオブジェクト指向ライブラリと密接に連携コードがあり、UI ライブラリなど、オブジェクト指向型システムを拡張するがある場合に特にクラスは、適切な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-184">If your F# code has to work closely with the .NET Framework or another object-oriented library, and especially if you have to extend from an object-oriented type system such as a UI library, classes are probably appropriate.</span></span>

<span data-ttu-id="bba8b-185">いない相互運用する密接にオブジェクト指向のコードでは、オブジェクト指向のコードの頻繁なやり取りからそのために保護され、自己完結型コードを記述する場合やは、レコードの使用を検討し、判別共用体。</span><span class="sxs-lookup"><span data-stu-id="bba8b-185">If you are not interoperating closely with object-oriented code, or if you are writing code that is self-contained and therefore protected from frequent interaction with object-oriented code, you should consider using records and discriminated unions.</span></span> <span data-ttu-id="bba8b-186">1 つも思考 – アウト適切なパターン一致、コードと共に、判別共用体は、オブジェクトの階層構造を単純な代替手段としてよく使用できます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-186">A single, well thought–out discriminated union, together with appropriate pattern matching code, can often be used as a simpler alternative to an object hierarchy.</span></span> <span data-ttu-id="bba8b-187">判別共用体の詳細については、次を参照してください。[判別共用体](discriminated-unions.md)します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-187">For more information about discriminated unions, see [Discriminated Unions](discriminated-unions.md).</span></span>

<span data-ttu-id="bba8b-188">レコードは、クラスよりも簡単になるというメリットが型の要求はその簡素性を実現できるを超えたときにレコードが適切でないです。</span><span class="sxs-lookup"><span data-stu-id="bba8b-188">Records have the advantage of being simpler than classes, but records are not appropriate when the demands of a type exceed what can be accomplished with their simplicity.</span></span> <span data-ttu-id="bba8b-189">レコードは、基本的に単純な集計の値、カスタム アクションを実行できる別のコンス トラクターを持たない、隠しフィールド、および継承またはインターフェイスの実装を含まないです。</span><span class="sxs-lookup"><span data-stu-id="bba8b-189">Records are basically simple aggregates of values, without separate constructors that can perform custom actions, without hidden fields, and without inheritance or interface implementations.</span></span> <span data-ttu-id="bba8b-190">プロパティやメソッドなどのメンバーは、その動作をさらに複雑なレコードに追加できる、レコードに格納されているフィールドが値の単純な集計。</span><span class="sxs-lookup"><span data-stu-id="bba8b-190">Although members such as properties and methods can be added to records to make their behavior more complex, the fields stored in a record are still a simple aggregate of values.</span></span> <span data-ttu-id="bba8b-191">レコードの詳細については、次を参照してください。[レコード](records.md)します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-191">For more information about records, see [Records](records.md).</span></span>

<span data-ttu-id="bba8b-192">構造体も、データの小規模な集約に便利ですが、.NET 値型という点でクラスやレコードからが異なります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-192">Structures are also useful for small aggregates of data, but they differ from classes and records in that they are .NET value types.</span></span> <span data-ttu-id="bba8b-193">クラスやレコードは、.NET 参照型です。</span><span class="sxs-lookup"><span data-stu-id="bba8b-193">Classes and records are .NET reference types.</span></span> <span data-ttu-id="bba8b-194">値型と参照型のセマンティクスは、値型は値によって渡される点で異なります。</span><span class="sxs-lookup"><span data-stu-id="bba8b-194">The semantics of value types and reference types are different in that value types are passed by value.</span></span> <span data-ttu-id="bba8b-195">つまり、コピーされるビット単位では、パラメーターとして渡されるまたは関数から返されます。</span><span class="sxs-lookup"><span data-stu-id="bba8b-195">This means that they are copied bit for bit when they are passed as a parameter or returned from a function.</span></span> <span data-ttu-id="bba8b-196">格納されるスタック上かの代わりに親オブジェクト内に埋め込まれた、フィールドとして使用される場合は、ヒープ上のそれぞれの場所に格納されています。</span><span class="sxs-lookup"><span data-stu-id="bba8b-196">They are also stored on the stack or, if they are used as a field, embedded inside the parent object instead of stored in their own separate location on the heap.</span></span> <span data-ttu-id="bba8b-197">そのため、構造体は、ヒープへのアクセスのオーバーヘッドが問題と頻繁にアクセスされるデータに適しています。</span><span class="sxs-lookup"><span data-stu-id="bba8b-197">Therefore, structures are appropriate for frequently accessed data when the overhead of accessing the heap is a problem.</span></span> <span data-ttu-id="bba8b-198">構造体の詳細については、次を参照してください。[構造](structures.md)します。</span><span class="sxs-lookup"><span data-stu-id="bba8b-198">For more information about structures, see [Structures](structures.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bba8b-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="bba8b-199">See also</span></span>

- [<span data-ttu-id="bba8b-200">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="bba8b-200">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bba8b-201">メンバー</span><span class="sxs-lookup"><span data-stu-id="bba8b-201">Members</span></span>](members/index.md)
- [<span data-ttu-id="bba8b-202">継承</span><span class="sxs-lookup"><span data-stu-id="bba8b-202">Inheritance</span></span>](inheritance.md)
- [<span data-ttu-id="bba8b-203">インターフェイス</span><span class="sxs-lookup"><span data-stu-id="bba8b-203">Interfaces</span></span>](interfaces.md)
