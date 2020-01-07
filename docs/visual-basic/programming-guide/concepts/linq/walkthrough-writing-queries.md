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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636758"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="eea57-102">チュートリアル: Visual Basic でクエリを記述する</span><span class="sxs-lookup"><span data-stu-id="eea57-102">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="eea57-103">このチュートリアルでは、Visual Basic 言語機能を使用して、統合言語クエリ (LINQ) クエリ式を記述する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eea57-103">This walkthrough demonstrates how you can use Visual Basic language features to write Language-Integrated Query (LINQ) query expressions.</span></span> <span data-ttu-id="eea57-104">このチュートリアルでは、Student オブジェクトのリスト、クエリの実行方法、およびその変更方法に関するクエリを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eea57-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="eea57-105">クエリには、オブジェクト初期化子、ローカル型推論、匿名型など、いくつかの機能が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="eea57-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="eea57-106">このチュートリアルを完了すると、目的の特定の LINQ プロバイダーのサンプルとドキュメントに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="eea57-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific LINQ provider you are interested in.</span></span> <span data-ttu-id="eea57-107">LINQ プロバイダーには、[!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]、LINQ to DataSet、[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]が含まれます。</span><span class="sxs-lookup"><span data-stu-id="eea57-107">LINQ providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="eea57-108">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="eea57-108">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="eea57-109">コンソールアプリケーションプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="eea57-109">To create a console application project</span></span>

1. <span data-ttu-id="eea57-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="eea57-110">Start Visual Studio.</span></span>

2. <span data-ttu-id="eea57-111">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eea57-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="eea57-112">**[インストールされたテンプレート]** の一覧で、 **[Visual Basic]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eea57-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="eea57-113">プロジェクトの種類の一覧で、 **[コンソールアプリケーション]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eea57-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="eea57-114">**[名前]** ボックスにプロジェクトの名前を入力し、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eea57-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="eea57-115">プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-115">A project is created.</span></span> <span data-ttu-id="eea57-116">既定では、このファイルには、system.servicemodel への参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eea57-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="eea57-117">また、[参照] ページの [インポートされた**名前空間**] の一覧にある[プロジェクトデザイナー (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)には、<xref:System.Linq?displayProperty=nameWithType> 名前空間が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eea57-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="eea57-118">[[コンパイル] ページのプロジェクトデザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)で、[**推定]** が **[オン**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eea57-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="eea57-119">メモリ内データソースを追加する</span><span class="sxs-lookup"><span data-stu-id="eea57-119">Add an In-Memory Data Source</span></span>

<span data-ttu-id="eea57-120">このチュートリアルのクエリのデータソースは、`Student` オブジェクトの一覧です。</span><span class="sxs-lookup"><span data-stu-id="eea57-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="eea57-121">各 `Student` オブジェクトには、学生の本文で、名、姓、クラスの年、および教育の順位が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eea57-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="eea57-122">データ ソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="eea57-122">To add the data source</span></span>

- <span data-ttu-id="eea57-123">`Student` クラスを定義し、クラスのインスタンスの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="eea57-123">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="eea57-124">`Student` クラスを定義し、チュートリアルの例で使用するリストを作成するために必要なコードは、 [「方法: 項目のリストを作成](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)する」に記載されています。</span><span class="sxs-lookup"><span data-stu-id="eea57-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="eea57-125">そこからコピーして、プロジェクトに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="eea57-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="eea57-126">新しいコードは、プロジェクトの作成時に表示されたコードを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="eea57-126">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="eea57-127">学生リストに新しい学生を追加するには</span><span class="sxs-lookup"><span data-stu-id="eea57-127">To add a new student to the students list</span></span>

- <span data-ttu-id="eea57-128">`getStudents` メソッドのパターンに従って、`Student` クラスの別のインスタンスを一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="eea57-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="eea57-129">学生を追加すると、オブジェクト初期化子が導入されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="eea57-130">詳細については、「[オブジェクト初期化子: 名前付きの型と匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea57-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="eea57-131">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="eea57-131">Create a Query</span></span>

<span data-ttu-id="eea57-132">実行すると、このセクションに追加されたクエリによって、教育機関のランクが上位10に配置される学生のリストが生成されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="eea57-133">クエリは毎回、完全な `Student` オブジェクトを選択するので、クエリ結果の型は `IEnumerable(Of Student)`になります。</span><span class="sxs-lookup"><span data-stu-id="eea57-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="eea57-134">ただし、クエリの型は、通常、クエリ定義では指定されていません。</span><span class="sxs-lookup"><span data-stu-id="eea57-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="eea57-135">代わりに、コンパイラはローカル型の推論を使用して型を決定します。</span><span class="sxs-lookup"><span data-stu-id="eea57-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="eea57-136">詳細については、「[ローカル型の推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea57-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="eea57-137">クエリの範囲変数 `currentStudent`は、ソース内の各 `Student` インスタンスへの参照として機能します。 `students`は、`students`内の各オブジェクトのプロパティへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="eea57-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="eea57-138">簡単なクエリを作成するには</span><span class="sxs-lookup"><span data-stu-id="eea57-138">To create a simple query</span></span>

1. <span data-ttu-id="eea57-139">プロジェクトの `Main` メソッドで、次のようにマークされている場所を見つけます。</span><span class="sxs-lookup"><span data-stu-id="eea57-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="eea57-140">次のコードをコピーし、に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="eea57-140">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="eea57-141">コード内の `studentQuery` 上にマウスポインターを置き、コンパイラによって割り当てられた型が `IEnumerable(Of Student)`ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="eea57-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="eea57-142">クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="eea57-142">Run the Query</span></span>

<span data-ttu-id="eea57-143">変数 `studentQuery` には、クエリの実行結果ではなく、クエリの定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eea57-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="eea57-144">クエリを実行するための一般的なメカニズムは、`For Each` ループです。</span><span class="sxs-lookup"><span data-stu-id="eea57-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="eea57-145">返されたシーケンスの各要素は、ループ反復変数を介してアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="eea57-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="eea57-146">クエリ実行の詳細については、「初めての[LINQ クエリの作成](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea57-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="eea57-147">クエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="eea57-147">To run the query</span></span>

1. <span data-ttu-id="eea57-148">プロジェクトのクエリの下に、次の `For Each` ループを追加します。</span><span class="sxs-lookup"><span data-stu-id="eea57-148">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="eea57-149">マウスポインターをループコントロール変数 `studentRecord` 上に置くと、データ型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="eea57-150">`studentQuery` は `Student` インスタンスのコレクションを返すため、`studentRecord` の型は `Student`されることが推定されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="eea57-151">CTRL キーを押しながら F5 キーを押して、アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="eea57-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="eea57-152">コンソールウィンドウに結果が記録されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-152">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="eea57-153">クエリの変更</span><span class="sxs-lookup"><span data-stu-id="eea57-153">Modify the Query</span></span>

<span data-ttu-id="eea57-154">指定された順序でクエリを実行すると、クエリの結果を簡単にスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="eea57-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="eea57-155">返されたシーケンスは、使用可能な任意のフィールドに基づいて並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="eea57-155">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="eea57-156">結果を並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="eea57-156">To order the results</span></span>

1. <span data-ttu-id="eea57-157">`Where` ステートメントとクエリの `Select` ステートメントの間に、次の `Order By` 句を追加します。</span><span class="sxs-lookup"><span data-stu-id="eea57-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="eea57-158">`Order By` 句は、各学生の姓に従って、結果をアルファベット順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="eea57-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="eea57-159">姓と名の順序を指定するには、両方のフィールドをクエリに追加します。</span><span class="sxs-lookup"><span data-stu-id="eea57-159">To order by last name and then first name, add both fields to the query:</span></span>

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="eea57-160">`Descending` を指定して、Z から A への順序を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="eea57-160">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="eea57-161">CTRL キーを押しながら F5 キーを押して、アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="eea57-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="eea57-162">コンソールウィンドウに結果が記録されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-162">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="eea57-163">ローカル識別子を導入するには</span><span class="sxs-lookup"><span data-stu-id="eea57-163">To introduce a local identifier</span></span>

1. <span data-ttu-id="eea57-164">このセクションのコードを追加して、クエリ式にローカル識別子を導入します。</span><span class="sxs-lookup"><span data-stu-id="eea57-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="eea57-165">ローカル識別子は、中間結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="eea57-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="eea57-166">次の例では、`name` は、学生の姓と名の連結を保持する識別子です。</span><span class="sxs-lookup"><span data-stu-id="eea57-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="eea57-167">ローカル識別子は便宜上使用できます。または、複数回計算される式の結果を格納することによって、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="eea57-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="eea57-168">CTRL キーを押しながら F5 キーを押して、アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="eea57-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="eea57-169">コンソールウィンドウに結果が記録されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-169">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="eea57-170">Select 句で1つのフィールドを射影するには</span><span class="sxs-lookup"><span data-stu-id="eea57-170">To project one field in the Select clause</span></span>

1. <span data-ttu-id="eea57-171">このセクションからクエリと `For Each` ループを追加して、ソース内の要素とは異なる要素を持つシーケンスを生成するクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="eea57-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="eea57-172">次の例では、ソースは `Student` オブジェクトのコレクションですが、返されるのは各オブジェクトの1つのメンバーのみです。姓が指定されている学生の名は、最初の名前になります。</span><span class="sxs-lookup"><span data-stu-id="eea57-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="eea57-173">`currentStudent.First` は文字列であるため、`studentQuery3` によって返されるシーケンスのデータ型は `IEnumerable(Of String)`、文字列のシーケンスです。</span><span class="sxs-lookup"><span data-stu-id="eea57-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="eea57-174">前の例と同様に、`studentQuery3` のデータ型の割り当ては、コンパイラがローカル型の推論を使用して判断するために残されています。</span><span class="sxs-lookup"><span data-stu-id="eea57-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="eea57-175">コード内の `studentQuery3` 上にマウスポインターを置いて、割り当てられている型が `IEnumerable(Of String)`ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="eea57-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="eea57-176">CTRL キーを押しながら F5 キーを押して、アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="eea57-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="eea57-177">コンソールウィンドウに結果が記録されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-177">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="eea57-178">Select 句で匿名型を作成するには</span><span class="sxs-lookup"><span data-stu-id="eea57-178">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="eea57-179">クエリで匿名型がどのように使用されるかを確認するには、このセクションのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="eea57-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="eea57-180">クエリで使用するのは、完全なレコード (前の例では`currentStudent` レコード) または1つのフィールド (前のセクションで`First`) ではなく、データソースから複数のフィールドを返す場合です。</span><span class="sxs-lookup"><span data-stu-id="eea57-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="eea57-181">結果に含めるフィールドを含む新しい名前付きの型を定義する代わりに、`Select` 句でフィールドを指定すると、そのフィールドをプロパティとして持つ匿名型がコンパイラによって作成されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="eea57-182">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eea57-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="eea57-183">次の例では、学術ランクが 1 ~ 10 の範囲の seniors の名前とランクを返すクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="eea57-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="eea57-184">この例では、`Select` 句が匿名型のインスタンスを返し、匿名型に使用可能な名前がないため、`studentQuery4` の型を推論する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eea57-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="eea57-185">CTRL キーを押しながら F5 キーを押して、アプリケーションをビルドして実行します。</span><span class="sxs-lookup"><span data-stu-id="eea57-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="eea57-186">コンソールウィンドウに結果が記録されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-186">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="eea57-187">その他の例</span><span class="sxs-lookup"><span data-stu-id="eea57-187">Additional Examples</span></span>

<span data-ttu-id="eea57-188">基本を理解したところで、LINQ クエリの柔軟性と機能を示すその他の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="eea57-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of LINQ queries.</span></span> <span data-ttu-id="eea57-189">各例には、その動作についての簡単な説明が付いています。</span><span class="sxs-lookup"><span data-stu-id="eea57-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="eea57-190">各クエリのクエリ結果変数の上にマウスポインターを置くと、推論された型が表示されます。</span><span class="sxs-lookup"><span data-stu-id="eea57-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="eea57-191">結果を生成するには、`For Each` ループを使用します。</span><span class="sxs-lookup"><span data-stu-id="eea57-191">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="eea57-192">追加情報</span><span class="sxs-lookup"><span data-stu-id="eea57-192">Additional Information</span></span>

<span data-ttu-id="eea57-193">クエリの使用に関する基本的な概念を理解した後は、関心のある特定の種類の LINQ プロバイダーのドキュメントとサンプルを読むことができます。</span><span class="sxs-lookup"><span data-stu-id="eea57-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of LINQ provider that you are interested in:</span></span>

- [<span data-ttu-id="eea57-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="eea57-194">LINQ to Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [<span data-ttu-id="eea57-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eea57-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="eea57-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="eea57-196">LINQ to XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [<span data-ttu-id="eea57-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="eea57-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="eea57-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="eea57-198">See also</span></span>

- [<span data-ttu-id="eea57-199">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eea57-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="eea57-200">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="eea57-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="eea57-201">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="eea57-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="eea57-202">オブジェクト初期化子 : 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="eea57-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="eea57-203">匿名型</span><span class="sxs-lookup"><span data-stu-id="eea57-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="eea57-204">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="eea57-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="eea57-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="eea57-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="eea57-206">クエリ</span><span class="sxs-lookup"><span data-stu-id="eea57-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
