---
title: XML スキーマ (XSD) からの DataSet リレーションの生成
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: 2673280ebb94dcc10c130f3969f3e3250d3706a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198588"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="2c94e-102">XML スキーマ (XSD) からの DataSet リレーションの生成</span><span class="sxs-lookup"><span data-stu-id="2c94e-102">Generating DataSet Relations from XML Schema (XSD)</span></span>

<span data-ttu-id="2c94e-103"><xref:System.Data.DataSet> では、親子のリレーションを作成することにより、2 つ以上の列間の関連付けを行います。</span><span class="sxs-lookup"><span data-stu-id="2c94e-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="2c94e-104">XML スキーマ定義言語 (XSD) スキーマ内で **DataSet** のリレーションを表すには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2c94e-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="2c94e-105">入れ子になった複合型を指定する方法</span><span class="sxs-lookup"><span data-stu-id="2c94e-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="2c94e-106">**msdata:Relationship** 注釈を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="2c94e-107">**msdata:ConstraintOnly** 注釈を使用せずに **xs:keyref** を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="2c94e-108">入れ子になった複合型</span><span class="sxs-lookup"><span data-stu-id="2c94e-108">Nested Complex Types</span></span>  

 <span data-ttu-id="2c94e-109">スキーマ内で複数の複合型の定義が入れ子になっている場合は、それらの入れ子状の要素間に親子のリレーションシップがあります。</span><span class="sxs-lookup"><span data-stu-id="2c94e-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="2c94e-110">**OrderDetail** が **Order** 要素の子要素であることを示す XML スキーマのフラグメントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="2c94e-111">XML スキーマの割り当て処理によって、スキーマの入れ子になった複合型に対応する **DataSet** にテーブルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c94e-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="2c94e-112">また、生成されたテーブルの親 **-** 子列として使用される追加列も作成されます。</span><span class="sxs-lookup"><span data-stu-id="2c94e-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="2c94e-113">その親 **-** 子列ではリレーションシップが指定されますが、主キー制約や外部キー制約の指定とは異なるため注意してください。</span><span class="sxs-lookup"><span data-stu-id="2c94e-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="2c94e-114">msdata:Relationship 注釈</span><span class="sxs-lookup"><span data-stu-id="2c94e-114">msdata:Relationship Annotation</span></span>  

 <span data-ttu-id="2c94e-115">**msdata:Relationship** 注釈を使用すると、入れ子になっていないスキーマの要素間の親子のリレーションシップを明示的に指定できます。</span><span class="sxs-lookup"><span data-stu-id="2c94e-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="2c94e-116">**Relationship** 要素の構造を示す例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="2c94e-117">**msdata:Relationship** 注釈の属性は、リレーションシップに必要な **parentkey** 要素と **childkey** 要素、および属性と同様に親子のリレーションシップに必要な要素を示します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="2c94e-118">割り当て処理では、その情報に基づいて **DataSet** にテーブルを作成し、それらのテーブル間に主キーと外部キーのリレーションシップを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="2c94e-119">たとえば、同じレベルで (入れ子にせずに) **Order** 要素と **OrderDetail** 要素を指定するスキーマのフラグメントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="2c94e-120">スキーマに **msdata:Relationship** 注釈を指定すると、その 2 つの要素間に親子のリレーションシップが指定されます。</span><span class="sxs-lookup"><span data-stu-id="2c94e-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="2c94e-121">この場合、**msdata:Relationship** 注釈を使用してリレーションシップを明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c94e-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="2c94e-122">割り当て処理では、**Relationship** 要素を使用して、**DataSet** にある **Order** テーブルの **OrderNumber** 列と **OrderDetail** テーブルの **OrderNo** 列に親子のリレーションシップが生成されます。</span><span class="sxs-lookup"><span data-stu-id="2c94e-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="2c94e-123">割り当て処理で指定されるのはリレーションシップだけで、リレーショナル データベースにおける主キー制約や外部キー制約の場合とは異なり、該当する列の値に対する制約が自動的に指定されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2c94e-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="2c94e-124">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2c94e-124">In This Section</span></span>  

 [<span data-ttu-id="2c94e-125">入れ子になっているスキーマ要素間の暗黙的なリレーションの割り当て</span><span class="sxs-lookup"><span data-stu-id="2c94e-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="2c94e-126">XML スキーマ内で要素が入れ子になっている場合に、**DataSet** 内に暗黙的に作成される制約とリレーションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="2c94e-127">入れ子になっている要素に指定したリレーションシップの割り当て</span><span class="sxs-lookup"><span data-stu-id="2c94e-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="2c94e-128">XML スキーマで入れ子になっている要素に対して、**DataSet** におけるリレーションを明示的に設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="2c94e-129">入れ子になっていない要素間のリレーションの指定</span><span class="sxs-lookup"><span data-stu-id="2c94e-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="2c94e-130">XML スキーマで入れ子になっていない要素間に、**DataSet** におけるリレーションを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="2c94e-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c94e-131">Related Sections</span></span>  

 [<span data-ttu-id="2c94e-132">XML スキーマ (XSD) からの DataSet リレーショナル構造の派生</span><span class="sxs-lookup"><span data-stu-id="2c94e-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="2c94e-133">XML スキーマ定義言語 (XSD) スキーマから作成された **DataSet** のリレーショナル構造 (スキーマ) について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="2c94e-134">XML スキーマ (XSD) 制約の DataSet 制約への割り当て</span><span class="sxs-lookup"><span data-stu-id="2c94e-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="2c94e-135">**DataSet** での一意制約および外部キー制約の作成に使用する XML スキーマの要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2c94e-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c94e-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c94e-136">See also</span></span>

- [<span data-ttu-id="2c94e-137">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="2c94e-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
