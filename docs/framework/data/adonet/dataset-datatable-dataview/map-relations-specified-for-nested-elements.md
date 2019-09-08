---
title: 入れ子になっている要素に指定したリレーションシップの割り当て
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: e8cdf73b6277abdaab1256ca87e615a5e25e7336
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786085"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="b5b39-102">入れ子になっている要素に指定したリレーションシップの割り当て</span><span class="sxs-lookup"><span data-stu-id="b5b39-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="b5b39-103">スキーマには、スキーマ内の2つの要素間のマッピングを明示的に指定する**msdata: Relationship**注釈を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b5b39-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="b5b39-104">**Msdata: Relationship**で指定する2つの要素は、スキーマで入れ子にすることができますが、である必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b5b39-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="b5b39-105">マッピングプロセスでは、スキーマ内で**msdata: Relationship**を使用して、2つの列の間に主キー/外部キーのリレーションシップを生成します。</span><span class="sxs-lookup"><span data-stu-id="b5b39-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="b5b39-106">次の例は、 **Orderdetail**要素が**Order**の子要素である XML スキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="b5b39-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="b5b39-107">**Msdata: relationship**は、この親子リレーションシップを識別し、結果として得られる**Order**テーブルの**ordernumber**列が、結果の**ordernumber**テーブルの**ordernumber**列に関連付けられるように指定します。</span><span class="sxs-lookup"><span data-stu-id="b5b39-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
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
  
 <span data-ttu-id="b5b39-108">XML スキーマの割り当て処理によって <xref:System.Data.DataSet> に作成される内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b5b39-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="b5b39-109">**Order**および**orderdetail**テーブル。</span><span class="sxs-lookup"><span data-stu-id="b5b39-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="b5b39-110">**Order**テーブルと**orderdetail**テーブル間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="b5b39-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="b5b39-111">**Order**および**orderdetail**要素がスキーマで入れ子になっているため、このリレーションシップの**nested**プロパティは**True**に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b5b39-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="b5b39-112">割り当て処理によって制約は作成されません。</span><span class="sxs-lookup"><span data-stu-id="b5b39-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b39-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="b5b39-113">See also</span></span>

- [<span data-ttu-id="b5b39-114">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="b5b39-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="b5b39-115">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="b5b39-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="b5b39-116">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="b5b39-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
