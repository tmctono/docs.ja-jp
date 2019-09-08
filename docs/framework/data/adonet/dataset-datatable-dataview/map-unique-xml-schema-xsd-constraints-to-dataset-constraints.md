---
title: XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 4aa94dfaf088a2a934c8901e2720f166d3a38dae
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784412"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="bca18-102">XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="bca18-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="bca18-103">XML スキーマ定義言語 (XSD) スキーマでは、 **unique**要素は要素または属性の一意性制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="bca18-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="bca18-104">XML スキーマをリレーショナル スキーマに変換する処理では、XML スキーマの要素または属性で指定した UNIQUE 制約が、生成される <xref:System.Data.DataTable> に対応する <xref:System.Data.DataSet> の UNIQUE 制約に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="bca18-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="bca18-105">次の表は、 **unique**要素で指定できる**msdata**属性の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="bca18-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="bca18-106">属性名</span><span class="sxs-lookup"><span data-stu-id="bca18-106">Attribute name</span></span>|<span data-ttu-id="bca18-107">説明</span><span class="sxs-lookup"><span data-stu-id="bca18-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bca18-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="bca18-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="bca18-109">この属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="bca18-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="bca18-110">それ以外の場合、 **name**属性は制約名の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="bca18-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="bca18-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="bca18-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="bca18-112">Unique `PrimaryKey="true"`要素にが存在する場合は、 **IsPrimaryKey**プロパティを**true**に設定して unique 制約が作成されます。</span><span class="sxs-lookup"><span data-stu-id="bca18-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="bca18-113">Unique 制約を指定するために**unique**要素を使用する XML スキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="bca18-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"   
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"   
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="bca18-114">スキーマ内の**unique**要素は、ドキュメントインスタンス内のすべての**Customers**要素について、 **CustomerID**子要素の値が一意である必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="bca18-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="bca18-115">**データセット**の構築では、マッピングプロセスによってこのスキーマが読み取られ、次のテーブルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bca18-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="bca18-116">また、次の**データセット**に示すように、マッピングプロセスによって**CustomerID**列に unique 制約が作成されます。</span><span class="sxs-lookup"><span data-stu-id="bca18-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="bca18-117">(わかりやすいように、関連するプロパティだけを示します)。</span><span class="sxs-lookup"><span data-stu-id="bca18-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="bca18-118">生成された**データセット**では、unique 制約に対して**IsPrimaryKey**プロパティが**False**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="bca18-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="bca18-119">列の**unique**プロパティは、 **CustomerID**列の値が一意である必要があることを示します (ただし、列の**allowdbnull**プロパティで指定されているように、null 参照にすることができます)。</span><span class="sxs-lookup"><span data-stu-id="bca18-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="bca18-120">スキーマを変更し、オプションの**msdata: PrimaryKey**属性値を**True**に設定すると、unique 制約がテーブルに作成されます。</span><span class="sxs-lookup"><span data-stu-id="bca18-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="bca18-121">**Allowdbnull**列のプロパティが**False**に設定され、制約の**IsPrimaryKey**プロパティが**True**に設定されているため、 **CustomerID**列が主キー列になります。</span><span class="sxs-lookup"><span data-stu-id="bca18-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="bca18-122">XML スキーマの要素や属性を組み合わせて UNIQUE 制約を指定できます。</span><span class="sxs-lookup"><span data-stu-id="bca18-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="bca18-123">次の例では、スキーマに別の**xs: field**要素を追加することにより、 **CustomerID**値と**CompanyName**値の組み合わせを任意のインスタンスのすべての**顧客**に対して一意にする必要があることを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="bca18-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="bca18-124">これは、結果の**データセット**で作成される制約です。</span><span class="sxs-lookup"><span data-stu-id="bca18-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="bca18-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="bca18-125">See also</span></span>

- [<span data-ttu-id="bca18-126">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="bca18-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="bca18-127">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="bca18-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="bca18-128">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="bca18-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
