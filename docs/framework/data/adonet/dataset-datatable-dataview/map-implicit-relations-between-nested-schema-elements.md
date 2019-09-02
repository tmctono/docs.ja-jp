---
title: 入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: e9ea85db98a577991e06e0239a0738a2ca5bada6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203483"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a><span data-ttu-id="b4090-102">入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て</span><span class="sxs-lookup"><span data-stu-id="b4090-102">Map Implicit Relations Between Nested Schema Elements</span></span>
<span data-ttu-id="b4090-103">XML スキーマ言語定義 (XSD) スキーマでは、複数の複合型を入れ子にして指定できます。</span><span class="sxs-lookup"><span data-stu-id="b4090-103">An XML Schema definition language (XSD) schema can have complex types nested inside one another.</span></span> <span data-ttu-id="b4090-104">この場合、割り当て処理には既定の割り当てが適用されます。その際、<xref:System.Data.DataSet> に作成される内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b4090-104">In this case, the mapping process applies default mapping and creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="b4090-105">複合型 (親および子) それぞれに対して 1 つのテーブル。</span><span class="sxs-lookup"><span data-stu-id="b4090-105">One table for each of the complex types (parent and child).</span></span>  
  
- <span data-ttu-id="b4090-106">親に unique 制約が存在しない場合は、 *tablename*_Id という名前のテーブル定義ごとに主キー列が1つ追加されます。 *tablename*は親テーブルの名前です。</span><span class="sxs-lookup"><span data-stu-id="b4090-106">If no unique constraint exists on the parent, one additional primary key column per table definition named *TableName*_Id where *TableName* is the name of the parent table.</span></span>  
  
- <span data-ttu-id="b4090-107">親テーブルの primary key 制約で、追加の列を主キーとして識別します ( **IsPrimaryKey**プロパティを**True**に設定します)。</span><span class="sxs-lookup"><span data-stu-id="b4090-107">A primary key constraint on the parent table identifying the additional column as the primary key (by setting the **IsPrimaryKey** property to **True**).</span></span> <span data-ttu-id="b4090-108">制約には、Constraint\# (\# は、1、2、3 など) という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="b4090-108">The constraint is named Constraint\# where \# is 1, 2, 3, and so on.</span></span> <span data-ttu-id="b4090-109">たとえば、最初の制約の既定の名前は Constraint1 となります。</span><span class="sxs-lookup"><span data-stu-id="b4090-109">For example, the default name for the first constraint is Constraint1.</span></span>  
  
- <span data-ttu-id="b4090-110">子テーブルの外部キー制約により、追加された列が親テーブルの主キーを参照する外部キーとして認識されます。</span><span class="sxs-lookup"><span data-stu-id="b4090-110">A foreign key constraint on the child table identifying the additional column as the foreign key referring to the primary key of the parent table.</span></span> <span data-ttu-id="b4090-111">制約には*ParentTable_ChildTable*という名前が付けられます。 *parenttable*は親テーブルの名前、 *childtable*は子テーブルの名前です。</span><span class="sxs-lookup"><span data-stu-id="b4090-111">The constraint is named *ParentTable_ChildTable* where *ParentTable* is the name of the parent table and *ChildTable* is the name of the child table.</span></span>  
  
- <span data-ttu-id="b4090-112">その結果、親テーブルと子テーブル間のデータが関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="b4090-112">A data relation between the parent and child tables.</span></span>  
  
 <span data-ttu-id="b4090-113">次の例は、 **Orderdetail**が**Order**の子要素であるスキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4090-113">The following example shows a schema where **OrderDetail** is a child element of **Order**.</span></span>  
  
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
  
 <span data-ttu-id="b4090-114">XML スキーマの割り当て処理では、**データセット**に次のものが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b4090-114">The XML Schema mapping process creates the following in the **DataSet**:</span></span>  
  
- <span data-ttu-id="b4090-115">**Order**および**orderdetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b4090-115">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- <span data-ttu-id="b4090-116">**Order**テーブルに対する unique 制約です。</span><span class="sxs-lookup"><span data-stu-id="b4090-116">A unique constraint on the **Order** table.</span></span> <span data-ttu-id="b4090-117">**IsPrimaryKey**プロパティが**True**に設定されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b4090-117">Note that the **IsPrimaryKey** property is set to **True**.</span></span>  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
- <span data-ttu-id="b4090-118">**Orderdetail**テーブルの foreign key 制約。</span><span class="sxs-lookup"><span data-stu-id="b4090-118">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
- <span data-ttu-id="b4090-119">**Order**テーブルと**orderdetail**テーブル間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="b4090-119">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="b4090-120">**Order**および**orderdetail**要素がスキーマで入れ子になっているため、このリレーションシップの**nested**プロパティは**True**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b4090-120">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: Order_Id   
    ChildTable: OrderDetail  
    ChildColumns: Order_Id   
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b4090-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="b4090-121">See also</span></span>

- [<span data-ttu-id="b4090-122">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="b4090-122">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="b4090-123">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="b4090-123">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="b4090-124">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="b4090-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
