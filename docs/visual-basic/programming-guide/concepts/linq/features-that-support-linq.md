---
title: LINQ をサポートする機能
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: e81d0434aa60e0c7b316b72fb78ebfe2a3782cbb
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353516"
---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="36e43-102">LINQ をサポートする Visual Basic の機能</span><span class="sxs-lookup"><span data-stu-id="36e43-102">Visual Basic Features That Support LINQ</span></span>
<span data-ttu-id="36e43-103">[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 名前は、クエリ構文やその他の言語構成を言語で直接サポートする Visual Basic のテクノロジを指します。</span><span class="sxs-lookup"><span data-stu-id="36e43-103">The name [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="36e43-104">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]では、外部データソースに対してクエリを実行するための新しい言語を習得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36e43-104">With [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="36e43-105">Visual Basic を使用すると、リレーショナルデータベース、XML ストア、またはオブジェクトのデータに対してクエリを実行できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-105">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="36e43-106">この言語へのクエリ機能の統合により、コンパイル時に構文エラーやタイプセーフをチェックできるようになります。</span><span class="sxs-lookup"><span data-stu-id="36e43-106">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="36e43-107">また、この統合により、Visual Basic で豊富な多様なクエリを作成するために必要な知識のほとんどを把握しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="36e43-107">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="36e43-108">以下のセクションでは、入門ドキュメント、コード例、およびサンプルアプリケーションの概要を理解できるように、LINQ をサポートするための詳細な言語構成要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36e43-108">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="36e43-109">また、リンクをクリックして、言語機能の詳細な説明を参照して、統合言語クエリを有効にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="36e43-109">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="36e43-110">まず、 「 [チュートリアル: Visual Basic でのクエリの作成](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)」をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="36e43-110">A good place to start is [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="36e43-111">クエリ式</span><span class="sxs-lookup"><span data-stu-id="36e43-111">Query Expressions</span></span>  
 <span data-ttu-id="36e43-112">Visual Basic のクエリ式は、SQL または XQuery と同様の宣言構文で表現できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-112">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="36e43-113">コンパイル時に、クエリ構文は、LINQ プロバイダーによる標準クエリ演算子の拡張メソッドの実装に対するメソッド呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-113">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="36e43-114">アプリケーションでは、`Imports` ステートメントを使用して適切な名前空間を指定することによって、スコープ内の標準クエリ演算子を制御します。</span><span class="sxs-lookup"><span data-stu-id="36e43-114">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="36e43-115">Visual Basic のクエリ式の構文は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="36e43-115">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="36e43-116">詳細については、「 [Visual Basic での LINQ の概要](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e43-116">For more information, see [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="36e43-117">暗黙的に型指定された変数</span><span class="sxs-lookup"><span data-stu-id="36e43-117">Implicitly Typed Variables</span></span>  
 <span data-ttu-id="36e43-118">変数を宣言して初期化するときに型を明示的に指定する代わりに、コンパイラが型を推論して割り当てられるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="36e43-118">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="36e43-119">これは、*ローカル型の推論*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="36e43-119">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="36e43-120">型が推論される変数は、明示的に指定した型を持つ変数と同じように、厳密に型指定されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-120">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="36e43-121">ローカル型の推論は、メソッド本体内でローカル変数を定義する場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="36e43-121">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="36e43-122">詳細については、「[オプション推論ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e43-122">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="36e43-123">ローカル型の推論の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="36e43-123">The following example illustrates local type inference.</span></span> <span data-ttu-id="36e43-124">この例を使用するには、`Option Infer` を `On`に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36e43-124">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="36e43-125">ローカル型の推論では、匿名型を作成することもできます。これについては、このセクションの後半で説明します。 LINQ クエリに必要です。</span><span class="sxs-lookup"><span data-stu-id="36e43-125">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="36e43-126">次の LINQ の例では、`Option Infer` が `On` または `Off`の場合、型の推定が行われます。</span><span class="sxs-lookup"><span data-stu-id="36e43-126">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="36e43-127">`Option Infer` が `Off`、`Option Strict` が `On`場合、コンパイル時エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="36e43-127">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a><span data-ttu-id="36e43-128">オブジェクト初期化子</span><span class="sxs-lookup"><span data-stu-id="36e43-128">Object Initializers</span></span>  
 <span data-ttu-id="36e43-129">オブジェクト初期化子は、クエリの結果を保持する匿名型を作成する必要がある場合に、クエリ式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-129">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="36e43-130">また、クエリの外部で名前付きの型のオブジェクトを初期化するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="36e43-130">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="36e43-131">オブジェクト初期化子を使用すると、コンストラクターを明示的に呼び出すことなく、1行でオブジェクトを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-131">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="36e43-132">パブリック `Name` と `Phone` プロパティを持つ `Customer` という名前のクラスと、その他のプロパティがあると仮定すると、オブジェクト初期化子を次のように使用できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-132">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 <span data-ttu-id="36e43-133">詳細については、「[オブジェクト初期化子: 名前付きの型と匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e43-133">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="36e43-134">匿名型</span><span class="sxs-lookup"><span data-stu-id="36e43-134">Anonymous Types</span></span>  
 <span data-ttu-id="36e43-135">匿名型を使用すると、一連のプロパティを一時的にクエリ結果に含める要素にグループ化することができます。</span><span class="sxs-lookup"><span data-stu-id="36e43-135">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="36e43-136">これにより、クエリ内の使用可能なフィールドの任意の組み合わせを任意の順序で選択できます。要素の名前付きデータ型を定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="36e43-136">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="36e43-137">*匿名型*は、コンパイラによって動的に構築されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-137">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="36e43-138">型の名前はコンパイラによって割り当てられ、新しいコンパイルのたびに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="36e43-138">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="36e43-139">そのため、名前を直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="36e43-139">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="36e43-140">匿名型は、次の方法で初期化されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-140">Anonymous types are initialized in the following way:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 <span data-ttu-id="36e43-141">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e43-141">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="36e43-142">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="36e43-142">Extension Methods</span></span>  
 <span data-ttu-id="36e43-143">拡張メソッドを使用すると、定義の外部からデータ型またはインターフェイスにメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-143">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="36e43-144">この機能を使用すると、実際に型を変更することなく、既存の型に新しいメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-144">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="36e43-145">標準クエリ演算子は、それ自体が、<xref:System.Collections.Generic.IEnumerable%601>を実装する任意の型に対して [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] クエリ機能を提供する拡張メソッドのセットです。</span><span class="sxs-lookup"><span data-stu-id="36e43-145">The standard query operators are themselves a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="36e43-146">その他の <xref:System.Collections.Generic.IEnumerable%601> の拡張機能には、<xref:System.Linq.Enumerable.Count%2A>、<xref:System.Linq.Enumerable.Union%2A>、および <xref:System.Linq.Enumerable.Intersect%2A>が含まれます。</span><span class="sxs-lookup"><span data-stu-id="36e43-146">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="36e43-147">次の拡張メソッドは、print メソッドを <xref:System.String> クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="36e43-147">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 <span data-ttu-id="36e43-148">メソッドは、<xref:System.String>の通常のインスタンスメソッドと同様に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-148">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 <span data-ttu-id="36e43-149">詳細については、「[拡張メソッド](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e43-149">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="36e43-150">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="36e43-150">Lambda Expressions</span></span>  
 <span data-ttu-id="36e43-151">ラムダ式は、1つの値を計算して返す名前のない関数です。</span><span class="sxs-lookup"><span data-stu-id="36e43-151">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="36e43-152">名前付き関数とは異なり、ラムダ式は同時に定義および実行できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-152">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="36e43-153">次の例では、4が表示されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-153">The following example displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="36e43-154">ラムダ式の定義を変数名に割り当ててから、その名前を使用して関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="36e43-154">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="36e43-155">次の例では、4も表示されます。</span><span class="sxs-lookup"><span data-stu-id="36e43-155">The following example also displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 <span data-ttu-id="36e43-156">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]では、ラムダ式は多くの標準クエリ演算子を基にしています。</span><span class="sxs-lookup"><span data-stu-id="36e43-156">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="36e43-157">コンパイラは、`Where`、`Select`、`Order By`、`Take While`などの基本的なクエリメソッドで定義されている計算をキャプチャするラムダ式を作成します。</span><span class="sxs-lookup"><span data-stu-id="36e43-157">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="36e43-158">たとえば、次のコードでは、学生のリストからすべての上級学生を返すクエリを定義しています。</span><span class="sxs-lookup"><span data-stu-id="36e43-158">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 <span data-ttu-id="36e43-159">クエリ定義は、次の例のようなコードにコンパイルされます。この例では、2つのラムダ式を使用して `Where` と `Select`の引数を指定しています。</span><span class="sxs-lookup"><span data-stu-id="36e43-159">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 <span data-ttu-id="36e43-160">どちらのバージョンも、`For Each` ループを使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="36e43-160">Either version can be run by using a `For Each` loop:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 <span data-ttu-id="36e43-161">詳しくは、「[ラムダ式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="36e43-161">For more information, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36e43-162">参照</span><span class="sxs-lookup"><span data-stu-id="36e43-162">See also</span></span>

- [<span data-ttu-id="36e43-163">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36e43-163">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="36e43-164">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="36e43-164">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="36e43-165">LINQ と文字列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36e43-165">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="36e43-166">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="36e43-166">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="36e43-167">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="36e43-167">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
