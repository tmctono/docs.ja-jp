---
title: リレーションシップの推論
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 92a4953dc7f5119ffbf171ff2a7bf5b58e896638
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204772"
---
# <a name="inferring-relationships"></a><span data-ttu-id="6f39e-102">リレーションシップの推論</span><span class="sxs-lookup"><span data-stu-id="6f39e-102">Inferring Relationships</span></span>
<span data-ttu-id="6f39e-103">テーブルとして推論される要素に、同じくテーブルとして推論される子の要素が含まれている場合には、2 つのテーブル間に <xref:System.Data.DataRelation> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="6f39e-104">**ParentTableName_Id**という名前の新しい列が、親要素用に作成されたテーブルと、子要素に対して作成されたテーブルの両方に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="6f39e-105">この id 列の**ColumnMapping**プロパティは、 **Mappingtype. Hidden**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="6f39e-106">この列は、親テーブルの自動インクリメント主キーになり、2つのテーブル間の**DataRelation**に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="6f39e-107">追加された id 列のデータ型は、他のすべての推定列 (system.string) のデータ型とは異なり、 **system.string**になります。</span><span class="sxs-lookup"><span data-stu-id="6f39e-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="6f39e-108">**DeleteRule** <xref:System.Data.ForeignKeyConstraint> Cascade = を指定したは、親テーブルと子テーブルの両方で新しい列を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="6f39e-109">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="6f39e-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="6f39e-110">推論プロセスでは、次の2つのテーブルが生成されます。**Element1**と**ChildElement1**。</span><span class="sxs-lookup"><span data-stu-id="6f39e-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="6f39e-111">**Element1**テーブルには、次の2つの列があります。**Element1_Id**と**ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="6f39e-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="6f39e-112">**Element1_Id**列の**ColumnMapping**プロパティは、 **mappingtype. Hidden**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="6f39e-113">**ChildElement2**列の**ColumnMapping**プロパティは、 **mappingtype. Element**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="6f39e-114">**Element1_Id**列は、 **Element1**テーブルの主キーとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="6f39e-115">**ChildElement1**テーブルには、 **attr1**、 **attr2** 、 **Element1_Id**の3つの列があります。</span><span class="sxs-lookup"><span data-stu-id="6f39e-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="6f39e-116">**Attr1**列と**Attr2**列の**ColumnMapping**プロパティは、 **mappingtype. Attribute**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="6f39e-117">**Element1_Id**列の**ColumnMapping**プロパティは、 **mappingtype. Hidden**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="6f39e-118">両方のテーブルの**Element1_Id**列を使用して、 **DataRelation**と**ForeignKeyConstraint**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6f39e-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="6f39e-119">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="6f39e-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="6f39e-120">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="6f39e-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="6f39e-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="6f39e-121">Element1_Id</span></span>|<span data-ttu-id="6f39e-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="6f39e-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="6f39e-123">0</span><span class="sxs-lookup"><span data-stu-id="6f39e-123">0</span></span>|<span data-ttu-id="6f39e-124">Text2</span><span class="sxs-lookup"><span data-stu-id="6f39e-124">Text2</span></span>|  
  
 <span data-ttu-id="6f39e-125">**一覧**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="6f39e-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="6f39e-126">attr1</span><span class="sxs-lookup"><span data-stu-id="6f39e-126">attr1</span></span>|<span data-ttu-id="6f39e-127">attr2</span><span class="sxs-lookup"><span data-stu-id="6f39e-127">attr2</span></span>|<span data-ttu-id="6f39e-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="6f39e-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="6f39e-129">value1</span><span class="sxs-lookup"><span data-stu-id="6f39e-129">value1</span></span>|<span data-ttu-id="6f39e-130">value2</span><span class="sxs-lookup"><span data-stu-id="6f39e-130">value2</span></span>|<span data-ttu-id="6f39e-131">0</span><span class="sxs-lookup"><span data-stu-id="6f39e-131">0</span></span>|  
  
 <span data-ttu-id="6f39e-132">**DataRelation**Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="6f39e-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="6f39e-133">**Parentcolumn**Element1</span><span class="sxs-lookup"><span data-stu-id="6f39e-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="6f39e-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="6f39e-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="6f39e-135">**ChildTable**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="6f39e-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="6f39e-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="6f39e-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="6f39e-137">**複合**True</span><span class="sxs-lookup"><span data-stu-id="6f39e-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="6f39e-138">**ForeignKeyConstraint**Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="6f39e-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="6f39e-139">**項目**Element1_Id</span><span class="sxs-lookup"><span data-stu-id="6f39e-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="6f39e-140">**Parentcolumn**Element1</span><span class="sxs-lookup"><span data-stu-id="6f39e-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="6f39e-141">**ChildTable**ChildElement1</span><span class="sxs-lookup"><span data-stu-id="6f39e-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="6f39e-142">**DeleteRule**Cascade</span><span class="sxs-lookup"><span data-stu-id="6f39e-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="6f39e-143">**AcceptRejectRule**なし</span><span class="sxs-lookup"><span data-stu-id="6f39e-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f39e-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="6f39e-144">See also</span></span>

- [<span data-ttu-id="6f39e-145">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="6f39e-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="6f39e-146">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="6f39e-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="6f39e-147">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="6f39e-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="6f39e-148">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="6f39e-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="6f39e-149">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="6f39e-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="6f39e-150">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="6f39e-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="6f39e-151">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="6f39e-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
