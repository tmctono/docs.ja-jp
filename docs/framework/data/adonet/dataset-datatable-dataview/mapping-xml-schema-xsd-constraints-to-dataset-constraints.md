---
title: XML スキーマ (XSD) 制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: b0082b534b8df10ac5277cf2f5aa5b2d2e40c11b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204619"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="02b93-102">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="02b93-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="02b93-103">XML スキーマ定義言語 (XSD) を使用すると、定義する要素と属性で制約を指定できます。</span><span class="sxs-lookup"><span data-stu-id="02b93-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="02b93-104">Xml スキーマを内の<xref:System.Data.DataSet>リレーショナルスキーマにマップする場合、xml スキーマ制約は、**データセット**内のテーブルおよび列に対する適切なリレーショナル制約にマップされます。</span><span class="sxs-lookup"><span data-stu-id="02b93-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="02b93-105">このセクションでは、次の XML スキーマの制約の割り当てについて説明します。</span><span class="sxs-lookup"><span data-stu-id="02b93-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="02b93-106">**Unique**要素を使用して指定された一意性制約。</span><span class="sxs-lookup"><span data-stu-id="02b93-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="02b93-107">**Key**要素を使用して指定されたキー制約。</span><span class="sxs-lookup"><span data-stu-id="02b93-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="02b93-108">**Keyref**要素を使用して指定された keyref 制約。</span><span class="sxs-lookup"><span data-stu-id="02b93-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="02b93-109">要素または属性に対して制約を指定することにより、同じスキーマに基づくあらゆるドキュメントで、その要素の値について特定の制限を適用できます。</span><span class="sxs-lookup"><span data-stu-id="02b93-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="02b93-110">たとえば、スキーマ内の**Customer**要素の**customerid**子要素のキー制約は、 **customerid**子要素の値がドキュメントインスタンス内で一意であること、および null 値が許可されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="02b93-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="02b93-111">さらに、ドキュメント内のリレーションシップを確立するために、ドキュメント内の要素および属性間に制約を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="02b93-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="02b93-112">ドキュメント内で制約を指定するためにスキーマ内で key 制約または keyref 制約を使用すると、ドキュメントの要素と属性間にリレーションシップを持つことになります。</span><span class="sxs-lookup"><span data-stu-id="02b93-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="02b93-113">マッピングプロセスでは、これらのスキーマ制約が、**データセット**内に作成されたテーブルに対する適切な制約に変換されます。</span><span class="sxs-lookup"><span data-stu-id="02b93-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02b93-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="02b93-114">In This Section</span></span>  
 [<span data-ttu-id="02b93-115">XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="02b93-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="02b93-116">**データセット**内に unique 制約を作成するために使用される XML スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b93-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="02b93-117">XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="02b93-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="02b93-118">**データセット**内のキー制約 (null 値が許可されない) を作成するために使用される XML スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b93-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="02b93-119">XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="02b93-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="02b93-120">**DataSet**で keyref (外部キー) 制約を作成するために使用される XML スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b93-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="02b93-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="02b93-121">Related Sections</span></span>  
 [<span data-ttu-id="02b93-122">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="02b93-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="02b93-123">XSD スキーマから作成される**データセット**のリレーショナル構造 (スキーマ) について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b93-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="02b93-124">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="02b93-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="02b93-125">**データセット**内のテーブル列間のリレーションを作成するために使用される XML スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="02b93-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02b93-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="02b93-126">See also</span></span>

- [<span data-ttu-id="02b93-127">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="02b93-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
