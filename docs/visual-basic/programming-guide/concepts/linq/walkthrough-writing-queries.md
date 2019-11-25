---
title: クエリの作成
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ [Visual Basic], walkthroughs
- LINQ [Visual Basic], writing queries
- writing LINQ queries [Visual Basic]
ms.assetid: f0045808-b9fe-4d31-88d1-473d9957211e
ms.openlocfilehash: 6a9f229697ce3d6328c6fb09d18d4cc2627eab10
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351013"
---
# <a name="walkthrough-writing-queries-in-visual-basic"></a><span data-ttu-id="43e23-102">チュートリアル: Visual Basic でクエリを記述する</span><span class="sxs-lookup"><span data-stu-id="43e23-102">Walkthrough: Writing Queries in Visual Basic</span></span>

<span data-ttu-id="43e23-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span><span class="sxs-lookup"><span data-stu-id="43e23-103">This walkthrough demonstrates how you can use Visual Basic language features to write [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] query expressions.</span></span> <span data-ttu-id="43e23-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span><span class="sxs-lookup"><span data-stu-id="43e23-104">The walkthrough demonstrates how to create queries on a list of Student objects, how to run the queries, and how to modify them.</span></span> <span data-ttu-id="43e23-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span><span class="sxs-lookup"><span data-stu-id="43e23-105">The queries incorporate several features including object initializers, local type inference, and anonymous types.</span></span>

<span data-ttu-id="43e23-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span><span class="sxs-lookup"><span data-stu-id="43e23-106">After completing this walkthrough, you will be ready to move on to the samples and documentation for the specific [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider you are interested in.</span></span> [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] <span data-ttu-id="43e23-107">providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43e23-107">providers include [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], LINQ to DataSet, and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>

## <a name="create-a-project"></a><span data-ttu-id="43e23-108">プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="43e23-108">Create a Project</span></span>

### <a name="to-create-a-console-application-project"></a><span data-ttu-id="43e23-109">To create a console application project</span><span class="sxs-lookup"><span data-stu-id="43e23-109">To create a console application project</span></span>

1. <span data-ttu-id="43e23-110">Visual Studio を起動します。</span><span class="sxs-lookup"><span data-stu-id="43e23-110">Start Visual Studio.</span></span>

2. <span data-ttu-id="43e23-111">**[ファイル]** メニューの **[新規作成]** をポイントし、 **[プロジェクト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43e23-111">On the **File** menu, point to **New**, and then click **Project**.</span></span>

3. <span data-ttu-id="43e23-112">In the **Installed Templates** list, click **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="43e23-112">In the **Installed Templates** list, click **Visual Basic**.</span></span>

4. <span data-ttu-id="43e23-113">In the list of project types, click **Console Application**.</span><span class="sxs-lookup"><span data-stu-id="43e23-113">In the list of project types, click **Console Application**.</span></span> <span data-ttu-id="43e23-114">In the **Name** box, type a name for the project, and then click **OK**.</span><span class="sxs-lookup"><span data-stu-id="43e23-114">In the **Name** box, type a name for the project, and then click **OK**.</span></span>

    <span data-ttu-id="43e23-115">A project is created.</span><span class="sxs-lookup"><span data-stu-id="43e23-115">A project is created.</span></span> <span data-ttu-id="43e23-116">By default, it contains a reference to System.Core.dll.</span><span class="sxs-lookup"><span data-stu-id="43e23-116">By default, it contains a reference to System.Core.dll.</span></span> <span data-ttu-id="43e23-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span><span class="sxs-lookup"><span data-stu-id="43e23-117">Also, the **Imported namespaces** list on the [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic) includes the <xref:System.Linq?displayProperty=nameWithType> namespace.</span></span>

5. <span data-ttu-id="43e23-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span><span class="sxs-lookup"><span data-stu-id="43e23-118">On the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), ensure that **Option infer** is set to **On**.</span></span>

## <a name="add-an-in-memory-data-source"></a><span data-ttu-id="43e23-119">Add an In-Memory Data Source</span><span class="sxs-lookup"><span data-stu-id="43e23-119">Add an In-Memory Data Source</span></span>

<span data-ttu-id="43e23-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span><span class="sxs-lookup"><span data-stu-id="43e23-120">The data source for the queries in this walkthrough is a list of `Student` objects.</span></span> <span data-ttu-id="43e23-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span><span class="sxs-lookup"><span data-stu-id="43e23-121">Each `Student` object contains a first name, a last name, a class year, and an academic rank in the student body.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="43e23-122">データ ソースを追加するには</span><span class="sxs-lookup"><span data-stu-id="43e23-122">To add the data source</span></span>

- <span data-ttu-id="43e23-123">Define a `Student` class, and create a list of instances of the class.</span><span class="sxs-lookup"><span data-stu-id="43e23-123">Define a `Student` class, and create a list of instances of the class.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="43e23-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span><span class="sxs-lookup"><span data-stu-id="43e23-124">The code needed to define the `Student` class and create the list used in the walkthrough examples is provided in [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).</span></span> <span data-ttu-id="43e23-125">You can copy it from there and paste it into your project.</span><span class="sxs-lookup"><span data-stu-id="43e23-125">You can copy it from there and paste it into your project.</span></span> <span data-ttu-id="43e23-126">The new code replaces the code that appeared when you created the project.</span><span class="sxs-lookup"><span data-stu-id="43e23-126">The new code replaces the code that appeared when you created the project.</span></span>

### <a name="to-add-a-new-student-to-the-students-list"></a><span data-ttu-id="43e23-127">To add a new student to the students list</span><span class="sxs-lookup"><span data-stu-id="43e23-127">To add a new student to the students list</span></span>

- <span data-ttu-id="43e23-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span><span class="sxs-lookup"><span data-stu-id="43e23-128">Follow the pattern in the `getStudents` method to add another instance of the `Student` class to the list.</span></span> <span data-ttu-id="43e23-129">Adding the student will introduce you to object initializers.</span><span class="sxs-lookup"><span data-stu-id="43e23-129">Adding the student will introduce you to object initializers.</span></span> <span data-ttu-id="43e23-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="43e23-130">For more information, see [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md).</span></span>

## <a name="create-a-query"></a><span data-ttu-id="43e23-131">クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="43e23-131">Create a Query</span></span>

<span data-ttu-id="43e23-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span><span class="sxs-lookup"><span data-stu-id="43e23-132">When executed, the query added in this section produces a list of the students whose academic rank puts them in the top ten.</span></span> <span data-ttu-id="43e23-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span><span class="sxs-lookup"><span data-stu-id="43e23-133">Because the query selects the complete `Student` object each time, the type of the query result is `IEnumerable(Of Student)`.</span></span> <span data-ttu-id="43e23-134">However, the type of the query typically is not specified in query definitions.</span><span class="sxs-lookup"><span data-stu-id="43e23-134">However, the type of the query typically is not specified in query definitions.</span></span> <span data-ttu-id="43e23-135">Instead, the compiler uses local type inference to determine the type.</span><span class="sxs-lookup"><span data-stu-id="43e23-135">Instead, the compiler uses local type inference to determine the type.</span></span> <span data-ttu-id="43e23-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="43e23-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span> <span data-ttu-id="43e23-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span><span class="sxs-lookup"><span data-stu-id="43e23-137">The query's range variable, `currentStudent`, serves as a reference to each `Student` instance in the source, `students`, providing access to the properties of each object in `students`.</span></span>

### <a name="to-create-a-simple-query"></a><span data-ttu-id="43e23-138">簡単なクエリを作成するには</span><span class="sxs-lookup"><span data-stu-id="43e23-138">To create a simple query</span></span>

1. <span data-ttu-id="43e23-139">Find the place in the `Main` method of the project that is marked as follows:</span><span class="sxs-lookup"><span data-stu-id="43e23-139">Find the place in the `Main` method of the project that is marked as follows:</span></span>

    [!code-vb[VbLINQWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#1)]

    <span data-ttu-id="43e23-140">Copy the following code and paste it in.</span><span class="sxs-lookup"><span data-stu-id="43e23-140">Copy the following code and paste it in.</span></span>

    [!code-vb[VbLINQWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#2)]

2. <span data-ttu-id="43e23-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span><span class="sxs-lookup"><span data-stu-id="43e23-141">Rest the mouse pointer over `studentQuery` in your code to verify that the compiler-assigned type is `IEnumerable(Of Student)`.</span></span>

## <a name="run-the-query"></a><span data-ttu-id="43e23-142">Run the Query</span><span class="sxs-lookup"><span data-stu-id="43e23-142">Run the Query</span></span>

<span data-ttu-id="43e23-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span><span class="sxs-lookup"><span data-stu-id="43e23-143">The variable `studentQuery` contains the definition of the query, not the results of running the query.</span></span> <span data-ttu-id="43e23-144">A typical mechanism for running a query is a `For Each` loop.</span><span class="sxs-lookup"><span data-stu-id="43e23-144">A typical mechanism for running a query is a `For Each` loop.</span></span> <span data-ttu-id="43e23-145">Each element in the returned sequence is accessed through the loop iteration variable.</span><span class="sxs-lookup"><span data-stu-id="43e23-145">Each element in the returned sequence is accessed through the loop iteration variable.</span></span> <span data-ttu-id="43e23-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span><span class="sxs-lookup"><span data-stu-id="43e23-146">For more information about query execution, see [Writing Your First LINQ Query](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).</span></span>

### <a name="to-run-the-query"></a><span data-ttu-id="43e23-147">To run the query</span><span class="sxs-lookup"><span data-stu-id="43e23-147">To run the query</span></span>

1. <span data-ttu-id="43e23-148">Add the following `For Each` loop below the query in your project.</span><span class="sxs-lookup"><span data-stu-id="43e23-148">Add the following `For Each` loop below the query in your project.</span></span>

    [!code-vb[VbLINQWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#3)]

2. <span data-ttu-id="43e23-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span><span class="sxs-lookup"><span data-stu-id="43e23-149">Rest the mouse pointer over the loop control variable `studentRecord` to see its data type.</span></span> <span data-ttu-id="43e23-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span><span class="sxs-lookup"><span data-stu-id="43e23-150">The type of `studentRecord` is inferred to be `Student`, because `studentQuery` returns a collection of `Student` instances.</span></span>

3. <span data-ttu-id="43e23-151">Build and run the application by pressing CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="43e23-151">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="43e23-152">Note the results in the console window.</span><span class="sxs-lookup"><span data-stu-id="43e23-152">Note the results in the console window.</span></span>

## <a name="modify-the-query"></a><span data-ttu-id="43e23-153">クエリの変更</span><span class="sxs-lookup"><span data-stu-id="43e23-153">Modify the Query</span></span>

<span data-ttu-id="43e23-154">It is easier to scan query results if they are in a specified order.</span><span class="sxs-lookup"><span data-stu-id="43e23-154">It is easier to scan query results if they are in a specified order.</span></span> <span data-ttu-id="43e23-155">You can sort the returned sequence based on any available field.</span><span class="sxs-lookup"><span data-stu-id="43e23-155">You can sort the returned sequence based on any available field.</span></span>

### <a name="to-order-the-results"></a><span data-ttu-id="43e23-156">結果を並べ替えるには</span><span class="sxs-lookup"><span data-stu-id="43e23-156">To order the results</span></span>

1. <span data-ttu-id="43e23-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span><span class="sxs-lookup"><span data-stu-id="43e23-157">Add the following `Order By` clause between the `Where` statement and the `Select` statement of the query.</span></span> <span data-ttu-id="43e23-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span><span class="sxs-lookup"><span data-stu-id="43e23-158">The `Order By` clause will order the results alphabetically from A to Z, according to the last name of each student.</span></span>

    ```vb
    Order By currentStudent.Last Ascending
    ```

2. <span data-ttu-id="43e23-159">To order by last name and then first name, add both fields to the query:</span><span class="sxs-lookup"><span data-stu-id="43e23-159">To order by last name and then first name, add both fields to the query:</span></span>

    ```vb
    Order By currentStudent.Last Ascending, currentStudent.First Ascending
    ```

    <span data-ttu-id="43e23-160">You can also specify `Descending` to order from Z to A.</span><span class="sxs-lookup"><span data-stu-id="43e23-160">You can also specify `Descending` to order from Z to A.</span></span>

3. <span data-ttu-id="43e23-161">Build and run the application by pressing CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="43e23-161">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="43e23-162">Note the results in the console window.</span><span class="sxs-lookup"><span data-stu-id="43e23-162">Note the results in the console window.</span></span>

### <a name="to-introduce-a-local-identifier"></a><span data-ttu-id="43e23-163">To introduce a local identifier</span><span class="sxs-lookup"><span data-stu-id="43e23-163">To introduce a local identifier</span></span>

1. <span data-ttu-id="43e23-164">Add the code in this section to introduce a local identifier in the query expression.</span><span class="sxs-lookup"><span data-stu-id="43e23-164">Add the code in this section to introduce a local identifier in the query expression.</span></span> <span data-ttu-id="43e23-165">The local identifier will hold an intermediate result.</span><span class="sxs-lookup"><span data-stu-id="43e23-165">The local identifier will hold an intermediate result.</span></span> <span data-ttu-id="43e23-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span><span class="sxs-lookup"><span data-stu-id="43e23-166">In the following example, `name` is an identifier that holds a concatenation of the student's first and last names.</span></span> <span data-ttu-id="43e23-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span><span class="sxs-lookup"><span data-stu-id="43e23-167">A local identifier can be used for convenience, or it can enhance performance by storing the results of an expression that would otherwise be calculated multiple times.</span></span>

    [!code-vb[VbLINQWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#4)]

2. <span data-ttu-id="43e23-168">Build and run the application by pressing CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="43e23-168">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="43e23-169">Note the results in the console window.</span><span class="sxs-lookup"><span data-stu-id="43e23-169">Note the results in the console window.</span></span>

### <a name="to-project-one-field-in-the-select-clause"></a><span data-ttu-id="43e23-170">To project one field in the Select clause</span><span class="sxs-lookup"><span data-stu-id="43e23-170">To project one field in the Select clause</span></span>

1. <span data-ttu-id="43e23-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span><span class="sxs-lookup"><span data-stu-id="43e23-171">Add the query and `For Each` loop from this section to create a query that produces a sequence whose elements differ from the elements in the source.</span></span> <span data-ttu-id="43e23-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span><span class="sxs-lookup"><span data-stu-id="43e23-172">In the following example, the source is a collection of `Student` objects, but only one member of each object is returned: the first name of students whose last name is Garcia.</span></span> <span data-ttu-id="43e23-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span><span class="sxs-lookup"><span data-stu-id="43e23-173">Because `currentStudent.First` is a string, the data type of the sequence returned by `studentQuery3` is `IEnumerable(Of String)`, a sequence of strings.</span></span> <span data-ttu-id="43e23-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span><span class="sxs-lookup"><span data-stu-id="43e23-174">As in earlier examples, the assignment of a data type for `studentQuery3` is left for the compiler to determine by using local type inference.</span></span>

    [!code-vb[VbLINQWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#5)]

2. <span data-ttu-id="43e23-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="43e23-175">Rest the mouse pointer over `studentQuery3` in your code to verify that the assigned type is `IEnumerable(Of String)`.</span></span>

3. <span data-ttu-id="43e23-176">Build and run the application by pressing CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="43e23-176">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="43e23-177">Note the results in the console window.</span><span class="sxs-lookup"><span data-stu-id="43e23-177">Note the results in the console window.</span></span>

### <a name="to-create-an-anonymous-type-in-the-select-clause"></a><span data-ttu-id="43e23-178">To create an anonymous type in the Select clause</span><span class="sxs-lookup"><span data-stu-id="43e23-178">To create an anonymous type in the Select clause</span></span>

1. <span data-ttu-id="43e23-179">Add the code from this section to see how anonymous types are used in queries.</span><span class="sxs-lookup"><span data-stu-id="43e23-179">Add the code from this section to see how anonymous types are used in queries.</span></span> <span data-ttu-id="43e23-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span><span class="sxs-lookup"><span data-stu-id="43e23-180">You use them in queries when you want to return several fields from the data source rather than complete records (`currentStudent` records in previous examples) or single fields (`First` in the preceding section).</span></span> <span data-ttu-id="43e23-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span><span class="sxs-lookup"><span data-stu-id="43e23-181">Instead of defining a new named type that contains the fields you want to include in the result, you specify the fields in the `Select` clause and the compiler creates an anonymous type with those fields as its properties.</span></span> <span data-ttu-id="43e23-182">詳細については、「[匿名型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43e23-182">For more information, see [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>

    <span data-ttu-id="43e23-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span><span class="sxs-lookup"><span data-stu-id="43e23-183">The following example creates a query that returns the name and rank of seniors whose academic rank is between 1 and 10, in order of academic rank.</span></span> <span data-ttu-id="43e23-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span><span class="sxs-lookup"><span data-stu-id="43e23-184">In this example, the type of `studentQuery4` must be inferred because the `Select` clause returns an instance of an anonymous type, and an anonymous type has no usable name.</span></span>

    [!code-vb[VbLINQWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#6)]

2. <span data-ttu-id="43e23-185">Build and run the application by pressing CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="43e23-185">Build and run the application by pressing CTRL+F5.</span></span> <span data-ttu-id="43e23-186">Note the results in the console window.</span><span class="sxs-lookup"><span data-stu-id="43e23-186">Note the results in the console window.</span></span>

## <a name="additional-examples"></a><span data-ttu-id="43e23-187">Additional Examples</span><span class="sxs-lookup"><span data-stu-id="43e23-187">Additional Examples</span></span>

<span data-ttu-id="43e23-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span><span class="sxs-lookup"><span data-stu-id="43e23-188">Now that you understand the basics, the following is a list of additional examples to illustrate the flexibility and power of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries.</span></span> <span data-ttu-id="43e23-189">Each example is preceded by a brief description of what it does.</span><span class="sxs-lookup"><span data-stu-id="43e23-189">Each example is preceded by a brief description of what it does.</span></span> <span data-ttu-id="43e23-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span><span class="sxs-lookup"><span data-stu-id="43e23-190">Rest the mouse pointer over the query result variable for each query to see the inferred type.</span></span> <span data-ttu-id="43e23-191">Use a `For Each` loop to produce the results.</span><span class="sxs-lookup"><span data-stu-id="43e23-191">Use a `For Each` loop to produce the results.</span></span>

[!code-vb[VbLINQWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQWalkthrough/VB/Class1.vb#7)]

## <a name="additional-information"></a><span data-ttu-id="43e23-192">追加情報</span><span class="sxs-lookup"><span data-stu-id="43e23-192">Additional Information</span></span>

<span data-ttu-id="43e23-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span><span class="sxs-lookup"><span data-stu-id="43e23-193">After you are familiar with the basic concepts of working with queries, you are ready to read the documentation and samples for the specific type of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider that you are interested in:</span></span>

- [<span data-ttu-id="43e23-194">LINQ to Objects</span><span class="sxs-lookup"><span data-stu-id="43e23-194">LINQ to Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)

- [<span data-ttu-id="43e23-195">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="43e23-195">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)

- [<span data-ttu-id="43e23-196">LINQ to XML</span><span class="sxs-lookup"><span data-stu-id="43e23-196">LINQ to XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)

- [<span data-ttu-id="43e23-197">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="43e23-197">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)

## <a name="see-also"></a><span data-ttu-id="43e23-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="43e23-198">See also</span></span>

- [<span data-ttu-id="43e23-199">統合言語クエリ (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43e23-199">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="43e23-200">Visual Basic の LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="43e23-200">Getting Started with LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [<span data-ttu-id="43e23-201">ローカル型の推論</span><span class="sxs-lookup"><span data-stu-id="43e23-201">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="43e23-202">オブジェクト初期化子 : 名前付きの型と匿名型</span><span class="sxs-lookup"><span data-stu-id="43e23-202">Object Initializers: Named and Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="43e23-203">匿名型</span><span class="sxs-lookup"><span data-stu-id="43e23-203">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="43e23-204">Visual Basic における LINQ の概要</span><span class="sxs-lookup"><span data-stu-id="43e23-204">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="43e23-205">LINQ</span><span class="sxs-lookup"><span data-stu-id="43e23-205">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="43e23-206">クエリ</span><span class="sxs-lookup"><span data-stu-id="43e23-206">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
