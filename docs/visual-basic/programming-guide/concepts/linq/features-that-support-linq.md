---
title: LINQ をサポートする Visual Basic の機能
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic, LINQ features
- LINQ [Visual Basic], features supporting LINQ
ms.assetid: c821bb50-b6f6-4cf9-8aba-2717e465bd3a
ms.openlocfilehash: 155d5c36483accc12d066a5530fea20a563e1498
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977562"
---
# <a name="visual-basic-features-that-support-linq"></a><span data-ttu-id="7b787-102">LINQ をサポートする Visual Basic の機能</span><span class="sxs-lookup"><span data-stu-id="7b787-102">Visual Basic Features That Support LINQ</span></span>
<span data-ttu-id="7b787-103">名前[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]クエリ構文のサポートを言語で直接その他の言語を構築します、Visual Basic でのテクノロジを参照します。</span><span class="sxs-lookup"><span data-stu-id="7b787-103">The name [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] refers to technology in Visual Basic that supports query syntax and other language constructs directly in the language.</span></span> <span data-ttu-id="7b787-104">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]、外部データ ソースに対してクエリを新しい言語を習得する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7b787-104">With [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], you do not have to learn a new language to query against an external data source.</span></span> <span data-ttu-id="7b787-105">Visual Basic を使用してリレーショナル データベース、XML ストア、またはオブジェクト内のデータのクエリを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7b787-105">You can query against data in relational databases, XML stores, or objects by using Visual Basic.</span></span> <span data-ttu-id="7b787-106">この統合言語クエリ機能の有効に構文エラーとタイプ セーフのコンパイル時にチェックします。</span><span class="sxs-lookup"><span data-stu-id="7b787-106">This integration of query capabilities into the language enables compile-time checking for syntax errors and type safety.</span></span> <span data-ttu-id="7b787-107">この統合は、Visual Basic での高度でさまざまなクエリを記述するために必要なほとんどを既に把握しているにも確認します。</span><span class="sxs-lookup"><span data-stu-id="7b787-107">This integration also ensures that you already know most of what you have to know to write rich, varied queries in Visual Basic.</span></span>  
  
 <span data-ttu-id="7b787-108">次のセクションでは、入門ドキュメント、コード例については、およびサンプル アプリケーションの読み取りを開始するための十分な詳細で LINQ をサポートする言語構造について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b787-108">The following sections describe the language constructs that support LINQ in enough detail to enable you to get started in reading the introductory documentation, code examples, and sample applications.</span></span> <span data-ttu-id="7b787-109">統合言語クエリを有効にする言語機能がどのように一緒に付属のより詳細な説明を検索するリンクをクリックすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7b787-109">You can also click the links to find more detailed explanations of how the language features come together to enable language-integrated query.</span></span> <span data-ttu-id="7b787-110">開始点としては[チュートリアル。Visual Basic でクエリを記述](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b787-110">A good place to start is [Walkthrough: Writing Queries in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md).</span></span>  
  
## <a name="query-expressions"></a><span data-ttu-id="7b787-111">クエリ式</span><span class="sxs-lookup"><span data-stu-id="7b787-111">Query Expressions</span></span>  
 <span data-ttu-id="7b787-112">Visual Basic でのクエリ式は、SQL や XQuery に似た宣言型の構文で表現できます。</span><span class="sxs-lookup"><span data-stu-id="7b787-112">Query expressions in Visual Basic can be expressed in a declarative syntax similar to that of SQL or XQuery.</span></span> <span data-ttu-id="7b787-113">コンパイル時に、クエリの構文は、標準クエリ演算子の拡張メソッドの LINQ プロバイダーの実装に対するメソッド呼び出しに変換されます。</span><span class="sxs-lookup"><span data-stu-id="7b787-113">At compile time, query syntax is converted into method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="7b787-114">標準クエリ演算子がスコープ内で適切な名前空間を指定することで、アプリケーション制御、`Imports`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="7b787-114">Applications control which standard query operators are in scope by specifying the appropriate namespace with an `Imports` statement.</span></span> <span data-ttu-id="7b787-115">Visual Basic のクエリ式の構文のようになります。</span><span class="sxs-lookup"><span data-stu-id="7b787-115">Syntax for a Visual Basic query expression looks like this:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="7b787-116">詳細については、次を参照してください。 [Visual Basic における LINQ の概要](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b787-116">For more information, see [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md).</span></span>  
  
## <a name="implicitly-typed-variables"></a><span data-ttu-id="7b787-117">暗黙的に型指定された変数</span><span class="sxs-lookup"><span data-stu-id="7b787-117">Implicitly Typed Variables</span></span>  
 <span data-ttu-id="7b787-118">明示的に宣言し、変数を初期化するときに、型を指定する、代わりに、型をコンパイラを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7b787-118">Instead of explicitly specifying a type when you declare and initialize a variable, you can enable the compiler to infer and assign the type.</span></span> <span data-ttu-id="7b787-119">呼ばれる*ローカル型推論*します。</span><span class="sxs-lookup"><span data-stu-id="7b787-119">This is referred to as *local type inference*.</span></span>  
  
 <span data-ttu-id="7b787-120">型を明示的に指定した変数と同様、推論される型を持つ変数を厳密に入力します。</span><span class="sxs-lookup"><span data-stu-id="7b787-120">Variables whose types are inferred are strongly typed, just like variables whose type you specify explicitly.</span></span> <span data-ttu-id="7b787-121">ローカル型推論は、メソッド本文内のローカル変数を定義する場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7b787-121">Local type inference works only when you are defining a local variable inside a method body.</span></span> <span data-ttu-id="7b787-122">詳細については、次を参照してください。 [Option Infer ステートメント](../../../../visual-basic/language-reference/statements/option-infer-statement.md)と[ローカル型推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b787-122">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
 <span data-ttu-id="7b787-123">次の例では、ローカル型推論を示しています。</span><span class="sxs-lookup"><span data-stu-id="7b787-123">The following example illustrates local type inference.</span></span> <span data-ttu-id="7b787-124">この例を使用するに設定する必要があります`Option Infer`に`On`します。</span><span class="sxs-lookup"><span data-stu-id="7b787-124">To use this example, you must set `Option Infer` to `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#2)]  
  
 <span data-ttu-id="7b787-125">ローカル型推論では、このセクションで後で説明して、LINQ クエリのために必要な匿名型を作成することです。</span><span class="sxs-lookup"><span data-stu-id="7b787-125">Local type inference also makes it possible to create anonymous types, which are described later in this section and are necessary for LINQ queries.</span></span>  
  
 <span data-ttu-id="7b787-126">場合は次の LINQ の例で型の推定が発生する`Option Infer`か`On`または`Off`します。</span><span class="sxs-lookup"><span data-stu-id="7b787-126">In the following LINQ example, type inference occurs if `Option Infer` is either `On` or `Off`.</span></span> <span data-ttu-id="7b787-127">コンパイル時エラーが発生します`Option Infer`は`Off`と`Option Strict`は`On`します。</span><span class="sxs-lookup"><span data-stu-id="7b787-127">A compile-time error occurs if `Option Infer` is `Off` and `Option Strict` is `On`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#3)]  
  
## <a name="object-initializers"></a><span data-ttu-id="7b787-128">オブジェクト初期化子</span><span class="sxs-lookup"><span data-stu-id="7b787-128">Object Initializers</span></span>  
 <span data-ttu-id="7b787-129">オブジェクト初期化子は、クエリの結果を保持するために匿名型を作成するときに、クエリ式で使用されます。</span><span class="sxs-lookup"><span data-stu-id="7b787-129">Object initializers are used in query expressions when you have to create an anonymous type to hold the results of a query.</span></span> <span data-ttu-id="7b787-130">クエリの外部で名前付きの型のオブジェクトを初期化するために使用することがことができます。</span><span class="sxs-lookup"><span data-stu-id="7b787-130">They also can be used to initialize objects of named types outside of queries.</span></span> <span data-ttu-id="7b787-131">オブジェクト初期化子を使用すると、コンス トラクターを明示的に呼び出さずに、1 行でオブジェクトを初期化できます。</span><span class="sxs-lookup"><span data-stu-id="7b787-131">By using an object initializer, you can initialize an object in a single line without explicitly calling a constructor.</span></span> <span data-ttu-id="7b787-132">という名前のクラスがあると仮定`Customer`を持つパブリック`Name`と`Phone`プロパティ、その他のプロパティと共に、オブジェクト初期化子をこの方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="7b787-132">Assuming that you have a class named `Customer` that has public `Name` and `Phone` properties, along with other properties, an object initializer can be used in this manner:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#4)]  
  
 <span data-ttu-id="7b787-133">詳細については、次を参照してください。[オブジェクト初期化子。名前付きの匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="7b787-133">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="anonymous-types"></a><span data-ttu-id="7b787-134">匿名型</span><span class="sxs-lookup"><span data-stu-id="7b787-134">Anonymous Types</span></span>  
 <span data-ttu-id="7b787-135">匿名型は、クエリ結果に追加する要素にプロパティのセットを一時的にグループ化する便利な手段を提供します。</span><span class="sxs-lookup"><span data-stu-id="7b787-135">Anonymous types provide a convenient way to temporarily group a set of properties into an element that you want to include in a query result.</span></span> <span data-ttu-id="7b787-136">これにより、要素の名前付きのデータ型を定義することがなく、任意の順序でのクエリで使用可能なフィールドの任意の組み合わせを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="7b787-136">This enables you to choose any combination of available fields in the query, in any order, without defining a named data type for the element.</span></span>  
  
 <span data-ttu-id="7b787-137">*匿名型*はコンパイラによって動的に構築します。</span><span class="sxs-lookup"><span data-stu-id="7b787-137">An *anonymous type* is constructed dynamically by the compiler.</span></span> <span data-ttu-id="7b787-138">型の名前は、コンパイラによって割り当てられ、新しいコンパイルのたびに変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7b787-138">The name of the type is assigned by the compiler, and it might change with each new compilation.</span></span> <span data-ttu-id="7b787-139">そのため、名前を直接使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b787-139">Therefore, the name cannot be used directly.</span></span> <span data-ttu-id="7b787-140">匿名型は、次のように初期化されます。</span><span class="sxs-lookup"><span data-stu-id="7b787-140">Anonymous types are initialized in the following way:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#5)]  
  
 <span data-ttu-id="7b787-141">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b787-141">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="extension-methods"></a><span data-ttu-id="7b787-142">拡張メソッド</span><span class="sxs-lookup"><span data-stu-id="7b787-142">Extension Methods</span></span>  
 <span data-ttu-id="7b787-143">拡張メソッドを使用すると、データ型またはインターフェイスの定義の外部にメソッドを追加できます。</span><span class="sxs-lookup"><span data-stu-id="7b787-143">Extension methods enable you to add methods to a data type or interface from outside the definition.</span></span> <span data-ttu-id="7b787-144">この機能では、実際には、実際には、型を変更することがなく既存の型に新しいメソッドを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="7b787-144">This feature enables you to, in effect, add new methods to an existing type without actually modifying the type.</span></span> <span data-ttu-id="7b787-145">標準クエリ演算子は、それ自体が提供する拡張メソッドのセットを[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]クエリ機能を実装する任意の型<xref:System.Collections.Generic.IEnumerable%601>します。</span><span class="sxs-lookup"><span data-stu-id="7b787-145">The standard query operators are themselves a set of extension methods that provide [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="7b787-146">その他の拡張機能を<xref:System.Collections.Generic.IEnumerable%601>含める<xref:System.Linq.Enumerable.Count%2A>、<xref:System.Linq.Enumerable.Union%2A>と<xref:System.Linq.Enumerable.Intersect%2A>します。</span><span class="sxs-lookup"><span data-stu-id="7b787-146">Other extensions to <xref:System.Collections.Generic.IEnumerable%601> include <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Intersect%2A>.</span></span>  
  
 <span data-ttu-id="7b787-147">次の拡張メソッドを print メソッドの追加、<xref:System.String>クラス。</span><span class="sxs-lookup"><span data-stu-id="7b787-147">The following extension method adds a print method to the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#6)]  
  
 <span data-ttu-id="7b787-148">メソッドは通常のインスタンス メソッドのような<xref:System.String>:</span><span class="sxs-lookup"><span data-stu-id="7b787-148">The method is called like an ordinary instance method of <xref:System.String>:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#7)]  
  
 <span data-ttu-id="7b787-149">詳細については、「[拡張メソッド](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b787-149">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="lambda-expressions"></a><span data-ttu-id="7b787-150">ラムダ式</span><span class="sxs-lookup"><span data-stu-id="7b787-150">Lambda Expressions</span></span>  
 <span data-ttu-id="7b787-151">ラムダ式は、計算して 1 つの値を返す名前のない関数です。</span><span class="sxs-lookup"><span data-stu-id="7b787-151">A lambda expression is a function without a name that calculates and returns a single value.</span></span> <span data-ttu-id="7b787-152">名前付きの関数とは異なり、ラムダ式の定義し、同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="7b787-152">Unlike named functions, a lambda expression can be defined and executed at the same time.</span></span> <span data-ttu-id="7b787-153">次の例では、4 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b787-153">The following example displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#8)]  
  
 <span data-ttu-id="7b787-154">変数名にラムダ式の定義を割り当てるし、名を使用して、関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7b787-154">You can assign the lambda expression definition to a variable name and then use the name to call the function.</span></span> <span data-ttu-id="7b787-155">次の例では、4 も表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b787-155">The following example also displays 4.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#12)]  
  
 <span data-ttu-id="7b787-156">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]ラムダ式の基本となる多くの標準クエリ演算子。</span><span class="sxs-lookup"><span data-stu-id="7b787-156">In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], lambda expressions underlie many of the standard query operators.</span></span> <span data-ttu-id="7b787-157">コンパイラなど、基本的なクエリ メソッドで定義されている計算をキャプチャするラムダ式を作成する`Where`、 `Select`、 `Order By`、 `Take While`、およびその他。</span><span class="sxs-lookup"><span data-stu-id="7b787-157">The compiler creates lambda expressions to capture the calculations that are defined in fundamental query methods such as `Where`, `Select`, `Order By`, `Take While`, and others.</span></span>  
  
 <span data-ttu-id="7b787-158">たとえば、次のコードは、受講者の一覧から上級のすべての学生を返すクエリを定義します。</span><span class="sxs-lookup"><span data-stu-id="7b787-158">For example, the following code defines a query that returns all senior students from a list of students.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#9)]  
  
 <span data-ttu-id="7b787-159">クエリの定義は次の例は、引数を指定する 2 つのラムダ式を使用して次のようなコードにコンパイル`Where`と`Select`します。</span><span class="sxs-lookup"><span data-stu-id="7b787-159">The query definition is compiled into code that is similar to the following example, which uses two lambda expressions to specify the arguments for `Where` and `Select`.</span></span>  
  
 [!code-vb[VbLINQVbFeatures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#10)]  
  
 <span data-ttu-id="7b787-160">使用していずれかのバージョンを実行することができます、`For Each`ループ。</span><span class="sxs-lookup"><span data-stu-id="7b787-160">Either version can be run by using a `For Each` loop:</span></span>  
  
 [!code-vb[VbLINQVbFeatures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQVbFeatures/VB/Class1.vb#11)]  
  
 <span data-ttu-id="7b787-161">詳細については、「[ラムダ式](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b787-161">For more information, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b787-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b787-162">See also</span></span>

- [<span data-ttu-id="7b787-163">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b787-163">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="7b787-164">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="7b787-164">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="7b787-165">LINQ と文字列 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b787-165">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="7b787-166">Option Infer ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b787-166">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="7b787-167">Option Strict ステートメント</span><span class="sxs-lookup"><span data-stu-id="7b787-167">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
