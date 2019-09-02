---
title: 要素のテキストの推論
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: d8d64c0cbb0aecf736a54fa6816e286ab7efa191
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203530"
---
# <a name="inferring-element-text"></a><span data-ttu-id="44484-102">要素のテキストの推論</span><span class="sxs-lookup"><span data-stu-id="44484-102">Inferring Element Text</span></span>
<span data-ttu-id="44484-103">要素にテキストが含まれており、テーブルとして推論される子要素がない場合 (属性を持つ要素や要素が繰り返される場合など)、 **TableName_Text**という名前の新しい列が、要素に対して推論されるテーブルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="44484-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="44484-104">要素に含まれているテキストはテーブルの行に追加され、新しい列に格納されます。</span><span class="sxs-lookup"><span data-stu-id="44484-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="44484-105">新しい列の**ColumnMapping**プロパティは、 **Mappingtype. SimpleContent**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="44484-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="44484-106">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="44484-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="44484-107">推論プロセスでは、 **attr1**と**Element1_Text**の2つの列を持つ**Element1**という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="44484-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="44484-108">**Attr1**列の**ColumnMapping**プロパティは、 **mappingtype. Attribute**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="44484-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="44484-109">**Element1_Text**列の**ColumnMapping**プロパティは、 **mappingtype. SimpleContent**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="44484-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="44484-110">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="44484-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="44484-111">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="44484-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="44484-112">attr1</span><span class="sxs-lookup"><span data-stu-id="44484-112">attr1</span></span>|<span data-ttu-id="44484-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="44484-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="44484-114">value1</span><span class="sxs-lookup"><span data-stu-id="44484-114">value1</span></span>|<span data-ttu-id="44484-115">Text1</span><span class="sxs-lookup"><span data-stu-id="44484-115">Text1</span></span>|  
  
 <span data-ttu-id="44484-116">要素にテキストだけでなく、テキストを含む子の要素も含まれている場合は、その要素に含まれているテキストを格納するための列はテーブルに追加されません。</span><span class="sxs-lookup"><span data-stu-id="44484-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="44484-117">要素に含まれるテキストは無視されますが、子の要素のテキストはテーブルの行に追加されます。</span><span class="sxs-lookup"><span data-stu-id="44484-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="44484-118">たとえば、次のような XML があるとします。</span><span class="sxs-lookup"><span data-stu-id="44484-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="44484-119">推論プロセスでは、 **ChildElement1**という名前の1つの列を持つ**Element1**という名前のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="44484-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="44484-120">**ChildElement1**要素のテキストは、テーブルの行に含まれます。</span><span class="sxs-lookup"><span data-stu-id="44484-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="44484-121">その他のテキストは無視されます。</span><span class="sxs-lookup"><span data-stu-id="44484-121">The other text will be ignored.</span></span> <span data-ttu-id="44484-122">**ChildElement1**列の**ColumnMapping**プロパティは、 **mappingtype. Element**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="44484-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="44484-123">**セット**DocumentElement</span><span class="sxs-lookup"><span data-stu-id="44484-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="44484-124">**一覧**Element1</span><span class="sxs-lookup"><span data-stu-id="44484-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="44484-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="44484-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="44484-126">Text2</span><span class="sxs-lookup"><span data-stu-id="44484-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44484-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="44484-127">See also</span></span>

- [<span data-ttu-id="44484-128">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="44484-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="44484-129">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="44484-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="44484-130">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="44484-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="44484-131">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="44484-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="44484-132">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="44484-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="44484-133">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="44484-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
