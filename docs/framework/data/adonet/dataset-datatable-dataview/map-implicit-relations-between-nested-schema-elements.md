---
title: 入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: dc5b81fd06f2860283c8c5fa028af4b945e2b1e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150964"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="0d25d-102">入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て</span><span class="sxs-lookup"><span data-stu-id="0d25d-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="0d25d-103">XML スキーマ言語定義 (XSD) スキーマでは、複数の複合型を入れ子にして指定できます。</span><span class="sxs-lookup"><span data-stu-id="0d25d-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="0d25d-104">この場合、割り当て処理には既定の割り当てが適用されます。その際、<xref:System.Data.DataSet> に作成される内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d25d-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="0d25d-105">複合型 (親および子) それぞれに対して 1 つのテーブル。</span><span class="sxs-lookup"><span data-stu-id="0d25d-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="0d25d-106">親に一意制約がない場合、テーブル定義ごとに 1 つの、*TableName*_Id という名前の追加主キー列。*TableName* は親テーブルの名前です、</span><span class="sxs-lookup"><span data-stu-id="0d25d-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="0d25d-107">追加された列を主キーとする、親テーブルに対する主キー制約 (**IsPrimaryKey** プロパティを **True** に設定することで)。</span><span class="sxs-lookup"><span data-stu-id="0d25d-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="0d25d-108">制約には、Constraint\# (\# は、1、2、3 など) という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="0d25d-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="0d25d-109">たとえば、最初の制約の既定の名前は Constraint1 となります。</span><span class="sxs-lookup"><span data-stu-id="0d25d-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="0d25d-110">子テーブルの外部キー制約により、追加された列が親テーブルの主キーを参照する外部キーとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="0d25d-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="0d25d-111">制約には *ParentTable_ChildTable* という名前が付けられます。ここで、*ParentTable* は親テーブルの名前、*ChildTable* は子テーブルの名前です。</span><span class="sxs-lookup"><span data-stu-id="0d25d-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="0d25d-112">その結果、親テーブルと子テーブル間のデータが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="0d25d-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="0d25d-113">**OrderDetail** が **Order** 要素の子要素であるスキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0d25d-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="0d25d-114">XML スキーマ マッピング処理によって **DataSet** に作成される内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d25d-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="0d25d-115">**Order** および **OrderDetail** テーブル。</span><span class="sxs-lookup"><span data-stu-id="0d25d-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="0d25d-116">**Order** テーブルの一意制約。</span><span class="sxs-lookup"><span data-stu-id="0d25d-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="0d25d-117">**IsPrimaryKey** プロパティが **True** に設定されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0d25d-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="0d25d-118">**OrderDetail** テーブルの外部キー制約。</span><span class="sxs-lookup"><span data-stu-id="0d25d-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- <span data-ttu-id="0d25d-119">**Order** テーブルと **OrderDetail** テーブルの間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="0d25d-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="0d25d-120">スキーマの **Order** 要素と **OrderDetail** 要素が入れ子になっているため、このリレーションシップの **Nested** プロパティは **True** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0d25d-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d25d-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d25d-121">See also</span></span>

- [<span data-ttu-id="0d25d-122">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="0d25d-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="0d25d-123">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="0d25d-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="0d25d-124">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="0d25d-124">ADO.NET Overview</span></span>](../ado-net-overview.md)
