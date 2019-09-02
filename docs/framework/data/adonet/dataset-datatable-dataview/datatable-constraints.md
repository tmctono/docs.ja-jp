---
title: DataTable の制約
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 68b99e834428261d59c5fb27277b24eb0f6e77e4
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205056"
---
# <a name="datatable-constraints"></a><span data-ttu-id="66e63-102">DataTable の制約</span><span class="sxs-lookup"><span data-stu-id="66e63-102">DataTable Constraints</span></span>
<span data-ttu-id="66e63-103">制約を使用すると、データの整合性を維持するために <xref:System.Data.DataTable> のデータを強制的に制限できます。</span><span class="sxs-lookup"><span data-stu-id="66e63-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="66e63-104">制約は、1 つの列または関連付けられた複数の列に対して自動的に適用される規則であり、行の値がなんらかの方法で変更されたときに実行されるアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="66e63-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="66e63-105">のプロパティ`System.Data.DataSet.EnforceConstraints`がtrueの場合、制約が適用されます。 <xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="66e63-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="66e63-106">`EnforceConstraints` プロパティの設定方法のコード例については、<xref:System.Data.DataSet.EnforceConstraints%2A> のリファレンス トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66e63-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="66e63-107">ADO.NET には、<xref:System.Data.ForeignKeyConstraint> と <xref:System.Data.UniqueConstraint> の 2 種類の制約があります。</span><span class="sxs-lookup"><span data-stu-id="66e63-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="66e63-108">既定では、2つ以上のテーブル間のリレーションシップを作成するときに、**データセット**に<xref:System.Data.DataRelation>を追加することによって、両方の制約が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="66e63-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="66e63-109">ただし、リレーションシップの作成時に**createConstraints** = **false**を指定することで、この動作を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="66e63-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="66e63-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="66e63-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="66e63-111">**ForeignKeyConstraint**は、関連テーブルの更新と削除がどのように反映されるかに関する規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="66e63-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="66e63-112">たとえば、1つのテーブルの行の値が更新または削除され、その同じ値が1つ以上の関連テーブルでも使用されている場合、 **ForeignKeyConstraint**は関連テーブルでの処理を決定します。</span><span class="sxs-lookup"><span data-stu-id="66e63-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="66e63-113">ForeignKeyConstraint <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A>の<xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>プロパティとプロパティは、ユーザーが関連テーブル内の行を削除または更新しようとしたときに実行されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="66e63-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="66e63-114">次の表では、 **ForeignKeyConstraint**の**DeleteRule**プロパティと**UpdateRule**プロパティで使用できるさまざまな設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="66e63-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="66e63-115">規則の設定</span><span class="sxs-lookup"><span data-stu-id="66e63-115">Rule setting</span></span>|<span data-ttu-id="66e63-116">説明</span><span class="sxs-lookup"><span data-stu-id="66e63-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="66e63-117">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="66e63-117">**Cascade**</span></span>|<span data-ttu-id="66e63-118">関連付けられている行を削除または更新します。</span><span class="sxs-lookup"><span data-stu-id="66e63-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="66e63-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="66e63-119">**SetNull**</span></span>|<span data-ttu-id="66e63-120">関連する行の値を**DBNull**に設定します。</span><span class="sxs-lookup"><span data-stu-id="66e63-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="66e63-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="66e63-121">**SetDefault**</span></span>|<span data-ttu-id="66e63-122">関連付けられている行の値を既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="66e63-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="66e63-123">**None**</span><span class="sxs-lookup"><span data-stu-id="66e63-123">**None**</span></span>|<span data-ttu-id="66e63-124">関連付けられている行に対してアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="66e63-124">Take no action on related rows.</span></span> <span data-ttu-id="66e63-125">既定値です。</span><span class="sxs-lookup"><span data-stu-id="66e63-125">This is the default.</span></span>|  
  
 <span data-ttu-id="66e63-126">**ForeignKeyConstraint**を使用すると、関連する列に対する変更を制限および反映することができます。</span><span class="sxs-lookup"><span data-stu-id="66e63-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="66e63-127">列の**ForeignKeyConstraint**に設定されているプロパティによっては、**データセット**の**EnforceConstraints**プロパティが**true**の場合、親行に対して特定の操作を実行すると例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="66e63-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="66e63-128">たとえば、 **ForeignKeyConstraint**の**DeleteRule**プロパティが**None**の場合、子行がある場合、親行を削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="66e63-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="66e63-129">**ForeignKeyConstraint**コンストラクターを使用して、単一の列間または列の配列間の foreign key 制約を作成できます。</span><span class="sxs-lookup"><span data-stu-id="66e63-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="66e63-130">結果の**ForeignKeyConstraint**オブジェクトをテーブルの**Constraints**プロパティの**Add**メソッド ( **ConstraintCollection**) に渡します。</span><span class="sxs-lookup"><span data-stu-id="66e63-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="66e63-131">また、 **ConstraintCollection**の**Add**メソッドのいくつかのオーバーロードにコンストラクター引数を渡して、 **ForeignKeyConstraint**を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="66e63-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="66e63-132">**ForeignKeyConstraint**を作成するときに、 **DeleteRule**と**UpdateRule**の値を引数としてコンストラクターに渡すか、次の例のようにプロパティとして設定できます ( **DeleteRule**の値がに**設定されている場合)。なし**)。</span><span class="sxs-lookup"><span data-stu-id="66e63-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
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
  
### <a name="acceptrejectrule"></a><span data-ttu-id="66e63-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="66e63-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="66e63-134">行への変更は、 **AcceptChanges**メソッドを使用して受け入れるか、 **DataSet**、 **DataTable**、または**DataRow**の**RejectChanges**メソッドを使用して取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="66e63-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="66e63-135">**データセット**に**ForeignKeyConstraints**が含まれている場合、 **AcceptChanges**メソッドまたは**RejectChanges**メソッドを呼び出すと、 **AcceptRejectRule**が適用されます。</span><span class="sxs-lookup"><span data-stu-id="66e63-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="66e63-136">**ForeignKeyConstraint**の**AcceptRejectRule**プロパティは、親行で**AcceptChanges**または**RejectChanges**が呼び出されたときに、子の行に対して実行されるアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="66e63-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="66e63-137">次の表に、 **AcceptRejectRule**で使用可能な設定の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="66e63-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="66e63-138">規則の設定</span><span class="sxs-lookup"><span data-stu-id="66e63-138">Rule setting</span></span>|<span data-ttu-id="66e63-139">説明</span><span class="sxs-lookup"><span data-stu-id="66e63-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="66e63-140">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="66e63-140">**Cascade**</span></span>|<span data-ttu-id="66e63-141">子の行への変更を受け入れるかまたは拒否します。</span><span class="sxs-lookup"><span data-stu-id="66e63-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="66e63-142">**None**</span><span class="sxs-lookup"><span data-stu-id="66e63-142">**None**</span></span>|<span data-ttu-id="66e63-143">子の行に対してアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="66e63-143">Take no action on child rows.</span></span> <span data-ttu-id="66e63-144">既定値です。</span><span class="sxs-lookup"><span data-stu-id="66e63-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="66e63-145">例</span><span class="sxs-lookup"><span data-stu-id="66e63-145">Example</span></span>  
 <span data-ttu-id="66e63-146">次の例では、<xref:System.Data.ForeignKeyConstraint> を作成し、<xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A> を含む複数のプロパティを設定して、<xref:System.Data.ConstraintCollection> オブジェクトの <xref:System.Data.DataTable> に追加します。</span><span class="sxs-lookup"><span data-stu-id="66e63-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="66e63-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="66e63-147">UniqueConstraint</span></span>  
 <span data-ttu-id="66e63-148">**UniqueConstraint**オブジェクトは、単一の列または**DataTable**内の列の配列に割り当てることができます。これにより、指定された1つまたは複数の列のすべてのデータが行ごとに一意になります。</span><span class="sxs-lookup"><span data-stu-id="66e63-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="66e63-149">**UniqueConstraint**コンストラクターを使用して、列または列の配列に unique 制約を作成できます。</span><span class="sxs-lookup"><span data-stu-id="66e63-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="66e63-150">結果の**UniqueConstraint**オブジェクトをテーブルの**Constraints**プロパティの**Add**メソッド ( **ConstraintCollection**) に渡します。</span><span class="sxs-lookup"><span data-stu-id="66e63-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="66e63-151">また、 **ConstraintCollection**の**Add**メソッドのいくつかのオーバーロードにコンストラクター引数を渡して、 **UniqueConstraint**を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="66e63-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="66e63-152">1つまたは複数の列に対して**UniqueConstraint**を作成する場合は、必要に応じて、列または列が主キーであるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="66e63-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="66e63-153">列の**unique**プロパティを**true**に設定することによって、列に unique 制約を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="66e63-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="66e63-154">または、1つの列の**unique**プロパティを**false**に設定すると、存在する可能性がある一意の制約が削除されます。</span><span class="sxs-lookup"><span data-stu-id="66e63-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="66e63-155">1 つの列 (または複数の列) をテーブルの主キーとして定義すると、指定した列 (または複数の列) の UNIQUE 制約が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="66e63-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="66e63-156">**DataTable**の**PrimaryKey**プロパティから列を削除すると、 **UniqueConstraint**が削除されます。</span><span class="sxs-lookup"><span data-stu-id="66e63-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="66e63-157">次の例では、 **DataTable**の2つの列に対して**UniqueConstraint**を作成します。</span><span class="sxs-lookup"><span data-stu-id="66e63-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66e63-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="66e63-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="66e63-159">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="66e63-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="66e63-160">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="66e63-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="66e63-161">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="66e63-161">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
