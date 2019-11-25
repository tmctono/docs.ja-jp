---
title: メソッド
description: F#メソッドが、オブジェクトと型の機能および動作を公開および実装するために使用される型に関連付けられた関数であることを説明します。
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976645"
---
# <a name="methods"></a><span data-ttu-id="7c522-103">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c522-103">Methods</span></span>

<span data-ttu-id="7c522-104">*メソッド*は、型に関連付けられている関数です。</span><span class="sxs-lookup"><span data-stu-id="7c522-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="7c522-105">オブジェクト指向プログラミングでは、メソッドを使用して、オブジェクトと型の機能および動作を公開および実装します。</span><span class="sxs-lookup"><span data-stu-id="7c522-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="7c522-106">構文</span><span class="sxs-lookup"><span data-stu-id="7c522-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="7c522-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c522-107">Remarks</span></span>

<span data-ttu-id="7c522-108">前の構文では、さまざまな形式のメソッド宣言と定義を確認できます。</span><span class="sxs-lookup"><span data-stu-id="7c522-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="7c522-109">メソッド本体が長い場合、改行は等号 (=) に従い、メソッド本体全体がインデントされます。</span><span class="sxs-lookup"><span data-stu-id="7c522-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="7c522-110">属性は、任意のメソッド宣言に適用できます。</span><span class="sxs-lookup"><span data-stu-id="7c522-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="7c522-111">これらは、メソッド定義の構文の前にあり、通常は別の行に表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c522-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="7c522-112">詳細については、「[属性](../attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c522-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="7c522-113">メソッドは `inline`としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="7c522-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="7c522-114">`inline` の詳細については、「[Inline Functions](../functions/inline-functions.md)」(インライン関数) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c522-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="7c522-115">非インラインメソッドは、型の中で再帰的に使用できます。`rec` キーワードを明示的に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7c522-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="7c522-116">インスタンスメソッド</span><span class="sxs-lookup"><span data-stu-id="7c522-116">Instance Methods</span></span>

<span data-ttu-id="7c522-117">インスタンスメソッドは、`member` キーワードと*自己識別子*を使用して宣言し、その後にピリオド (.) とメソッド名とパラメーターを指定して宣言します。</span><span class="sxs-lookup"><span data-stu-id="7c522-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="7c522-118">`let` バインドの場合と同様に、*パラメーターリスト*はパターンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7c522-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="7c522-119">通常、メソッドのパラメーターは、他の .NET Framework 言語で作成されたときにメソッドがF#に表示されるように、組形式でかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="7c522-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="7c522-120">ただし、カリー化形式 (パラメーターはスペースで区切られています) も一般的であり、他のパターンもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="7c522-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="7c522-121">次の例は、非抽象インスタンスメソッドの定義と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c522-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="7c522-122">インスタンスメソッド内では、let バインドを使用して定義されたフィールドにアクセスするために、自己識別子を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7c522-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="7c522-123">他のメンバーやプロパティにアクセスするときは、自己識別子を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c522-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="7c522-124">静的メソッド</span><span class="sxs-lookup"><span data-stu-id="7c522-124">Static Methods</span></span>

<span data-ttu-id="7c522-125">キーワード `static` は、インスタンスを使用せずにメソッドを呼び出すことができ、オブジェクトインスタンスに関連付けられていないことを指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c522-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="7c522-126">それ以外の場合、メソッドはインスタンスメソッドです。</span><span class="sxs-lookup"><span data-stu-id="7c522-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="7c522-127">次のセクションの例では、`let` キーワード、`member` キーワードで宣言されたプロパティメンバー、および `static` キーワードで宣言された静的メソッドを使用して宣言されたフィールドを示します。</span><span class="sxs-lookup"><span data-stu-id="7c522-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="7c522-128">次の例は、静的メソッドの定義と使用方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7c522-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="7c522-129">これらのメソッド定義は、前のセクションの `SomeType` クラスにあるものとします。</span><span class="sxs-lookup"><span data-stu-id="7c522-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="7c522-130">抽象メソッドと仮想メソッド</span><span class="sxs-lookup"><span data-stu-id="7c522-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="7c522-131">キーワード `abstract` は、メソッドに仮想ディスパッチスロットがあり、クラスに定義がない可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="7c522-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="7c522-132">*仮想ディスパッチスロット*は、オブジェクト指向の型の仮想関数呼び出しを検索するために実行時に使用される、内部的に管理された関数のテーブル内のエントリです。</span><span class="sxs-lookup"><span data-stu-id="7c522-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="7c522-133">仮想ディスパッチ機構は、オブジェクト指向プログラミングの重要な機能である*ポリモーフィズム*を実装するメカニズムです。</span><span class="sxs-lookup"><span data-stu-id="7c522-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="7c522-134">定義のない抽象メソッドを1つ以上持つクラスは*抽象クラス*であるため、そのクラスのインスタンスを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="7c522-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="7c522-135">抽象クラスの詳細については、「[抽象クラス](../abstract-classes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7c522-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="7c522-136">抽象メソッドの宣言には、メソッドの本体は含まれません。</span><span class="sxs-lookup"><span data-stu-id="7c522-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="7c522-137">代わりに、メソッドの名前の後にコロン (:)およびメソッドの型シグネチャ。</span><span class="sxs-lookup"><span data-stu-id="7c522-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="7c522-138">メソッドの型シグネチャは、パラメーター名がない場合を除き、Visual Studio Code エディターでメソッド名の上にマウスポインターを置くと IntelliSense によって表示されるものと同じです。</span><span class="sxs-lookup"><span data-stu-id="7c522-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="7c522-139">型シグネチャは、対話的に作業しているときにインタープリター fsi.exe によっても表示されます。</span><span class="sxs-lookup"><span data-stu-id="7c522-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="7c522-140">メソッドの型シグネチャは、適切な区切り記号を使用して、パラメーターの型と戻り値の型を一覧表示することによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="7c522-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="7c522-141">カリー化されたパラメーターは `->` で区切られ、組のパラメーターは `*`で区切られます。</span><span class="sxs-lookup"><span data-stu-id="7c522-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="7c522-142">戻り値は常に、引数と `->` 記号で区切られます。</span><span class="sxs-lookup"><span data-stu-id="7c522-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="7c522-143">かっこを使用すると、関数の型がパラメーターである場合や、組が2つのパラメーターとしてではなく1つのパラメーターとして扱われるタイミングを指定する場合など、複雑なパラメーターをグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="7c522-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="7c522-144">また、このトピックの構文ブロックに示すように、クラスに定義を追加し、`default` キーワードを使用して、抽象メソッドの既定の定義を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c522-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="7c522-145">同じクラス内に定義を持つ抽象メソッドは、他の .NET Framework 言語の仮想メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="7c522-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="7c522-146">定義が存在するかどうかにかかわらず、`abstract` キーワードによって、クラスの仮想関数テーブルに新しいディスパッチスロットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7c522-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="7c522-147">基底クラスが抽象メソッドを実装するかどうかに関係なく、派生クラスは抽象メソッドの実装を提供できます。</span><span class="sxs-lookup"><span data-stu-id="7c522-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="7c522-148">派生クラスで抽象メソッドを実装するには、派生クラスで同じ名前とシグネチャを持つメソッドを定義します。ただし、`override` または `default` キーワードを使用し、メソッド本体を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c522-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="7c522-149">キーワード `override` と `default` は、まったく同じことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7c522-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="7c522-150">新しいメソッドが基底クラスの実装をオーバーライドする場合は、`override` を使用します。元の抽象宣言と同じクラスに実装を作成する場合は、`default` を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c522-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="7c522-151">基底クラスで abstract として宣言されたメソッドを実装するメソッドでは、`abstract` キーワードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="7c522-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="7c522-152">次の例は、.NET Framework 仮想メソッドに相当する既定の実装を持つ `Rotate` 抽象メソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="7c522-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="7c522-153">基底クラスのメソッドをオーバーライドする派生クラスの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7c522-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="7c522-154">この場合、オーバーライドは、メソッドが何も実行しないように動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="7c522-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="7c522-155">オーバーロードされたメソッド</span><span class="sxs-lookup"><span data-stu-id="7c522-155">Overloaded Methods</span></span>

<span data-ttu-id="7c522-156">オーバーロードされたメソッドは、指定された型の名前が同じで、引数が異なるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="7c522-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="7c522-157">でF#は、通常、オーバーロードされたメソッドの代わりに、省略可能な引数が使用されます。</span><span class="sxs-lookup"><span data-stu-id="7c522-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="7c522-158">ただし、オーバーロードされたメソッドは、引数がカリー化形式ではなくタプル形式である場合に、その言語で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7c522-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="7c522-159">省略可能な引数</span><span class="sxs-lookup"><span data-stu-id="7c522-159">Optional Arguments</span></span>

<span data-ttu-id="7c522-160">F# 4.1 以降では、メソッドに既定のパラメーター値を持つ省略可能な引数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="7c522-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="7c522-161">これは、コードとのC#相互運用を容易にするためのものです。</span><span class="sxs-lookup"><span data-stu-id="7c522-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="7c522-162">構文の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7c522-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="7c522-163">`DefaultParameterValue` に渡される値は入力型と一致する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7c522-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="7c522-164">上のサンプルでは、これは `int`です。</span><span class="sxs-lookup"><span data-stu-id="7c522-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="7c522-165">整数以外の値を `DefaultParameterValue` に渡そうとすると、コンパイルエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="7c522-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="7c522-166">例: プロパティとメソッド</span><span class="sxs-lookup"><span data-stu-id="7c522-166">Example: Properties and Methods</span></span>

<span data-ttu-id="7c522-167">次の例には、フィールド、プライベート関数、プロパティ、および静的メソッドの例を含む型が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7c522-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="7c522-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="7c522-168">See also</span></span>

- [<span data-ttu-id="7c522-169">メンバー</span><span class="sxs-lookup"><span data-stu-id="7c522-169">Members</span></span>](index.md)
