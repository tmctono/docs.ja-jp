---
title: リレーションシップの推論
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 4c9c13453e4a830fcda337e8163649ba6491a995
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785365"
---
# <a name="inferring-relationships"></a><span data-ttu-id="25840-102">リレーションシップの推論</span><span class="sxs-lookup"><span data-stu-id="25840-102">Inferring Relationships</span></span>
<span data-ttu-id="25840-103">テーブルとして推論される要素に、同じくテーブルとして推論される子の要素が含まれている場合には、2 つのテーブル間に <xref:System.Data.DataRelation> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="25840-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="25840-104">**ParentTableName_Id**という名前の新しい列が、親要素用に作成されたテーブルと、子要素に対して作成されたテーブルの両方に追加されます。</span><span class="sxs-lookup"><span data-stu-id="25840-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="25840-105">この id 列の**ColumnMapping**プロパティは、 **Mappingtype. Hidden**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="25840-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="25840-106">この列は、親テーブルの自動インクリメント主キーになり、2つのテーブル間の**DataRelation**に使用されます。</span><span class="sxs-lookup"><span data-stu-id="25840-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="25840-107">追加された id 列のデータ型は、他のすべての推定列 ( **system.string**) のデータ型とは異なり、system.string に**なります。**</span><span class="sxs-lookup"><span data-stu-id="25840-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="25840-108">**DeleteRule** <xref:System.Data.ForeignKeyConstraint> Cascade = を指定したは、親テーブルと子テーブルの両方で新しい列を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="25840-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="25840-109">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="25840-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="25840-110">推論プロセスでは、次の2つのテーブルが生成されます。**Element1**と**ChildElement1**。</span><span class="sxs-lookup"><span data-stu-id="25840-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="25840-111">**Element1**テーブルには、次の2つの列があります。**Element1_Id**と**ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="25840-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="25840-112">**Element1_Id**列の**ColumnMapping**プロパティは、 **mappingtype. Hidden**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="25840-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="25840-113">**ChildElement2**列の**ColumnMapping**プロパティは、 **mappingtype. Element**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="25840-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="25840-114">**Element1_Id**列は、 **Element1**テーブルの主キーとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="25840-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="25840-115">**ChildElement1**テーブルには、 **attr1**、 **attr2** 、 **Element1_Id**の3つの列があります。</span><span class="sxs-lookup"><span data-stu-id="25840-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="25840-116">**Attr1**列と**Attr2**列の**ColumnMapping**プロパティは、 **mappingtype. Attribute**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="25840-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="25840-117">**Element1_Id**列の**ColumnMapping**プロパティは、 **mappingtype. Hidden**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="25840-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="25840-118">両方のテーブルの**Element1_Id**列を使用して、 **DataRelation**と**ForeignKeyConstraint**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="25840-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="25840-119">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="25840-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="25840-120">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="25840-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="25840-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25840-121">Element1_Id</span></span>|<span data-ttu-id="25840-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="25840-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="25840-123">0</span><span class="sxs-lookup"><span data-stu-id="25840-123">0</span></span>|<span data-ttu-id="25840-124">Text2</span><span class="sxs-lookup"><span data-stu-id="25840-124">Text2</span></span>|  
  
 <span data-ttu-id="25840-125">**一覧**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25840-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="25840-126">attr1</span><span class="sxs-lookup"><span data-stu-id="25840-126">attr1</span></span>|<span data-ttu-id="25840-127">attr2</span><span class="sxs-lookup"><span data-stu-id="25840-127">attr2</span></span>|<span data-ttu-id="25840-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25840-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="25840-129">value1</span><span class="sxs-lookup"><span data-stu-id="25840-129">value1</span></span>|<span data-ttu-id="25840-130">value2</span><span class="sxs-lookup"><span data-stu-id="25840-130">value2</span></span>|<span data-ttu-id="25840-131">0</span><span class="sxs-lookup"><span data-stu-id="25840-131">0</span></span>|  
  
 <span data-ttu-id="25840-132">**DataRelation**Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25840-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="25840-133">**Parentcolumn**Element1</span><span class="sxs-lookup"><span data-stu-id="25840-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="25840-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25840-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="25840-135">**ChildTable**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25840-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="25840-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25840-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="25840-137">**複合**True</span><span class="sxs-lookup"><span data-stu-id="25840-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="25840-138">**ForeignKeyConstraint**Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25840-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="25840-139">**項目**Element1_Id</span><span class="sxs-lookup"><span data-stu-id="25840-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="25840-140">**Parentcolumn**Element1</span><span class="sxs-lookup"><span data-stu-id="25840-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="25840-141">**ChildTable**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="25840-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="25840-142">**DeleteRule**Cascade</span><span class="sxs-lookup"><span data-stu-id="25840-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="25840-143">**AcceptRejectRule**なし</span><span class="sxs-lookup"><span data-stu-id="25840-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25840-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="25840-144">See also</span></span>

- [<span data-ttu-id="25840-145">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="25840-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="25840-146">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="25840-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="25840-147">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="25840-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="25840-148">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="25840-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="25840-149">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="25840-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="25840-150">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="25840-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="25840-151">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="25840-151">ADO.NET Overview</span></span>](../ado-net-overview.md)
