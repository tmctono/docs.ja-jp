---
title: テーブルの推論
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 84cee828f2d3c918a12e449da5b01a3d72d86333
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203520"
---
# <a name="inferring-tables"></a><span data-ttu-id="bcfdf-102">テーブルの推論</span><span class="sxs-lookup"><span data-stu-id="bcfdf-102">Inferring Tables</span></span>
<span data-ttu-id="bcfdf-103">XML ドキュメントから <xref:System.Data.DataSet> のスキーマを推論するときには、ADO.NET では、テーブルを表す XML 要素を最初に決定します。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="bcfdf-104">次の XML 構造は、 **DataSet**スキーマのテーブルになります。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="bcfdf-105">属性を持つ要素</span><span class="sxs-lookup"><span data-stu-id="bcfdf-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="bcfdf-106">子要素を持つ要素</span><span class="sxs-lookup"><span data-stu-id="bcfdf-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="bcfdf-107">繰り返し出現する要素</span><span class="sxs-lookup"><span data-stu-id="bcfdf-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="bcfdf-108">属性を持つ要素</span><span class="sxs-lookup"><span data-stu-id="bcfdf-108">Elements with Attributes</span></span>  
 <span data-ttu-id="bcfdf-109">要素に属性が指定されている場合は、それらの要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="bcfdf-110">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bcfdf-111">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="bcfdf-112">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bcfdf-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bcfdf-113">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bcfdf-114">attr1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-114">attr1</span></span>|<span data-ttu-id="bcfdf-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="bcfdf-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="bcfdf-116">value1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-116">value1</span></span>||  
|<span data-ttu-id="bcfdf-117">value2</span><span class="sxs-lookup"><span data-stu-id="bcfdf-117">value2</span></span>|<span data-ttu-id="bcfdf-118">Text1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="bcfdf-119">子要素を持つ要素</span><span class="sxs-lookup"><span data-stu-id="bcfdf-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="bcfdf-120">子要素を持つ要素は、テーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="bcfdf-121">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bcfdf-122">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="bcfdf-123">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bcfdf-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bcfdf-124">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bcfdf-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="bcfdf-126">Text1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-126">Text1</span></span>|  
  
 <span data-ttu-id="bcfdf-127">ドキュメント (ルート) 要素に属性または子要素があり、それらが列として推論される場合には、そのドキュメント要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="bcfdf-128">ドキュメント要素に属性がなく、列として推論される子要素がない場合、要素は**データセット**として推論されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="bcfdf-129">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bcfdf-130">推論プロセスにより、"DocumentElement" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="bcfdf-131">**セット**NewDataSet</span><span class="sxs-lookup"><span data-stu-id="bcfdf-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="bcfdf-132">**一覧**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bcfdf-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="bcfdf-133">Element1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-133">Element1</span></span>|<span data-ttu-id="bcfdf-134">Element2</span><span class="sxs-lookup"><span data-stu-id="bcfdf-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="bcfdf-135">Text1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-135">Text1</span></span>|<span data-ttu-id="bcfdf-136">Text2</span><span class="sxs-lookup"><span data-stu-id="bcfdf-136">Text2</span></span>|  
  
 <span data-ttu-id="bcfdf-137">または、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bcfdf-138">推論プロセスにより、"Element1" という名前のテーブルを含む "DocumentElement" という名前の**データセット**が生成されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="bcfdf-139">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bcfdf-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bcfdf-140">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bcfdf-141">attr1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-141">attr1</span></span>|<span data-ttu-id="bcfdf-142">attr2</span><span class="sxs-lookup"><span data-stu-id="bcfdf-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="bcfdf-143">value1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-143">value1</span></span>|<span data-ttu-id="bcfdf-144">value2</span><span class="sxs-lookup"><span data-stu-id="bcfdf-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="bcfdf-145">繰り返し出現する要素</span><span class="sxs-lookup"><span data-stu-id="bcfdf-145">Repeating Elements</span></span>  
 <span data-ttu-id="bcfdf-146">繰り返し出現する要素は、単一のテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="bcfdf-147">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="bcfdf-148">推論プロセスにより、"Element1" という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bcfdf-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="bcfdf-149">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="bcfdf-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="bcfdf-150">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="bcfdf-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="bcfdf-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="bcfdf-152">Text1</span><span class="sxs-lookup"><span data-stu-id="bcfdf-152">Text1</span></span>|  
|<span data-ttu-id="bcfdf-153">Text2</span><span class="sxs-lookup"><span data-stu-id="bcfdf-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcfdf-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcfdf-154">See also</span></span>

- [<span data-ttu-id="bcfdf-155">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="bcfdf-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="bcfdf-156">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="bcfdf-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="bcfdf-157">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="bcfdf-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="bcfdf-158">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="bcfdf-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="bcfdf-159">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="bcfdf-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="bcfdf-160">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="bcfdf-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
