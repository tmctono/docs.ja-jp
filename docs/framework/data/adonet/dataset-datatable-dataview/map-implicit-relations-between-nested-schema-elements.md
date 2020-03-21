---
title: 入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150964"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="699b8-102">入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て</span><span class="sxs-lookup"><span data-stu-id="699b8-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="699b8-103">XML スキーマ言語定義 (XSD) スキーマでは、複数の複合型を入れ子にして指定できます。</span><span class="sxs-lookup"><span data-stu-id="699b8-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="699b8-104">この場合、割り当て処理には既定の割り当てが適用されます。その際、<xref:System.Data.DataSet> に作成される内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="699b8-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="699b8-105">複合型 (親および子) それぞれに対して 1 つのテーブル。</span><span class="sxs-lookup"><span data-stu-id="699b8-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="699b8-106">親に UNIQUE 制約が存在しない場合は *、TableName*という名前のテーブル定義ごとに 1 つの追加の主キー列_Id *TableName*が親テーブルの名前になります。</span><span class="sxs-lookup"><span data-stu-id="699b8-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="699b8-107">追加の列を主キーとして識別する親テーブルの主キー制約 ( **IsPrimaryKey**プロパティを**True**に設定して )</span><span class="sxs-lookup"><span data-stu-id="699b8-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="699b8-108">制約には、Constraint\# (\# は、1、2、3 など) という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="699b8-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="699b8-109">たとえば、最初の制約の既定の名前は Constraint1 となります。</span><span class="sxs-lookup"><span data-stu-id="699b8-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="699b8-110">子テーブルの外部キー制約により、追加された列が親テーブルの主キーを参照する外部キーとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="699b8-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="699b8-111">制約は、*親テーブル*の名前が親テーブルの名前、子テーブルの名前である*場合\*\*、ParentTable_ChildTable*名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="699b8-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="699b8-112">その結果、親テーブルと子テーブル間のデータが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="699b8-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="699b8-113">次の例は **、OrderDetail**が**Order**の子要素であるスキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="699b8-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="699b8-114">XML スキーマ マッピング プロセスでは **、DataSet**に次の情報が作成されます。</span><span class="sxs-lookup"><span data-stu-id="699b8-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="699b8-115">**注文テーブル**と**注文明細**テーブル。</span><span class="sxs-lookup"><span data-stu-id="699b8-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="699b8-116">**Order**テーブルの一意性制約。</span><span class="sxs-lookup"><span data-stu-id="699b8-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="699b8-117">**プロパティが** **True**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="699b8-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="699b8-118">**OrderDetail**テーブルの外部キー制約。</span><span class="sxs-lookup"><span data-stu-id="699b8-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- <span data-ttu-id="699b8-119">**Order**テーブルと**OrderDetail**テーブルの間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="699b8-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="699b8-120">このリレーションシップの**入れ子になった**プロパティは **、Order**要素と**OrderDetail**要素がスキーマ内で入れ子になっているため **、True**に設定されます。</span><span class="sxs-lookup"><span data-stu-id="699b8-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="699b8-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="699b8-121">See also</span></span>

- [<span data-ttu-id="699b8-122">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="699b8-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="699b8-123">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="699b8-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="699b8-124">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="699b8-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
