---
title: XML スキーマ (XSD) からの DataSet リレーショナル構造の派生
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151170"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="ebbd2-102">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="ebbd2-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="ebbd2-103">ここでは、XML スキーマ定義言語 (XSD) スキーマ ドキュメントから `DataSet` のリレーショナル スキーマを生成する方法についての概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="ebbd2-104">一般に、スキーマ`complexType`要素の子要素ごとに、テーブルが`DataSet`.</span><span class="sxs-lookup"><span data-stu-id="ebbd2-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="ebbd2-105">テーブル構造は、複合型の定義に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="ebbd2-106">テーブルは、スキーマの`DataSet`最上位要素で作成されます。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="ebbd2-107">`complexType`ただし、最上位の要素に対してのみテーブルが作成されるのは、`complexType``complexType``complexType`要素が別の要素内に入れ子になっている場合`DataTable`です。 `DataSet`</span><span class="sxs-lookup"><span data-stu-id="ebbd2-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="ebbd2-108">XSD の詳細については、「 WWW (W3C) [XML スキーマ パート 0: 入門勧告](https://www.w3.org/TR/xmlschema-0/) [、XML スキーマパート 1: 構造体の推奨](https://www.w3.org/TR/xmlschema-1/)」、および[「XML スキーマパート 2: データ型の推奨事項](https://www.w3.org/TR/xmlschema-2/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="ebbd2-109">次の例は、**要素**の子要素`customers``MyDataSet`である XML スキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ebbd2-110">上記の例では、`customers` 要素は複合型の要素です。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="ebbd2-111">したがって、複合型の定義が解析され、割り当て処理によって次のテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="ebbd2-112">テーブルの各列のデータ型は、それに対応する指定された要素または属性の XML スキーマ型から派生します。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ebbd2-113">要素`customers`が**整数**などの単純な XML スキーマ データ型の場合、テーブルは生成されません。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="ebbd2-114">テーブルが作成されるのは、複合型のトップレベル要素に対してだけです。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="ebbd2-115">次の XML スキーマでは **、Schema**要素には 2 `InStateCustomers` `OutOfStateCustomers`つの要素子と .</span><span class="sxs-lookup"><span data-stu-id="ebbd2-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"
            xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="ebbd2-116">`InStateCustomers` と `OutOfStateCustomers` の 2 つの子要素は、複合型の要素です (`customerType`)。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="ebbd2-117">したがって、マッピング プロセスでは、次の 2 つの同`DataSet`一テーブルが で生成されます。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="ebbd2-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ebbd2-118">In This Section</span></span>  
 [<span data-ttu-id="ebbd2-119">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="ebbd2-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="ebbd2-120">で一意キー制約と外部キー制約を作成するために使用する XML`DataSet`スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ebbd2-121">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="ebbd2-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="ebbd2-122">テーブルの列間のリレーションシップを作成するために使用する XML スキーマ`DataSet`要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="ebbd2-123">XML スキーマ制約およびリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="ebbd2-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="ebbd2-124">XML スキーマ要素を使用して 制約を作成する場合に、リレーションが暗黙的`DataSet`に作成される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ebbd2-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebbd2-125">Related Sections</span></span>  
 [<span data-ttu-id="ebbd2-126">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="ebbd2-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="ebbd2-127">リレーショナル構造およびデータを XML データとして読み込んで`DataSet`保持する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ebbd2-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebbd2-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebbd2-128">See also</span></span>

- [<span data-ttu-id="ebbd2-129">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ebbd2-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
