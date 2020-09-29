---
title: テーブルの推論
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 4a3d7b239dbc405cf2acae967b5be401dc772e38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177554"
---
# <a name="inferring-tables"></a><span data-ttu-id="868fa-102">テーブルの推論</span><span class="sxs-lookup"><span data-stu-id="868fa-102">Inferring Tables</span></span>

<span data-ttu-id="868fa-103">XML ドキュメントから <xref:System.Data.DataSet> のスキーマを推論するときには、ADO.NET では、テーブルを表す XML 要素を最初に決定します。</span><span class="sxs-lookup"><span data-stu-id="868fa-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="868fa-104">次に示す XML 構造では、**DataSet** スキーマのテーブルが推論されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="868fa-105">属性を持つ要素</span><span class="sxs-lookup"><span data-stu-id="868fa-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="868fa-106">子要素を持つ要素</span><span class="sxs-lookup"><span data-stu-id="868fa-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="868fa-107">繰り返し出現する要素</span><span class="sxs-lookup"><span data-stu-id="868fa-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="868fa-108">属性を持つ要素</span><span class="sxs-lookup"><span data-stu-id="868fa-108">Elements with Attributes</span></span>  

 <span data-ttu-id="868fa-109">要素に属性が指定されている場合は、それらの要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="868fa-110">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="868fa-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="868fa-111">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="868fa-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="868fa-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="868fa-113">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="868fa-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="868fa-114">attr1</span><span class="sxs-lookup"><span data-stu-id="868fa-114">attr1</span></span>|<span data-ttu-id="868fa-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="868fa-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="868fa-116">value1</span><span class="sxs-lookup"><span data-stu-id="868fa-116">value1</span></span>||  
|<span data-ttu-id="868fa-117">value2</span><span class="sxs-lookup"><span data-stu-id="868fa-117">value2</span></span>|<span data-ttu-id="868fa-118">Text1</span><span class="sxs-lookup"><span data-stu-id="868fa-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="868fa-119">子要素を持つ要素</span><span class="sxs-lookup"><span data-stu-id="868fa-119">Elements with Child Elements</span></span>  

 <span data-ttu-id="868fa-120">子要素を持つ要素は、テーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="868fa-121">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="868fa-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="868fa-122">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="868fa-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="868fa-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="868fa-124">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="868fa-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="868fa-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="868fa-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="868fa-126">Text1</span><span class="sxs-lookup"><span data-stu-id="868fa-126">Text1</span></span>|  
  
 <span data-ttu-id="868fa-127">ドキュメント (ルート) 要素に属性または子要素があり、それらが列として推論される場合には、そのドキュメント要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="868fa-128">ドキュメント要素の属性や子要素が列として推論されない場合、そのドキュメント要素は **DataSet** として推論されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="868fa-129">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="868fa-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="868fa-130">推論プロセスにより、"DocumentElement" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="868fa-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="868fa-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="868fa-132">**テーブル:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="868fa-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="868fa-133">Element1</span><span class="sxs-lookup"><span data-stu-id="868fa-133">Element1</span></span>|<span data-ttu-id="868fa-134">Element2</span><span class="sxs-lookup"><span data-stu-id="868fa-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="868fa-135">Text1</span><span class="sxs-lookup"><span data-stu-id="868fa-135">Text1</span></span>|<span data-ttu-id="868fa-136">Text2</span><span class="sxs-lookup"><span data-stu-id="868fa-136">Text2</span></span>|  
  
 <span data-ttu-id="868fa-137">または、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="868fa-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="868fa-138">推論プロセスにより、"Element1" という名前のテーブルを含む "DocumentElement" という名前の **DataSet** が生成されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="868fa-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="868fa-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="868fa-140">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="868fa-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="868fa-141">attr1</span><span class="sxs-lookup"><span data-stu-id="868fa-141">attr1</span></span>|<span data-ttu-id="868fa-142">attr2</span><span class="sxs-lookup"><span data-stu-id="868fa-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="868fa-143">value1</span><span class="sxs-lookup"><span data-stu-id="868fa-143">value1</span></span>|<span data-ttu-id="868fa-144">value2</span><span class="sxs-lookup"><span data-stu-id="868fa-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="868fa-145">繰り返し出現する要素</span><span class="sxs-lookup"><span data-stu-id="868fa-145">Repeating Elements</span></span>  

 <span data-ttu-id="868fa-146">繰り返し出現する要素は、単一のテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="868fa-147">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="868fa-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="868fa-148">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="868fa-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="868fa-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="868fa-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="868fa-150">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="868fa-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="868fa-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="868fa-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="868fa-152">Text1</span><span class="sxs-lookup"><span data-stu-id="868fa-152">Text1</span></span>|  
|<span data-ttu-id="868fa-153">Text2</span><span class="sxs-lookup"><span data-stu-id="868fa-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="868fa-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="868fa-154">See also</span></span>

- [<span data-ttu-id="868fa-155">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="868fa-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="868fa-156">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="868fa-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="868fa-157">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="868fa-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="868fa-158">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="868fa-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="868fa-159">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="868fa-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="868fa-160">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="868fa-160">ADO.NET Overview</span></span>](../ado-net-overview.md)
