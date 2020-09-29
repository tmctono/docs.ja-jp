---
title: リレーションシップの推論
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177567"
---
# <a name="inferring-relationships"></a><span data-ttu-id="3a1ad-102">リレーションシップの推論</span><span class="sxs-lookup"><span data-stu-id="3a1ad-102">Inferring Relationships</span></span>

<span data-ttu-id="3a1ad-103">テーブルとして推論される要素に、同じくテーブルとして推論される子の要素が含まれている場合には、2 つのテーブル間に <xref:System.Data.DataRelation> が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="3a1ad-104">この場合、**ParentTableName_Id** という名前の新しい列が、親の要素に対して作成されたテーブルと、子の要素に対して作成されたテーブルの両方に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="3a1ad-105">この ID 列の **ColumnMapping** プロパティは、**MappingType.Hidden** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="3a1ad-106">この列が、親テーブルの自動的にインクリメントされる主キーとなり、2 つのテーブル間の **DataRelation** で使用されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="3a1ad-107">推論される他のすべての列のデータ型は **System.String** になりますが、追加される ID 列のデータ型は **System.Int32** になります。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="3a1ad-108">親テーブルと子テーブル両方の新しい列を使用して、**DeleteRule** = **Cascade** である <xref:System.Data.ForeignKeyConstraint> も作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="3a1ad-109">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="3a1ad-110">推論プロセスにより 2 つのテーブルが生成されます: **Element1** と **ChildElement1**。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="3a1ad-111">**Element1** テーブルには、次の 2 つの列があります: **Element1_Id** と **ChildElement2**。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="3a1ad-112">**Element1_Id** 列の **ColumnMapping** プロパティは、**MappingType.Hidden** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="3a1ad-113">**ChildElement2** 列の **ColumnMapping** プロパティは、**MappingType.Element** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="3a1ad-114">**Element1_Id** 列は、**Element1** テーブルの主キーとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="3a1ad-115">**ChildElement1** テーブルには、**attr1**、**attr2**、**Element1_Id** という名前の 3 つの列があります。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="3a1ad-116">**attr1** 列と **attr2** 列の **ColumnMapping** プロパティは、**MappingType.Attribute** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="3a1ad-117">**Element1_Id** 列の **ColumnMapping** プロパティは、**MappingType.Hidden** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="3a1ad-118">両方のテーブルの **Element1_Id** 列を使用して、**DataRelation** と **ForeignKeyConstraint** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a1ad-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="3a1ad-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="3a1ad-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="3a1ad-120">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="3a1ad-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="3a1ad-121">Element1_Id</span></span>|<span data-ttu-id="3a1ad-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="3a1ad-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="3a1ad-123">0</span><span class="sxs-lookup"><span data-stu-id="3a1ad-123">0</span></span>|<span data-ttu-id="3a1ad-124">Text2</span><span class="sxs-lookup"><span data-stu-id="3a1ad-124">Text2</span></span>|  
  
 <span data-ttu-id="3a1ad-125">**テーブル:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="3a1ad-126">attr1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-126">attr1</span></span>|<span data-ttu-id="3a1ad-127">attr2</span><span class="sxs-lookup"><span data-stu-id="3a1ad-127">attr2</span></span>|<span data-ttu-id="3a1ad-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="3a1ad-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="3a1ad-129">value1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-129">value1</span></span>|<span data-ttu-id="3a1ad-130">value2</span><span class="sxs-lookup"><span data-stu-id="3a1ad-130">value2</span></span>|<span data-ttu-id="3a1ad-131">0</span><span class="sxs-lookup"><span data-stu-id="3a1ad-131">0</span></span>|  
  
 <span data-ttu-id="3a1ad-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="3a1ad-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="3a1ad-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="3a1ad-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="3a1ad-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="3a1ad-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="3a1ad-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="3a1ad-137">**Nested:** True</span><span class="sxs-lookup"><span data-stu-id="3a1ad-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="3a1ad-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="3a1ad-139">**Column:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="3a1ad-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="3a1ad-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="3a1ad-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="3a1ad-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="3a1ad-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="3a1ad-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="3a1ad-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="3a1ad-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a1ad-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a1ad-144">See also</span></span>

- [<span data-ttu-id="3a1ad-145">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="3a1ad-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="3a1ad-146">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="3a1ad-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="3a1ad-147">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="3a1ad-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="3a1ad-148">DataRelation の入れ子化</span><span class="sxs-lookup"><span data-stu-id="3a1ad-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="3a1ad-149">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="3a1ad-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="3a1ad-150">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="3a1ad-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="3a1ad-151">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="3a1ad-151">ADO.NET Overview</span></span>](../ado-net-overview.md)
