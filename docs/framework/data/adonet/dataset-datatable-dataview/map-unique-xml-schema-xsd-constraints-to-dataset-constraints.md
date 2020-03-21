---
title: XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150845"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="a0153-102">XML スキーマ (XSD) の UNIQUE 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="a0153-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="a0153-103">XML スキーマ定義言語 (XSD) スキーマでは **、unique**要素は、要素または属性の一意性制約を指定します。</span><span class="sxs-lookup"><span data-stu-id="a0153-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="a0153-104">XML スキーマをリレーショナル スキーマに変換する処理では、XML スキーマの要素または属性で指定した UNIQUE 制約が、生成される <xref:System.Data.DataTable> に対応する <xref:System.Data.DataSet> の UNIQUE 制約に割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a0153-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="a0153-105">次の表は、**一意**の要素で指定できる**msdata**属性の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="a0153-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="a0153-106">属性名</span><span class="sxs-lookup"><span data-stu-id="a0153-106">Attribute name</span></span>|<span data-ttu-id="a0153-107">説明</span><span class="sxs-lookup"><span data-stu-id="a0153-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a0153-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="a0153-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="a0153-109">この属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0153-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="a0153-110">それ以外の場合は **、name**属性によって制約名の値が指定されます。</span><span class="sxs-lookup"><span data-stu-id="a0153-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="a0153-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="a0153-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="a0153-112">`PrimaryKey="true"`**一意**の要素に存在する場合は **、IsPrimaryKey**プロパティを true に設定して一意の制約が作成**されます**。</span><span class="sxs-lookup"><span data-stu-id="a0153-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="a0153-113">UNIQUE 要素を使用して**一意**性制約を指定する XML スキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a0153-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="a0153-114">スキーマ内の**一意**の要素は、ドキュメント インスタンス内のすべての**Customers**要素に対して **、CustomerID**子要素の値が一意である必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="a0153-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="a0153-115">**DataSet**を構築する場合、マッピング プロセスはこのスキーマを読み取り、次のテーブルを生成します。</span><span class="sxs-lookup"><span data-stu-id="a0153-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="a0153-116">マッピング プロセスでは、次の**DataSet**に示すように **、CustomerID**列に一意の制約も作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0153-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="a0153-117">(わかりやすいように、関連するプロパティだけを示します)。</span><span class="sxs-lookup"><span data-stu-id="a0153-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
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
  
 <span data-ttu-id="a0153-118">生成される**データセット**では、一意制約に対して**IsPrimaryKey**プロパティが**False**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a0153-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="a0153-119">列の**一意**のプロパティは **、CustomerID**列の値が一意である必要があることを示します (ただし、列の**AllowDBNull**プロパティで指定された null 参照を指定できます)。</span><span class="sxs-lookup"><span data-stu-id="a0153-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="a0153-120">スキーマを変更し、オプションの**msdata:PrimaryKey**属性値を**True**に設定すると、テーブルに UNIQUE 制約が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0153-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="a0153-121">**AllowDBNull**列プロパティは**False**に設定され、制約の**IsPrimaryKey**プロパティは**True**に設定されているため **、CustomerID**列は主キー列になります。</span><span class="sxs-lookup"><span data-stu-id="a0153-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="a0153-122">XML スキーマの要素や属性を組み合わせて UNIQUE 制約を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a0153-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="a0153-123">次の例では、スキーマに別の**xs:field**要素を追加することによって **、CustomerID**と**CompanyName**の値の組み合わせが、任意のインスタンス内のすべての**顧客**に対して一意である必要があることを指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a0153-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="a0153-124">これは、結果として得られる**DataSet**で作成される制約です。</span><span class="sxs-lookup"><span data-stu-id="a0153-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="a0153-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0153-125">See also</span></span>

- [<span data-ttu-id="a0153-126">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="a0153-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="a0153-127">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="a0153-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="a0153-128">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="a0153-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
