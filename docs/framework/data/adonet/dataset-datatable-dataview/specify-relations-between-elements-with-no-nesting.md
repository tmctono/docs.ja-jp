---
title: 入れ子になっていない要素間のリレーションの指定
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: 6684e992242d5c695f3c237f70de61b4dae1c48f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183404"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="df4b1-102">入れ子になっていない要素間のリレーションの指定</span><span class="sxs-lookup"><span data-stu-id="df4b1-102">Specify Relations Between Elements with No Nesting</span></span>

<span data-ttu-id="df4b1-103">要素が入れ子になっていない場合、暗黙的なリレーションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="df4b1-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="df4b1-104">それに対し、**msdata:Relationship** 注釈を使用すると、入れ子になっていない要素間にリレーションを明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="df4b1-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="df4b1-105">互いに入れ子になっていない **Order** 要素と **OrderDetail** 要素の間に **msdata:Relationship** 注釈を指定する XML スキーマの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="df4b1-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="df4b1-106">**msdata:Relationship** 注釈は、**Schema** 要素の子要素として指定します。</span><span class="sxs-lookup"><span data-stu-id="df4b1-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"
                            msdata:child="OrderDetail"
                            msdata:parentkey="OrderNumber"
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 <span data-ttu-id="df4b1-107">次に示すように、XML スキーマ定義言語 (XSD) スキーマ マッピング処理によって、**Order** テーブルと **OrderDetail** テーブルを含む <xref:System.Data.DataSet> が作成され、それらのテーブル間にリレーションシップが指定されます。</span><span class="sxs-lookup"><span data-stu-id="df4b1-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="df4b1-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="df4b1-108">See also</span></span>

- [<span data-ttu-id="df4b1-109">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="df4b1-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="df4b1-110">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="df4b1-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="df4b1-111">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="df4b1-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
