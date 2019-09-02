---
title: XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 611322065a4df53d1a3149ef4e1ca5592f149081
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203442"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="5e861-102">XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="5e861-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="5e861-103">**Keyref**要素を使用すると、ドキュメント内の要素間のリンクを確立できます。</span><span class="sxs-lookup"><span data-stu-id="5e861-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="5e861-104">これは、リレーショナル データベースの外部キーのリレーションシップと同様です。</span><span class="sxs-lookup"><span data-stu-id="5e861-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="5e861-105">スキーマで**keyref**要素が指定されている場合、要素はスキーママッピングプロセス中に、 <xref:System.Data.DataSet>のテーブル内の列に対応する外部キー制約に変換されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="5e861-106">既定では、 **keyref**要素は、リレーションシップに対して指定されている**parenttable**、 **childtable**、 **parenttable**、および**childtable**プロパティを使用して、リレーションシップも生成します。</span><span class="sxs-lookup"><span data-stu-id="5e861-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="5e861-107">次の表は、 **keyref**要素で指定できる**msdata**属性の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="5e861-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="5e861-108">属性名</span><span class="sxs-lookup"><span data-stu-id="5e861-108">Attribute name</span></span>|<span data-ttu-id="5e861-109">説明</span><span class="sxs-lookup"><span data-stu-id="5e861-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="5e861-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="5e861-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="5e861-111">スキーマの**keyref**要素で**ConstraintOnly = "true"** が指定されている場合、制約が作成されますが、リレーションシップは作成されません。</span><span class="sxs-lookup"><span data-stu-id="5e861-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="5e861-112">この属性が指定されていない場合 (または**False**に設定されている場合) は、制約とリレーションシップの両方が**DataSet**に作成されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="5e861-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="5e861-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="5e861-114">**ConstraintName**属性が指定されている場合、その値は制約の名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="5e861-115">それ以外の場合は、スキーマの**keyref**要素の**name**属性によって、**データセット**内の制約名が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="5e861-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="5e861-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="5e861-117">スキーマの**keyref**要素に**UpdateRule**属性が指定されている場合、その値は**データセット**の**UpdateRule** constraint プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5e861-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="5e861-118">それ以外の場合、 **UpdateRule**プロパティは**Cascade**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="5e861-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="5e861-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="5e861-120">スキーマの**keyref**要素に**DeleteRule**属性が指定されている場合、その値は**データセット**の**DeleteRule** constraint プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5e861-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="5e861-121">それ以外の場合、 **DeleteRule**プロパティは**Cascade**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="5e861-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="5e861-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="5e861-123">スキーマの**keyref**要素に**AcceptRejectRule**属性が指定されている場合、その値は**データセット**の**AcceptRejectRule** constraint プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="5e861-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="5e861-124">それ以外の場合、 **AcceptRejectRule**プロパティは**None**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="5e861-125">次の例には、 **Order**要素の**ordernumber**子要素と**ordernumber**の**ordernumber**子要素間の**キー**および**keyref**リレーションシップを指定するスキーマが含まれています。element.</span><span class="sxs-lookup"><span data-stu-id="5e861-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="5e861-126">この例では、 **Ordernumber**要素の**ordernumber**子要素は、 **Order**要素の**ordernumber**キー子要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="5e861-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="5e861-127">XML スキーマ定義言語 (XSD) スキーマのマッピングプロセスでは、次の2つのテーブルを含む**データセット**が生成されます。</span><span class="sxs-lookup"><span data-stu-id="5e861-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="5e861-128">また、**データセット**は、次の制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="5e861-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="5e861-129">**Order**テーブルに対する unique 制約です。</span><span class="sxs-lookup"><span data-stu-id="5e861-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="5e861-130">**Order**テーブルと**orderdetail**テーブル間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="5e861-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="5e861-131">2つの要素がスキーマで入れ子になっていないため、 **nested**プロパティは**False**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="5e861-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="5e861-132">**Orderdetail**テーブルの foreign key 制約。</span><span class="sxs-lookup"><span data-stu-id="5e861-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5e861-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e861-133">See also</span></span>

- [<span data-ttu-id="5e861-134">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="5e861-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="5e861-135">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="5e861-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="5e861-136">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="5e861-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
