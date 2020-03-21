---
title: XML スキーマ制約およびリレーションシップ
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150715"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="2d9b3-102">XML スキーマ制約およびリレーションシップ</span><span class="sxs-lookup"><span data-stu-id="2d9b3-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="2d9b3-103">XML スキーマ定義言語 (XSD) スキーマでは、制約 (一意制約、キー制約、およびキー参照制約) とリレーションシップ **(msdata:Relationship**アノテーションを使用) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="2d9b3-104">このトピックでは、XML スキーマで指定した制約およびリレーションシップを解釈して <xref:System.Data.DataSet> を生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="2d9b3-105">一般に、XML スキーマでは、 **DataSet**でリレーションシップのみを生成する場合は **、 msdata:Relationship**アノテーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="2d9b3-106">詳細については、「 [XML スキーマからのデータセット関係の生成 (XSD)」](generating-dataset-relations-from-xml-schema-xsd.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="2d9b3-107">制約 (一意性、キー、およびキー参照) を指定するには、 **DataSet**で制約を生成します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="2d9b3-108">このトピックの後に説明されているように、リレーションシップを生成するにはキー制約とキー参照制約も使用するので注意してください。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="2d9b3-109">キー制約およびキー参照制約によるリレーションシップの生成</span><span class="sxs-lookup"><span data-stu-id="2d9b3-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="2d9b3-110">**msdata:Relationship**アノテーションを指定する代わりに、XML スキーママッピングプロセスで使用されるキー制約とキー参照制約を指定して、制約だけでなく**DataSet**内の関係も生成できます。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="2d9b3-111">ただし **、keyref** `msdata:ConstraintOnly="true"`要素で指定した場合 **、DataSet**には制約のみが含まれ、リレーションシップは含まれません。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="2d9b3-112">次の例は、入れ子になっていない**Order**要素と**OrderDetail**要素を含む XML スキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="2d9b3-113">スキーマでは、キー制約とキー参照制約も指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="2d9b3-114">XML スキーマ マッピング プロセス中に生成される**データセット**には **、Order**テーブルと**OrderDetail**テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="2d9b3-115">さらに、**データセット**にはリレーションシップと制約が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="2d9b3-116">そのリレーションシップと制約の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="2d9b3-117">スキーマは**msdata:リレーションシップ**アノテーションを指定しないことに注意してください。代わりに、キーとキー参照の拘束を使用してリレーションを生成します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
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
  
 <span data-ttu-id="2d9b3-118">前のスキーマの例では **、Order**要素と**OrderDetail**要素は入れ子になっていません。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="2d9b3-119">入れ子になっている Order 要素と OrderDetail 要素を含むスキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="2d9b3-120">ただし **、msdata:リレーションシップ**の注釈が指定されていません。したがって、暗黙のリレーションが想定されます。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="2d9b3-121">詳細については、「[入れ子になったスキーマ要素間の暗黙的な関係のマップ](map-implicit-relations-between-nested-schema-elements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="2d9b3-122">スキーマでは、キー制約とキー参照制約も指定します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="2d9b3-123">XML スキーマ マッピング プロセスの結果として得られる**DataSet**には、次の 2 つのテーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="2d9b3-124">**DataSet**には、2 つのリレーションシップ **(msdata: リレーションシップ**アノテーションに基づくものと、キー制約とキー参照制約に基づくリレーションシップ) とさまざまな制約も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="2d9b3-125">リレーションおよび制約の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-125">The following example shows the relations and constraints.</span></span>  
  
```text
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
  
 <span data-ttu-id="2d9b3-126">入れ子になったテーブルを参照するキー参照制約に**msdata:IsNested="true"** 注釈が含まれている場合 **、DataSet**は keyref 制約と関連する一意/キー制約に基づいて単一のネストされたリレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d9b3-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d9b3-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="2d9b3-127">See also</span></span>

- [<span data-ttu-id="2d9b3-128">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="2d9b3-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="2d9b3-129">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="2d9b3-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
