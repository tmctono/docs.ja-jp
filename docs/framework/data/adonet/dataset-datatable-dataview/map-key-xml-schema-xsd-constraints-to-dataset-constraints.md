---
title: XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: d6fcdae77c2f2ac07ea5cd16baf07cd5de36d25b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203462"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="4b3e9-102">XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="4b3e9-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="4b3e9-103">スキーマでは、 **key**要素を使用して、要素または属性に対してキー制約を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="4b3e9-104">キー制約を指定する要素または属性の値は、スキーマ インスタンス内で一意になる必要があります。また、null 値にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="4b3e9-105">キー制約を定義する列の値を null 値にできない点を除くと、キー制約は UNIQUE 制約と同じです。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="4b3e9-106">次の表は、 **key**要素で指定できる**msdata**属性の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="4b3e9-107">属性名</span><span class="sxs-lookup"><span data-stu-id="4b3e9-107">Attribute name</span></span>|<span data-ttu-id="4b3e9-108">説明</span><span class="sxs-lookup"><span data-stu-id="4b3e9-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4b3e9-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="4b3e9-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="4b3e9-110">この属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="4b3e9-111">それ以外の場合、 **name**属性は制約名の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="4b3e9-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="4b3e9-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="4b3e9-113">が`PrimaryKey="true"`存在する場合、 **IsPrimaryKey** constraint プロパティは**true**に設定されるため、主キーになります。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="4b3e9-114">プライマリキーは null 値を持つことができないため、 **Allowdbnull**列プロパティは**false**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="4b3e9-115">キー制約が指定されているスキーマの変換では、制約の各列に対して**Allowdbnull** column プロパティを**false**に設定して、テーブルに unique 制約を作成します。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="4b3e9-116">**Key**要素でを指定`msdata:PrimaryKey="true"`しない限り、unique 制約の**IsPrimaryKey**プロパティも**false**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="4b3e9-117">これは、スキーマに `PrimaryKey="true"` が指定される UNIQUE 制約と同じです。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="4b3e9-118">次のスキーマ例では、 **key**要素は**CustomerID**要素のキー制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="4b3e9-119">**Key**要素は、 **Customers**要素の**CustomerID**子要素の値が一意の値を持つ必要があり、null 値を持つことができないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="4b3e9-120">XML スキーマ定義言語 (XSD) スキーマの変換では、割り当て処理によって次のテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="4b3e9-121">また、次<xref:System.Data.DataSet>に示すように、XML スキーママッピングによって**CustomerID**列に**UniqueConstraint**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4b3e9-122">(わかりやすいように、関連するプロパティだけを示します)。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="4b3e9-123">生成された**データセット**では、 **UniqueConstraint**の**IsPrimaryKey**プロパティが**true**に設定されてい`msdata:PrimaryKey="true"`ます。これは、スキーマで**key**要素が指定されているためです。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="4b3e9-124">**データセット**内の**UniqueConstraint**の**ConstraintName**プロパティの値は、スキーマの**key**要素で指定されている**msdata: ConstraintName**属性の値です。</span><span class="sxs-lookup"><span data-stu-id="4b3e9-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b3e9-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b3e9-125">See also</span></span>

- [<span data-ttu-id="4b3e9-126">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="4b3e9-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="4b3e9-127">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="4b3e9-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="4b3e9-128">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="4b3e9-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
