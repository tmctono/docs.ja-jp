---
title: メソッド
description: 学習方法、F#メソッドは、公開し、オブジェクトと型の動作と機能の実装に使用される型に関連付けられている関数。
ms.date: 05/16/2016
ms.openlocfilehash: 03150cc67f79bfde58cf27e4a9d4dfa9e9ff3f55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666496"
---
# <a name="methods"></a><span data-ttu-id="a02f7-103">メソッド</span><span class="sxs-lookup"><span data-stu-id="a02f7-103">Methods</span></span>

<span data-ttu-id="a02f7-104">A*メソッド*型に関連付けられている関数です。</span><span class="sxs-lookup"><span data-stu-id="a02f7-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="a02f7-105">オブジェクト指向のプログラミングで公開し、オブジェクトと型の動作と機能を実装するメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="a02f7-106">構文</span><span class="sxs-lookup"><span data-stu-id="a02f7-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="a02f7-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a02f7-107">Remarks</span></span>

<span data-ttu-id="a02f7-108">前の構文では、メソッドの宣言と定義のさまざまなフォームを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="a02f7-109">長いメソッド本体では、改行されるように等号 (=) と、メソッド本体の全体がインデントされます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="a02f7-110">属性は、任意のメソッド宣言に適用できます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="a02f7-111">メソッド定義の構文の前に、個別の行に、通常は一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="a02f7-112">詳細については、「[属性](../attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a02f7-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="a02f7-113">メソッドをマークする`inline`します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="a02f7-114">`inline` の詳細については、「[Inline Functions](../functions/inline-functions.md)」(インライン関数) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a02f7-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="a02f7-115">非インライン メソッドは、型内で再帰的に使用できます。明示的に使用する必要はありません、`rec`キーワード。</span><span class="sxs-lookup"><span data-stu-id="a02f7-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="a02f7-116">インスタンス メソッド</span><span class="sxs-lookup"><span data-stu-id="a02f7-116">Instance Methods</span></span>

<span data-ttu-id="a02f7-117">インスタンス メソッドを宣言すると、`member`キーワードと*自己識別子*、その後にピリオド (.) とメソッド名とパラメーター。</span><span class="sxs-lookup"><span data-stu-id="a02f7-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="a02f7-118">場合と同様`let`、バインド、*パラメーター リスト*パターンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="a02f7-119">通常、他の .NET Framework 言語で作成されるときに、F# の方法は、組の形式でのかっこ内のパラメーターの表示方法を囲みます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="a02f7-120">ただし、カリー化された形式 (パラメーターをスペースで区切られた) は一般的でも、その他のパターンもサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="a02f7-121">次の例では、定義とインスタンスの非抽象メソッドの使用方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="a02f7-122">インスタンスのメソッド内では、let バインドを使用して定義されているフィールドにアクセスする、自己識別子を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a02f7-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="a02f7-123">その他のメンバーとプロパティにアクセスする場合は、自己識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="a02f7-124">静的メソッド</span><span class="sxs-lookup"><span data-stu-id="a02f7-124">Static Methods</span></span>

<span data-ttu-id="a02f7-125">キーワード`static`インスタンスがないメソッドを呼び出すことができますを指定するために使用して、オブジェクトのインスタンスに関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="a02f7-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="a02f7-126">それ以外の場合、メソッドは、インスタンス メソッドです。</span><span class="sxs-lookup"><span data-stu-id="a02f7-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="a02f7-127">次のセクションの例で宣言されたフィールドを示しています、`let`キーワード、プロパティのメンバーを使って宣言する場合、`member`キーワード、および静的メソッドで宣言された、`static`キーワード。</span><span class="sxs-lookup"><span data-stu-id="a02f7-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="a02f7-128">次の例は、定義と静的メソッドの使用を示しています。</span><span class="sxs-lookup"><span data-stu-id="a02f7-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="a02f7-129">これらのメソッド定義であると仮定、`SomeType`クラスは、前のセクションでします。</span><span class="sxs-lookup"><span data-stu-id="a02f7-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="a02f7-130">抽象メソッドと仮想メソッド</span><span class="sxs-lookup"><span data-stu-id="a02f7-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="a02f7-131">キーワード`abstract`メソッドが仮想ディスパッチ スロットを持つクラスの定義がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="a02f7-132">A*仮想ディスパッチ スロット*はオブジェクト指向型の仮想関数を検索する実行時に使用される関数の内部で維持されるテーブル内のエントリを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="a02f7-133">仮想ディスパッチ メカニズムを実装するメカニズムは、*ポリモーフィズム*、オブジェクト指向プログラミングの重要な機能です。</span><span class="sxs-lookup"><span data-stu-id="a02f7-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="a02f7-134">定義のない 1 つ以上の抽象メソッドを持つクラスは、*抽象クラス*、つまり、そのクラスのインスタンスを作成できないことができます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="a02f7-135">抽象クラスの詳細については、次を参照してください。[抽象クラス](../abstract-classes.md)します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="a02f7-136">抽象メソッドの宣言では、メソッド本体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="a02f7-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="a02f7-137">代わりに、メソッドの名前は後にコロン (:) と、メソッドの型シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="a02f7-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="a02f7-138">メソッドの型のシグネチャは、一時停止すると、マウス ポインター経由での Visual Studio コード エディターでメソッドの名前を除くパラメーターの名前のない、IntelliSense によって表示されるのと同じ。</span><span class="sxs-lookup"><span data-stu-id="a02f7-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="a02f7-139">型のシグネチャは、対話形式で作業している場合にも、インタープリター fsi.exe をで表示されます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="a02f7-140">戻り値の型の適切な区切り記号の後に、パラメーターの型を一覧することにより、メソッドの型シグネチャが形成されます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="a02f7-141">カリー化されたパラメーターを指定する`->`タプルのパラメーターを指定して`*`します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="a02f7-142">戻り値がによって引数から常に区切られた、`->`シンボル。</span><span class="sxs-lookup"><span data-stu-id="a02f7-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="a02f7-143">かっこは、パラメーター、関数型の場合など、複雑なパラメーターをグループ化するかを示すタプルが扱われると、2 つのパラメーターとしてではなく、1 つのパラメーターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="a02f7-144">与えることができますも抽象メソッド default 定義、クラスを定義を追加しを使用して、`default`キーワードは、このトピックの「構文のブロックに示されました。</span><span class="sxs-lookup"><span data-stu-id="a02f7-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="a02f7-145">同じクラスの定義を持つ抽象メソッドは、他の .NET Framework 言語での仮想メソッドと同じです。</span><span class="sxs-lookup"><span data-stu-id="a02f7-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="a02f7-146">定義が存在するかどうか、`abstract`キーワードは、クラスの仮想関数テーブルに新しいディスパッチ スロットを作成します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="a02f7-147">派生クラスは基底クラスが抽象メソッドを実装するかどうかに関係なく、抽象メソッドの実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="a02f7-148">使用してを除く、派生クラスで、同じ名前とシグネチャを持つメソッドを定義する派生クラスで抽象メソッドを実装するために、`override`または`default`キーワード、メソッド本体を提供します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="a02f7-149">キーワード`override`と`default`まったく同じことを意味します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="a02f7-150">使用して、`override`新しいメソッドは、基本クラス実装をオーバーライドする場合を使用して、`default`は元の抽象宣言と同じクラスで実装を作成するとします。</span><span class="sxs-lookup"><span data-stu-id="a02f7-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="a02f7-151">使用しないでください、`abstract`抽象基本クラスで宣言されたメソッドを実装するメソッドのキーワード。</span><span class="sxs-lookup"><span data-stu-id="a02f7-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="a02f7-152">次の例は、抽象メソッドを示しています。`Rotate`を持つ既定の実装では、.NET Framework の仮想メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="a02f7-153">次の例は、基底クラス メソッドをオーバーライドする派生クラスを示しています。</span><span class="sxs-lookup"><span data-stu-id="a02f7-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="a02f7-154">この場合、オーバーライドでは、何も実行するために、動作が変わります。</span><span class="sxs-lookup"><span data-stu-id="a02f7-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="a02f7-155">オーバーロードされたメソッド</span><span class="sxs-lookup"><span data-stu-id="a02f7-155">Overloaded Methods</span></span>

<span data-ttu-id="a02f7-156">オーバー ロードされたメソッドは、特定の型で同じ名前があるが、異なる引数を指定する方法です。</span><span class="sxs-lookup"><span data-stu-id="a02f7-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="a02f7-157">F#、省略可能な引数は、通常、オーバー ロードされたメソッドの代わりに使用します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="a02f7-158">ただし、オーバー ロードされたメソッドは、されるとき、引数が、組形式いないカリー化された形式では、言語では、許可されます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="a02f7-159">省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="a02f7-159">Optional Arguments</span></span>

<span data-ttu-id="a02f7-160">以降でF#4.1、メソッドで、既定パラメーター値は省略可能な引数を用意することもできます。</span><span class="sxs-lookup"><span data-stu-id="a02f7-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="a02f7-161">これは、c# コードとの相互運用の促進を支援します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="a02f7-162">次の例では、構文を示しています。</span><span class="sxs-lookup"><span data-stu-id="a02f7-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="a02f7-163">値が渡されたメモ`DefaultParameterValue`入力の型に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a02f7-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="a02f7-164">上記のサンプルでは、`int`します。</span><span class="sxs-lookup"><span data-stu-id="a02f7-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="a02f7-165">整数以外の値を渡そうとした`DefaultParameterValue`コンパイル エラーになります。</span><span class="sxs-lookup"><span data-stu-id="a02f7-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="a02f7-166">例:プロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="a02f7-166">Example: Properties and Methods</span></span>

<span data-ttu-id="a02f7-167">次の例には、フィールド、プライベート関数、プロパティ、および静的メソッドの例を紹介する型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a02f7-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="a02f7-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="a02f7-168">See also</span></span>

- [<span data-ttu-id="a02f7-169">メンバー</span><span class="sxs-lookup"><span data-stu-id="a02f7-169">Members</span></span>](index.md)