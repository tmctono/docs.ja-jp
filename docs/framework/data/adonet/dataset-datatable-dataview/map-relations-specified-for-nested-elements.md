---
title: 入れ子になっている要素に指定したリレーションシップの割り当て
ms.date: 03/30/2017
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
ms.openlocfilehash: cd652f51f01dcfa16a8b707f35c658043c20670d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150897"
---
# <a name="map-relations-specified-for-nested-elements"></a><span data-ttu-id="a696e-102">入れ子になっている要素に指定したリレーションシップの割り当て</span><span class="sxs-lookup"><span data-stu-id="a696e-102">Map Relations Specified for Nested Elements</span></span>
<span data-ttu-id="a696e-103">スキーマには、その中の 2 つの要素間の割り当てを明示的に指定するために、**msdata:Relationship** 注釈をインクルードすることができます。</span><span class="sxs-lookup"><span data-stu-id="a696e-103">A schema can include an **msdata:Relationship** annotation to explicitly specify the mapping between any two elements in the schema.</span></span> <span data-ttu-id="a696e-104">**msdata:Relationship** で指定されたスキーマの 2 つの要素は、必要に応じて、入れ子にすることができます。</span><span class="sxs-lookup"><span data-stu-id="a696e-104">The two elements specified in **msdata:Relationship** can be nested in the schema, but do not have to be.</span></span> <span data-ttu-id="a696e-105">割り当て処理では、スキーマの **msdata:Relationship** を使用して 2 つの列間に主キー/外部キーのリレーションシップを生成します。</span><span class="sxs-lookup"><span data-stu-id="a696e-105">The mapping process uses **msdata:Relationship** in the schema to generate the primary key/foreign key relationship between the two columns.</span></span>  
  
 <span data-ttu-id="a696e-106">**OrderDetail** 要素が **Order** の子要素であることを示す XML スキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a696e-106">The following example shows an XML Schema in which the **OrderDetail** element is a child element of **Order**.</span></span> <span data-ttu-id="a696e-107">**msdata:Relationship** はこの親子のリレーションシップを識別し、生成された **Order** テーブルの **OrderNumber** 列と生成された **OrderDetail** テーブルの **OrderNo** 列が関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="a696e-107">The **msdata:Relationship** identifies this parent-child relationship and specifies that the **OrderNumber** column of the resulting **Order** table is related to the **OrderNo** column of the resulting **OrderDetail** table.</span></span>  
  
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
  
 <span data-ttu-id="a696e-108">XML スキーマの割り当て処理によって <xref:System.Data.DataSet> に作成される内容は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a696e-108">The XML Schema mapping process creates the following in the <xref:System.Data.DataSet>:</span></span>  
  
- <span data-ttu-id="a696e-109">**Order** および **OrderDetail** テーブル。</span><span class="sxs-lookup"><span data-stu-id="a696e-109">An **Order** and an **OrderDetail** table.</span></span>  
  
    ```text  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
- <span data-ttu-id="a696e-110">**Order** テーブルと **OrderDetail** テーブルの間のリレーションシップ。</span><span class="sxs-lookup"><span data-stu-id="a696e-110">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="a696e-111">スキーマの **Order** 要素と **OrderDetail** 要素が入れ子になっているため、このリレーションシップの **Nested** プロパティは **True** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="a696e-111">The **Nested** property for this relationship is set to **True** because the **Order** and **OrderDetail** elements are nested in the schema.</span></span>  
  
    ```text  
    ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 <span data-ttu-id="a696e-112">割り当て処理によって制約は作成されません。</span><span class="sxs-lookup"><span data-stu-id="a696e-112">The mapping process does not create any constraints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a696e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="a696e-113">See also</span></span>

- [<span data-ttu-id="a696e-114">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="a696e-114">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="a696e-115">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="a696e-115">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="a696e-116">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="a696e-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
