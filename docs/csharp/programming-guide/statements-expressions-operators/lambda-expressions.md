---
title: ラムダ式 - C# プログラミング ガイド
ms.date: 07/29/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: c549b9fcc91401aed846afd39e656b60e16afb74
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937600"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="f2355-102">ラムダ式 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="f2355-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="f2355-103">"*ラムダ式*" は、次の 2 つのいずれかの形式を持つ式です。</span><span class="sxs-lookup"><span data-stu-id="f2355-103">A *lambda expression* is an expression of any of the following two forms:</span></span>

- <span data-ttu-id="f2355-104">[式形式のラムダ](#expression-lambdas)は、式本体に式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2355-104">[Expression lambda](#expression-lambdas) that has an expression as its body:</span></span>

  ```csharp
  (input-parameters) => expression
  ```

- <span data-ttu-id="f2355-105">[ステートメント形式のラムダ](#statement-lambdas)は、式本体にステートメント ブロックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2355-105">[Statement lambda](#statement-lambdas) that has a statement block as its body:</span></span>

  ```csharp  
  (input-parameters) => { <sequence-of-statements> }
  ```

<span data-ttu-id="f2355-106">[ラムダ宣言演算子`=>`](../../language-reference/operators/lambda-operator.md)を使用して、ラムダのパラメーター リストを式本体から分離します。</span><span class="sxs-lookup"><span data-stu-id="f2355-106">Use the [lambda declaration operator `=>`](../../language-reference/operators/lambda-operator.md) to separate the lambda's parameter list from its body.</span></span> <span data-ttu-id="f2355-107">ラムダ式を作成するには、ラムダ演算子の左辺に入力パラメーターを指定し (ある場合)、右辺に式またはステートメント ブロックを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2355-107">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator and an expression or a statement block on the other side.</span></span>

<span data-ttu-id="f2355-108">ラムダ式は、[デリゲート](../../language-reference/builtin-types/reference-types.md#the-delegate-type)型に変換できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-108">Any lambda expression can be converted to a [delegate](../../language-reference/builtin-types/reference-types.md#the-delegate-type) type.</span></span> <span data-ttu-id="f2355-109">ラムダ式を変換できるデリゲート型は、パラメータと戻り値の型で定義されます。</span><span class="sxs-lookup"><span data-stu-id="f2355-109">The delegate type to which a lambda expression can be converted is defined by the types of its parameters and return value.</span></span> <span data-ttu-id="f2355-110">ラムダ式が値を返さない場合は `Action` デリゲート型のいずれかに変換でき、値を返す場合は`Func` デリゲート型のいずれかに変換できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-110">If a lambda expression doesn't return a value, it can be converted to one of the `Action` delegate types; otherwise, it can be converted to one of the `Func` delegate types.</span></span> <span data-ttu-id="f2355-111">たとえば、2 つのパラメーターがあり、値を返さないラムダ式は、<xref:System.Action%602> デリゲートに変換できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-111">For example, a lambda expression that has two parameters and returns no value can be converted to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="f2355-112">1 つのパラメーターがあり、値を返すラムダ式は、<xref:System.Func%602> デリゲートに変換できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-112">A lambda expression that has one parameter and returns a value can be converted to a <xref:System.Func%602> delegate.</span></span> <span data-ttu-id="f2355-113">次の例では、`x` という名前のパラメーターを指定し、`x` の二乗値を返すラムダ式 `x => x * x` をデリゲート型の変数に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f2355-113">In the following example, the lambda expression `x => x * x`, which specifies a parameter that’s named `x` and returns the value of `x` squared, is assigned to a variable of a delegate type:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="f2355-114">式形式のラムダは、次の例に示すように、[式ツリー](../concepts/expression-trees/index.md)型にも変換できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-114">Expression lambdas also can be converted to the [expression tree](../concepts/expression-trees/index.md) types, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="f2355-115">ラムダ式は、デリゲート型または式ツリーのインスタンスを必要とするすべてのコードで使用できます。たとえば、<xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> メソッドの引数として使用すると、バックグラウンドで実行する必要があるコードを渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2355-115">You can use lambda expressions in any code that requires instances of delegate types or expression trees, for example as an argument to the <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> method to pass the code that should be executed in the background.</span></span> <span data-ttu-id="f2355-116">また、次の例に示すように、[C# で LINQ](../../linq/index.md) を作成する場合にもラムダ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-116">You also can use lambda expressions when you write [LINQ in C#](../../linq/index.md), as the following example shows:</span></span>

[!code-csharp-interactive[lambda is argument in LINQ](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="f2355-117">メソッド ベースの構文を使用して <xref:System.Linq.Enumerable?displayProperty=nameWithType> クラス (たとえば、LINQ to Objects、LINQ to XML など) の <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> メソッドを呼び出すと、パラメーターはデリゲート型 <xref:System.Func%602?displayProperty=nameWithType> になります。</span><span class="sxs-lookup"><span data-stu-id="f2355-117">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class, for example in LINQ to Objects and LINQ to XML, the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2355-118"><xref:System.Linq.Queryable?displayProperty=nameWithType> クラス (たとえば、LINQ to SQL など) の <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> メソッドを呼び出すと、パラメーター型は式ツリー型 [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>) になります。</span><span class="sxs-lookup"><span data-stu-id="f2355-118">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class, for example in LINQ to SQL, the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="f2355-119">どちらの場合も、同じラムダ式を使用してパラメーター値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-119">In both cases you can use the same lambda expression to specify the parameter value.</span></span> <span data-ttu-id="f2355-120">これにより、2 つの `Select` 呼び出しは外観が似ていますが、ラムダから実際に作成されるオブジェクトの型は異なります。</span><span class="sxs-lookup"><span data-stu-id="f2355-120">That makes the two `Select` calls to look similar although in fact the type of objects created from the lambdas is different.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="f2355-121">式形式のラムダ</span><span class="sxs-lookup"><span data-stu-id="f2355-121">Expression lambdas</span></span>

<span data-ttu-id="f2355-122">`=>` 演算子の右辺に式があるラムダ式を "*式形式のラムダ*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="f2355-122">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="f2355-123">式形式のラムダは、[式ツリー](../concepts/expression-trees/index.md)の構築に幅広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2355-123">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="f2355-124">式形式のラムダは式の結果を返します。基本的な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f2355-124">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="f2355-125">かっこはラムダの入力パラメーターが 1 つの場合のみ省略可能で、それ以外の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="f2355-125">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="f2355-126">入力パラメーターがないことを指定するには、次のように空のかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="f2355-126">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="f2355-127">入力パラメーターが 2 つ以上ある場合は、かっこで囲んで各パラメーターをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f2355-127">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="f2355-128">コンパイラによる入力の型の推論が不可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="f2355-128">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="f2355-129">次の例のように、型を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-129">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="f2355-130">入力パラメーターの型は、すべて明示的またはすべて暗黙的である必要があります。それ以外の場合は、[CS0748](../../misc/cs0748.md) コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f2355-130">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="f2355-131">式形式のラムダの本体を、メソッド呼び出しで構成できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-131">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="f2355-132">ただし、SQL Server などの .NET 共通言語ランタイムの外部で評価される式ツリーを作成する場合は、ラムダ式内でメソッド呼び出しを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2355-132">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="f2355-133">.NET 共通言語ランタイムのコンテキストの外部では、これらのメソッドは通用しません。</span><span class="sxs-lookup"><span data-stu-id="f2355-133">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="f2355-134">ステートメント形式のラムダ</span><span class="sxs-lookup"><span data-stu-id="f2355-134">Statement lambdas</span></span>

<span data-ttu-id="f2355-135">ステートメント形式のラムダは式形式のラムダに似ていますが、ステートメントが中かっこで囲まれる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f2355-135">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { <sequence-of-statements> }
```

<span data-ttu-id="f2355-136">ステートメント形式のラムダの本体は任意の数のステートメントで構成できますが、実際面では通常、2、3 個以下にします。</span><span class="sxs-lookup"><span data-stu-id="f2355-136">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="f2355-137">ステートメント形式のラムダを使用して式ツリーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="f2355-137">Statement lambdas cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="f2355-138">非同期ラムダ</span><span class="sxs-lookup"><span data-stu-id="f2355-138">Async lambdas</span></span>

<span data-ttu-id="f2355-139">[async](../../language-reference/keywords/async.md) キーワードと [await](../../language-reference/operators/await.md) キーワードを使用すると、非同期処理を組み込んだラムダ式およびステートメントを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-139">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/operators/await.md) keywords.</span></span> <span data-ttu-id="f2355-140">たとえば、次に示す Windows フォーム例には、非同期メソッド `ExampleMethodAsync`を呼び出して待機するイベント ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2355-140">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += button1_Click;
    }

    private async void button1_Click(object sender, EventArgs e)
    {
        await ExampleMethodAsync();
        textBox1.Text += "\r\nControl returned to Click event handler.\n";
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="f2355-141">非同期ラムダを使用して、同じイベント ハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-141">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="f2355-142">このハンドラーを追加するには、次の例に示すように、ラムダ パラメーター リストの前に `async` 修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="f2355-142">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

```csharp
public partial class Form1 : Form
{
    public Form1()
    {
        InitializeComponent();
        button1.Click += async (sender, e) =>
        {
            await ExampleMethodAsync();
            textBox1.Text += "\r\nControl returned to Click event handler.\n";
        };
    }

    private async Task ExampleMethodAsync()
    {
        // The following line simulates a task-returning asynchronous process.
        await Task.Delay(1000);
    }
}
```

<span data-ttu-id="f2355-143">非同期メソッドの作成および使用方法の詳細については、「[Async および Await を使用した非同期プログラミング](../concepts/async/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2355-143">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="f2355-144">ラムダ式とタプル</span><span class="sxs-lookup"><span data-stu-id="f2355-144">Lambda expressions and tuples</span></span>

<span data-ttu-id="f2355-145">C# 7.0 以降、C# 言語には、[タプル](../../tuples.md)のサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="f2355-145">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="f2355-146">タプルは、ラムダ式への引数として指定できるほか、ラムダ式で返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="f2355-146">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="f2355-147">場合によっては、C# コンパイラは、型の推定を使用して、タプル コンポーネントの型を判定することもあります。</span><span class="sxs-lookup"><span data-stu-id="f2355-147">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="f2355-148">タプルを定義するには、そのコンポーネントのコンマ区切りリストをかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="f2355-148">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="f2355-149">次の例では、3 つのコンポーネントを持つタプルを使用して、ラムダ式に連続した数値を渡します。このラムダ式により、各値が 2 倍になり、乗算の結果を格納する 3 つのコンポーネントを持つタプルが返されます。</span><span class="sxs-lookup"><span data-stu-id="f2355-149">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="f2355-150">通常、タプルのフィールド名は `Item1`、`Item2` のようになります。ただし、次の例のとおり、名前付きのコンポーネントを持つタプルを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="f2355-150">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="f2355-151">C# のタプルの詳細については、「[C# のタプル型](../../tuples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2355-151">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="f2355-152">標準クエリ演算子を使用したラムダ</span><span class="sxs-lookup"><span data-stu-id="f2355-152">Lambdas with the standard query operators</span></span>

<span data-ttu-id="f2355-153">いくつかある実装の中で特に、LINQ to Objects は、汎用デリゲートの <xref:System.Func%601> ファミリに属する型の入力パラメーターを持ちます。</span><span class="sxs-lookup"><span data-stu-id="f2355-153">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="f2355-154">これらのデリゲートは、型パラメーターを使用して、入力パラメーターの数と型に加え、デリゲートの戻り値の型を定義します。</span><span class="sxs-lookup"><span data-stu-id="f2355-154">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="f2355-155">`Func` デリゲートは、ソース データのセット内の各要素に適用されるユーザー定義の式をカプセル化する場合に非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="f2355-155">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="f2355-156">たとえば、<xref:System.Func%602>デリゲート型を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="f2355-156">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="f2355-157">このデリゲートを `Func<int, bool>` としてインスタンス化できます。 `int` は入力パラメーター、`bool` は戻り値です。</span><span class="sxs-lookup"><span data-stu-id="f2355-157">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="f2355-158">戻り値は必ず最後の型パラメーターで指定されます。</span><span class="sxs-lookup"><span data-stu-id="f2355-158">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="f2355-159">たとえば、`Func<int, string, bool>` は 2 つの入力パラメーター ( `int` と `string`) と戻り値の型 `bool` を持つデリゲートを定義しています。</span><span class="sxs-lookup"><span data-stu-id="f2355-159">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="f2355-160">次の `Func` デリゲートを呼び出すと、入力パラメーターが 5 に等しいかどうかを示す true または false が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2355-160">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="f2355-161">たとえば、<xref:System.Linq.Queryable> 型で定義された標準クエリ演算子において、引数型が <xref:System.Linq.Expressions.Expression%601> の場合もラムダ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-161">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="f2355-162"><xref:System.Linq.Expressions.Expression%601> 引数を指定すると、ラムダは式ツリーにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="f2355-162">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="f2355-163">次の例では、<xref:System.Linq.Enumerable.Count%2A> 標準クエリ演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2355-163">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="f2355-164">入力パラメーターの型はコンパイラが推論できますが、明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2355-164">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="f2355-165">この特定のラムダ式は、2 で除算したときに剰余が 1 になる整数 (`n`) をカウントします。</span><span class="sxs-lookup"><span data-stu-id="f2355-165">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="f2355-166">次の例では、`numbers` 配列内で 9 より前にある要素をすべて含むシーケンスを作成します。これは、9 がシーケンス内で条件を満たさない最初の数値であるためです。</span><span class="sxs-lookup"><span data-stu-id="f2355-166">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="f2355-167">次の例では、複数の入力パラメーターをかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="f2355-167">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="f2355-168">このメソッドは、値が `numbers` 配列内のその位置を表す序数よりも小さい数値が出現するまで、その配列に含まれるすべての要素を返します。</span><span class="sxs-lookup"><span data-stu-id="f2355-168">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="f2355-169">ラムダ式の型の推定</span><span class="sxs-lookup"><span data-stu-id="f2355-169">Type inference in lambda expressions</span></span>

<span data-ttu-id="f2355-170">ラムダを記述する際、多くの場合は入力パラメーターの型を指定する必要はありません。これは、ラムダ本体やパラメーターの型など C# 言語仕様に記述されている要素に基づいて、コンパイラが型を推定できるためです。</span><span class="sxs-lookup"><span data-stu-id="f2355-170">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="f2355-171">ほとんどの標準クエリ演算子では、最初の入力がソース シーケンス内の要素の型です。</span><span class="sxs-lookup"><span data-stu-id="f2355-171">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="f2355-172">`IEnumerable<Customer>` を問い合わせると、入力変数は `Customer` オブジェクトであると推論されます。これは、そのメソッドとプロパティにアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f2355-172">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="f2355-173">ラムダの型の推定の一般規則は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f2355-173">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="f2355-174">ラムダにはデリゲート型と同じ数のパラメーターが含まれていなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f2355-174">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="f2355-175">ラムダに含まれる各入力パラメーターは、対応するデリゲート パラメーターに暗黙的に変換できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f2355-175">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="f2355-176">ラムダの戻り値 (ある場合) は、デリゲートの戻り値の型に暗黙的に変換できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="f2355-176">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="f2355-177">共通型システムには "ラムダ式" の概念が組み込まれていないため、ラムダ式自体は型を持ちません。</span><span class="sxs-lookup"><span data-stu-id="f2355-177">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="f2355-178">しかし、変則的ではあってもラムダ式の "型" を表現できると都合が良い場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f2355-178">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="f2355-179">このような場合の型は、ラムダ式の変換後のデリゲート型または <xref:System.Linq.Expressions.Expression> 型を指します。</span><span class="sxs-lookup"><span data-stu-id="f2355-179">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="capture-of-outer-variables-and-variable-scope-in-lambda-expressions"></a><span data-ttu-id="f2355-180">ラムダ式における外部変数のキャプチャと変数のスコープ</span><span class="sxs-lookup"><span data-stu-id="f2355-180">Capture of outer variables and variable scope in lambda expressions</span></span>

<span data-ttu-id="f2355-181">ラムダでは "*外部変数*" を参照できます。</span><span class="sxs-lookup"><span data-stu-id="f2355-181">Lambdas can refer to *outer variables*.</span></span> <span data-ttu-id="f2355-182">それは、そのラムダ式を定義しているメソッドのスコープ内にある変数、またはそのラムダ式を含む型のスコープ内にある変数です。</span><span class="sxs-lookup"><span data-stu-id="f2355-182">These are the variables that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="f2355-183">こうして取り込まれた変数は、ラムダ式で使用するために格納されます。これは、変数がスコープ外に出てガベージ コレクトされる場合でも変わりません。</span><span class="sxs-lookup"><span data-stu-id="f2355-183">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="f2355-184">外部変数は、ラムダ式で使用される前に明示的に代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2355-184">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="f2355-185">次の例は、こうした規則を示しています。</span><span class="sxs-lookup"><span data-stu-id="f2355-185">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="f2355-186">ラムダ式における変数のスコープには、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2355-186">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="f2355-187">取り込まれた変数は、その変数を参照するデリゲートがガベージ コレクションの対象になるまでガベージ コレクトされません。</span><span class="sxs-lookup"><span data-stu-id="f2355-187">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="f2355-188">ラムダ式内に導入された変数は、外側のメソッドでは参照できません。</span><span class="sxs-lookup"><span data-stu-id="f2355-188">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="f2355-189">ラムダ式は、外側のメソッドから [in](../../language-reference/keywords/in-parameter-modifier.md)、[ref](../../language-reference/keywords/ref.md)、または [out](../../language-reference/keywords/out-parameter-modifier.md) パラメーターを直接取り込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="f2355-189">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="f2355-190">ラムダ式に含まれる [return](../../language-reference/keywords/return.md) ステートメントで外側のメソッドが戻ることはありません。</span><span class="sxs-lookup"><span data-stu-id="f2355-190">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="f2355-191">ジャンプ先がラムダ式ブロックの外側にある場合は、ラムダ式に [goto](../../language-reference/keywords/goto.md)、[break](../../language-reference/keywords/break.md)、または [continue](../../language-reference/keywords/continue.md) ステートメントを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f2355-191">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="f2355-192">また、ジャンプ先がブロックの内部にある場合に、ラムダ式ブロックの外部でジャンプ ステートメントを使用するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="f2355-192">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f2355-193">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="f2355-193">C# language specification</span></span>

<span data-ttu-id="f2355-194">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2355-194">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="f2355-195">参考書籍の該当する章</span><span class="sxs-lookup"><span data-stu-id="f2355-195">Featured book chapter</span></span>

<span data-ttu-id="f2355-196">「[Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)」(『[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers (C# 3.0 クックブック (第 3 版): C# 3.0 プログラマ向けの 250 以上のソリューション)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)』)</span><span class="sxs-lookup"><span data-stu-id="f2355-196">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2355-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="f2355-197">See also</span></span>

- [<span data-ttu-id="f2355-198">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f2355-198">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f2355-199">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="f2355-199">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="f2355-200">式ツリー</span><span class="sxs-lookup"><span data-stu-id="f2355-200">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="f2355-201">ローカル関数とラムダ式の比較</span><span class="sxs-lookup"><span data-stu-id="f2355-201">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="f2355-202">暗黙的に型指定されるラムダ式</span><span class="sxs-lookup"><span data-stu-id="f2355-202">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="f2355-203">Visual Studio 2008 C# Samples (Visual Studio 2008 の C# サンプル) (LINQ サンプル クエリ ファイルと XQuery プログラムを参照してください)</span><span class="sxs-lookup"><span data-stu-id="f2355-203">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="f2355-204">Recursive lambda expressions (再帰的なラムダ式)</span><span class="sxs-lookup"><span data-stu-id="f2355-204">Recursive lambda expressions</span></span>](https://docs.microsoft.com/archive/blogs/madst/recursive-lambda-expressions)
