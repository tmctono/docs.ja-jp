---
title: XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 4cc4cb530b7252f35469fd4bb43bf6da9c1a3e24
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64604025"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="ef1b7-102">XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="ef1b7-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="ef1b7-103">**Keyref**要素では、ドキュメント内の要素間のリンクを確立することができます。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="ef1b7-104">これは、リレーショナル データベースの外部キーのリレーションシップと同様です。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="ef1b7-105">スキーマが指定されている場合、 **keyref**要素で、要素の変換のテーブル内の列に対応する外部キー制約にスキーマのマッピング プロセス中に、<xref:System.Data.DataSet>します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ef1b7-106">既定で、 **keyref**要素で、リレーションシップも生成されます、 **ParentTable**、 **ChildTable**、 **ParentColumn**、および**ChildColumn**リレーションの指定されたプロパティ。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="ef1b7-107">次の表にアウトライン、 **msdata**属性で指定することができます、 **keyref**要素。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="ef1b7-108">属性名</span><span class="sxs-lookup"><span data-stu-id="ef1b7-108">Attribute name</span></span>|<span data-ttu-id="ef1b7-109">説明</span><span class="sxs-lookup"><span data-stu-id="ef1b7-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ef1b7-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="ef1b7-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="ef1b7-111">場合**ConstraintOnly ="true"** が指定されて、 **keyref**スキーマ内の要素、制約が作成されますが、リレーションシップは作成されません。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="ef1b7-112">この属性が指定されていない場合 (またはに設定されている**False**)、制約とリレーションシップの両方に作成されます、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="ef1b7-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="ef1b7-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="ef1b7-114">場合、 **ConstraintName**属性を指定すると、その値、制約の名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="ef1b7-115">それ以外の場合、**名前**の属性、 **keyref**スキーマ内の要素で、制約の名前を提供します、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="ef1b7-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="ef1b7-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="ef1b7-117">場合、 **UpdateRule**属性が指定されて、 **keyref**スキーマ内の要素、その値に割り当てられている、 **UpdateRule**制約プロパティ、 **データセット**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="ef1b7-118">それ以外の場合、 **UpdateRule**プロパティに設定されて**Cascade**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="ef1b7-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="ef1b7-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="ef1b7-120">場合、 **DeleteRule**属性が指定されて、 **keyref**スキーマ内の要素、その値に割り当てられている、 **DeleteRule**制約プロパティ、 **データセット**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="ef1b7-121">それ以外の場合、 **DeleteRule**プロパティに設定されて**Cascade**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="ef1b7-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="ef1b7-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="ef1b7-123">場合、 **AcceptRejectRule**属性が指定されて、 **keyref**スキーマ内の要素、その値に割り当てられている、 **AcceptRejectRule** 制約プロパティ**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="ef1b7-124">それ以外の場合、 **AcceptRejectRule**プロパティに設定されて**None**します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="ef1b7-125">次の例に示すスキーマが含まれています、**キー**と**keyref**間のリレーションシップ、 **OrderNumber**の子要素、**順序**要素と**OrderNo**の子要素、 **OrderDetail**要素。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="ef1b7-126">例では、 **OrderNumber**の子要素、 **OrderDetail**要素が参照する、 **OrderNo**のキーの子要素、**順序**要素。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="ef1b7-127">結果は次の XML スキーマ定義言語 (XSD) スキーマの割り当て処理**データセット**2 つのテーブル。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="ef1b7-128">さらに、**データセット**次の制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="ef1b7-129">Unique 制約、**順序**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="ef1b7-130">間のリレーションシップ、**順序**と**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="ef1b7-131">**入れ子になった**プロパティに設定されて**False**スキーマの 2 つの要素が入れ子にされていないためです。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="ef1b7-132">外部キー制約、 **OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="ef1b7-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ef1b7-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="ef1b7-133">See also</span></span>

- [<span data-ttu-id="ef1b7-134">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="ef1b7-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="ef1b7-135">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="ef1b7-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="ef1b7-136">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="ef1b7-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
