---
title: 列の推論
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 45d27b78b5d83d333c16192e172e7b7e3dd88c10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164702"
---
# <a name="inferring-columns"></a><span data-ttu-id="3a8cb-102">列の推論</span><span class="sxs-lookup"><span data-stu-id="3a8cb-102">Inferring Columns</span></span>

<span data-ttu-id="3a8cb-103">ADO.NET は、<xref:System.Data.DataSet> のテーブルとして推論する要素を、XML ドキュメントから決定した後、それらのテーブルの列を推論します。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="3a8cb-104">ADO.NET 2.0 では、各 **simpleType** 要素の厳密に型指定されたデータ型を推論する新しいスキーマ推論エンジンが導入されました。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="3a8cb-105">以前のバージョンでは、推論される **simpleType** 要素のデータ型は、常に **xsd:string** でした。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="3a8cb-106">移行および下位互換性</span><span class="sxs-lookup"><span data-stu-id="3a8cb-106">Migration and Backward Compatibility</span></span>  

 <span data-ttu-id="3a8cb-107">**ReadXml** メソッドは、**InferSchema** 型の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="3a8cb-108">この引数を使用することにより、以前のバージョンと互換性のある推論方法を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="3a8cb-109">**InferSchema** 列挙型で使用できる値を、次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="3a8cb-110">単純型を <xref:System.String> として常に推論することで下位互換性を提供します。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="3a8cb-111">厳密に型指定されたデータ型を推論します。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="3a8cb-112"><xref:System.Data.DataTable> で使用した場合、例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="3a8cb-113">インライン スキーマを無視し、データを既存の <xref:System.Data.DataSet> スキーマに読み取ります。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="3a8cb-114">属性</span><span class="sxs-lookup"><span data-stu-id="3a8cb-114">Attributes</span></span>  

 <span data-ttu-id="3a8cb-115">「[テーブルの推論](inferring-tables.md)」で説明されているように、属性を持つ要素は、テーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="3a8cb-116">その要素の属性は、そのテーブルの列として推論されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="3a8cb-117">スキーマが XML に書き戻される場合に、列の名前が確実に属性として書き込まれるように、推論された列の **ColumnMapping** プロパティは **MappingType.Attribute** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="3a8cb-118">属性の値は、テーブルの行に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="3a8cb-119">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="3a8cb-120">推論プロセスにより、**attr1** および **attr2** という 2 つの列を持つ **Element1** という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="3a8cb-121">2 つの列の **ColumnMapping** プロパティは、**MappingType.Attribute** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="3a8cb-122">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="3a8cb-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="3a8cb-123">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="3a8cb-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="3a8cb-124">attr1</span><span class="sxs-lookup"><span data-stu-id="3a8cb-124">attr1</span></span>|<span data-ttu-id="3a8cb-125">attr2</span><span class="sxs-lookup"><span data-stu-id="3a8cb-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="3a8cb-126">value1</span><span class="sxs-lookup"><span data-stu-id="3a8cb-126">value1</span></span>|<span data-ttu-id="3a8cb-127">value2</span><span class="sxs-lookup"><span data-stu-id="3a8cb-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="3a8cb-128">属性または子の要素を持たない要素</span><span class="sxs-lookup"><span data-stu-id="3a8cb-128">Elements Without Attributes or Child Elements</span></span>  

 <span data-ttu-id="3a8cb-129">要素に子の要素または属性がない場合、その要素は列として推論されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="3a8cb-130">列の **ColumnMapping** プロパティは、**MappingType.Element** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="3a8cb-131">子の要素のテキストは、テーブルの行に格納されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="3a8cb-132">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="3a8cb-133">推論プロセスにより、**ChildElement1** および **ChildElement2** という 2 つの列を持つ **Element1** という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="3a8cb-134">2 つの列の **ColumnMapping** プロパティは、**MappingType.Element** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3a8cb-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="3a8cb-135">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="3a8cb-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="3a8cb-136">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="3a8cb-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="3a8cb-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="3a8cb-137">ChildElement1</span></span>|<span data-ttu-id="3a8cb-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="3a8cb-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="3a8cb-139">Text1</span><span class="sxs-lookup"><span data-stu-id="3a8cb-139">Text1</span></span>|<span data-ttu-id="3a8cb-140">Text2</span><span class="sxs-lookup"><span data-stu-id="3a8cb-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a8cb-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a8cb-141">See also</span></span>

- [<span data-ttu-id="3a8cb-142">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="3a8cb-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="3a8cb-143">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="3a8cb-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="3a8cb-144">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="3a8cb-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="3a8cb-145">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="3a8cb-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="3a8cb-146">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="3a8cb-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="3a8cb-147">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="3a8cb-147">ADO.NET Overview</span></span>](../ado-net-overview.md)
