---
title: XML スキーマ (XSD) からの DataSet リレーションの生成
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: d00f07ee3338941b7de1bb890f71cd3c2d120246
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784646"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="98414-102">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="98414-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="98414-103"><xref:System.Data.DataSet> では、親子のリレーションを作成することにより、2 つ以上の列間の関連付けを行います。</span><span class="sxs-lookup"><span data-stu-id="98414-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="98414-104">XML スキーマ定義言語 (XSD) スキーマ内の**データセット**の関係を表すには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="98414-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="98414-105">入れ子になった複合型を指定する方法</span><span class="sxs-lookup"><span data-stu-id="98414-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="98414-106">**Msdata: Relationship**注釈を使用します。</span><span class="sxs-lookup"><span data-stu-id="98414-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="98414-107">**Msdata: ConstraintOnly**注釈を付けずに**xs: keyref**を指定します。</span><span class="sxs-lookup"><span data-stu-id="98414-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="98414-108">入れ子になった複合型</span><span class="sxs-lookup"><span data-stu-id="98414-108">Nested Complex Types</span></span>  
 <span data-ttu-id="98414-109">スキーマ内で複数の複合型の定義が入れ子になっている場合は、それらの入れ子状の要素間に親子のリレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="98414-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="98414-110">次の XML スキーマフラグメントは、 **Orderdetail**が**Order**要素の子要素であることを示しています。</span><span class="sxs-lookup"><span data-stu-id="98414-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="98414-111">XML スキーマの割り当て処理により、スキーマ内の入れ子になった複合型に対応するテーブルが**データセット**に作成されます。</span><span class="sxs-lookup"><span data-stu-id="98414-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="98414-112">また、生成されたテーブルの親 **-** 子列として使用される追加の列も作成されます。</span><span class="sxs-lookup"><span data-stu-id="98414-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="98414-113">これらの親子 **-** 列ではリレーションシップが指定されていることに注意してください。これは、primary key 制約または foreign key 制約を指定するのと同じではありません。</span><span class="sxs-lookup"><span data-stu-id="98414-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="98414-114">msdata:Relationship 注釈</span><span class="sxs-lookup"><span data-stu-id="98414-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="98414-115">**Msdata: Relationship**注釈を使用すると、入れ子になっていないスキーマ内の要素間の親子リレーションシップを明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="98414-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="98414-116">次の例は、**リレーションシップ**要素の構造を示しています。</span><span class="sxs-lookup"><span data-stu-id="98414-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="98414-117">**Msdata: relationship**注釈の属性は、リレーションシップに関係する**parentkey**要素と**childkey**要素および属性に加えて、親子リレーションシップに関係する要素を識別します。</span><span class="sxs-lookup"><span data-stu-id="98414-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="98414-118">このマッピングプロセスでは、この情報を使用して、**データセット**内のテーブルを生成し、これらのテーブル間に主キー/外部キーのリレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="98414-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="98414-119">たとえば、次のスキーマフラグメントでは、 **Order**および**orderdetail**要素が同じレベル (入れ子になっていない) で指定されています。</span><span class="sxs-lookup"><span data-stu-id="98414-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="98414-120">スキーマでは、これら2つの要素間の親子リレーションシップを指定する**msdata: Relationship**注釈を指定します。</span><span class="sxs-lookup"><span data-stu-id="98414-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="98414-121">この場合は、 **msdata: relationship**注釈を使用して明示的なリレーションシップを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98414-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="98414-122">マッピングプロセスでは、**リレーションシップ**要素を使用して、 **Order**テーブルの**Ordernumber**列と**データセット**の**ordernumber**テーブルの**ordernumber**列の間に親子リレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="98414-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="98414-123">割り当て処理で指定されるのはリレーションシップだけで、リレーショナル データベースにおける主キー制約や外部キー制約の場合とは異なり、該当する列の値に対する制約が自動的に指定されることはありません。</span><span class="sxs-lookup"><span data-stu-id="98414-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="98414-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="98414-124">In This Section</span></span>  
 [<span data-ttu-id="98414-125">入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て</span><span class="sxs-lookup"><span data-stu-id="98414-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="98414-126">XML スキーマで入れ子になった要素が検出された場合に、**データセット**に暗黙的に作成される制約とリレーションシップについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98414-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="98414-127">入れ子になっている要素に指定したリレーションシップの割り当て</span><span class="sxs-lookup"><span data-stu-id="98414-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="98414-128">XML スキーマの入れ子になった要素に対して、**データセット**内のリレーションを明示的に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98414-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="98414-129">入れ子になっていない要素間のリレーションの指定</span><span class="sxs-lookup"><span data-stu-id="98414-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="98414-130">入れ子になっていない XML スキーマ要素間の**データセット**内のリレーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="98414-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="98414-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="98414-131">Related Sections</span></span>  
 [<span data-ttu-id="98414-132">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="98414-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="98414-133">XML スキーマ定義言語 (XSD) スキーマから作成される**データセット**のリレーショナル構造 (スキーマ) について説明します。</span><span class="sxs-lookup"><span data-stu-id="98414-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="98414-134">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="98414-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="98414-135">**DataSet**で unique および foreign key 制約を作成するために使用される XML スキーマ要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="98414-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98414-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="98414-136">See also</span></span>

- [<span data-ttu-id="98414-137">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="98414-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
