---
title: in パラメーター修飾子 - C# リファレンス
ms.custom: seodec18
ms.date: 02/12/2019
helpviewer_keywords:
- parameters [C#], in
- in parameters [C#]
ms.openlocfilehash: 5a765a330e4d9efe22943538503c0822e1c9dfdb
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219556"
---
# <a name="in-parameter-modifier-c-reference"></a><span data-ttu-id="a2335-102">in パラメーター修飾子 (C# リファレンス)</span><span class="sxs-lookup"><span data-stu-id="a2335-102">in parameter modifier (C# Reference)</span></span>

<span data-ttu-id="a2335-103">`in` キーワードによって、参照により引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="a2335-103">The `in` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="a2335-104">これは、[ref](ref.md) または [out](out-parameter-modifier.md) キーワードと似ています。ただし、呼び出されたメソッドで `in` 引数を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2335-104">It is like the [ref](ref.md) or [out](out-parameter-modifier.md) keywords, except that `in` arguments cannot be modified by the called method.</span></span> <span data-ttu-id="a2335-105">`ref` 引数には変更が許される一方で、`out` 引数の場合、呼び出されたメソッドによって変更される必要があります。そのような変更は、呼び出し元のコンテキストで観察できます。</span><span class="sxs-lookup"><span data-stu-id="a2335-105">Whereas `ref` arguments may be modified,  `out` arguments must be modified by the called method, and those modifications are observable in the calling context.</span></span>

[!code-csharp-interactive[cs-in-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/InParameterModifier.cs#1)]  

<span data-ttu-id="a2335-106">前の例は、通常、`in` 修飾子が呼び出しサイトでは不要であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a2335-106">The preceding example demonstrates that the `in` modifier is usually unnecessary at the call site.</span></span> <span data-ttu-id="a2335-107">これはメソッド宣言でのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="a2335-107">It is only required in the method declaration.</span></span>


> [!NOTE] 
> <span data-ttu-id="a2335-108">`foreach` ステートメントの一部、または LINQ クエリの `join` 句の一部として、型パラメーターが反変であることを示すために `in` キーワードをジェネリック型パラメーターで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2335-108">The `in` keyword can also be used with a generic type parameter to specify that the type parameter is contravariant, as part of a `foreach` statement, or as part of a `join` clause in a LINQ query.</span></span> <span data-ttu-id="a2335-109">これらのコンテキストでの `in` キーワードの使用の詳細については、これらすべての使用に関するリンクを提供する「[in](in.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2335-109">For more information on the use of the `in` keyword in these contexts, see [in](in.md), which provides links to all those uses.</span></span>
  
 <span data-ttu-id="a2335-110">`in` 引数として渡される変数は、メソッド呼び出しで渡される前に初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2335-110">Variables passed as `in` arguments must be initialized before being passed in a method call.</span></span> <span data-ttu-id="a2335-111">ただし、呼び出されたメソッドでは値の割り当てや、引数の変更を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="a2335-111">However, the called method may not assign a value or modify the argument.</span></span>  

<span data-ttu-id="a2335-112">`in` パラメーター修飾子は C# 7.2 以降で使用可能です。</span><span class="sxs-lookup"><span data-stu-id="a2335-112">The `in` parameter modifier is available in C# 7.2 and later.</span></span> <span data-ttu-id="a2335-113">以前のバージョンでは、コンパイラ エラー `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="a2335-113">Previous versions generate compiler error `CS8107` ("Feature 'readonly references' is not available in C# 7.0.</span></span> <span data-ttu-id="a2335-114">Please use language version 7.2 or greater." ('読み取り専用参照' 機能は C# 7.0 では使用できません。7.2 以上の言語バージョンを使用してください)) が生成されました。コンパイラ言語のバージョンを構成するには、「[C# 言語のバージョンの選択](../configure-language-version.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a2335-114">Please use language version 7.2 or greater.") To configure the compiler language version, see [Select the C# language version](../configure-language-version.md).</span></span>

 <span data-ttu-id="a2335-115">`in`、`ref`、`out`キーワードは実行時の動作が異なりますが、コンパイル時にメソッド シグネチャの一部とは見なされません。</span><span class="sxs-lookup"><span data-stu-id="a2335-115">Although the `in`, `ref`, and `out` keywords cause different run-time behavior, they are not considered part of the method signature at compile time.</span></span> <span data-ttu-id="a2335-116">したがって、唯一の違いが、1 つのメソッドは `ref` または `in` 引数を受け取り、もう一方のメソッドは `out` 引数を受け取ることである場合、メソッドはオーバーロードできません。</span><span class="sxs-lookup"><span data-stu-id="a2335-116">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="a2335-117">たとえば、次のコードはコンパイルされません。</span><span class="sxs-lookup"><span data-stu-id="a2335-117">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on in, ref and out".
    public void SampleMethod(in int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="a2335-118">`in` の有無に基づくオーバーロードが可能です。</span><span class="sxs-lookup"><span data-stu-id="a2335-118">Overloading based on the presence of `in` is allowed:</span></span>  
  
```csharp
class InOverloads
{
    public void SampleMethod(in int i) { }
    public void SampleMethod(int i) { }
}
```

## <a name="overload-resolution-rules"></a><span data-ttu-id="a2335-119">オーバーロードの解決ルール</span><span class="sxs-lookup"><span data-stu-id="a2335-119">Overload resolution rules</span></span>

<span data-ttu-id="a2335-120">`in` 引数の意図を理解して、値と `in` 引数の比較によって、メソッドに対するオーバーロードの解決ルールを理解できます。</span><span class="sxs-lookup"><span data-stu-id="a2335-120">You can understand the overload resolution rules for methods with by value vs. `in` arguments by understanding the motivation for `in` arguments.</span></span> <span data-ttu-id="a2335-121">`in` パラメーターを使用してメソッドを定義すると、パフォーマンスを最適化できる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a2335-121">Defining methods using `in` parameters is a potential performance optimization.</span></span> <span data-ttu-id="a2335-122">一部の `struct` 型引数は、サイズが大きくなる可能性があり、メソッドが短いループまたは重要なコード パスで呼び出される場合、その構造のコピーのコストが重要になります。</span><span class="sxs-lookup"><span data-stu-id="a2335-122">Some `struct` type arguments may be large in size, and when methods are called in tight loops or critical code paths, the cost of copying those structures is critical.</span></span> <span data-ttu-id="a2335-123">呼び出されたメソッドは引数の状態を変更しないため、メソッドで `in` パラメーターを宣言して、参照で安全に渡すことができる引数を指定します。</span><span class="sxs-lookup"><span data-stu-id="a2335-123">Methods declare `in` parameters to specify that arguments may be passed by reference safely because the called method does not modify the state of that argument.</span></span> <span data-ttu-id="a2335-124">参照によりこれらの引数を渡して、(可能性がある) 高額なコピーを回避します。</span><span class="sxs-lookup"><span data-stu-id="a2335-124">Passing those arguments by reference avoids the (potentially) expensive copy.</span></span> 

<span data-ttu-id="a2335-125">呼び出しサイトで引数に `in` を指定することは、通常は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a2335-125">Specifying `in` for arguments at the call site is typically optional.</span></span> <span data-ttu-id="a2335-126">値で引数を渡す場合と `in` 修飾子を使用して参照で渡す場合の間に、セマンティックの相違点はありません。</span><span class="sxs-lookup"><span data-stu-id="a2335-126">There is no semantic difference between passing arguments by value and passing them by reference using the `in` modifier.</span></span> <span data-ttu-id="a2335-127">引数の値が変更される可能性があることを示す必要はないため、呼び出しサイトの `in` 修飾子は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a2335-127">The `in` modifier at the call site is optional because you don't need to indicate that the argument's value might be changed.</span></span> <span data-ttu-id="a2335-128">呼び出しサイトで `in` 修飾子を明示的に追加して、引数が値ではなく、参照で渡されるようにします。</span><span class="sxs-lookup"><span data-stu-id="a2335-128">You explicitly add the `in` modifier at the call site to ensure the argument is passed by reference, not by value.</span></span> <span data-ttu-id="a2335-129">明示的に `in` を使用すると、次の 2 つの効果があります。</span><span class="sxs-lookup"><span data-stu-id="a2335-129">Explicitly using `in` has the following two effects:</span></span>

<span data-ttu-id="a2335-130">1 つ目は、呼び出しサイトで `in` を指定すると、一致する `in` パラメーターで定義されたメソッドがコンパイラで強制的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="a2335-130">First, specifying `in` at the call site forces the compiler to select a method defined with a matching `in` parameter.</span></span> <span data-ttu-id="a2335-131">それ以外の場合は、2 つのメソッドで `in` の有無のみが異なるときは、値によるオーバーロードの方が適しています。</span><span class="sxs-lookup"><span data-stu-id="a2335-131">Otherwise, when two methods differ only in the presence of `in`, the by value overload is a better match.</span></span>

<span data-ttu-id="a2335-132">2 つ目は、`in` を指定して、参照で引数を渡す意図を宣言します。</span><span class="sxs-lookup"><span data-stu-id="a2335-132">Second, specifying `in` declares your intent to pass an argument by reference.</span></span> <span data-ttu-id="a2335-133">`in` で使用される引数では、直接参照できる場所を表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2335-133">The argument used with `in` must represent a location that can be directly referred to.</span></span> <span data-ttu-id="a2335-134">`out` および `ref` 引数と同じ一般ルールが適用されます。定数、通常のプロパティ、または値を生成するその他の式を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2335-134">The same general rules for `out` and `ref` arguments apply: You cannot use constants, ordinary properties, or other expressions that produce values.</span></span> <span data-ttu-id="a2335-135">それ以外の場合は、呼び出しサイトで `in` を省略すると、メソッドに読み取り専用の参照で渡すために、一時変数の作成を許可することが、コンパイラに通知されます。</span><span class="sxs-lookup"><span data-stu-id="a2335-135">Otherwise, omitting `in` at the call site informs the compiler that you will allow it to create a temporary variable to pass by read-only reference to the method.</span></span> <span data-ttu-id="a2335-136">コンパイラでは、一時変数を作成して、`in` 引数でのいくつかの制限に対処します。</span><span class="sxs-lookup"><span data-stu-id="a2335-136">The compiler creates a temporary variable to overcome several restrictions with `in` arguments:</span></span>

- <span data-ttu-id="a2335-137">一時変数では、`in` パラメーターとしてコンパイル時の定数を許可します。</span><span class="sxs-lookup"><span data-stu-id="a2335-137">A temporary variable allows compile-time constants as `in` parameters.</span></span>
- <span data-ttu-id="a2335-138">一時変数では、プロパティ、または `in` パラメーターのその他の式を許可します。</span><span class="sxs-lookup"><span data-stu-id="a2335-138">A temporary variable allows properties, or other expressions for `in` parameters.</span></span>
- <span data-ttu-id="a2335-139">一時変数では、引数型からパラメーターの型への暗黙の変換がある引数を許可します。</span><span class="sxs-lookup"><span data-stu-id="a2335-139">A temporary variable allows arguments where there is an implicit conversion from the argument type to the parameter type.</span></span>

<span data-ttu-id="a2335-140">先のすべてのインスタンスで、コンパイラは定数、プロパティ、またはその他の式の値を格納する一時変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="a2335-140">In all the preceding instances, the compiler creates a temporary variable that stores the value of the constant, property, or other expression.</span></span>

<span data-ttu-id="a2335-141">これらのルールが発生するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a2335-141">The following code illustrates these rules:</span></span>

```csharp
static void Method(in int argument)
{
    // implementation removed
}

Method(5); // OK, temporary variable created.
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // OK, temporary int created with the value 0
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // passed by readonly reference
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="a2335-142">ここでは、値の引数で使用する別のメソッドが使用できたと想定します。</span><span class="sxs-lookup"><span data-stu-id="a2335-142">Now, suppose another method using by value arguments was available.</span></span> <span data-ttu-id="a2335-143">次のコードに示すように、結果が変更されます。</span><span class="sxs-lookup"><span data-stu-id="a2335-143">The results change as shown in the following code:</span></span>

```csharp
static void Method(int argument)
{
    // implementation removed
}

static void Method(in int argument)
{
    // implementation removed
}

Method(5); // Calls overload passed by value
Method(5L); // CS1503: no implicit conversion from long to int
short s = 0;
Method(s); // Calls overload passed by value.
Method(in s); // CS1503: cannot convert from in short to in int
int i = 42;
Method(i); // Calls overload passed by value
Method(in i); // passed by readonly reference, explicitly using `in`
```

<span data-ttu-id="a2335-144">引数が参照で渡されるメソッドの呼び出しは、最後のメソッドのみです。</span><span class="sxs-lookup"><span data-stu-id="a2335-144">The only method call where the argument is passed by reference is the final one.</span></span>

> [!NOTE]
> <span data-ttu-id="a2335-145">先のコードでは、わかりやすくするために `int` を引数型として使用します。</span><span class="sxs-lookup"><span data-stu-id="a2335-145">The preceding code uses `int` as the argument type for simplicity.</span></span> <span data-ttu-id="a2335-146">`int` は最新のマシンの参照より大きくなることはないため、読み取り専用の参照として単一の `int` を渡すメリットはありません。</span><span class="sxs-lookup"><span data-stu-id="a2335-146">Because `int` is no larger than a reference in most modern machines, there is no benefit to passing a single `int` as a readonly reference.</span></span> 

## <a name="limitations-on-in-parameters"></a><span data-ttu-id="a2335-147">`in` パラメーターの制限</span><span class="sxs-lookup"><span data-stu-id="a2335-147">Limitations on `in` parameters</span></span>

<span data-ttu-id="a2335-148">次の種類のメソッドには、`in`、`ref`、`out` キーワードを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2335-148">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="a2335-149">[async](async.md) 修飾子を使用して定義した Async メソッド。</span><span class="sxs-lookup"><span data-stu-id="a2335-149">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="a2335-150">[yield return](yield.md) または `yield break` ステートメントを含む Iterator メソッド。</span><span class="sxs-lookup"><span data-stu-id="a2335-150">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="a2335-151">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="a2335-151">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2335-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2335-152">See also</span></span>

- [<span data-ttu-id="a2335-153">C# リファレンス</span><span class="sxs-lookup"><span data-stu-id="a2335-153">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a2335-154">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="a2335-154">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a2335-155">C# のキーワード</span><span class="sxs-lookup"><span data-stu-id="a2335-155">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a2335-156">メソッド パラメーター</span><span class="sxs-lookup"><span data-stu-id="a2335-156">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="a2335-157">安全で効率的なコードを記述する</span><span class="sxs-lookup"><span data-stu-id="a2335-157">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
