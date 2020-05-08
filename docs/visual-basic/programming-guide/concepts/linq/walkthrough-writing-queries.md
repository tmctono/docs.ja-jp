---
title: クエリの作成
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 6d2e472cc996c42aa091ed95c6954d0879c98372
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636758"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="1fce0-102">チュートリアル: Visual Basic でのクエリの作成</span><span class="sxs-lookup"><span data-stu-id="1fce0-102">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="1fce0-103">このチュートリアルでは、Visual Basic 言語の機能を使用して統合言語クエリ (LINQ) のクエリ式を記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-103">This walkthrough demonstrates how you can use Visual Basic language features to write Language-Integrated Query (LINQ) query expressions.</span></span> <span data-ttu-id="1fce0-104">このチュートリアルでは、Student オブジェクトのリストに対するクエリを作成する方法とそのクエリを実行する方法、さらにクエリに変更を加える方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="1fce0-105">クエリには、オブジェクト初期化子、ローカル型推論、匿名型などさまざまな機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="1fce0-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="1fce0-106">このチュートリアルを完了すれば、いつでも、興味がある特定の LINQ プロバイダーのサンプルやドキュメントに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific LINQ provider you are interested in.</span></span> <span data-ttu-id="1fce0-107">LINQ プロバイダーには、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]、LINQ to DataSet、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-107">LINQ providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="1fce0-108">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="1fce0-108">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="1fce0-109">コンソール アプリケーション プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-109">To create a console application project</span></span>

1. <span data-ttu-id="1fce0-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-110">Start Visual Studio.</span></span>

2. <span data-ttu-id="1fce0-111">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fce0-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="1fce0-112">**[インストールされたテンプレート]** の一覧で、 **[Visual Basic]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fce0-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="1fce0-113">プロジェクトの種類の一覧の **[コンソール アプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fce0-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="1fce0-114">**[名前]** ボックスにプロジェクトの名前を入力して、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fce0-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="1fce0-115">プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-115">A project is created.</span></span> <span data-ttu-id="1fce0-116">System.Core.dll への参照は、既定で追加されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="1fce0-117">また、[プロジェクト デザイナー (Visual Basic) の [参照] ページ](/visualstudio/ide/reference/references-page-project-designer-visual-basic)にある **[インポートされた名前空間]** の一覧には <xref:System.Linq?displayProperty=nameWithType> 名前空間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="1fce0-118">[プロジェクト デザイナー (Visual Basic) の [コンパイル] ページ](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)で、 **[Option infer]** が **[On]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="1fce0-119">インメモリ データ ソースを追加する</span><span class="sxs-lookup"><span data-stu-id="1fce0-119">Add an In-Memory Data Source</span></span>

<span data-ttu-id="1fce0-120">このチュートリアルで使用するクエリのデータ ソースは、`Student` オブジェクトのリストです。</span><span class="sxs-lookup"><span data-stu-id="1fce0-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="1fce0-121">それぞれの `Student` オブジェクトには、名、姓、学年、全学生における成績のランクが格納されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="1fce0-122">データ ソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-122">To add the data source</span></span>

- <span data-ttu-id="1fce0-123">`Student` クラスを定義し、クラスのインスタンスのリストを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-123">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1fce0-124">`Student` クラスを定義し、このチュートリアルの各例で使用するリストを作成するために必要なコードは、「[方法: 項目のリストを作成する](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)」に掲載されています。</span><span class="sxs-lookup"><span data-stu-id="1fce0-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="1fce0-125">そこからコピーして、自分のプロジェクトに貼り付けてください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="1fce0-126">プロジェクトの作成時にあったコードを新しいコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-126">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="1fce0-127">学生リストに新しい学生を追加するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-127">To add a new student to the students list</span></span>

- <span data-ttu-id="1fce0-128">`getStudents` メソッドのパターンに従って、`Student` クラスのインスタンスを新たにリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="1fce0-129">学生を追加すると、オブジェクト初期化子が挿入されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="1fce0-130">詳細については、「[オブジェクト初期化子: 名前付きの型と匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="1fce0-131">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="1fce0-131">Create a Query</span></span>

<span data-ttu-id="1fce0-132">このセクションで追加したクエリを実行すると、成績のランクがトップ 10 に入る学生のリストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="1fce0-133">このクエリでは都度、完全な `Student` オブジェクトが選択されるため、クエリの結果の型は `IEnumerable(Of Student)` です。</span><span class="sxs-lookup"><span data-stu-id="1fce0-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="1fce0-134">ただし通常、クエリの定義にクエリの型は指定されません。</span><span class="sxs-lookup"><span data-stu-id="1fce0-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="1fce0-135">コンパイラがローカル型推論を使用して型を特定します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="1fce0-136">詳細については、「[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="1fce0-137">クエリの範囲変数 `currentStudent` は、ソース `students` に含まれる各 `Student` インスタンスへの参照として機能します。`students` 内の各オブジェクトのプロパティには、それを通じてアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="1fce0-138">簡単なクエリを作成するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-138">To create a simple query</span></span>

1. <span data-ttu-id="1fce0-139">プロジェクトの `Main` メソッドから、次のように記述されている箇所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="1fce0-140">次のコードをコピーして、そこに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-140">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="1fce0-141">コード内の `studentQuery` にマウス ポインターを合わせて、コンパイラによって割り当てられた型が `IEnumerable(Of Student)` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="1fce0-142">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="1fce0-142">Run the Query</span></span>

<span data-ttu-id="1fce0-143">変数 `studentQuery` には、クエリの実行結果ではなくクエリの定義が格納されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="1fce0-144">クエリを実行するための通常のメカニズムは `For Each` ループです。</span><span class="sxs-lookup"><span data-stu-id="1fce0-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="1fce0-145">返されたシーケンス内の各要素には、ループの反復変数を介してアクセスします。</span><span class="sxs-lookup"><span data-stu-id="1fce0-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="1fce0-146">クエリの実行の詳細については、「[初めての LINQ クエリの作成](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="1fce0-147">クエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-147">To run the query</span></span>

1. <span data-ttu-id="1fce0-148">対象のプロジェクトで、クエリの下に次の `For Each` ループを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-148">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="1fce0-149">ループの制御変数 `studentRecord` にマウス ポインターを合わせて、そのデータ型を確認します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="1fce0-150">`studentQuery` から返されるのは `Student` インスタンスのコレクションであるため、`studentRecord` の型も `Student` であると推定されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="1fce0-151">Ctrl キーを押しながら F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="1fce0-152">コンソール ウィンドウで結果を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-152">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="1fce0-153">クエリの変更</span><span class="sxs-lookup"><span data-stu-id="1fce0-153">Modify the Query</span></span>

<span data-ttu-id="1fce0-154">クエリの結果は、特定の順序で並んでいた方が見やすくなります。</span><span class="sxs-lookup"><span data-stu-id="1fce0-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="1fce0-155">返されたシーケンスは、使用できるあらゆるフィールドを基準にして並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-155">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="1fce0-156">結果を並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="1fce0-156">To order the results</span></span>

1. <span data-ttu-id="1fce0-157">クエリの `Where` ステートメントと `Select` ステートメントの間に、次の `Order By` 句を追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="1fce0-158">`Order By` 句は、各学生の姓を基準にして、A から Z のアルファベット順に結果を並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="1fce0-159">まず姓で並べ替えたうえで、名で並べ替えるために、その両方のフィールドをクエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-159">To order by last name and then first name, add both fields to the query:</span></span>

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="1fce0-160">`Descending` を指定して、Z から A の順に並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-160">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="1fce0-161">Ctrl キーを押しながら F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="1fce0-162">コンソール ウィンドウで結果を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-162">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="1fce0-163">ローカルの識別子を挿入するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-163">To introduce a local identifier</span></span>

1. <span data-ttu-id="1fce0-164">ローカルの識別子をクエリ式に挿入するには、このセクションのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="1fce0-165">ローカルの識別子には中間結果が保持されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="1fce0-166">次の例の `name` は、学生の名と姓を連結した値を保持する識別子です。</span><span class="sxs-lookup"><span data-stu-id="1fce0-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="1fce0-167">ローカルの識別子は利便性を目的に使用できるほか、式の結果を格納しておくことで、計算を何度も行う必要がなくなるのでパフォーマンスの向上にもつながります。</span><span class="sxs-lookup"><span data-stu-id="1fce0-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="1fce0-168">Ctrl キーを押しながら F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="1fce0-169">コンソール ウィンドウで結果を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-169">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="1fce0-170">Select 句で 1 つのフィールドを投影するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-170">To project one field in the Select clause</span></span>

1. <span data-ttu-id="1fce0-171">ソース内の要素とは異なる要素のシーケンスを生成するクエリを作成するには、このセクションのクエリと `For Each` ループを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="1fce0-172">次の例のソースは `Student` オブジェクトのコレクションですが、返されるのは各オブジェクトの 1 つのメンバー (姓が Garcia である学生の名) だけです。</span><span class="sxs-lookup"><span data-stu-id="1fce0-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="1fce0-173">`currentStudent.First` は文字列であるため、`studentQuery3` から返されるシーケンスのデータ型は `IEnumerable(Of String)`、つまり一連の文字列です。</span><span class="sxs-lookup"><span data-stu-id="1fce0-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="1fce0-174">これまでの例と同様、`studentQuery3` に対するデータ型の割り当ては、コンパイラに委ねられ、ローカル型推論を使用して特定されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="1fce0-175">コード内の `studentQuery3` にマウス ポインターを合わせて、割り当てられた型が `IEnumerable(Of String)` であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="1fce0-176">Ctrl キーを押しながら F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="1fce0-177">コンソール ウィンドウで結果を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-177">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="1fce0-178">Select 句で匿名型を作成するには</span><span class="sxs-lookup"><span data-stu-id="1fce0-178">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="1fce0-179">クエリにおける匿名型の使用法を確認するために、このセクションのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="1fce0-180">これらをクエリで使用するのは、レコード全体 (前の例では `currentStudent` レコード) や単一のフィールド (前セクションの `First`) ではなく複数のフィールドがデータ ソースから返されるようにしたい場合です。</span><span class="sxs-lookup"><span data-stu-id="1fce0-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="1fce0-181">結果に含めたいフィールドを格納する名前付きの型を新たに定義するのではなく、`Select` 句でフィールドを指定すると、それらのフィールドをプロパティとして持つ匿名型がコンパイラによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="1fce0-182">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="1fce0-183">次の例では、成績のランクが 1 から 10 である最上級生 (Senior) の名前とランクを、成績のランク順に返すクエリを作成しています。</span><span class="sxs-lookup"><span data-stu-id="1fce0-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="1fce0-184">この例では、`studentQuery4` の型を推定する必要があります。`Select` 句で返されるのは匿名型のインスタンスであり、使用できる名前が匿名型にはないためです。</span><span class="sxs-lookup"><span data-stu-id="1fce0-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="1fce0-185">Ctrl キーを押しながら F5 キーを押してアプリケーションをビルドし、実行します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="1fce0-186">コンソール ウィンドウで結果を確認してください。</span><span class="sxs-lookup"><span data-stu-id="1fce0-186">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="1fce0-187">その他の例</span><span class="sxs-lookup"><span data-stu-id="1fce0-187">Additional Examples</span></span>

<span data-ttu-id="1fce0-188">これで基本的な事柄を理解できたので、別の一連の例で、LINQ クエリの柔軟性と機能を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="1fce0-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of LINQ queries.</span></span> <span data-ttu-id="1fce0-189">それぞれの例には、その処理の内容について最初に簡潔な説明が記述されています。</span><span class="sxs-lookup"><span data-stu-id="1fce0-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="1fce0-190">それぞれのクエリの結果変数にマウス ポインターを合わせると、推定された型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fce0-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="1fce0-191">結果の生成には、`For Each` ループを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fce0-191">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="1fce0-192">追加情報</span><span class="sxs-lookup"><span data-stu-id="1fce0-192">Additional Information</span></span>

<span data-ttu-id="1fce0-193">クエリ操作の基本的な概念が理解できたら、興味がある種類の LINQ プロバイダーについて、ドキュメントやサンプルを読んでみましょう。</span><span class="sxs-lookup"><span data-stu-id="1fce0-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of LINQ provider that you are interested in:</span></span>

- [<span data-ttu-id="1fce0-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="1fce0-194">LINQ to Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [<span data-ttu-id="1fce0-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1fce0-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="1fce0-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="1fce0-196">LINQ to XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [<span data-ttu-id="1fce0-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="1fce0-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="1fce0-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fce0-198">See also</span></span>

- [<span data-ttu-id="1fce0-199">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1fce0-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="1fce0-200">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="1fce0-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="1fce0-201">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="1fce0-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="1fce0-202">オブジェクト初期化子: 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="1fce0-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="1fce0-203">匿名型</span><span class="sxs-lookup"><span data-stu-id="1fce0-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="1fce0-204">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="1fce0-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="1fce0-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="1fce0-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="1fce0-206">クエリ</span><span class="sxs-lookup"><span data-stu-id="1fce0-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
