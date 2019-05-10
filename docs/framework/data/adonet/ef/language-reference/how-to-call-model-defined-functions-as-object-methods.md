---
title: '方法: モデル定義関数をオブジェクト メソッドとして呼び出す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33bae8a8-4ed8-4a1f-85d1-c62ff288cc61
ms.openlocfilehash: 53ec7122a3601a2da53513f25a546a08c2aa4307
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631556"
---
# <a name="how-to-call-model-defined-functions-as-object-methods"></a><span data-ttu-id="a2247-102">方法: モデル定義関数をオブジェクト メソッドとして呼び出す</span><span class="sxs-lookup"><span data-stu-id="a2247-102">How to: Call Model-Defined Functions as Object Methods</span></span>
<span data-ttu-id="a2247-103">ここでは、モデル定義関数を <xref:System.Data.Objects.ObjectContext> オブジェクトのメソッドまたはカスタム クラスの静的メソッドとして呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a2247-103">This topic describes how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object or as a static method on a custom class.</span></span> <span data-ttu-id="a2247-104">A*モデル定義関数*は概念モデルで定義されている関数です。</span><span class="sxs-lookup"><span data-stu-id="a2247-104">A *model-defined function* is a function that is defined in the conceptual model.</span></span> <span data-ttu-id="a2247-105">このトピックで説明する手順は、これらの関数を LINQ to Entities クエリから呼び出すのではなく、直接呼び出す方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="a2247-105">The procedures in the topic describe how to call these functions directly instead of calling them from LINQ to Entities queries.</span></span> <span data-ttu-id="a2247-106">Linq to Entities クエリ モデル定義関数を呼び出す方法の詳細については、次を参照してください。[方法。クエリ モデル定義関数を呼び出す](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md)します。</span><span class="sxs-lookup"><span data-stu-id="a2247-106">For information about calling model-defined functions in LINQ to Entities queries, see [How to: Call Model-Defined Functions in Queries](../../../../../../docs/framework/data/adonet/ef/language-reference/how-to-call-model-defined-functions-in-queries.md).</span></span>  
  
 <span data-ttu-id="a2247-107">モデル定義関数を <xref:System.Data.Objects.ObjectContext> メソッドとして呼び出す場合も、カスタム クラスの静的メソッドとして呼び出す場合も、ます <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> でメソッドをモデル定義関数にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2247-107">Whether you call a model-defined function as an <xref:System.Data.Objects.ObjectContext> method or as a static method on a custom class, you must first map the method to the model-defined function with an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="a2247-108">ただし、<xref:System.Data.Objects.ObjectContext> クラスのメソッドを定義するときには、<xref:System.Data.Objects.ObjectContext.QueryProvider%2A> プロパティを使用して LINQ プロバイダーを公開する必要があります。それに対して、カスタム クラスの静的メソッドを定義するときには、<xref:System.Linq.IQueryable.Provider%2A> プロパティを使用して LINQ プロバイダーを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2247-108">However, when you define a method on the <xref:System.Data.Objects.ObjectContext> class, you must use the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property to expose the LINQ provider, whereas when you define a static method on a custom class, you must use the <xref:System.Linq.IQueryable.Provider%2A> property to expose the LINQ provider.</span></span> <span data-ttu-id="a2247-109">詳細については、下の手順の後に示した例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2247-109">For more information, see the examples that follow the procedures below.</span></span>  
  
 <span data-ttu-id="a2247-110">下の手順は、モデル定義関数を <xref:System.Data.Objects.ObjectContext> オブジェクトのメソッドおよびカスタム クラスの静的メソッドとして呼び出す方法の概要を示したものです。</span><span class="sxs-lookup"><span data-stu-id="a2247-110">The procedures below provide high-level outlines for calling a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object and as a static method on a custom class.</span></span> <span data-ttu-id="a2247-111">詳細な手順は、その後の例で示します。</span><span class="sxs-lookup"><span data-stu-id="a2247-111">The examples that follow provide more detail about the steps in the procedures.</span></span> <span data-ttu-id="a2247-112">この手順では、関数を概念モデルで定義済みであると想定します。</span><span class="sxs-lookup"><span data-stu-id="a2247-112">The procedures assume that you have defined a function in the conceptual model.</span></span> <span data-ttu-id="a2247-113">詳細については、「[方法 :概念モデルでカスタム関数を定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="a2247-113">For more information, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).</span></span>  
  
### <a name="to-call-a-model-defined-function-as-a-method-on-an-objectcontext-object"></a><span data-ttu-id="a2247-114">モデル定義関数を ObjectContext オブジェクトのメソッドとして呼び出すには</span><span class="sxs-lookup"><span data-stu-id="a2247-114">To call a model-defined function as a method on an ObjectContext object</span></span>  
  
1. <span data-ttu-id="a2247-115">ソース ファイルを追加して、部分クラスを拡張します。このクラスは、<xref:System.Data.Objects.ObjectContext> クラスから派生したものであり、Entity Framework ツールによって自動生成されます。</span><span class="sxs-lookup"><span data-stu-id="a2247-115">Add a source file to extend the partial class derived from the <xref:System.Data.Objects.ObjectContext> class, auto-generated by the Entity Framework tools.</span></span> <span data-ttu-id="a2247-116">CLR スタブを別のソース ファイルで定義すると、ファイルを再生成しても変更内容が失われません。</span><span class="sxs-lookup"><span data-stu-id="a2247-116">Defining the CLR stub in a separate source file will prevent the changes from being lost when the file is regenerated.</span></span>  
  
2. <span data-ttu-id="a2247-117">共通言語ランタイム (CLR) メソッドを、次のことを行う <xref:System.Data.Objects.ObjectContext> クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2247-117">Add a common language runtime (CLR) method to your <xref:System.Data.Objects.ObjectContext> class that does the following:</span></span>  
  
    - <span data-ttu-id="a2247-118">概念モデルで定義された関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="a2247-118">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="a2247-119">メソッドをマップするには、ユーザーが <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> をメソッドに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2247-119">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="a2247-120">属性の <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> パラメーターと <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> パラメーターが、それぞれ概念モデルの名前空間と概念モデルの関数名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a2247-120">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span> <span data-ttu-id="a2247-121">LINQ の関数名解決では、大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="a2247-121">Function name resolution for LINQ is case sensitive.</span></span>  
  
    - <span data-ttu-id="a2247-122"><xref:System.Linq.IQueryProvider.Execute%2A> プロパティによって返される <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> メソッドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="a2247-122">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Data.Objects.ObjectContext.QueryProvider%2A> property.</span></span>  
  
3. <span data-ttu-id="a2247-123">メソッドを <xref:System.Data.Objects.ObjectContext> クラスのインスタンスのメンバーとして呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2247-123">Call the method as a member on an instance of the <xref:System.Data.Objects.ObjectContext> class.</span></span>  
  
### <a name="to-call-a-model-defined-function-as-static-method-on-a-custom-class"></a><span data-ttu-id="a2247-124">モデル定義関数をカスタム クラスの静的メソッドとして呼び出すには</span><span class="sxs-lookup"><span data-stu-id="a2247-124">To call a model-defined function as static method on a custom class</span></span>  
  
1. <span data-ttu-id="a2247-125">クラスを次のことを行う静的メソッドでアプリケーションに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2247-125">Add a class to your application with a static method that does the following:</span></span>  
  
    - <span data-ttu-id="a2247-126">概念モデルで定義された関数にマップします。</span><span class="sxs-lookup"><span data-stu-id="a2247-126">Maps to the function defined in the conceptual model.</span></span> <span data-ttu-id="a2247-127">メソッドをマップするには、ユーザーが <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> をメソッドに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2247-127">To map the method, you must apply an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method.</span></span> <span data-ttu-id="a2247-128">属性の <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> パラメーターと <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> パラメーターが、それぞれ概念モデルの名前空間と概念モデルの関数名であることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a2247-128">Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model, respectively.</span></span>  
  
    - <span data-ttu-id="a2247-129"><xref:System.Linq.IQueryable> 引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="a2247-129">Accepts an <xref:System.Linq.IQueryable> argument.</span></span>  
  
    - <span data-ttu-id="a2247-130"><xref:System.Linq.IQueryProvider.Execute%2A> プロパティによって返される <xref:System.Linq.IQueryable.Provider%2A> メソッドの結果を返します。</span><span class="sxs-lookup"><span data-stu-id="a2247-130">Returns the results of the <xref:System.Linq.IQueryProvider.Execute%2A> method that is returned by the <xref:System.Linq.IQueryable.Provider%2A> property.</span></span>  
  
2. <span data-ttu-id="a2247-131">メソッドをカスタム クラスの静的メソッドのメンバーとして呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2247-131">Call the method as a member a static method on the custom class</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2247-132">例</span><span class="sxs-lookup"><span data-stu-id="a2247-132">Example</span></span>  
 <span data-ttu-id="a2247-133">**モデル定義関数を ObjectContext オブジェクトのメソッドとして呼び出す**</span><span class="sxs-lookup"><span data-stu-id="a2247-133">**Calling a Model-Defined Function as a Method on an ObjectContext Object**</span></span>  
  
 <span data-ttu-id="a2247-134">次の例で、モデル定義関数を <xref:System.Data.Objects.ObjectContext> オブジェクトのメソッドとして呼び出す方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a2247-134">The following example demonstrates how to call a model-defined function as a method on an <xref:System.Data.Objects.ObjectContext> object.</span></span> <span data-ttu-id="a2247-135">この例では、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)します。</span><span class="sxs-lookup"><span data-stu-id="a2247-135">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
 <span data-ttu-id="a2247-136">指定製品の製品収益を返す下の概念モデル関数について考察してください </span><span class="sxs-lookup"><span data-stu-id="a2247-136">Consider the conceptual model function below that returns product revenue for a specified product.</span></span> <span data-ttu-id="a2247-137">(概念モデルに関数を追加する方法の詳細については、次を参照してください。[方法。概念モデルでカスタム関数を定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)))。</span><span class="sxs-lookup"><span data-stu-id="a2247-137">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).)</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#4](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#4)]  

## <a name="example"></a><span data-ttu-id="a2247-138">例</span><span class="sxs-lookup"><span data-stu-id="a2247-138">Example</span></span>  
 <span data-ttu-id="a2247-139">次のコードでは、メソッドを上の概念モデル関数にマップする `AdventureWorksEntities` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2247-139">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#2)]
 [!code-vb[DP L2E Methods on ObjectContext#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="a2247-140">例</span><span class="sxs-lookup"><span data-stu-id="a2247-140">Example</span></span>  
 <span data-ttu-id="a2247-141">次のコードでは、上のメソッドを呼び出して、指定製品の製品収益を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2247-141">The following code calls the method above to display the product revenue for a specified product:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#3)]
 [!code-vb[DP L2E Methods on ObjectContext#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="a2247-142">例</span><span class="sxs-lookup"><span data-stu-id="a2247-142">Example</span></span>  
 <span data-ttu-id="a2247-143">次の例で、コレクション (<xref:System.Linq.IQueryable%601> オブジェクトとして) を返すモデル定義関数を呼び出す方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a2247-143">The following example demonstrates how to call a model-defined function that returns a collection (as an <xref:System.Linq.IQueryable%601> object).</span></span> <span data-ttu-id="a2247-144">指定された製品 ID に関して `SalesOrderDetails` をすべて返す下の概念モデル関数について考察してください。</span><span class="sxs-lookup"><span data-stu-id="a2247-144">Consider the conceptual model function below that returns all the `SalesOrderDetails` for a given product ID.</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#7](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#7)]  
  
## <a name="example"></a><span data-ttu-id="a2247-145">例</span><span class="sxs-lookup"><span data-stu-id="a2247-145">Example</span></span>  
 <span data-ttu-id="a2247-146">次のコードでは、メソッドを上の概念モデル関数にマップする `AdventureWorksEntities` クラスに追加します。</span><span class="sxs-lookup"><span data-stu-id="a2247-146">The following code adds a method to the `AdventureWorksEntities` class that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#8)]
 [!code-vb[DP L2E Methods on ObjectContext#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="a2247-147">例</span><span class="sxs-lookup"><span data-stu-id="a2247-147">Example</span></span>  
 <span data-ttu-id="a2247-148">次のコードは、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="a2247-148">The following code calls the method.</span></span> <span data-ttu-id="a2247-149">返された <xref:System.Linq.IQueryable%601> クエリがさらに絞り込まれて、各 `SalesOrderDetail` のライン合計を返すことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a2247-149">Note that the returned <xref:System.Linq.IQueryable%601> query is further refined to return line totals for each `SalesOrderDetail`.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#9)]
 [!code-vb[DP L2E Methods on ObjectContext#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="a2247-150">例</span><span class="sxs-lookup"><span data-stu-id="a2247-150">Example</span></span>  
 <span data-ttu-id="a2247-151">**モデル定義関数をカスタム クラスの静的メソッドとして呼び出す**</span><span class="sxs-lookup"><span data-stu-id="a2247-151">**Calling a Model-Defined Function as a Static Method on a Custom Class**</span></span>  
  
 <span data-ttu-id="a2247-152">次の例で、モデル定義関数をカスタム クラスの静的メソッドとして呼び出す方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="a2247-152">The next example demonstrates how to call a model-defined function as a static method on a custom class.</span></span> <span data-ttu-id="a2247-153">この例では、 [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)します。</span><span class="sxs-lookup"><span data-stu-id="a2247-153">The example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2247-154">ユーザーが、モデル定義関数をカスタム クラスの静的メソッドとして呼び出すときには、モデル定義関数はコレクションを受け取って、コレクションの値の集計結果を返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2247-154">When you call a model-defined function as a static method on a custom class, the model-defined function must accept a collection and return an aggregation of values in the collection.</span></span>  
  
 <span data-ttu-id="a2247-155">SalesOrderDetail コレクションの製品収益を返す下の概念モデル関数について考察してください </span><span class="sxs-lookup"><span data-stu-id="a2247-155">Consider the conceptual model function below that returns product revenue for a SalesOrderDetail collection.</span></span> <span data-ttu-id="a2247-156">(概念モデルに関数を追加する方法の詳細については、次を参照してください。[方法。概念モデルでカスタム関数を定義](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100))。)。</span><span class="sxs-lookup"><span data-stu-id="a2247-156">(For information about adding the function to your conceptual model, see [How to: Define Custom Functions in the Conceptual Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd456812(v=vs.100)).).</span></span>  
  
 [!code-xml[DP L2E Methods on ObjectContext#1](../../../../../../samples/snippets/xml/VS_Snippets_Data/dp l2e methods on objectcontext/xml/adventureworks.edmx#1)]
  
## <a name="example"></a><span data-ttu-id="a2247-157">例</span><span class="sxs-lookup"><span data-stu-id="a2247-157">Example</span></span>  
 <span data-ttu-id="a2247-158">次のコードでは、上の概念モデル関数にマップする静的メソッドを持つアプリケーションにクラスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a2247-158">The following code adds a class to your application that contains a static method that maps to the conceptual model function above.</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#5)]
 [!code-vb[DP L2E Methods on ObjectContext#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/class1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="a2247-159">例</span><span class="sxs-lookup"><span data-stu-id="a2247-159">Example</span></span>  
 <span data-ttu-id="a2247-160">次のコードでは、上のメソッドを呼び出して、SalesOrderDetail コレクションの製品収益を表示します。</span><span class="sxs-lookup"><span data-stu-id="a2247-160">The following code calls the method above to display the product revenue for a SalesOrderDetail collection:</span></span>  
  
 [!code-csharp[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e methods on objectcontext/cs/program.cs#6)]
 [!code-vb[DP L2E Methods on ObjectContext#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e methods on objectcontext/vb/module1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="a2247-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2247-161">See also</span></span>

- <span data-ttu-id="a2247-162">[.edmx ファイルの概要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a2247-162">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="a2247-163">LINQ to Entities でのクエリ</span><span class="sxs-lookup"><span data-stu-id="a2247-163">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
- [<span data-ttu-id="a2247-164">LINQ to Entities クエリ内の関数の呼び出し</span><span class="sxs-lookup"><span data-stu-id="a2247-164">Calling Functions in LINQ to Entities Queries</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)
