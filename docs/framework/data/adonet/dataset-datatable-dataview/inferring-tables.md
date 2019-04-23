---
title: テーブルの推論
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 2c2a93d413f301dc3006b701e4bc7979a3fa7a1d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181832"
---
# <a name="inferring-tables"></a><span data-ttu-id="76010-102">テーブルの推論</span><span class="sxs-lookup"><span data-stu-id="76010-102">Inferring Tables</span></span>
<span data-ttu-id="76010-103">XML ドキュメントから <xref:System.Data.DataSet> のスキーマを推論するときには、ADO.NET では、テーブルを表す XML 要素を最初に決定します。</span><span class="sxs-lookup"><span data-stu-id="76010-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="76010-104">次の XML 構造の結果のテーブルに、**データセット**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="76010-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="76010-105">属性を持つ要素</span><span class="sxs-lookup"><span data-stu-id="76010-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="76010-106">子要素を持つ要素</span><span class="sxs-lookup"><span data-stu-id="76010-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="76010-107">繰り返し出現する要素</span><span class="sxs-lookup"><span data-stu-id="76010-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="76010-108">属性を持つ要素</span><span class="sxs-lookup"><span data-stu-id="76010-108">Elements with Attributes</span></span>  
 <span data-ttu-id="76010-109">要素に属性が指定されている場合は、それらの要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="76010-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="76010-110">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="76010-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76010-111">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="76010-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="76010-112">**データセット:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76010-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="76010-113">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="76010-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="76010-114">attr1</span><span class="sxs-lookup"><span data-stu-id="76010-114">attr1</span></span>|<span data-ttu-id="76010-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="76010-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="76010-116">value1</span><span class="sxs-lookup"><span data-stu-id="76010-116">value1</span></span>||  
|<span data-ttu-id="76010-117">value2</span><span class="sxs-lookup"><span data-stu-id="76010-117">value2</span></span>|<span data-ttu-id="76010-118">Text1</span><span class="sxs-lookup"><span data-stu-id="76010-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="76010-119">子要素を持つ要素</span><span class="sxs-lookup"><span data-stu-id="76010-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="76010-120">子要素を持つ要素は、テーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="76010-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="76010-121">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="76010-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76010-122">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="76010-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="76010-123">**データセット:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76010-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="76010-124">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="76010-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="76010-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="76010-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="76010-126">Text1</span><span class="sxs-lookup"><span data-stu-id="76010-126">Text1</span></span>|  
  
 <span data-ttu-id="76010-127">ドキュメント (ルート) 要素に属性または子要素があり、それらが列として推論される場合には、そのドキュメント要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="76010-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="76010-128">ドキュメント要素の属性も列として推論される子要素はありませんが、要素として推論されます、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="76010-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="76010-129">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="76010-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76010-130">推論プロセスにより、"DocumentElement" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="76010-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="76010-131">**データセット:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="76010-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="76010-132">**テーブル:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76010-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="76010-133">Element1</span><span class="sxs-lookup"><span data-stu-id="76010-133">Element1</span></span>|<span data-ttu-id="76010-134">Element2</span><span class="sxs-lookup"><span data-stu-id="76010-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="76010-135">Text1</span><span class="sxs-lookup"><span data-stu-id="76010-135">Text1</span></span>|<span data-ttu-id="76010-136">Text2</span><span class="sxs-lookup"><span data-stu-id="76010-136">Text2</span></span>|  
  
 <span data-ttu-id="76010-137">または、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="76010-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76010-138">推論プロセスによって生成される、**データセット**"Element1"という名前のテーブルを含む"DocumentElement"という名前</span><span class="sxs-lookup"><span data-stu-id="76010-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="76010-139">**データセット:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76010-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="76010-140">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="76010-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="76010-141">attr1</span><span class="sxs-lookup"><span data-stu-id="76010-141">attr1</span></span>|<span data-ttu-id="76010-142">attr2</span><span class="sxs-lookup"><span data-stu-id="76010-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="76010-143">value1</span><span class="sxs-lookup"><span data-stu-id="76010-143">value1</span></span>|<span data-ttu-id="76010-144">value2</span><span class="sxs-lookup"><span data-stu-id="76010-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="76010-145">繰り返し出現する要素</span><span class="sxs-lookup"><span data-stu-id="76010-145">Repeating Elements</span></span>  
 <span data-ttu-id="76010-146">繰り返し出現する要素は、単一のテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="76010-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="76010-147">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="76010-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="76010-148">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="76010-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="76010-149">**データセット:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="76010-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="76010-150">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="76010-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="76010-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="76010-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="76010-152">Text1</span><span class="sxs-lookup"><span data-stu-id="76010-152">Text1</span></span>|  
|<span data-ttu-id="76010-153">Text2</span><span class="sxs-lookup"><span data-stu-id="76010-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76010-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="76010-154">See also</span></span>

- [<span data-ttu-id="76010-155">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="76010-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="76010-156">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="76010-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="76010-157">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="76010-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="76010-158">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="76010-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="76010-159">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="76010-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="76010-160">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="76010-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
