---
title: XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150936"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="6bcf4-102">XML スキーマ (XSD) のキー制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="6bcf4-102">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="6bcf4-103">スキーマでは、キー要素を使用して要素または属性に**キー**制約を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-103">In a schema, you can specify a key constraint on an element or attribute using the **key** element.</span></span> <span data-ttu-id="6bcf4-104">キー制約を指定する要素または属性の値は、スキーマ インスタンス内で一意になる必要があります。また、null 値にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-104">The element or attribute on which a key constraint is specified must have unique values in any schema instance, and cannot have null values.</span></span>  
  
 <span data-ttu-id="6bcf4-105">キー制約を定義する列の値を null 値にできない点を除くと、キー制約は UNIQUE 制約と同じです。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-105">The key constraint is similar to the unique constraint, except that the column on which a key constraint is defined cannot have null values.</span></span>  
  
 <span data-ttu-id="6bcf4-106">次の表は、キー要素で指定できる**msdata**属性の概要を**示**しています。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-106">The following table outlines the **msdata** attributes that you can specify in the **key** element.</span></span>  
  
|<span data-ttu-id="6bcf4-107">属性名</span><span class="sxs-lookup"><span data-stu-id="6bcf4-107">Attribute name</span></span>|<span data-ttu-id="6bcf4-108">説明</span><span class="sxs-lookup"><span data-stu-id="6bcf4-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6bcf4-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="6bcf4-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="6bcf4-110">この属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="6bcf4-111">それ以外の場合は **、name**属性によって制約名の値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="6bcf4-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="6bcf4-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="6bcf4-113">存在`PrimaryKey="true"`する場合 **、IsPrimaryKey**制約プロパティは**true**に設定され、主キーになります。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-113">If `PrimaryKey="true"` is present, the **IsPrimaryKey** constraint property is set to **true**, thus making it a primary key.</span></span> <span data-ttu-id="6bcf4-114">主キーは NULL 値を持つことができないため **、AllowDBNull**列プロパティは**false**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-114">The **AllowDBNull** column property is set to **false**, because primary keys cannot have null values.</span></span>|  
  
 <span data-ttu-id="6bcf4-115">キー制約が指定されているスキーマを変換する場合、マッピング プロセスは、制約内の各列に対して**AllowDBNull**列プロパティを**false**に設定して、テーブルに一意の制約を作成します。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-115">In converting schema in which a key constraint is specified, the mapping process creates a unique constraint on the table with the **AllowDBNull** column property set to **false** for each column in the constraint.</span></span> <span data-ttu-id="6bcf4-116">**一**意制約の**IsPrimaryKey**プロパティも、キー**false**要素に指定`msdata:PrimaryKey="true"`されていない限り false に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-116">The **IsPrimaryKey** property of the unique constraint is also set to **false** unless you have specified `msdata:PrimaryKey="true"` on the **key** element.</span></span> <span data-ttu-id="6bcf4-117">これは、スキーマに `PrimaryKey="true"` が指定される UNIQUE 制約と同じです。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-117">This is identical to a unique constraint in the schema in which `PrimaryKey="true"`.</span></span>  
  
 <span data-ttu-id="6bcf4-118">次のスキーマ例では **、key**要素は**CustomerID**要素のキー制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-118">In the following schema example, the **key** element specifies the key constraint on the **CustomerID** element.</span></span>  
  
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
  
 <span data-ttu-id="6bcf4-119">**key**要素は **、Customers**要素の**CustomerID**子要素の値が一意の値を持つ必要があり、null 値を持つことができないことを指定します。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-119">The **key** element specifies that the values of the **CustomerID** child element of the **Customers** element must have unique values and cannot have null values.</span></span> <span data-ttu-id="6bcf4-120">XML スキーマ定義言語 (XSD) スキーマの変換では、割り当て処理によって次のテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-120">In translating the XML Schema definition language (XSD) schema, the mapping process creates the following table:</span></span>  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="6bcf4-121">XML スキーマ マッピングでは、次<xref:System.Data.DataSet>の図のように **、CustomerID**列にも**一意の制約**が作成されます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-121">The XML Schema mapping also creates a **UniqueConstraint** on the **CustomerID** column, as shown in the following <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6bcf4-122">(わかりやすいように、関連するプロパティだけを示します)。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-122">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
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
  
 <span data-ttu-id="6bcf4-123">生成される**データセット**では、スキーマが**キー**要素で指定`msdata:PrimaryKey="true"`されているため、**一意制約**の**IsPrimaryKey**プロパティが**true**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-123">In the **DataSet** that is generated, the **IsPrimaryKey** property of the **UniqueConstraint** is set to **true** because the schema specifies `msdata:PrimaryKey="true"` in the **key** element.</span></span>  
  
 <span data-ttu-id="6bcf4-124">**データセット**内の**一意制約**の**制約名**プロパティの値は、スキーマの**キー**要素で指定された**msdata:制約名**属性の値です。</span><span class="sxs-lookup"><span data-stu-id="6bcf4-124">The value of the **ConstraintName** property of the **UniqueConstraint** in the **DataSet** is the value of the **msdata:ConstraintName** attribute specified in the **key** element in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcf4-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="6bcf4-125">See also</span></span>

- [<span data-ttu-id="6bcf4-126">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="6bcf4-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="6bcf4-127">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="6bcf4-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="6bcf4-128">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="6bcf4-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
