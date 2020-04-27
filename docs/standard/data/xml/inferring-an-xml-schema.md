---
title: XML スキーマの推論
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b18e7ffd-3c04-482d-9934-ba2f6a59b2c9
ms.openlocfilehash: a65247f1786acea11879abf0405038446068c118
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710766"
---
# <a name="inferring-an-xml-schema"></a><span data-ttu-id="d8d18-102">XML スキーマの推論</span><span class="sxs-lookup"><span data-stu-id="d8d18-102">Inferring an XML Schema</span></span>
<span data-ttu-id="d8d18-103">スキーマ オブジェクト モデル (SOM) <xref:System.Xml.Schema.XmlSchemaInference> クラスを使用して、XML ドキュメントの構造から XML スキーマ定義言語 (XSD) スキーマを推論する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8d18-103">Describes how to use the Schema Object Model (SOM) <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XML Schema definition language (XSD) schema from the structure of an XML document.</span></span>  
  
 <span data-ttu-id="d8d18-104"><xref:System.Xml.Schema.XmlSchemaInference> 名前空間内のスキーマ オブジェクト モデル (SOM) <xref:System.Xml.Schema?displayProperty=nameWithType> クラスを使用すれば、XML ドキュメントの構造から XML スキーマ定義言語 (XSD) スキーマを推論できます。</span><span class="sxs-lookup"><span data-stu-id="d8d18-104">The Schema Object Model (SOM) <xref:System.Xml.Schema.XmlSchemaInference> class in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace allows you to infer an XML Schema definition language (XSD) schema from the structure of an XML document.</span></span> <span data-ttu-id="d8d18-105"><xref:System.Xml.Schema.XmlSchemaInference> クラスは XML ドキュメントの検証に使える XML スキーマを出力します。</span><span class="sxs-lookup"><span data-stu-id="d8d18-105">The <xref:System.Xml.Schema.XmlSchemaInference> class outputs an XML schema that can validate the XML document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8d18-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d8d18-106">In This Section</span></span>  
 [<span data-ttu-id="d8d18-107">XML ドキュメントからのスキーマの推論</span><span class="sxs-lookup"><span data-stu-id="d8d18-107">Inferring Schemas from XML Documents</span></span>](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)  
 <span data-ttu-id="d8d18-108"><xref:System.Xml.Schema.XmlSchemaInference> クラスを使用して XML ドキュメントの構造からスキーマを推論する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8d18-108">Describes how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer a schema from the structure of an XML document.</span></span>  
  
 [<span data-ttu-id="d8d18-109">スキーマのノード型および構造を推論するときの規則</span><span class="sxs-lookup"><span data-stu-id="d8d18-109">Rules for Inferring Schema Node Types and Structure</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)  
 <span data-ttu-id="d8d18-110">XML ドキュメントで検出されたノード型をスキーマ構造に変換する推論のプロセスを説明します。</span><span class="sxs-lookup"><span data-stu-id="d8d18-110">Describes how the inference process translates the node types encountered in an XML document into a schema structure.</span></span>  
  
 [<span data-ttu-id="d8d18-111">単純型を推論するときの規則</span><span class="sxs-lookup"><span data-stu-id="d8d18-111">Rules for Inferring Simple Types</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)  
 <span data-ttu-id="d8d18-112"><xref:System.Xml.Schema.XmlSchemaInference> クラスが属性と要素のデータ型を推論する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="d8d18-112">Describes how the <xref:System.Xml.Schema.XmlSchemaInference> class infers the data type for attributes and elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d18-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8d18-113">See also</span></span>

- [<span data-ttu-id="d8d18-114">XML スキーマ オブジェクト モデル (SOM)</span><span class="sxs-lookup"><span data-stu-id="d8d18-114">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)
- [<span data-ttu-id="d8d18-115">XML ドキュメントからのスキーマの推論</span><span class="sxs-lookup"><span data-stu-id="d8d18-115">Inferring Schemas from XML Documents</span></span>](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)
- [<span data-ttu-id="d8d18-116">スキーマのノード型および構造を推論するときの規則</span><span class="sxs-lookup"><span data-stu-id="d8d18-116">Rules for Inferring Schema Node Types and Structure</span></span>](../../../../docs/standard/data/xml/rules-for-inferring-schema-node-types-and-structure.md)
