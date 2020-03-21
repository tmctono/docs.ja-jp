---
title: DataTable の制約
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151287"
---
# <a name="datatable-constraints"></a><span data-ttu-id="b3c89-102">DataTable の制約</span><span class="sxs-lookup"><span data-stu-id="b3c89-102">DataTable Constraints</span></span>
<span data-ttu-id="b3c89-103">制約を使用すると、データの整合性を維持するために <xref:System.Data.DataTable> のデータを強制的に制限できます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="b3c89-104">制約は、1 つの列または関連付けられた複数の列に対して自動的に適用される規則であり、行の値がなんらかの方法で変更されたときに実行されるアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="b3c89-105">制約は、 の`System.Data.DataSet.EnforceConstraints`プロパティ<xref:System.Data.DataSet>が true**の**場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="b3c89-106">`EnforceConstraints` プロパティの設定方法のコード例については、<xref:System.Data.DataSet.EnforceConstraints%2A> のリファレンス トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3c89-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="b3c89-107">ADO.NET には、<xref:System.Data.ForeignKeyConstraint> と <xref:System.Data.UniqueConstraint> の 2 種類の制約があります。</span><span class="sxs-lookup"><span data-stu-id="b3c89-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="b3c89-108">既定では<xref:System.Data.DataRelation>**、DataSet**に a を追加して、2 つ以上のテーブル間のリレーションシップを作成すると、両方の制約が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="b3c89-109">ただし、リレーションシップの作成時に**createConstraints** = **false**を指定することで、この動作を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="b3c89-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="b3c89-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="b3c89-111">**外部キー制約**は、更新と削除を関連するテーブルに伝達する方法に関する規則を適用します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="b3c89-112">たとえば、あるテーブルの行の値が更新または削除され、その同じ値が 1 つ以上の関連テーブルでも使用されている場合 **、ForeignKeyConstraint は**関連テーブルでの動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="b3c89-113">**ForeignKeyConstraint**の プロパティ<xref:System.Data.ForeignKeyConstraint.DeleteRule%2A><xref:System.Data.ForeignKeyConstraint.UpdateRule%2A>は、ユーザーが関連テーブルの行を削除または更新しようとしたときに実行されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="b3c89-114">次の表に、**外部キー制約**の**DeleteRule**プロパティと**UpdateRule**プロパティで使用できるさまざまな設定を示します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="b3c89-115">規則の設定</span><span class="sxs-lookup"><span data-stu-id="b3c89-115">Rule setting</span></span>|<span data-ttu-id="b3c89-116">説明</span><span class="sxs-lookup"><span data-stu-id="b3c89-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="b3c89-117">**カスケード**</span><span class="sxs-lookup"><span data-stu-id="b3c89-117">**Cascade**</span></span>|<span data-ttu-id="b3c89-118">関連付けられている行を削除または更新します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="b3c89-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="b3c89-119">**SetNull**</span></span>|<span data-ttu-id="b3c89-120">関連する行の値を**DBNull**に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="b3c89-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="b3c89-121">**SetDefault**</span></span>|<span data-ttu-id="b3c89-122">関連付けられている行の値を既定値に設定します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="b3c89-123">**なし**</span><span class="sxs-lookup"><span data-stu-id="b3c89-123">**None**</span></span>|<span data-ttu-id="b3c89-124">関連付けられている行に対してアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="b3c89-124">Take no action on related rows.</span></span> <span data-ttu-id="b3c89-125">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b3c89-125">This is the default.</span></span>|  
  
 <span data-ttu-id="b3c89-126">**外部キー制約**は、関連する列への変更を制限するだけでなく、反映することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="b3c89-127">列の**ForeignKeyConstraint**プロパティに設定されているプロパティに応じて **、DataSet**の**EnforceConstraints**プロパティが**true の**場合、親行に対して特定の操作を実行すると例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="b3c89-128">たとえば、**外部キー制約**の**DeleteRule**プロパティが**None**の場合、親行に子行がある場合は削除できません。</span><span class="sxs-lookup"><span data-stu-id="b3c89-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="b3c89-129">単一の列間、または列の配列間に**外部キー制約を作成するには、ForeignKeyConstraint**コンストラクターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="b3c89-130">結果として生成された**ForeignKeyConstraint**オブジェクトを、テーブルの**制約**プロパティの**Add**メソッドに渡**します**。</span><span class="sxs-lookup"><span data-stu-id="b3c89-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="b3c89-131">また、コンストラクタ引数を、外部**キー制約**を作成するために **、制約コレクション**の**Add**メソッドの複数のオーバーロードに渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="b3c89-132">**外部キー制約**を作成するときに、**引数として、コンストラクターに DeleteRule**値と**UpdateRule**値を渡すか、次の例のようにプロパティとして設定できます **(DeleteRule**値が**None**に設定されている場合)。</span><span class="sxs-lookup"><span data-stu-id="b3c89-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
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
  
### <a name="acceptrejectrule"></a><span data-ttu-id="b3c89-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="b3c89-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="b3c89-134">行への変更は **、AcceptChanges**メソッドを使用して受け入れるか、**データセット**、データセット、データ**テーブル**、または**データ行**の**RejectChanges**メソッドを使用してキャンセルできます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="b3c89-135">**データセット**に**外部キー制約**が含まれている場合 **、AcceptChanges**メソッドまたは**RejectChanges**メソッドを呼び出すと **、AcceptRejectRule**が強制的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="b3c89-136">**外部キー制約**の**AcceptRejectRule**プロパティは、親行に対して**AcceptChanges**または**RejectChanges**が呼び出されたときに、子行に対して実行されるアクションを決定します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="b3c89-137">次の表に **、AcceptRejectRule**で使用できる設定を示します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="b3c89-138">規則の設定</span><span class="sxs-lookup"><span data-stu-id="b3c89-138">Rule setting</span></span>|<span data-ttu-id="b3c89-139">説明</span><span class="sxs-lookup"><span data-stu-id="b3c89-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="b3c89-140">**カスケード**</span><span class="sxs-lookup"><span data-stu-id="b3c89-140">**Cascade**</span></span>|<span data-ttu-id="b3c89-141">子の行への変更を受け入れるかまたは拒否します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="b3c89-142">**なし**</span><span class="sxs-lookup"><span data-stu-id="b3c89-142">**None**</span></span>|<span data-ttu-id="b3c89-143">子の行に対してアクションは実行しません。</span><span class="sxs-lookup"><span data-stu-id="b3c89-143">Take no action on child rows.</span></span> <span data-ttu-id="b3c89-144">これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b3c89-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="b3c89-145">例</span><span class="sxs-lookup"><span data-stu-id="b3c89-145">Example</span></span>  
 <span data-ttu-id="b3c89-146">次の例では、<xref:System.Data.ForeignKeyConstraint> を作成し、<xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A> を含む複数のプロパティを設定して、<xref:System.Data.ConstraintCollection> オブジェクトの <xref:System.Data.DataTable> に追加します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="b3c89-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="b3c89-147">UniqueConstraint</span></span>  
 <span data-ttu-id="b3c89-148">1 つの列または**DataTable**内の列の配列に割り当てることができる**UniqueConstraint**オブジェクトは、指定した列または列のすべてのデータが行ごとに一意であることを保証します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="b3c89-149">UNIQUEConstraint コンストラクターを使用して、列または列の配列に対して**一意の**制約を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="b3c89-150">結果の**一意制約**オブジェクトを、テーブルの**制約**プロパティの**Add**メソッドに渡**します**。</span><span class="sxs-lookup"><span data-stu-id="b3c89-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="b3c89-151">また、コンストラクタ引数を **、制約コレクション**の**Add**メソッドの複数のオーバーロードに渡して **、UniqueConstraint**を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="b3c89-152">列に**対して一意性制約**を作成する場合、列が主キーであるかどうかをオプションで指定できます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="b3c89-153">列の Unique プロパティを**true**に設定して、列に**対する一意**の制約を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="b3c89-154">または、単一列の**Unique**プロパティを**false**に設定すると、存在する可能性のある UNIQUE 制約が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="b3c89-155">1 つの列 (または複数の列) をテーブルの主キーとして定義すると、指定した列 (または複数の列) の UNIQUE 制約が自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="b3c89-156">**列をデータ テーブル**の**主キー**プロパティから削除すると、**一意制約**が削除されます。</span><span class="sxs-lookup"><span data-stu-id="b3c89-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="b3c89-157">次の例では **、DataTable**の 2 つの列に対して**一意の制約**を作成します。</span><span class="sxs-lookup"><span data-stu-id="b3c89-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b3c89-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="b3c89-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="b3c89-159">DataTable スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="b3c89-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="b3c89-160">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="b3c89-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b3c89-161">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="b3c89-161">ADO.NET Overview</span></span>](../ado-net-overview.md)
