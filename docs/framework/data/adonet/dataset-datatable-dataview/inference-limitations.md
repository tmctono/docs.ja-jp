---
title: 推論の制限事項
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 10347abc5b01edb4ec6fbf97221d44f4bfb88f54
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784581"
---
# <a name="inference-limitations"></a><span data-ttu-id="f8483-102">推論の制限事項</span><span class="sxs-lookup"><span data-stu-id="f8483-102">Inference Limitations</span></span>
<span data-ttu-id="f8483-103">各ドキュメントに含まれている XML 要素によっては、XML から <xref:System.Data.DataSet> のスキーマを推論するプロセスにより、異なるスキーマが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f8483-103">The process of inferring a <xref:System.Data.DataSet> schema from XML can result in different schemas depending on the XML elements in each document.</span></span> <span data-ttu-id="f8483-104">たとえば、次のような XML ドキュメントがあるとします。</span><span class="sxs-lookup"><span data-stu-id="f8483-104">For example, consider the following XML documents.</span></span>  
  
 <span data-ttu-id="f8483-105">Document1:</span><span class="sxs-lookup"><span data-stu-id="f8483-105">Document1:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f8483-106">Document2:</span><span class="sxs-lookup"><span data-stu-id="f8483-106">Document2:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="f8483-107">推論プロセスでは、"Document1" については、"DocumentElement" という名前の **DataSet** と "Element1" という名前のテーブルが作成されます。これは、"Element1" が繰り返し出現する要素であるためです。</span><span class="sxs-lookup"><span data-stu-id="f8483-107">For "Document1," the inference process produces a **DataSet** named "DocumentElement" and a table named "Element1," because "Element1" is a repeating element.</span></span>  
  
 <span data-ttu-id="f8483-108">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f8483-108">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="f8483-109">**テーブル:** Element1</span><span class="sxs-lookup"><span data-stu-id="f8483-109">**Table:** Element1</span></span>  
  
|<span data-ttu-id="f8483-110">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="f8483-110">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="f8483-111">Text1</span><span class="sxs-lookup"><span data-stu-id="f8483-111">Text1</span></span>|  
|<span data-ttu-id="f8483-112">Text2</span><span class="sxs-lookup"><span data-stu-id="f8483-112">Text2</span></span>|  
  
 <span data-ttu-id="f8483-113">これに対して、"Document2" については、"NewDataSet" という名前の **DataSet** と "DocumentElement" という名前のテーブルが推論プロセスで生成されます。</span><span class="sxs-lookup"><span data-stu-id="f8483-113">However, for "Document2," the inference process produces a **DataSet** named "NewDataSet" and a table named "DocumentElement."</span></span> <span data-ttu-id="f8483-114">この場合、属性も子要素も持たない "Element1" は列として推論されます。</span><span class="sxs-lookup"><span data-stu-id="f8483-114">"Element1" is inferred as a column because it has no attributes and no child elements.</span></span>  
  
 <span data-ttu-id="f8483-115">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="f8483-115">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="f8483-116">**テーブル:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="f8483-116">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="f8483-117">Element1</span><span class="sxs-lookup"><span data-stu-id="f8483-117">Element1</span></span>|  
|--------------|  
|<span data-ttu-id="f8483-118">Text1</span><span class="sxs-lookup"><span data-stu-id="f8483-118">Text1</span></span>|  
  
 <span data-ttu-id="f8483-119">これらの 2 つの XML ドキュメントは、同じスキーマを生成することを意図して記述されていますが、推論プロセスでは、各ドキュメントに含まれる要素を基にまったく異なるスキーマが生成されてしまいます。</span><span class="sxs-lookup"><span data-stu-id="f8483-119">These two XML documents may have been intended to produce the same schema, but the inference process produces very different results based on the elements contained in each document.</span></span>  
  
 <span data-ttu-id="f8483-120">XML ドキュメントからスキーマを生成するときに生じる可能性のあるこのような矛盾を避けるため、XML から **DataSet** を読み込むときは、XSD (XML スキーマ定義言語) または XDR (XML-Data Reduced) を使用して、スキーマを明示的に指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f8483-120">To avoid the discrepancies that can occur when generating schema from an XML document, we recommend that you explicitly specify a schema using XML Schema definition language (XSD) or XML-Data Reduced (XDR) when loading a **DataSet** from XML.</span></span> <span data-ttu-id="f8483-121">XML スキーマを使用して **DataSet** スキーマを明示的に指定する方法については、「[XML スキーマ (XSD) からの DataSet リレーショナル構造の派生](deriving-dataset-relational-structure-from-xml-schema-xsd.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f8483-121">For more information about explicitly specifying a **DataSet** schema with XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8483-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="f8483-122">See also</span></span>

- [<span data-ttu-id="f8483-123">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="f8483-123">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="f8483-124">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="f8483-124">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="f8483-125">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="f8483-125">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="f8483-126">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="f8483-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="f8483-127">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="f8483-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="f8483-128">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f8483-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
