---
title: XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150884"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="18466-102">XML スキーマ (XSD) のキー参照制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="18466-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="18466-103">**keyref**要素を使用すると、ドキュメント内の要素間のリンクを確立できます。</span><span class="sxs-lookup"><span data-stu-id="18466-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="18466-104">これは、リレーショナル データベースの外部キーのリレーションシップと同様です。</span><span class="sxs-lookup"><span data-stu-id="18466-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="18466-105">スキーマが**keyref**要素を指定している場合、要素はスキーマ マッピングプロセス中に、 のテーブルの列に対する対応する外部<xref:System.Data.DataSet>キー制約に変換されます。</span><span class="sxs-lookup"><span data-stu-id="18466-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="18466-106">既定では **、keyref**要素は、リレーションシップに指定された**親テーブル**、**子テーブル**、**親列**、**および子列**のプロパティを持つリレーションシップも生成します。</span><span class="sxs-lookup"><span data-stu-id="18466-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="18466-107">次の表に **、keyref**要素で指定できる**msdata**属性の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="18466-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="18466-108">属性名</span><span class="sxs-lookup"><span data-stu-id="18466-108">Attribute name</span></span>|<span data-ttu-id="18466-109">説明</span><span class="sxs-lookup"><span data-stu-id="18466-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="18466-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="18466-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="18466-111">スキーマの**keyref**要素に**制約のみ="true" が**指定されている場合、制約は作成されますが、リレーションシップは作成されません。</span><span class="sxs-lookup"><span data-stu-id="18466-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="18466-112">この属性が指定されていない (または**False**に設定されている) 場合、制約とリレーションの両方が**DataSet**に作成されます。</span><span class="sxs-lookup"><span data-stu-id="18466-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="18466-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="18466-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="18466-114">**制約名**属性を指定すると、その値が制約の名前として使用されます。</span><span class="sxs-lookup"><span data-stu-id="18466-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="18466-115">それ以外の場合は、スキーマ内の**keyref**要素の**name**属性が **、DataSet**に制約名を提供します。</span><span class="sxs-lookup"><span data-stu-id="18466-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="18466-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="18466-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="18466-117">**スキーマ**の**keyref**要素で属性が指定されている場合、その値は**DataSet**の**UpdateRule**制約プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="18466-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="18466-118">それ以外の場合は、**プロパティ**が**カスケード**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="18466-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="18466-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="18466-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="18466-120">スキーマの**keyref**要素で**DeleteRule**属性が指定されている場合、その値は**DataSet**の**DeleteRule**制約プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="18466-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="18466-121">それ以外の場合は **、DeleteRule**プロパティがカスケードに設定**されます**。</span><span class="sxs-lookup"><span data-stu-id="18466-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="18466-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="18466-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="18466-123">属性が**スキーマ**の**キー参照**要素で指定されている場合、その値は**データセット**の**AcceptRejectRule**制約プロパティに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="18466-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="18466-124">それ以外の場合は **、"拒否拒否ルールの受け入れ"** プロパティが **[なし]** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="18466-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="18466-125">次の例には **、Order**要素の OrderNumber 子要素と**OrderDetail**要素の**OrderNo** **OrderNo**子要素との間の**キー**と**キー参照**の関係を指定するスキーマが含まれています。</span><span class="sxs-lookup"><span data-stu-id="18466-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="18466-126">この例では **、OrderDetail**要素の **"OrderNumber/受注番号**" 子要素は **、Order**要素の **"OrderNo/順序**なし" キーの子要素を参照しています。</span><span class="sxs-lookup"><span data-stu-id="18466-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="18466-127">XML スキーマ定義言語 (XSD) スキーマ マッピング プロセスでは、次の**DataSet**が 2 つのテーブルで生成されます。</span><span class="sxs-lookup"><span data-stu-id="18466-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="18466-128">さらに、**データセットは**次の制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="18466-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="18466-129">**Order**テーブルの一意性制約。</span><span class="sxs-lookup"><span data-stu-id="18466-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="18466-130">**Order**テーブルと**OrderDetail**テーブルの間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="18466-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="18466-131">2 つの要素がスキーマ内で入れ子になっていないため **、Nested**プロパティは**False**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="18466-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="18466-132">**OrderDetail**テーブルの外部キー制約。</span><span class="sxs-lookup"><span data-stu-id="18466-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="18466-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="18466-133">See also</span></span>

- [<span data-ttu-id="18466-134">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="18466-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="18466-135">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="18466-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="18466-136">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="18466-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
