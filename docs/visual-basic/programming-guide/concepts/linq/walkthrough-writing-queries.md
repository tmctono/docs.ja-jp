---
title: Visual Basic におけるクエリの作成
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 55ded2f2fbd5c2c6e33627ce7fafe6bb4248d5ef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783256"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="85ae0-102">チュートリアル: Visual Basic におけるクエリの作成</span><span class="sxs-lookup"><span data-stu-id="85ae0-102">Walkthrough: Writing Queries in Visual Basic</span></span>
<span data-ttu-id="85ae0-103">このチュートリアルでは、Visual Basic 言語の機能を使用して、記述する方法について説明[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]クエリ式。</span><span class="sxs-lookup"><span data-stu-id="85ae0-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="85ae0-104">このチュートリアルでは、学生オブジェクトの一覧にクエリを作成する方法、クエリを実行する方法、およびそれらを変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="85ae0-105">クエリでは、オブジェクト初期化子、ローカル型推論では、匿名型など、いくつかの機能を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>  
  
 <span data-ttu-id="85ae0-106">このチュートリアルを完了できるようになりますサンプルと、特定のドキュメントに移動する準備ができて[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]興味のあるプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="85ae0-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] <span data-ttu-id="85ae0-107">プロバイダーには、 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]、LINQ to DataSet、および[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-107">providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
## <a name="create-a-project"></a><span data-ttu-id="85ae0-108">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="85ae0-108">Create a Project</span></span>  
  
### <a name="to-create-a-console-application-project"></a><span data-ttu-id="85ae0-109">コンソール アプリケーション プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-109">To create a console application project</span></span>  
  
1. <span data-ttu-id="85ae0-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-110">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="85ae0-111">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85ae0-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="85ae0-112">**インストールされたテンプレート**一覧で、 **Visual Basic**します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>  
  
4. <span data-ttu-id="85ae0-113">プロジェクトの種類の一覧でクリックして**コンソール アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="85ae0-114">**名前**ボックスで、プロジェクトの名前を入力し、クリックして**OK**。</span><span class="sxs-lookup"><span data-stu-id="85ae0-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>  
  
     <span data-ttu-id="85ae0-115">プロジェクトが作成されます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-115">A project is created.</span></span> <span data-ttu-id="85ae0-116">既定では、System.Core.dll への参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="85ae0-117">また、**インポートされた名前空間**ボックスの一覧、[参照設定 ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)が含まれています、<xref:System.Linq?displayProperty=nameWithType>名前空間。</span><span class="sxs-lookup"><span data-stu-id="85ae0-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>  
  
5. <span data-ttu-id="85ae0-118">[[コンパイル] ページ、プロジェクト デザイナー (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)、いることを確認**Option infer**に設定されている**で**します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>  
  
## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="85ae0-119">メモリ内データ ソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-119">Add an In-Memory Data Source</span></span>  
 <span data-ttu-id="85ae0-120">このチュートリアルのクエリのデータ ソースの一覧は、`Student`オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="85ae0-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="85ae0-121">各`Student`オブジェクトには、名、姓、名、クラスの年、および学生の本文に教育機関のランクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="85ae0-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>  
  
### <a name="to-add-the-data-source"></a><span data-ttu-id="85ae0-122">データ ソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-122">To add the data source</span></span>  
  
- <span data-ttu-id="85ae0-123">定義、`Student`クラスおよびクラスのインスタンスの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-123">Define a `Student` class, and create a list of instances of the class.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="85ae0-124">定義に必要なコード、`Student`クラスを使用するリストの作成のチュートリアルで例が提供されている[方法。項目の一覧を作成](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)です。</span><span class="sxs-lookup"><span data-stu-id="85ae0-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="85ae0-125">そこからコピーして、プロジェクトに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="85ae0-126">新しいコード プロジェクトを作成したときに表示されたコードで置き換えます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-126">The new code replaces the code that appeared when you created the project.</span></span>  
  
### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="85ae0-127">学生のリストに新しい生徒を追加するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-127">To add a new student to the students list</span></span>  
  
- <span data-ttu-id="85ae0-128">パターンに従い、`getStudents`の別のインスタンスを追加するメソッドを`Student`クラスの一覧にします。</span><span class="sxs-lookup"><span data-stu-id="85ae0-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="85ae0-129">受講者を追加することをオブジェクト初期化子が紹介されます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="85ae0-130">詳細については、次を参照してください。[オブジェクト初期化子。名前付きの匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>  
  
## <a name="create-a-query"></a><span data-ttu-id="85ae0-131">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="85ae0-131">Create a Query</span></span>  
 <span data-ttu-id="85ae0-132">実行すると、このセクションでは追加のクエリは、学生の成績順位に上位 10 件の配置の一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="85ae0-133">完全なクエリが選択されるので`Student`オブジェクトたびに、クエリ結果の型が`IEnumerable(Of Student)`します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="85ae0-134">ただし、クエリの種類通常が指定されていないクエリの定義にします。</span><span class="sxs-lookup"><span data-stu-id="85ae0-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="85ae0-135">代わりに、コンパイラは、種類を決定するのにローカル型推論を使用します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="85ae0-136">詳細については、次を参照してください。[ローカル型推論](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="85ae0-137">クエリの範囲変数、 `currentStudent`、それぞれへの参照として機能`Student`、ソース内のインスタンス`students`、内の各オブジェクトのプロパティへのアクセスを提供する`students`します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>  
  
### <a name="to-create-a-simple-query"></a><span data-ttu-id="85ae0-138">簡単なクエリを作成するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-138">To create a simple query</span></span>  
  
1. <span data-ttu-id="85ae0-139">内の位置を検索、`Main`次のようにマークされているプロジェクトのメソッド。</span><span class="sxs-lookup"><span data-stu-id="85ae0-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>  
  
     [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]  
  
     <span data-ttu-id="85ae0-140">次のコードをコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-140">Copy the following code and paste it in.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]  
  
2. <span data-ttu-id="85ae0-141">マウス ポインターを合わせる`studentQuery`コンパイラによって割り当てられた型があることを確認するコードで`IEnumerable(Of Student)`します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>  
  
## <a name="run-the-query"></a><span data-ttu-id="85ae0-142">クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-142">Run the Query</span></span>  
 <span data-ttu-id="85ae0-143">変数`studentQuery`クエリの実行結果ではありません、クエリの定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="85ae0-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="85ae0-144">クエリを実行するための一般的なメカニズムは、`For Each`ループします。</span><span class="sxs-lookup"><span data-stu-id="85ae0-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="85ae0-145">返されたシーケンス内の各要素は、ループの反復変数を通じてアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="85ae0-146">クエリの実行の詳細については、次を参照してください。[書き込みで初めて Your の LINQ クエリ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>  
  
### <a name="to-run-the-query"></a><span data-ttu-id="85ae0-147">クエリを実行するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-147">To run the query</span></span>  
  
1. <span data-ttu-id="85ae0-148">次の追加`For Each`プロジェクト内のクエリの下のループします。</span><span class="sxs-lookup"><span data-stu-id="85ae0-148">Add the following `For Each` loop below the query in your project.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]  
  
2. <span data-ttu-id="85ae0-149">ループ コントロール変数の上にマウス ポインターを置く`studentRecord`にそのデータ型を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="85ae0-150">型`studentRecord`推論されます`Student`ため、`studentQuery`のコレクションを返します`Student`インスタンス。</span><span class="sxs-lookup"><span data-stu-id="85ae0-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>  
  
3. <span data-ttu-id="85ae0-151">構築し、CTRL + f5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="85ae0-152">コンソール ウィンドウに結果を注意してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-152">Note the results in the console window.</span></span>  
  
## <a name="modify-the-query"></a><span data-ttu-id="85ae0-153">クエリの変更</span><span class="sxs-lookup"><span data-stu-id="85ae0-153">Modify the Query</span></span>  
 <span data-ttu-id="85ae0-154">指定した順序内にある場合は、クエリの結果をスキャンしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="85ae0-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="85ae0-155">使用可能なフィールドに基づいて、返されたシーケンスを並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-155">You can sort the returned sequence based on any available field.</span></span>  
  
### <a name="to-order-the-results"></a><span data-ttu-id="85ae0-156">結果を並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="85ae0-156">To order the results</span></span>  
  
1. <span data-ttu-id="85ae0-157">次の追加`Order By`句の間、`Where`ステートメントおよび`Select`クエリのステートメント。</span><span class="sxs-lookup"><span data-stu-id="85ae0-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="85ae0-158">`Order By`句は結果の順序をアルファベット順に A から z、に従って最後の各生徒の名前。</span><span class="sxs-lookup"><span data-stu-id="85ae0-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending   
    ```  
  
2. <span data-ttu-id="85ae0-159">姓の最初の名前順で並べ替えには、クエリに両方のフィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-159">To order by last name and then first name, add both fields to the query:</span></span>  
  
    ```  
    Order By currentStudent.Last Ascending, currentStudent.First Ascending   
    ```  
  
     <span data-ttu-id="85ae0-160">指定することも`Descending`Z から a の順に</span><span class="sxs-lookup"><span data-stu-id="85ae0-160">You can also specify `Descending` to order from Z to A.</span></span>  
  
3. <span data-ttu-id="85ae0-161">構築し、CTRL + f5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="85ae0-162">コンソール ウィンドウに結果を注意してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-162">Note the results in the console window.</span></span>  
  
### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="85ae0-163">ローカル識別子を導入するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-163">To introduce a local identifier</span></span>  
  
1. <span data-ttu-id="85ae0-164">クエリ式でのローカル識別子を導入するには、このセクションでは、コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="85ae0-165">ローカルの識別子では、中間結果を保持します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="85ae0-166">次の例では、`name`受講者を連結したものを保持する識別子の最初と姓と名は、します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="85ae0-167">便宜上、ローカル識別子を使用できますか、複数回を計算するそれ以外の場合は、式の結果を格納することでパフォーマンスの向上につながります。</span><span class="sxs-lookup"><span data-stu-id="85ae0-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]  
  
2. <span data-ttu-id="85ae0-168">構築し、CTRL + f5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="85ae0-169">コンソール ウィンドウに結果を注意してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-169">Note the results in the console window.</span></span>  
  
### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="85ae0-170">Select 句で 1 つのフィールドを射影するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-170">To project one field in the Select clause</span></span>  
  
1. <span data-ttu-id="85ae0-171">クエリの追加と`For Each`ソース内の要素とは異なる要素のシーケンスを生成するクエリを作成するには、このセクションからループします。</span><span class="sxs-lookup"><span data-stu-id="85ae0-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="85ae0-172">次の例では、ソースが一連の`Student`オブジェクトではなく各オブジェクトの 1 メンバーのみが返されます。 姓が Garcia 学生の姓。</span><span class="sxs-lookup"><span data-stu-id="85ae0-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="85ae0-173">`currentStudent.First`によって返されるシーケンスのデータ型の文字列`studentQuery3`は`IEnumerable(Of String)`文字列のシーケンス。</span><span class="sxs-lookup"><span data-stu-id="85ae0-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="85ae0-174">前の例のように、データの割り当てを入力`studentQuery3`はローカル型推論を使用して確認するコンパイラの残しておきます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]  
  
2. <span data-ttu-id="85ae0-175">マウス ポインターを合わせる`studentQuery3`割り当てられた型があることを確認するコードで`IEnumerable(Of String)`します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>  
  
3. <span data-ttu-id="85ae0-176">構築し、CTRL + f5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="85ae0-177">コンソール ウィンドウに結果を注意してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-177">Note the results in the console window.</span></span>  
  
### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="85ae0-178">Select 句で匿名型を作成するには</span><span class="sxs-lookup"><span data-stu-id="85ae0-178">To create an anonymous type in the Select clause</span></span>  
  
1. <span data-ttu-id="85ae0-179">クエリで使用する方法に匿名型を表示するには、このセクションのコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="85ae0-180">完全な記録ではなく、データ ソースからいくつかのフィールドを取得するときにクエリで使用する (`currentStudent`前の例でのレコード) 1 つのフィールド (`First`前のセクションで)。</span><span class="sxs-lookup"><span data-stu-id="85ae0-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="85ae0-181">内のフィールドを指定する結果に含めるフィールドを含む新しい名前付きの型を定義するには、代わりに、`Select`句と、コンパイラは、それらのフィールドのプロパティとして持つ匿名型を作成します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="85ae0-182">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
     <span data-ttu-id="85ae0-183">次の例では、名前と成績順位の 1 ~ 10 の教育機関のランクの順序で、最上級生のランクを返すクエリを作成します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="85ae0-184">この例では、型で`studentQuery4`ため、推論する必要があります、`Select`句は、匿名型のインスタンスを返し、匿名型に使用できる名前がありません。</span><span class="sxs-lookup"><span data-stu-id="85ae0-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>  
  
     [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]  
  
2. <span data-ttu-id="85ae0-185">構築し、CTRL + f5 キーを押してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="85ae0-186">コンソール ウィンドウに結果を注意してください。</span><span class="sxs-lookup"><span data-stu-id="85ae0-186">Note the results in the console window.</span></span>  
  
## <a name="additional-examples"></a><span data-ttu-id="85ae0-187">その他の例</span><span class="sxs-lookup"><span data-stu-id="85ae0-187">Additional Examples</span></span>  
 <span data-ttu-id="85ae0-188">電源と柔軟性を説明するためにその他の例の一覧を次に、基本を理解したところで[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]クエリ。</span><span class="sxs-lookup"><span data-stu-id="85ae0-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="85ae0-189">それぞれの例には、機能の簡単な説明が付きます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="85ae0-190">推論された型を表示するには、各クエリのクエリ結果の変数にマウス ポインターを置きます。</span><span class="sxs-lookup"><span data-stu-id="85ae0-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="85ae0-191">使用して、`For Each`ループを使用して、結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="85ae0-191">Use a `For Each` loop to produce the results.</span></span>  
  
 [!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]  
  
## <a name="additional-information"></a><span data-ttu-id="85ae0-192">追加情報</span><span class="sxs-lookup"><span data-stu-id="85ae0-192">Additional Information</span></span>  
 <span data-ttu-id="85ae0-193">特定の種類のドキュメントとサンプルを読み取る準備が完了したらクエリの基本的な概念を理解したら、[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]興味のあるプロバイダー。</span><span class="sxs-lookup"><span data-stu-id="85ae0-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>  
  
 [<span data-ttu-id="85ae0-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="85ae0-194">LINQ to Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
  
 [<span data-ttu-id="85ae0-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="85ae0-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
  
 [<span data-ttu-id="85ae0-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="85ae0-196">LINQ to XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)  
  
 [<span data-ttu-id="85ae0-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="85ae0-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)  
  
## <a name="see-also"></a><span data-ttu-id="85ae0-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="85ae0-198">See also</span></span>

- [<span data-ttu-id="85ae0-199">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85ae0-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="85ae0-200">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="85ae0-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="85ae0-201">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="85ae0-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="85ae0-202">オブジェクト初期化子:名前付きの匿名型</span><span class="sxs-lookup"><span data-stu-id="85ae0-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="85ae0-203">匿名型</span><span class="sxs-lookup"><span data-stu-id="85ae0-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="85ae0-204">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="85ae0-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="85ae0-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="85ae0-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="85ae0-206">クエリ</span><span class="sxs-lookup"><span data-stu-id="85ae0-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
