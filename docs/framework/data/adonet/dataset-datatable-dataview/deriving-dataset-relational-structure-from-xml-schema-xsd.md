---
title: XML スキーマ (XSD) からの DataSet リレーショナル構造の派生
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 29b905c42f15cad4eb8521c4d702b56093982445
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203780"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="bb5a1-102">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="bb5a1-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="bb5a1-103">ここでは、XML スキーマ定義言語 (XSD) スキーマ ドキュメントから `DataSet` のリレーショナル スキーマを生成する方法についての概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="bb5a1-104">一般に、スキーマ要素`complexType`の各子要素に対して`DataSet`、でテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="bb5a1-105">テーブル構造は、複合型の定義に基づいて決定されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="bb5a1-106">テーブルは、スキーマ内`DataSet`の最上位の要素に対して、で作成されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="bb5a1-107">ただし、 `complexType`要素が別`complexType` `complexType`の要素の内部に入れ子になっている場合は、最上位レベルの要素に対してのみ`complexType`テーブルが作成され`DataTable` `DataSet`ます。この場合、入れ子になった要素は内のにマップされます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="bb5a1-108">XSD の詳細については、次を参照して[ください。 World Wide Web コンソーシアム (W3C) XML スキーマパート 0:入門勧告](https://www.w3.org/TR/xmlschema-0/) [、XML スキーマパート 1:構造に](https://www.w3.org/TR/xmlschema-1/)関する推奨事項[、および XML スキーマ第2部:Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/)」 (XML スキーマ第 2 部: データ型の推奨事項) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="bb5a1-109">次の例は、XML スキーマ`customers`を示しています。は、 `MyDataSet`要素の子要素であり、 **DataSet**要素です。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="bb5a1-110">上記の例では、`customers` 要素は複合型の要素です。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="bb5a1-111">したがって、複合型の定義が解析され、割り当て処理によって次のテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="bb5a1-112">テーブルの各列のデータ型は、それに対応する指定された要素または属性の XML スキーマ型から派生します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bb5a1-113">要素`customers`が**integer**のような単純な XML スキーマデータ型の場合、テーブルは生成されません。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="bb5a1-114">テーブルが作成されるのは、複合型のトップレベル要素に対してだけです。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="bb5a1-115">次の XML スキーマでは、**スキーマ**要素に`InStateCustomers`とと`OutOfStateCustomers`いう2つの子要素があります。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="bb5a1-116">`InStateCustomers` と `OutOfStateCustomers` の 2 つの子要素は、複合型の要素です (`customerType`)。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="bb5a1-117">したがって、マッピングプロセスでは、 `DataSet`で次の2つの同一のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="bb5a1-118">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bb5a1-118">In This Section</span></span>  
 [<span data-ttu-id="bb5a1-119">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="bb5a1-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="bb5a1-120">で unique および foreign key 制約を作成するために使用される XML `DataSet`スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="bb5a1-121">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="bb5a1-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="bb5a1-122">のテーブル列`DataSet`間のリレーションを作成するために使用される XML スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="bb5a1-123">XML スキーマ制約およびリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="bb5a1-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="bb5a1-124">XML スキーマ要素を使用してで制約を作成するときに、 `DataSet`暗黙的にリレーションシップを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bb5a1-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb5a1-125">Related Sections</span></span>  
 [<span data-ttu-id="bb5a1-126">DataSet での XML の使用</span><span class="sxs-lookup"><span data-stu-id="bb5a1-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="bb5a1-127">のリレーショナル構造とデータ`DataSet`を XML データとして読み込んで永続化する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bb5a1-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5a1-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="bb5a1-128">See also</span></span>

- [<span data-ttu-id="bb5a1-129">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="bb5a1-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
