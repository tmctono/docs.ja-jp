---
title: ラムダ式 - C# プログラミング ガイド
ms.custom: seodec18
ms.date: 03/14/2019
helpviewer_keywords:
- lambda expressions [C#]
- outer variables [C#]
- statement lambda [C#]
- expression lambda [C#]
- expressions [C#], lambda
ms.assetid: 57e3ba27-9a82-4067-aca7-5ca446b7bf93
ms.openlocfilehash: dd9b77a90030a96d17104c8c0e48964b6a85d165
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2019
ms.locfileid: "58125734"
---
# <a name="lambda-expressions-c-programming-guide"></a><span data-ttu-id="03c0b-102">ラムダ式 (C# プログラミング ガイド)</span><span class="sxs-lookup"><span data-stu-id="03c0b-102">Lambda expressions (C# Programming Guide)</span></span>

<span data-ttu-id="03c0b-103">"*ラムダ式*" は、オブジェクトとして扱われるコード ブロック (式またはステートメント ブロック) です。</span><span class="sxs-lookup"><span data-stu-id="03c0b-103">A *lambda expression* is a block of code (an expression or a statement block) that is treated as an object.</span></span> <span data-ttu-id="03c0b-104">これは、引数としてメソッドに渡すことができるほか、メソッドの呼び出しによって返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-104">It can be passed as an argument to methods, and it can also be returned by method calls.</span></span> <span data-ttu-id="03c0b-105">ラムダ式は、次の処理によく使用されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-105">Lambda expressions are used extensively for:</span></span>

- <span data-ttu-id="03c0b-106"><xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType> など、非同期メソッドに対して実行されるコードを渡す。</span><span class="sxs-lookup"><span data-stu-id="03c0b-106">Passing the code that is to be executed to asynchronous methods, such as <xref:System.Threading.Tasks.Task.Run(System.Action)?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="03c0b-107">[LINQ クエリ式](../../linq/index.md)を記述する。</span><span class="sxs-lookup"><span data-stu-id="03c0b-107">Writing [LINQ query expressions](../../linq/index.md).</span></span>

- <span data-ttu-id="03c0b-108">[式ツリー](../concepts/expression-trees/index.md)を作成する。</span><span class="sxs-lookup"><span data-stu-id="03c0b-108">Creating [expression trees](../concepts/expression-trees/index.md).</span></span>

<span data-ttu-id="03c0b-109">ラムダ式は、デリゲート、またはデリゲートにコンパイルされる式ツリーとして表現できるコードです。</span><span class="sxs-lookup"><span data-stu-id="03c0b-109">Lambda expressions are code that can be represented either as a delegate, or as an expression tree that compiles to a delegate.</span></span> <span data-ttu-id="03c0b-110">ラムダ式の特定のデリゲート型は、パラメーターや戻り値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-110">The specific delegate type of a lambda expression depends on its parameters and return value.</span></span> <span data-ttu-id="03c0b-111">値を返さないラムダ式は、そのパラメーター数に応じて、特定の `Action` デリゲートに対応します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-111">Lambda expressions that don't return a value correspond to a specific `Action` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="03c0b-112">値を返すラムダ式は、そのパラメーター数に応じて、特定の `Func` デリゲートに対応します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-112">Lambda expressions that return a value correspond to a specific `Func` delegate, depending on its number of parameters.</span></span> <span data-ttu-id="03c0b-113">たとえば、2 つのパラメーターがあっても値を返さないラムダ式は、<xref:System.Action%602> デリゲートに対応します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-113">For example, a lambda expression that has two parameters but returns no value corresponds to an <xref:System.Action%602> delegate.</span></span> <span data-ttu-id="03c0b-114">パラメーターが 1 つあり、値を返すラムダ式は、<xref:System.Func%602> デリゲートに対応します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-114">A lambda expression that has one parameter and returns a value corresponds to <xref:System.Func%602> delegate.</span></span>

<span data-ttu-id="03c0b-115">ラムダ式は、`=>` ([ラムダ宣言演算子](../../language-reference/operators/lambda-operator.md)) を使用して、ラムダのパラメーター リストを実行可能コードから分離します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-115">A lambda expression uses `=>`, the [lambda declaration operator](../../language-reference/operators/lambda-operator.md), to separate the lambda's parameter list from its executable code.</span></span> <span data-ttu-id="03c0b-116">ラムダ式を作成するには、ラムダ演算子の左側に入力パラメーター (ある場合) を指定し、反対側に式またはステートメント ブロックを置きます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-116">To create a lambda expression, you specify input parameters (if any) on the left side of the lambda operator, and you put the expression or statement block on the other side.</span></span> <span data-ttu-id="03c0b-117">たとえば、1 行のラムダ式 `x => x * x` は、`x` という名前のパラメーターを指定し、`x` を 2 乗した値を返します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-117">For example, the single-line lambda expression `x => x * x` specifies a parameter that’s named `x` and returns the value of `x` squared.</span></span> <span data-ttu-id="03c0b-118">次の例に示すように、この式をデリゲート型に割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-118">You can assign this expression to a delegate type, as the following example shows:</span></span>

[!code-csharp-interactive[lambda is delegate](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Delegate)]

<span data-ttu-id="03c0b-119">さらに、ラムダ式を式ツリー型に代入することもできます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-119">You also can assign a lambda expression to an expression tree type:</span></span>

[!code-csharp-interactive[lambda is expression tree](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#ExpressionTree)]

<span data-ttu-id="03c0b-120">また、メソッドの引数として直接渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-120">Or you can pass it directly as a method argument:</span></span>

[!code-csharp-interactive[lambda is argument](~/samples/snippets/csharp/programming-guide/lambda-expressions/Introduction.cs#Argument)]

<span data-ttu-id="03c0b-121">メソッド ベースの構文を使用して (LINQ to Objects および LINQ to XML の場合と同様に) <xref:System.Linq.Enumerable?displayProperty=nameWithType> クラスの <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> メソッドを呼び出すと、パラメーターはデリゲート型 <xref:System.Func%602?displayProperty=nameWithType> になります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-121">When you use method-based syntax to call the <xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Enumerable?displayProperty=nameWithType> class (as you do in LINQ to Objects and LINQ to XML) the parameter is a delegate type <xref:System.Func%602?displayProperty=nameWithType>.</span></span> <span data-ttu-id="03c0b-122">ラムダ式はデリゲートを作成するための最も便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="03c0b-122">A lambda expression is the most convenient way to create that delegate.</span></span> <span data-ttu-id="03c0b-123">メソッド ベースの構文を使用して (LINQ to XML の場合と同様に) <xref:System.Linq.Queryable?displayProperty=nameWithType> クラスの <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> メソッドを呼び出すと、パラメーターは式ツリー型 [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>) になります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-123">When you call the <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType> method in the <xref:System.Linq.Queryable?displayProperty=nameWithType> class (as you do in LINQ to SQL) the parameter type is an expression tree type [`Expression<Func<TSource,TResult>>`](<xref:System.Linq.Expressions.Expression%601>).</span></span> <span data-ttu-id="03c0b-124">ラムダ式は、こうした式ツリーを構築するための非常に簡潔な方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-124">Again, a lambda expression is just a very concise way to construct that expression tree.</span></span> <span data-ttu-id="03c0b-125">ラムダを使用すると `Select` 呼び出しの外観を似たものにできますが、ラムダから実際に作成されるオブジェクトの型は異なります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-125">The lambdas allow the `Select` calls to look similar although in fact the type of object created from the lambda is different.</span></span>

<span data-ttu-id="03c0b-126">[匿名メソッド](anonymous-methods.md)に適用される制限は、すべてラムダ式にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-126">All restrictions that apply to [anonymous methods](anonymous-methods.md) also apply to lambda expressions.</span></span>
  
## <a name="expression-lambdas"></a><span data-ttu-id="03c0b-127">式形式のラムダ</span><span class="sxs-lookup"><span data-stu-id="03c0b-127">Expression lambdas</span></span>

<span data-ttu-id="03c0b-128">`=>` 演算子の右辺に式があるラムダ式を "*式形式のラムダ*" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-128">A lambda expression with an expression on the right side of the `=>` operator is called an *expression lambda*.</span></span> <span data-ttu-id="03c0b-129">式形式のラムダは、[式ツリー](../concepts/expression-trees/index.md)の構築に幅広く使用されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-129">Expression lambdas are used extensively in the construction of [expression trees](../concepts/expression-trees/index.md).</span></span> <span data-ttu-id="03c0b-130">式形式のラムダは式の結果を返します。基本的な形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03c0b-130">An expression lambda returns the result of the expression and takes the following basic form:</span></span>

```csharp
(input-parameters) => expression
```

<span data-ttu-id="03c0b-131">かっこはラムダの入力パラメーターが 1 つの場合のみ省略可能で、それ以外の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="03c0b-131">The parentheses are optional only if the lambda has one input parameter; otherwise they are required.</span></span>

<span data-ttu-id="03c0b-132">入力パラメーターがないことを指定するには、次のように空のかっこを使用します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-132">Specify zero input parameters with empty parentheses:</span></span>  

[!code-csharp[zero parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ZeroParameters)]

<span data-ttu-id="03c0b-133">入力パラメーターが 2 つ以上ある場合は、かっこで囲んで各パラメーターをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-133">Two or more input parameters are separated by commas enclosed in parentheses:</span></span>

[!code-csharp[two parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#TwoParameters)]

<span data-ttu-id="03c0b-134">コンパイラによる入力の型の推論が不可能な場合があります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-134">Sometimes it's impossible for the compiler to infer the input types.</span></span> <span data-ttu-id="03c0b-135">次の例のように、型を明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-135">You can specify the types explicitly as shown in the following example:</span></span>

[!code-csharp[explicitly typed parameters](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#ExplicitlyTypedParameters)]

<span data-ttu-id="03c0b-136">入力パラメーターの型は、すべて明示的またはすべて暗黙的である必要があります。それ以外の場合は、[CS0748](../../misc/cs0748.md) コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-136">Input parameter types must be all explicit or all implicit; otherwise, a [CS0748](../../misc/cs0748.md) compiler error occurs.</span></span>

<span data-ttu-id="03c0b-137">式形式のラムダの本体を、メソッド呼び出しで構成できます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-137">The body of an expression lambda can consist of a method call.</span></span> <span data-ttu-id="03c0b-138">ただし、SQL Server などの .NET 共通言語ランタイムの外部で評価される式ツリーを作成する場合は、ラムダ式内でメソッド呼び出しを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-138">However, if you are creating expression trees that are evaluated outside the context of the .NET common language runtime, such as in SQL Server, you should not use method calls in lambda expressions.</span></span> <span data-ttu-id="03c0b-139">.NET 共通言語ランタイムのコンテキストの外部では、これらのメソッドは通用しません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-139">The methods will have no meaning outside the context of the .NET common language runtime.</span></span>

## <a name="statement-lambdas"></a><span data-ttu-id="03c0b-140">ステートメント形式のラムダ</span><span class="sxs-lookup"><span data-stu-id="03c0b-140">Statement lambdas</span></span>

<span data-ttu-id="03c0b-141">ステートメント形式のラムダは式形式のラムダに似ていますが、ステートメントが中かっこで囲まれる点が異なります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-141">A statement lambda resembles an expression lambda except that the statement(s) is enclosed in braces:</span></span>

```csharp  
(input-parameters) => { statement; }
```

<span data-ttu-id="03c0b-142">ステートメント形式のラムダの本体は任意の数のステートメントで構成できますが、実際面では通常、2、3 個以下にします。</span><span class="sxs-lookup"><span data-stu-id="03c0b-142">The body of a statement lambda can consist of any number of statements; however, in practice there are typically no more than two or three.</span></span>

[!code-csharp-interactive[statement lambda](~/samples/snippets/csharp/programming-guide/lambda-expressions/ExpressionAndStatementLambdas.cs#StatementLambda)]

<span data-ttu-id="03c0b-143">匿名メソッドと同様、ステートメント形式のラムダを使用して式ツリーを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-143">Statement lambdas, like anonymous methods, cannot be used to create expression trees.</span></span>
  
## <a name="async-lambdas"></a><span data-ttu-id="03c0b-144">非同期ラムダ</span><span class="sxs-lookup"><span data-stu-id="03c0b-144">Async lambdas</span></span>

<span data-ttu-id="03c0b-145">[async](../../language-reference/keywords/async.md) キーワードと [await](../../language-reference/keywords/await.md) キーワードを使用すると、非同期処理を組み込んだラムダ式およびステートメントを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-145">You can easily create lambda expressions and statements that incorporate asynchronous processing by using the [async](../../language-reference/keywords/async.md) and [await](../../language-reference/keywords/await.md) keywords.</span></span> <span data-ttu-id="03c0b-146">たとえば、次に示す Windows フォーム例には、非同期メソッド `ExampleMethodAsync`を呼び出して待機するイベント ハンドラーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="03c0b-146">For example, the following Windows Forms example contains an event handler that calls and awaits an async method, `ExampleMethodAsync`.</span></span>

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

<span data-ttu-id="03c0b-147">非同期ラムダを使用して、同じイベント ハンドラーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-147">You can add the same event handler by using an async lambda.</span></span> <span data-ttu-id="03c0b-148">このハンドラーを追加するには、次の例に示すように、ラムダ パラメーター リストの前に `async` 修飾子を追加します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-148">To add this handler, add an `async` modifier before the lambda parameter list, as the following example shows:</span></span>

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

<span data-ttu-id="03c0b-149">非同期メソッドの作成および使用方法の詳細については、「[Async および Await を使用した非同期プログラミング](../concepts/async/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03c0b-149">For more information about how to create and use async methods, see [Asynchronous Programming with async and await](../concepts/async/index.md).</span></span>

## <a name="lambda-expressions-and-tuples"></a><span data-ttu-id="03c0b-150">ラムダ式とタプル</span><span class="sxs-lookup"><span data-stu-id="03c0b-150">Lambda expressions and tuples</span></span>

<span data-ttu-id="03c0b-151">C# 7.0 以降、C# 言語には、[タプル](../../tuples.md)のサポートが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="03c0b-151">Starting with C# 7.0, the C# language provides built-in support for [tuples](../../tuples.md).</span></span> <span data-ttu-id="03c0b-152">タプルは、ラムダ式への引数として指定できるほか、ラムダ式で返すこともできます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-152">You can provide a tuple as an argument to a lambda expression, and your lambda expression can also return a tuple.</span></span> <span data-ttu-id="03c0b-153">場合によっては、C# コンパイラは、型の推定を使用して、タプル コンポーネントの型を判定することもあります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-153">In some cases, the C# compiler uses type inference to determine the types of tuple components.</span></span>

<span data-ttu-id="03c0b-154">タプルを定義するには、そのコンポーネントのコンマ区切りリストをかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-154">You define a tuple by enclosing a comma-delimited list of its components in parentheses.</span></span> <span data-ttu-id="03c0b-155">次の例では、3 つのコンポーネントを持つタプルを使用して、ラムダ式に連続した数値を渡します。このラムダ式により、各値が 2 倍になり、乗算の結果を格納する 3 つのコンポーネントを持つタプルが返されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-155">The following example uses tuple with three components to pass a sequence of numbers to a lambda expression, which doubles each value and returns a tuple with three components that contains the result of the multiplications.</span></span>

[!code-csharp-interactive[lambda and tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithoutComponentName)]

<span data-ttu-id="03c0b-156">通常、タプルのフィールド名は `Item1`、`Item2` のようになります。ただし、次の例のとおり、名前付きのコンポーネントを持つタプルを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-156">Ordinarily, the fields of a tuple are named `Item1`, `Item2`, etc. You can, however, define a tuple with named components, as the following example does.</span></span>

[!code-csharp-interactive[lambda and named tuples](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasAndTuples.cs#WithComponentName)]

<span data-ttu-id="03c0b-157">C# のタプルの詳細については、「[C# のタプル型](../../tuples.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03c0b-157">For more information about C# tuples, see [C# tuple types](../../tuples.md).</span></span>

## <a name="lambdas-with-the-standard-query-operators"></a><span data-ttu-id="03c0b-158">標準クエリ演算子を使用したラムダ</span><span class="sxs-lookup"><span data-stu-id="03c0b-158">Lambdas with the standard query operators</span></span>

<span data-ttu-id="03c0b-159">いくつかある実装の中で特に、LINQ to Objects は、汎用デリゲートの <xref:System.Func%601> ファミリに属する型の入力パラメーターを持ちます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-159">LINQ to Objects, among other implementations, have an input parameter whose type is one of the <xref:System.Func%601> family of generic delegates.</span></span> <span data-ttu-id="03c0b-160">これらのデリゲートは、型パラメーターを使用して、入力パラメーターの数と型に加え、デリゲートの戻り値の型を定義します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-160">These delegates use type parameters to define the number and type of input parameters, and the return type of the delegate.</span></span> <span data-ttu-id="03c0b-161">`Func` デリゲートは、ソース データのセット内の各要素に適用されるユーザー定義の式をカプセル化する場合に非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="03c0b-161">`Func` delegates are very useful for encapsulating user-defined expressions that are applied to each element in a set of source data.</span></span> <span data-ttu-id="03c0b-162">たとえば、<xref:System.Func%602>デリゲート型を考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="03c0b-162">For example, consider the <xref:System.Func%602> delegate type:</span></span>  

```csharp
public delegate TResult Func<in T, out TResult>(T arg)
```

<span data-ttu-id="03c0b-163">このデリゲートを `Func<int, bool>` としてインスタンス化できます。 `int` は入力パラメーター、`bool` は戻り値です。</span><span class="sxs-lookup"><span data-stu-id="03c0b-163">The delegate can be instantiated as a `Func<int, bool>` instance where `int` is an input parameter and `bool` is the return value.</span></span> <span data-ttu-id="03c0b-164">戻り値は必ず最後の型パラメーターで指定されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-164">The return value is always specified in the last type parameter.</span></span> <span data-ttu-id="03c0b-165">たとえば、`Func<int, string, bool>` は 2 つの入力パラメーター ( `int` と `string`) と戻り値の型 `bool` を持つデリゲートを定義しています。</span><span class="sxs-lookup"><span data-stu-id="03c0b-165">For example, `Func<int, string, bool>` defines a delegate with two input parameters, `int` and `string`, and a return type of `bool`.</span></span> <span data-ttu-id="03c0b-166">次の `Func` デリゲートを呼び出すと、入力パラメーターが 5 に等しいかどうかを示す true または false が返されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-166">The following `Func` delegate, when it's invoked, returns Boolean value that indicates whether the input parameter is equal to five:</span></span>

[!code-csharp-interactive[Func example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Func)]

<span data-ttu-id="03c0b-167">たとえば、<xref:System.Linq.Queryable> 型で定義された標準クエリ演算子において、引数型が <xref:System.Linq.Expressions.Expression%601> の場合もラムダ式を使用できます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-167">You can also supply a lambda expression when the argument type is an <xref:System.Linq.Expressions.Expression%601>, for example in the standard query operators that are defined in the <xref:System.Linq.Queryable> type.</span></span> <span data-ttu-id="03c0b-168"><xref:System.Linq.Expressions.Expression%601> 引数を指定すると、ラムダは式ツリーにコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-168">When you specify an <xref:System.Linq.Expressions.Expression%601> argument, the lambda is compiled to an expression tree.</span></span>
  
<span data-ttu-id="03c0b-169">次の例では、<xref:System.Linq.Enumerable.Count%2A> 標準クエリ演算子を使用します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-169">The following example uses the <xref:System.Linq.Enumerable.Count%2A> standard query operator:</span></span>

[!code-csharp-interactive[Count example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#Count)]

<span data-ttu-id="03c0b-170">入力パラメーターの型はコンパイラが推論できますが、明示的に指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-170">The compiler can infer the type of the input parameter, or you can also specify it explicitly.</span></span> <span data-ttu-id="03c0b-171">この特定のラムダ式は、2 で除算したときに剰余が 1 になる整数 (`n`) をカウントします。</span><span class="sxs-lookup"><span data-stu-id="03c0b-171">This particular lambda expression counts those integers (`n`) which when divided by two have a remainder of 1.</span></span>

<span data-ttu-id="03c0b-172">次の例では、`numbers` 配列内で 9 より前にある要素をすべて含むシーケンスを作成します。これは、9 がシーケンス内で条件を満たさない最初の数値であるためです。</span><span class="sxs-lookup"><span data-stu-id="03c0b-172">The following example produces a sequence that contains all elements in the `numbers` array that precede the 9, because that's the first number in the sequence that doesn't meet the condition:</span></span>

[!code-csharp-interactive[TakeWhile example](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhile)]

<span data-ttu-id="03c0b-173">次の例では、複数の入力パラメーターをかっこで囲んで指定します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-173">The following example specifies multiple input parameters by enclosing them in parentheses.</span></span> <span data-ttu-id="03c0b-174">このメソッドは、値が `numbers` 配列内のその位置を表す序数よりも小さい数値が出現するまで、その配列に含まれるすべての要素を返します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-174">The method returns all the elements in the `numbers` array until it encounters a number whose value is less than its ordinal position in the array:</span></span>

[!code-csharp-interactive[TakeWhile example 2](~/samples/snippets/csharp/programming-guide/lambda-expressions/LambdasWithQueryMethods.cs#TakeWhileWithIndex)]

## <a name="type-inference-in-lambda-expressions"></a><span data-ttu-id="03c0b-175">ラムダ式の型の推定</span><span class="sxs-lookup"><span data-stu-id="03c0b-175">Type inference in lambda expressions</span></span>

<span data-ttu-id="03c0b-176">ラムダを記述する際、多くの場合は入力パラメーターの型を指定する必要はありません。これは、ラムダ本体やパラメーターの型など C# 言語仕様に記述されている要素に基づいて、コンパイラが型を推定できるためです。</span><span class="sxs-lookup"><span data-stu-id="03c0b-176">When writing lambdas, you often don't have to specify a type for the input parameters because the compiler can infer the type based on the lambda body, the parameter types, and other factors as described in the C# language specification.</span></span> <span data-ttu-id="03c0b-177">ほとんどの標準クエリ演算子では、最初の入力がソース シーケンス内の要素の型です。</span><span class="sxs-lookup"><span data-stu-id="03c0b-177">For most of the standard query operators, the first input is the type of the elements in the source sequence.</span></span> <span data-ttu-id="03c0b-178">`IEnumerable<Customer>` を問い合わせると、入力変数は `Customer` オブジェクトであると推論されます。これは、そのメソッドとプロパティにアクセスできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-178">If you are querying an `IEnumerable<Customer>`, then the input variable is inferred to be a `Customer` object, which means you have access to its methods and properties:</span></span>  

```csharp
customers.Where(c => c.City == "London");
```

<span data-ttu-id="03c0b-179">ラムダの型の推定の一般規則は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="03c0b-179">The general rules for type inference for lambdas are as follows:</span></span>

- <span data-ttu-id="03c0b-180">ラムダにはデリゲート型と同じ数のパラメーターが含まれていなければなりません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-180">The lambda must contain the same number of parameters as the delegate type.</span></span>

- <span data-ttu-id="03c0b-181">ラムダに含まれる各入力パラメーターは、対応するデリゲート パラメーターに暗黙的に変換できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-181">Each input parameter in the lambda must be implicitly convertible to its corresponding delegate parameter.</span></span>

- <span data-ttu-id="03c0b-182">ラムダの戻り値 (ある場合) は、デリゲートの戻り値の型に暗黙的に変換できなければなりません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-182">The return value of the lambda (if any) must be implicitly convertible to the delegate's return type.</span></span>
  
<span data-ttu-id="03c0b-183">共通型システムには "ラムダ式" の概念が組み込まれていないため、ラムダ式自体は型を持ちません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-183">Note that lambda expressions in themselves don't have a type because the common type system has no intrinsic concept of "lambda expression."</span></span> <span data-ttu-id="03c0b-184">しかし、変則的ではあってもラムダ式の "型" を表現できると都合が良い場合もあります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-184">However, it's sometimes convenient to speak informally of the "type" of a lambda expression.</span></span> <span data-ttu-id="03c0b-185">このような場合の型は、ラムダ式の変換後のデリゲート型または <xref:System.Linq.Expressions.Expression> 型を指します。</span><span class="sxs-lookup"><span data-stu-id="03c0b-185">In these cases the type refers to the delegate type or <xref:System.Linq.Expressions.Expression> type to which the lambda expression is converted.</span></span>

## <a name="variable-scope-in-lambda-expressions"></a><span data-ttu-id="03c0b-186">ラムダ式における変数のスコープ</span><span class="sxs-lookup"><span data-stu-id="03c0b-186">Variable scope in lambda expressions</span></span>

<span data-ttu-id="03c0b-187">ラムダは、"*外部変数*" を参照できます (「[匿名メソッド](anonymous-methods.md)」を参照)。外部変数とは、ラムダ式を定義するメソッド内のスコープ、またはラムダ式を含む型のスコープに存在する変数のことです。</span><span class="sxs-lookup"><span data-stu-id="03c0b-187">Lambdas can refer to *outer variables* (see [Anonymous methods](anonymous-methods.md)) that are in scope in the method that defines the lambda expression, or in scope in the type that contains the lambda expression.</span></span> <span data-ttu-id="03c0b-188">こうして取り込まれた変数は、ラムダ式で使用するために格納されます。これは、変数がスコープ外に出てガベージ コレクトされる場合でも変わりません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-188">Variables that are captured in this manner are stored for use in the lambda expression even if the variables would otherwise go out of scope and be garbage collected.</span></span> <span data-ttu-id="03c0b-189">外部変数は、ラムダ式で使用される前に明示的に代入する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-189">An outer variable must be definitely assigned before it can be consumed in a lambda expression.</span></span> <span data-ttu-id="03c0b-190">次の例は、こうした規則を示しています。</span><span class="sxs-lookup"><span data-stu-id="03c0b-190">The following example demonstrates these rules:</span></span>

[!code-csharp[variable scope](~/samples/snippets/csharp/programming-guide/lambda-expressions/VariableScopeWithLambdas.cs#VariableScope)]

<span data-ttu-id="03c0b-191">ラムダ式における変数のスコープには、次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="03c0b-191">The following rules apply to variable scope in lambda expressions:</span></span>  

- <span data-ttu-id="03c0b-192">取り込まれた変数は、その変数を参照するデリゲートがガベージ コレクションの対象になるまでガベージ コレクトされません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-192">A variable that is captured will not be garbage-collected until the delegate that references it becomes eligible for garbage collection.</span></span>

- <span data-ttu-id="03c0b-193">ラムダ式内に導入された変数は、外側のメソッドでは参照できません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-193">Variables introduced within a lambda expression are not visible in the enclosing method.</span></span>

- <span data-ttu-id="03c0b-194">ラムダ式は、外側のメソッドから [in](../../language-reference/keywords/in-parameter-modifier.md)、[ref](../../language-reference/keywords/ref.md)、または [out](../../language-reference/keywords/out-parameter-modifier.md) パラメーターを直接取り込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-194">A lambda expression cannot directly capture an [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), or [out](../../language-reference/keywords/out-parameter-modifier.md) parameter from the enclosing method.</span></span>

- <span data-ttu-id="03c0b-195">ラムダ式に含まれる [return](../../language-reference/keywords/return.md) ステートメントで外側のメソッドが戻ることはありません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-195">A [return](../../language-reference/keywords/return.md) statement in a lambda expression doesn't cause the enclosing method to return.</span></span>

- <span data-ttu-id="03c0b-196">ジャンプ先がラムダ式ブロックの外側にある場合は、ラムダ式に [goto](../../language-reference/keywords/goto.md)、[break](../../language-reference/keywords/break.md)、または [continue](../../language-reference/keywords/continue.md) ステートメントを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="03c0b-196">A lambda expression cannot contain a [goto](../../language-reference/keywords/goto.md), [break](../../language-reference/keywords/break.md), or [continue](../../language-reference/keywords/continue.md) statement if the target of that jump statement is outside the lambda expression block.</span></span> <span data-ttu-id="03c0b-197">また、ジャンプ先がブロックの内部にある場合に、ラムダ式ブロックの外部でジャンプ ステートメントを使用するとエラーになります。</span><span class="sxs-lookup"><span data-stu-id="03c0b-197">It's also an error to have a jump statement outside the lambda expression block if the target is inside the block.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="03c0b-198">C# 言語仕様</span><span class="sxs-lookup"><span data-stu-id="03c0b-198">C# language specification</span></span>

<span data-ttu-id="03c0b-199">詳細については、「[C# 言語仕様](~/_csharplang/spec/introduction.md)」の[無名関数の式](~/_csharplang/spec/expressions.md#anonymous-function-expressions)に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="03c0b-199">For more information, see the [Anonymous function expressions](~/_csharplang/spec/expressions.md#anonymous-function-expressions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="featured-book-chapter"></a><span data-ttu-id="03c0b-200">参考書籍の該当する章</span><span class="sxs-lookup"><span data-stu-id="03c0b-200">Featured book chapter</span></span>

<span data-ttu-id="03c0b-201">「[Delegates, Events, and Lambda Expressions (デリゲート、イベント、およびラムダ式)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29)」(『[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers (C# 3.0 クックブック (第 3 版): C# 3.0 プログラマ向けの 250 以上のソリューション)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)』)</span><span class="sxs-lookup"><span data-stu-id="03c0b-201">[Delegates, Events, and Lambda Expressions](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c0b-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="03c0b-202">See also</span></span>

- [<span data-ttu-id="03c0b-203">C# プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="03c0b-203">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="03c0b-204">統合言語クエリ (LINQ)</span><span class="sxs-lookup"><span data-stu-id="03c0b-204">LINQ (Language-Integrated Query)</span></span>](../concepts/linq/index.md)
- [<span data-ttu-id="03c0b-205">匿名メソッド</span><span class="sxs-lookup"><span data-stu-id="03c0b-205">Anonymous Methods</span></span>](anonymous-methods.md)
- [<span data-ttu-id="03c0b-206">式ツリー</span><span class="sxs-lookup"><span data-stu-id="03c0b-206">Expression Trees</span></span>](../concepts/expression-trees/index.md)
- [<span data-ttu-id="03c0b-207">ローカル関数とラムダ式の比較</span><span class="sxs-lookup"><span data-stu-id="03c0b-207">Local functions compared to lambda expressions</span></span>](../../local-functions-vs-lambdas.md)
- [<span data-ttu-id="03c0b-208">暗黙的に型指定されるラムダ式</span><span class="sxs-lookup"><span data-stu-id="03c0b-208">Implicitly typed lambda expressions</span></span>](../../implicitly-typed-lambda-expressions.md)
- [<span data-ttu-id="03c0b-209">Visual Studio 2008 C# Samples (Visual Studio 2008 の C# サンプル) (LINQ サンプル クエリ ファイルと XQuery プログラムを参照してください)</span><span class="sxs-lookup"><span data-stu-id="03c0b-209">Visual Studio 2008 C# Samples (see LINQ Sample Queries files and XQuery program)</span></span>](https://code.msdn.microsoft.com/Visual-Studio-2008-C-d295cdba)
- [<span data-ttu-id="03c0b-210">Recursive lambda expressions (再帰的なラムダ式)</span><span class="sxs-lookup"><span data-stu-id="03c0b-210">Recursive lambda expressions</span></span>](https://blogs.msdn.microsoft.com/madst/2007/05/11/recursive-lambda-expressions/)
