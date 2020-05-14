---
title: XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150884"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="41d9b-102">XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="41d9b-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="41d9b-103">**keyref** 要素を使用すると、ドキュメント内の要素間にリンクを確立できます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="41d9b-104">これは、リレーショナル データベースの外部キーのリレーションシップと同様です。</span><span class="sxs-lookup"><span data-stu-id="41d9b-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="41d9b-105">スキーマに **keyref** 要素を指定すると、スキーマの割り当て処理時に keyref 要素がそれに対応する <xref:System.Data.DataSet> の列の外部キー制約に変換されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="41d9b-106">既定では、**keyref** 要素によってリレーションも生成され、リレーションに **ParentTable**、**ChildTable**、**ParentColumn**、**ChildColumn** プロパティが指定されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="41d9b-107">**keyref** 要素で指定できる **msdata** 属性を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="41d9b-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="41d9b-108">属性名</span><span class="sxs-lookup"><span data-stu-id="41d9b-108">Attribute name</span></span>|<span data-ttu-id="41d9b-109">説明</span><span class="sxs-lookup"><span data-stu-id="41d9b-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="41d9b-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="41d9b-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="41d9b-111">スキーマの **keyref** 要素で **ConstraintOnly="true"** を指定した場合、制約が作成されますが、リレーションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="41d9b-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="41d9b-112">この属性を指定しない (または **False** に設定する) 場合、制約およびリレーションが **DataSet** に作成されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="41d9b-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="41d9b-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="41d9b-114">**ConstraintName** 属性を指定した場合、その値が制約名として使用されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="41d9b-115">それ以外の場合、スキーマの **keyref** 要素の **name** 属性によって **DataSet** の制約名が設定されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="41d9b-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="41d9b-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="41d9b-117">スキーマの **keyref** 要素で **UpdateRule** 属性を指定した場合、その値が **DataSet** の **UpdateRule** 制約プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="41d9b-118">それ以外の場合、**UpdateRule** プロパティは **Cascade** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="41d9b-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="41d9b-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="41d9b-120">スキーマの **keyref** 要素で **DeleteRule** 属性を指定した場合、その値が **DataSet** の **DeleteRule** 制約プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="41d9b-121">それ以外の場合、**DeleteRule** プロパティは **Cascade** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="41d9b-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="41d9b-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="41d9b-123">スキーマの **keyref** 要素で **AcceptRejectRule** 属性を指定した場合、その値が **DataSet** の **AcceptRejectRule** 制約プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="41d9b-124">それ以外の場合、**AcceptRejectRule** プロパティは **None** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="41d9b-125">**Order** 要素の **OrderNumber** 子要素と **OrderDetail** 要素の **OrderNo** 子要素の間の **key** リレーションシップと **keyref** リレーションシップを指定するスキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41d9b-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="41d9b-126">例では、**OrderDetail** 要素の **OrderNumber** 子要素が、**Order** 要素の **OrderNo** キーの子要素を参照します。</span><span class="sxs-lookup"><span data-stu-id="41d9b-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="41d9b-127">XML スキーマ定義言語 (XSD) スキーマの割り当て処理によって、2 つのテーブルを持つ次の **DataSet** が生成されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="41d9b-128">さらに、**DataSet** によって次の制約が定義されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="41d9b-129">**Order** テーブルの一意制約。</span><span class="sxs-lookup"><span data-stu-id="41d9b-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="41d9b-130">**Order** テーブルと **OrderDetail** テーブルの間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="41d9b-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="41d9b-131">スキーマの 2 つの要素が入れ子になっていないため、**Nested** プロパティは **False** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="41d9b-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="41d9b-132">**OrderDetail** テーブルの外部キー制約。</span><span class="sxs-lookup"><span data-stu-id="41d9b-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41d9b-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="41d9b-133">See also</span></span>

- [<span data-ttu-id="41d9b-134">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="41d9b-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="41d9b-135">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="41d9b-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="41d9b-136">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="41d9b-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
