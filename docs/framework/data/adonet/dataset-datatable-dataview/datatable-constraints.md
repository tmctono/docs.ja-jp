---
title: DataTable の制約
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 1224518a9a16f48f770b6839317b9787da97377b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153275"
---
# <a name="datatable-constraints"></a><span data-ttu-id="485b6-102">DataTable の制約</span><span class="sxs-lookup"><span data-stu-id="485b6-102">DataTable Constraints</span></span>

<span data-ttu-id="485b6-103">制約を使用すると、データの整合性を維持するために <xref:System.Data.DataTable> のデータを強制的に制限できます。</span><span class="sxs-lookup"><span data-stu-id="485b6-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="485b6-104">制約は、1 つの列または関連付けられた複数の列に対して自動的に適用される規則であり、行の値がなんらかの方法で変更されたときに実行されるアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="485b6-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="485b6-105">制約は、<xref:System.Data.DataSet> の `System.Data.DataSet.EnforceConstraints` プロパティを **true** に設定したときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="485b6-106">`EnforceConstraints` プロパティの設定方法のコード例については、<xref:System.Data.DataSet.EnforceConstraints%2A> のリファレンス トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="485b6-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="485b6-107">ADO.NET には、<xref:System.Data.ForeignKeyConstraint> と <xref:System.Data.UniqueConstraint> の 2 種類の制約があります。</span><span class="sxs-lookup"><span data-stu-id="485b6-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="485b6-108">既定では、<xref:System.Data.DataRelation> を **DataSet** に追加して複数のテーブル間のリレーションシップを作成すると、この 2 種類の制約が両方とも自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="485b6-109">ただし、リレーションの作成時に **createConstraints** = **false** と指定することにより、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="485b6-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="485b6-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="485b6-110">ForeignKeyConstraint</span></span>  

 <span data-ttu-id="485b6-111">**ForeignKeyConstraint** では、関連付けられているテーブルに更新や削除を反映させる方法についての規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="485b6-112">たとえば、あるテーブルの行の値が更新または削除され、その同じ値が、関連付けられている別のテーブルでも使用されている場合、関連付けられているテーブル内で実行されるアクションは **ForeignKeyConstraint** によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="485b6-113">**ForeignKeyConstraint** の <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> プロパティおよび <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> プロパティでは、ユーザーが関連付けられているテーブルの行を削除または更新しようとしたときに実行されるアクションが定義されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="485b6-114">**ForeignKeyConstraint** の **DeleteRule** プロパティおよび **UpdateRule** プロパティに使用できるさまざまな設定の説明を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="485b6-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="485b6-115">規則の設定</span><span class="sxs-lookup"><span data-stu-id="485b6-115">Rule setting</span></span>|<span data-ttu-id="485b6-116">説明</span><span class="sxs-lookup"><span data-stu-id="485b6-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="485b6-117">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="485b6-117">**Cascade**</span></span>|<span data-ttu-id="485b6-118">関連付けられている行を削除または更新します。</span><span class="sxs-lookup"><span data-stu-id="485b6-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="485b6-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="485b6-119">**SetNull**</span></span>|<span data-ttu-id="485b6-120">関連付けられている行の値を **DBNull** に設定します。</span><span class="sxs-lookup"><span data-stu-id="485b6-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="485b6-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="485b6-121">**SetDefault**</span></span>|<span data-ttu-id="485b6-122">関連付けられている行の値を既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="485b6-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="485b6-123">**None**</span><span class="sxs-lookup"><span data-stu-id="485b6-123">**None**</span></span>|<span data-ttu-id="485b6-124">関連付けられている行に対してアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="485b6-124">Take no action on related rows.</span></span> <span data-ttu-id="485b6-125">既定値です。</span><span class="sxs-lookup"><span data-stu-id="485b6-125">This is the default.</span></span>|  
  
 <span data-ttu-id="485b6-126">**ForeignKeyConstraint** は、関連付けられている行への変更を制限したり、反映させたりできます。</span><span class="sxs-lookup"><span data-stu-id="485b6-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="485b6-127">列の **ForeignKeyConstraint** に対して設定されたプロパティによっては、**DataSet** の **EnforceConstraints** プロパティが **true** である場合に親の行に対して操作を実行すると、例外が発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="485b6-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="485b6-128">たとえば、**ForeignKeyConstraint** の **DeleteRule** プロパティが **None** の場合、子の行を持っている親の行は削除できません。</span><span class="sxs-lookup"><span data-stu-id="485b6-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="485b6-129">**ForeignKeyConstraint** コンストラクターを使用すると、単一列間または列配列間の外部キー制約を作成できます。</span><span class="sxs-lookup"><span data-stu-id="485b6-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="485b6-130">**ConstraintCollection** の 1 つである、テーブルの **Constraints** プロパティの **Add** メソッドに結果の **ForeignKeyConstraint** オブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="485b6-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="485b6-131">コンストラクター引数を **ConstraintCollection** の **Add** メソッドのいくつかのオーバーロードに渡すことにより、**ForeignKeyConstraint** を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="485b6-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="485b6-132">**ForeignKeyConstraint** を作成するときに、**DeleteRule** の値と **UpdateRule** の値を引数としてコンストラクターに渡したり、それらの値を次の例に示すようにプロパティとして設定したりできます。この例では、**DeleteRule** の値が **None** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="485b6-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="485b6-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="485b6-133">AcceptRejectRule</span></span>  

 <span data-ttu-id="485b6-134">行への変更は、**AcceptChanges** メソッドを使用して受け入れることができ、**DataSet**、**DataTable**、または **DataRow** の **RejectChanges** メソッドを使用してキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="485b6-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="485b6-135">**DataSet** に **ForeignKeyConstraints** が含まれている場合は、**AcceptChanges** メソッドまたは **RejectChanges** メソッドを呼び出すと、**AcceptRejectRule** が強制適用されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="485b6-136">**ForeignKeyConstraint** の **AcceptRejectRule** プロパティは、親の行に対して **AcceptChanges** または **RejectChanges** が呼び出されたときに、子の行に対して実行されるアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="485b6-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="485b6-137">**AcceptRejectRule** に使用できる設定の一覧を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="485b6-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="485b6-138">規則の設定</span><span class="sxs-lookup"><span data-stu-id="485b6-138">Rule setting</span></span>|<span data-ttu-id="485b6-139">説明</span><span class="sxs-lookup"><span data-stu-id="485b6-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="485b6-140">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="485b6-140">**Cascade**</span></span>|<span data-ttu-id="485b6-141">子の行への変更を受け入れるかまたは拒否します。</span><span class="sxs-lookup"><span data-stu-id="485b6-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="485b6-142">**None**</span><span class="sxs-lookup"><span data-stu-id="485b6-142">**None**</span></span>|<span data-ttu-id="485b6-143">子の行に対してアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="485b6-143">Take no action on child rows.</span></span> <span data-ttu-id="485b6-144">既定値です。</span><span class="sxs-lookup"><span data-stu-id="485b6-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="485b6-145">例</span><span class="sxs-lookup"><span data-stu-id="485b6-145">Example</span></span>  

 <span data-ttu-id="485b6-146">次の例では、<xref:System.Data.ForeignKeyConstraint> を作成し、<xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A> を含む複数のプロパティを設定して、<xref:System.Data.ConstraintCollection> オブジェクトの <xref:System.Data.DataTable> に追加します。</span><span class="sxs-lookup"><span data-stu-id="485b6-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="485b6-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="485b6-147">UniqueConstraint</span></span>  

 <span data-ttu-id="485b6-148">**UniqueConstraint** オブジェクトは、**DataTable** 内の 1 つの列または列の配列に対して割り当てることができ、指定された列内のすべてのデータが行ごとに一意になるようにします。</span><span class="sxs-lookup"><span data-stu-id="485b6-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="485b6-149">**UniqueConstraint** コンストラクターを使用して、1 つの列または列の配列に対する UNIQUE 制約を作成できます。</span><span class="sxs-lookup"><span data-stu-id="485b6-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="485b6-150">**ConstraintCollection** の 1 つである、テーブルの **Constraints** プロパティの **Add** メソッドに結果の **UniqueConstraint** オブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="485b6-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="485b6-151">コンストラクター引数を **ConstraintCollection** の **Add** メソッドのいくつかのオーバーロードに渡すことにより、**UniqueConstraint** を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="485b6-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="485b6-152">1 つの列または複数の列に対して **UniqueConstraint** を作成するときは、オプションで、その列または複数の列を主キーにするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="485b6-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="485b6-153">列の **Unique** プロパティを **true** に設定することにより、1 つの列に対する一意制約を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="485b6-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="485b6-154">また、1 つの列の **Unique** プロパティを **false** に設定することにより、既存の一意制約を削除できます。</span><span class="sxs-lookup"><span data-stu-id="485b6-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="485b6-155">1 つの列 (または複数の列) をテーブルの主キーとして定義すると、指定した列 (または複数の列) の UNIQUE 制約が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="485b6-156">**DataTable** の **PrimaryKey** プロパティから列を削除すると、**UniqueConstraint** が削除されます。</span><span class="sxs-lookup"><span data-stu-id="485b6-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="485b6-157">**DataTable** の 2 つの列の **UniqueConstraint** を作成する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="485b6-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="485b6-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="485b6-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="485b6-159">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="485b6-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="485b6-160">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="485b6-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="485b6-161">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="485b6-161">ADO.NET Overview</span></span>](../ado-net-overview.md)
