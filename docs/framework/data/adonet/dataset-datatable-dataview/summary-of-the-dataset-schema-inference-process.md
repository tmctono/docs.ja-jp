---
title: DataSet スキーマの推論プロセスの概要
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 35e9b67d2d0a47aa69eabdb4b7e94f95b0b9589f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833978"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="b63b5-102">DataSet スキーマの推論プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="b63b5-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="b63b5-103">推論プロセスでは、まず、テーブルとして推論する XML ドキュメントの要素を決定します。</span><span class="sxs-lookup"><span data-stu-id="b63b5-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="b63b5-104">XML ドキュメントの残りの要素から、それらのテーブルの列が推論によって決定されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="b63b5-105">入れ子状のテーブルの場合は、入れ子になった <xref:System.Data.DataRelation> オブジェクトと <xref:System.Data.ForeignKeyConstraint> オブジェクトが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="b63b5-106">推論規則の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b63b5-106">The following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="b63b5-107">属性を持つ要素は、テーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="b63b5-108">子要素を持つ要素は、テーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="b63b5-109">繰り返し出現する要素は、単一のテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="b63b5-110">ドキュメント (ルート) 要素に属性がなく、列として推論される子要素もない場合、その要素は <xref:System.Data.DataSet> として推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b63b5-111">それ以外の場合は、ドキュメント要素はテーブルとして推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="b63b5-112">属性は、列として推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="b63b5-113">属性または子要素を持たず、繰り返し出現することもない要素は、列として推論されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="b63b5-114">テーブルとして推論される他の要素内で入れ子になったテーブルとして推論される要素の場合は、2つのテーブル間に入れ子になった**DataRelation**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="b63b5-115">**TableName_Id**という名前の新しい主キー列が両方のテーブルに追加され、 **DataRelation**によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="b63b5-116">**TableName_Id**列を使用して、2つのテーブルの間に**ForeignKeyConstraint**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="b63b5-117">テーブルとして推論され、テキストを含み、子要素を持たない要素については、各要素のテキストに対して**TableName_Text**という名前の新しい列が作成されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="b63b5-118">テーブルとして推論される要素にテキストだけでなく、子要素もある場合、テキストは無視されます。</span><span class="sxs-lookup"><span data-stu-id="b63b5-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63b5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="b63b5-119">See also</span></span>

- [<span data-ttu-id="b63b5-120">XML からの DataSet リレーショナル構造の推論</span><span class="sxs-lookup"><span data-stu-id="b63b5-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="b63b5-121">XML からの DataSet の読み込み</span><span class="sxs-lookup"><span data-stu-id="b63b5-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="b63b5-122">XML の DataSet スキーマ情報の読み込み</span><span class="sxs-lookup"><span data-stu-id="b63b5-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="b63b5-123">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="b63b5-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="b63b5-124">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="b63b5-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b63b5-125">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="b63b5-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
