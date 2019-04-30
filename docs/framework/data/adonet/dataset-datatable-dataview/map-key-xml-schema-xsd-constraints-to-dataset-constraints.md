---
title: XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 46a980f06198c6f06bb13824c65cfb5309eec154
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034230"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="5c9d5-102">XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="5c9d5-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="5c9d5-103">スキーマで要素にキー制約を指定または属性を使用して、**キー**要素。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="5c9d5-104">キー制約を指定する要素または属性の値は、スキーマ インスタンス内で一意になる必要があります。また、null 値にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="5c9d5-105">キー制約を定義する列の値を null 値にできない点を除くと、キー制約は UNIQUE 制約と同じです。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="5c9d5-106">次の表にアウトライン、 **msdata**属性で指定することができます、**キー**要素。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="5c9d5-107">属性名</span><span class="sxs-lookup"><span data-stu-id="5c9d5-107">Attribute name</span></span>|<span data-ttu-id="5c9d5-108">説明</span><span class="sxs-lookup"><span data-stu-id="5c9d5-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5c9d5-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="5c9d5-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="5c9d5-110">この属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="5c9d5-111">それ以外の場合、**名前**属性は、制約の名前の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="5c9d5-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="5c9d5-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="5c9d5-113">場合`PrimaryKey="true"`が存在する、 **IsPrimaryKey**に制約が設定されて**true**、なり、主キー。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="5c9d5-114">**AllowDBNull**列のプロパティに設定されて**false**、主キーが null 値を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="5c9d5-115">キーの制約が指定されているスキーマを変換するには、マッピング プロセスが含まれているテーブルに unique 制約を作成、 **AllowDBNull**列プロパティを設定**false**の各列に対して、制約です。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="5c9d5-116">**IsPrimaryKey** unique 制約のプロパティに設定されても**false**指定していない限り`msdata:PrimaryKey="true"`上、**キー**要素。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="5c9d5-117">これは、スキーマに `PrimaryKey="true"` が指定される UNIQUE 制約と同じです。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="5c9d5-118">次のスキーマ例では、**キー**要素のキーの制約を指定します、 **CustomerID**要素。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>   
```  
  
 <span data-ttu-id="5c9d5-119">**キー**要素を指定する値、 **CustomerID**の子要素、**顧客**要素の一意の値が必要し、null 値を持つことはできません。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="5c9d5-120">XML スキーマ定義言語 (XSD) スキーマの変換では、割り当て処理によって次のテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="5c9d5-121">XML スキーマのマッピングも作成、 **UniqueConstraint**上、 **CustomerID**列では、次に示すように<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5c9d5-122">(わかりやすいように、関連するプロパティだけを示します)。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID   
      IsPrimaryKey: True  
```  
  
 <span data-ttu-id="5c9d5-123">**データセット**、生成された、 **IsPrimaryKey**のプロパティ、 **UniqueConstraint**に設定されている**true**のためスキーマ指定します`msdata:PrimaryKey="true"`で、**キー**要素。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="5c9d5-124">値、 **ConstraintName**のプロパティ、 **UniqueConstraint**で、**データセット**の値である、 **msdata:ConstraintName**指定された属性、**キー**スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="5c9d5-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c9d5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c9d5-125">See also</span></span>

- [<span data-ttu-id="5c9d5-126">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="5c9d5-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="5c9d5-127">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="5c9d5-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="5c9d5-128">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="5c9d5-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
