---
title: 入れ子になっていない要素間のリレーションの指定
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: bee427c6cdf76792773ea827c8772b276ff29c31
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150819"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a><span data-ttu-id="39ff4-102">入れ子になっていない要素間のリレーションの指定</span><span class="sxs-lookup"><span data-stu-id="39ff4-102">Specify Relations Between Elements with No Nesting</span></span>
<span data-ttu-id="39ff4-103">要素が入れ子になっていない場合、暗黙的なリレーションは作成されません。</span><span class="sxs-lookup"><span data-stu-id="39ff4-103">When elements are not nested, no implicit relations are created.</span></span> <span data-ttu-id="39ff4-104">ただし **、msdata:Relationship**アノテーションを使用して、入れ子になっていない要素間のリレーションを明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="39ff4-104">You can, however, explicitly specify relations between elements that are not nested by using the **msdata:Relationship** annotation.</span></span>  
  
 <span data-ttu-id="39ff4-105">次の例は、入れ子になっていない順序と**OrderDetail**要素の間で**Order** **msdata:リレーションシップ**の注釈が指定されている XML スキーマを示しています。</span><span class="sxs-lookup"><span data-stu-id="39ff4-105">The following example shows an XML Schema in which the **msdata:Relationship** annotation is specified between the **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="39ff4-106">**msdata:リレーションシップ**の注釈は、**スキーマ**要素の子要素として指定されます。</span><span class="sxs-lookup"><span data-stu-id="39ff4-106">The **msdata:Relationship** annotation is specified as the child element of the **Schema** element.</span></span>  
  
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
  
 <span data-ttu-id="39ff4-107">XML スキーマ定義言語 (XSD) スキーマ マッピング<xref:System.Data.DataSet>プロセスでは、次に示すように **、Order**テーブルと**OrderDetail**テーブル、およびこれら 2 つのテーブル間で指定されたリレーションシップが作成されます。</span><span class="sxs-lookup"><span data-stu-id="39ff4-107">The XML Schema definition language (XSD) schema mapping process creates a <xref:System.Data.DataSet> with **Order** and **OrderDetail** tables and a relationship specified between these two tables, as shown below.</span></span>  
  
```text  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber
ChildTable: OrderDetail  
ChildColumns: OrderNo
Nested: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="39ff4-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="39ff4-108">See also</span></span>

- [<span data-ttu-id="39ff4-109">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="39ff4-109">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="39ff4-110">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="39ff4-110">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="39ff4-111">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="39ff4-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
