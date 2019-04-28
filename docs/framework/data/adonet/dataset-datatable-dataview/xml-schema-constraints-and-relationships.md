---
title: XML スキーマ制約およびリレーションシップ
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 990ae2eef8d9fbd28472494c989ae9ecca34251d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61606984"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="e5fec-102">XML スキーマ制約およびリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="e5fec-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="e5fec-103">XML スキーマ定義言語 (XSD) スキーマでは、制約を指定することができます (一意、キー、およびキー参照制約) との関係 (を使用して、 **msdata:Relationship**注釈)。</span><span class="sxs-lookup"><span data-stu-id="e5fec-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="e5fec-104">このトピックでは、XML スキーマで指定した制約およびリレーションシップを解釈して <xref:System.Data.DataSet> を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="e5fec-105">指定した XML スキーマで一般に、 **msdata:Relationship**注釈でのリレーションシップだけを生成する場合、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="e5fec-106">詳細については、次を参照してください。 [XML スキーマ (XSD) からの DataSet リレーションの生成](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="e5fec-107">制約を指定する (一意、キー、およびキー参照) で制約を生成する場合、**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="e5fec-108">このトピックの後に説明されているように、リレーションシップを生成するにはキー制約とキー参照制約も使用するので注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5fec-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="e5fec-109">キー制約およびキー参照制約によるリレーションシップの生成</span><span class="sxs-lookup"><span data-stu-id="e5fec-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="e5fec-110">指定する代わりに、 **msdata:Relationship**注釈、XML スキーマのマッピング プロセス中に、で制約だけでなく、リレーションシップを生成するために使用するキーとキー参照制約を指定できます**データセット**します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="e5fec-111">ただし、指定した場合`msdata:ConstraintOnly="true"`で、 **keyref**要素、**データセット**制約のみを含めるし、リレーションシップには含まれません。</span><span class="sxs-lookup"><span data-stu-id="e5fec-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="e5fec-112">次の例では、XML スキーマを含む**順序**と**OrderDetail**要素で、入れ子にされていません。</span><span class="sxs-lookup"><span data-stu-id="e5fec-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="e5fec-113">スキーマでは、キー制約とキー参照制約も指定します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="e5fec-114">**データセット**マッピング プロセスでは、XML スキーマの中に生成された、**順序**と**OrderDetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="e5fec-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="e5fec-115">さらに、**データセット**リレーションシップと制約が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5fec-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="e5fec-116">そのリレーションシップと制約の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="e5fec-117">スキーマで指定されていないこと、 **msdata:Relationship**の注釈。 リレーションシップを生成するキーとキー参照制約を使用する代わりに、します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="e5fec-118">前のスキーマ例では、**順序**と**OrderDetail**要素が入れ子になっていません。</span><span class="sxs-lookup"><span data-stu-id="e5fec-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="e5fec-119">入れ子になっている Order 要素と OrderDetail 要素を含むスキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="e5fec-120">ただし、ありません**msdata:Relationship**注釈が指定されています。 そのため、暗黙のリレーションがと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e5fec-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="e5fec-121">詳細については、次を参照してください。[マップ暗黙的なリレーションの間で入れ子になっているスキーマ要素](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="e5fec-122">スキーマでは、キー制約とキー参照制約も指定します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-122">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="e5fec-123">**データセット**結果の XML スキーマのマッピング プロセスの 2 つのテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e5fec-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="e5fec-124">**データセット**も 2 つのリレーションシップが含まれます (に基づいて 1 つ、 **msdata:relationship**キー制約または keyref 制約に基づいて、注釈、および、その他) とさまざまな制約。</span><span class="sxs-lookup"><span data-stu-id="e5fec-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="e5fec-125">リレーションおよび制約の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-125">The following example shows the relations and constraints.</span></span>  
  
```  
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="e5fec-126">入れ子になったテーブルを参照するキー参照制約が含まれるかどうか、 **msdata:IsNested ="true"** 注釈、**データセット**keyref 制約に基づいている 1 つの入れ子になったリレーションシップを作成し、キー/一意制約に関連します。</span><span class="sxs-lookup"><span data-stu-id="e5fec-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fec-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5fec-127">See also</span></span>

- [<span data-ttu-id="e5fec-128">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="e5fec-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="e5fec-129">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="e5fec-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
