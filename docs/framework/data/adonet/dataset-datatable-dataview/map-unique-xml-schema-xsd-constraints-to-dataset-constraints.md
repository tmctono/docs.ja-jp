---
title: XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 650cd6b8b8149529f115f22a11d19178fbd6d302
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785374"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="e1e02-102">XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="e1e02-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="e1e02-103">XML スキーマ定義言語 (XSD) スキーマで、**一意**要素が要素または属性に一意性制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1e02-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="e1e02-104">XML スキーマをリレーショナル スキーマに変換する処理では、XML スキーマの要素または属性で指定した UNIQUE 制約が、生成される <xref:System.Data.DataTable> に対応する <xref:System.Data.DataSet> の UNIQUE 制約に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e1e02-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="e1e02-105">次の表にアウトライン、 **msdata**属性で指定することができます、**一意**要素。</span><span class="sxs-lookup"><span data-stu-id="e1e02-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="e1e02-106">属性名</span><span class="sxs-lookup"><span data-stu-id="e1e02-106">Attribute name</span></span>|<span data-ttu-id="e1e02-107">説明</span><span class="sxs-lookup"><span data-stu-id="e1e02-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="e1e02-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="e1e02-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="e1e02-109">この属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1e02-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="e1e02-110">それ以外の場合、**名前**属性は、制約の名前の値を提供します。</span><span class="sxs-lookup"><span data-stu-id="e1e02-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="e1e02-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="e1e02-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="e1e02-112">場合`PrimaryKey="true"`に存在するが、**一意**要素、unique 制約が作成され、 **IsPrimaryKey**プロパティに設定**true**。</span><span class="sxs-lookup"><span data-stu-id="e1e02-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="e1e02-113">次の例を使用する XML スキーマを示しています、**一意**一意性制約を指定する要素。</span><span class="sxs-lookup"><span data-stu-id="e1e02-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="e1e02-114">**一意**スキーマ内の要素を指定するすべての**顧客**ドキュメント内の要素のインスタンスの値、 **CustomerID**子要素は一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1e02-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="e1e02-115">ビル、**データセット**、マッピング プロセスがこのスキーマを読み取り、次の表を生成します。</span><span class="sxs-lookup"><span data-stu-id="e1e02-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="e1e02-116">マッピング プロセスで unique 制約を作成することも、 **CustomerID**列では、次に示すように**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="e1e02-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="e1e02-117">(わかりやすいように、関連するプロパティだけを示します)。</span><span class="sxs-lookup"><span data-stu-id="e1e02-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="e1e02-118">**データセット**、生成された、 **IsPrimaryKey**プロパティに設定されて**False**一意制約。</span><span class="sxs-lookup"><span data-stu-id="e1e02-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="e1e02-119">**一意**、列のプロパティを示す、 **CustomerID**列の値は一意である必要があります (で指定したとおり、null 参照になることができますが、 **AllowDBNull**列のプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="e1e02-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="e1e02-120">スキーマを変更し、省略可能な**msdata:PrimaryKey**属性に値**True**、unique 制約をテーブルに作成します。</span><span class="sxs-lookup"><span data-stu-id="e1e02-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="e1e02-121">**AllowDBNull**列のプロパティに設定されて**False**、および**IsPrimaryKey**プロパティに設定する制約の**True**のため、**CustomerID**主キー列の列。</span><span class="sxs-lookup"><span data-stu-id="e1e02-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="e1e02-122">XML スキーマの要素や属性を組み合わせて UNIQUE 制約を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e1e02-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="e1e02-123">次の例は、ことを指定する方法の組み合わせを示します**CustomerID**と**CompanyName**値はすべて一意である必要があります**顧客**任意のインスタンスで、追加する**xs:field**スキーマ内の要素。</span><span class="sxs-lookup"><span data-stu-id="e1e02-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="e1e02-124">これは、その結果で作成される制約**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="e1e02-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1e02-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1e02-125">See also</span></span>

- [<span data-ttu-id="e1e02-126">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="e1e02-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="e1e02-127">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="e1e02-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="e1e02-128">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e1e02-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
