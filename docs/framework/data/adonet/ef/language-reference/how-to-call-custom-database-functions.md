---
title: カスタム データベース関数を呼び出す方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: e357868361e11dc919fa09db9a36185923a6e40e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847093"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="f9696-102">カスタム データベース関数を呼び出す方法</span><span class="sxs-lookup"><span data-stu-id="f9696-102">How to: Call Custom Database Functions</span></span>

<span data-ttu-id="f9696-103">ここでは、データベースで定義されたカスタム関数を LINQ Entities クエリから呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9696-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>

<span data-ttu-id="f9696-104">LINQ to Entities クエリから呼び出されるデータベース関数は、データベース内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f9696-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="f9696-105">データベース内で関数を実行すると、アプリケーションのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="f9696-105">Executing functions in the database can improve application performance.</span></span>

<span data-ttu-id="f9696-106">下に示す手順は、カスタム データベース関数を呼び出す方法の概要をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="f9696-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="f9696-107">各手順の詳しい説明は、その後の例で示します。</span><span class="sxs-lookup"><span data-stu-id="f9696-107">The example that follows provides more detail about the steps in the procedure.</span></span>

## <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="f9696-108">データベースで定義されるカスタム関数を呼び出すには</span><span class="sxs-lookup"><span data-stu-id="f9696-108">To call custom functions that are defined in the database</span></span>

1. <span data-ttu-id="f9696-109">データベースにカスタム関数を作成します。</span><span class="sxs-lookup"><span data-stu-id="f9696-109">Create a custom function in your database.</span></span>

     <span data-ttu-id="f9696-110">SQL Server でカスタム関数を作成する方法の詳細については、「 [CREATE FUNCTION (transact-sql)](https://go.microsoft.com/fwlink/?LinkID=139871)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9696-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>

2. <span data-ttu-id="f9696-111">関数を .edmx ファイルのストア スキーマ定義言語 (SSDL) で宣言します。</span><span class="sxs-lookup"><span data-stu-id="f9696-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="f9696-112">関数の名前は、データベースで宣言される関数と同じ名前にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9696-112">The name of the function must be the same as the name of the function declared in the database.</span></span>

     <span data-ttu-id="f9696-113">詳細については、「 [Function 要素 (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9696-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>

3. <span data-ttu-id="f9696-114">対応するメソッドをアプリケーション コードのクラスに追加して、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> をそのメソッドに適用する必要があります。属性の <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> パラメーターと <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> パラメーターが、それぞれ概念モデルの名前空間名と概念モデルの関数名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9696-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="f9696-115">LINQ の関数名解決では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="f9696-115">Function name resolution for LINQ is case sensitive.</span></span>

4. <span data-ttu-id="f9696-116">LINQ to Entities クエリからメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f9696-116">Call the method in a LINQ to Entities query.</span></span>  

## <a name="example"></a><span data-ttu-id="f9696-117">例</span><span class="sxs-lookup"><span data-stu-id="f9696-117">Example</span></span>

<span data-ttu-id="f9696-118">次の例は、カスタム データベース関数を LINQ to Entities クエリから呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9696-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="f9696-119">この例では、School モデルを使用します。</span><span class="sxs-lookup"><span data-stu-id="f9696-119">The example uses the School model.</span></span> <span data-ttu-id="f9696-120">School モデルの詳細については、「 [School サンプルデータベースの作成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))」および「 [school .Edmx ファイルの生成](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f9696-120">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>

<span data-ttu-id="f9696-121">次のコードは、`AvgStudentGrade` 関数を School のサンプル データベースに追加しています。</span><span class="sxs-lookup"><span data-stu-id="f9696-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>

> [!NOTE]
> <span data-ttu-id="f9696-122">カスタム データベース関数を呼び出す手順は、データベース サーバーとは無関係にすべて同じです。</span><span class="sxs-lookup"><span data-stu-id="f9696-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="f9696-123">ただし、下に示すコードは、SQL Server データベースで関数を作成する方法に固有のものです。</span><span class="sxs-lookup"><span data-stu-id="f9696-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="f9696-124">他のデータベース サーバーでカスタム関数を作成する場合には、コードは異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="f9696-124">The code for creating a custom function in other database servers might differ.</span></span>

[!code-sql[DP L2E MapToDBFunction#1](~/samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]

## <a name="example"></a><span data-ttu-id="f9696-125">例</span><span class="sxs-lookup"><span data-stu-id="f9696-125">Example</span></span>

<span data-ttu-id="f9696-126">次に、 *.edmx*ファイルのストアスキーマ定義言語 (SSDL) で関数を宣言します。</span><span class="sxs-lookup"><span data-stu-id="f9696-126">Next, declare a function in the store schema definition language (SSDL) of your *.edmx* file.</span></span> <span data-ttu-id="f9696-127">次のコードは、SSDL の `AvgStudentGrade` 関数を宣言しています。</span><span class="sxs-lookup"><span data-stu-id="f9696-127">The following code declares the `AvgStudentGrade` function in SSDL:</span></span>

[!code-xml[DP L2E MapToDBFunction#2](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]

## <a name="example"></a><span data-ttu-id="f9696-128">例</span><span class="sxs-lookup"><span data-stu-id="f9696-128">Example</span></span>

<span data-ttu-id="f9696-129">ここで、メソッドを作成し、SSDL で宣言された関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="f9696-129">Now, create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="f9696-130">次のクラスのメソッドは、<xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> を使用して SSDL (上を参照) で定義される関数にマップされます。</span><span class="sxs-lookup"><span data-stu-id="f9696-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="f9696-131">このメソッドが呼び出されると、データベース内の対応する関数が実行されます。</span><span class="sxs-lookup"><span data-stu-id="f9696-131">When this method is called, the corresponding function in the database is executed.</span></span>

[!code-csharp[DP L2E MapToDBFunction#3](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
[!code-vb[DP L2E MapToDBFunction#3](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="f9696-132">例</span><span class="sxs-lookup"><span data-stu-id="f9696-132">Example</span></span>

<span data-ttu-id="f9696-133">最後に、メソッドを LINQ to Entities クエリで呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f9696-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="f9696-134">次のコードは、学生の姓と平均の成績をコンソールに表示します。</span><span class="sxs-lookup"><span data-stu-id="f9696-134">The following code displays students' last names and average grades to the console:</span></span>

[!code-csharp[DP L2E MapToDBFunction#4](~/samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
[!code-vb[DP L2E MapToDBFunction#4](~/samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="f9696-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9696-135">See also</span></span>

- <span data-ttu-id="f9696-136">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f9696-136">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="f9696-137">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="f9696-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
