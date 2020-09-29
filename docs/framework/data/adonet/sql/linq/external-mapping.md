---
title: 外部マップ
ms.date: 03/30/2017
ms.assetid: 076606b8-d889-4ba0-b5da-ae577b146f23
ms.openlocfilehash: 79427cde0784746480e851cf1be56c8bce854919
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161387"
---
# <a name="external-mapping"></a><span data-ttu-id="3907b-102">外部マップ</span><span class="sxs-lookup"><span data-stu-id="3907b-102">External Mapping</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3907b-103">では、"*外部マッピング*" がサポートされています。これは、個別の XML ファイルを使用して、データベースのデータ モデルとオブジェクト モデルの間のマッピングを指定するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="3907b-103">supports *external mapping*, a process by which you use a separate XML file to specify mapping between the data model of the database and your object model.</span></span> <span data-ttu-id="3907b-104">外部マッピング ファイルを使用すると、次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="3907b-104">Advantages of using an external mapping file include the following:</span></span>  
  
- <span data-ttu-id="3907b-105">マッピング コードをアプリケーション コードから分離できます。</span><span class="sxs-lookup"><span data-stu-id="3907b-105">You can keep your mapping code out of your application code.</span></span> <span data-ttu-id="3907b-106">この方法により、アプリケーション コードの煩雑さが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="3907b-106">This approach reduces clutter in your application code.</span></span>  
  
- <span data-ttu-id="3907b-107">外部マッピング ファイルは、構成ファイルのような方法で扱うことができます。</span><span class="sxs-lookup"><span data-stu-id="3907b-107">You can treat an external mapping file something like a configuration file.</span></span> <span data-ttu-id="3907b-108">たとえば、バイナリを配布した後、外部マッピング ファイルを交換するだけでアプリケーションの動作を更新できます。</span><span class="sxs-lookup"><span data-stu-id="3907b-108">For example, you can update how your application behaves after shipping the binaries by just swapping out the external mapping file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3907b-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="3907b-109">Requirements</span></span>  

 <span data-ttu-id="3907b-110">マッピング ファイルは XML ファイルである必要があります。また、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のスキーマ定義 (.xsd) ファイルに対して有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3907b-110">The mapping file must be an XML file, and the file must validate against a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] schema definition (.xsd) file.</span></span>  
  
 <span data-ttu-id="3907b-111">次の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3907b-111">The following rules apply:</span></span>  
  
- <span data-ttu-id="3907b-112">マッピング ファイルは XML ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3907b-112">The mapping file must be an XML file.</span></span>  
  
- <span data-ttu-id="3907b-113">XML マッピング ファイルは、XML スキーマ定義ファイルに対して有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3907b-113">The XML mapping file must be valid against the XML schema definition file.</span></span> <span data-ttu-id="3907b-114">詳細については、[DBML ファイルおよび外部マッピング ファイルを検証する](how-to-validate-dbml-and-external-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3907b-114">For more information, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
- <span data-ttu-id="3907b-115">外部マッピングは、属性ベースのマッピングをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="3907b-115">External mapping overrides attribute-based mapping.</span></span> <span data-ttu-id="3907b-116">言い換えると、外部マッピング ソースを使って <xref:System.Data.Linq.DataContext> を作成した場合、<xref:System.Data.Linq.DataContext> はクラスに作成したすべてのマッピング属性を無視します。</span><span class="sxs-lookup"><span data-stu-id="3907b-116">In other words, when you use an external mapping source to create a <xref:System.Data.Linq.DataContext>, the <xref:System.Data.Linq.DataContext> ignores all mapping attributes you have created on classes.</span></span> <span data-ttu-id="3907b-117">この動作は、クラスが外部マッピング ファイルに含まれるかどうかにかかわらず適用されます。</span><span class="sxs-lookup"><span data-stu-id="3907b-117">This behavior is true whether the class is included in the external mapping file.</span></span>  
  
- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3907b-118">では、2 つのマッピング方法 (属性ベースと外部) を組み合わせて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3907b-118">does not support the hybrid use of the two mapping approaches (attribute-based and external).</span></span>  
  
## <a name="xml-schema-definition-file"></a><span data-ttu-id="3907b-119">XML スキーマ定義ファイル</span><span class="sxs-lookup"><span data-stu-id="3907b-119">XML Schema Definition File</span></span>  

 <span data-ttu-id="3907b-120">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の外部マッピングは、以下のような XML スキーマ定義に対して有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3907b-120">External mapping in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be valid against the following XML schema definition.</span></span>  
  
 <span data-ttu-id="3907b-121">このスキーマ定義ファイルを、DBML ファイルの検証に使われるスキーマ定義ファイルと区別してください。</span><span class="sxs-lookup"><span data-stu-id="3907b-121">Distinguish this schema definition file from the schema definition file that is used to validate a DBML file.</span></span> <span data-ttu-id="3907b-122">詳しくは、「[LINQ to SQL でのコード生成](code-generation-in-linq-to-sql.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3907b-122">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md)).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3907b-123">また、Visual Studio のユーザーには、この XSD ファイルが [XML スキーマ] ダイアログ ボックスに "LinqToSqlMapping.xsd" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="3907b-123">Visual Studio users will also find this XSD file in the XML Schemas dialog box as "LinqToSqlMapping.xsd".</span></span> <span data-ttu-id="3907b-124">外部マッピング ファイルを検証するためにこのファイルを正しく使用する方法については、「[方法: DBML ファイルおよび外部マッピング ファイルを検証する](how-to-validate-dbml-and-external-mapping-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3907b-124">To use this file correctly for validating an external mapping file, see [How to: Validate DBML and External Mapping Files](how-to-validate-dbml-and-external-mapping-files.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-16"?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema" targetNamespace="http://schemas.microsoft.com/linqtosql/mapping/2007" xmlns="http://schemas.microsoft.com/linqtosql/mapping/2007"  
elementFormDefault="qualified" >  
  <xs:element name="Database" type="Database" />  
  <xs:complexType name="Database">  
    <xs:sequence>  
      <xs:element name="Table" type="Table" minOccurs="0" maxOccurs="unbounded" />  
      <xs:element name="Function" type="Function" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Provider" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Table">  
    <xs:sequence>  
      <xs:element name="Type" type="Type" minOccurs="1" maxOccurs="1" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Type">  
    <xs:sequence>  
      <xs:choice minOccurs="0" maxOccurs="unbounded">  
        <xs:element name="Column" type="Column" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Association" type="Association" minOccurs="0" maxOccurs="unbounded" />  
      </xs:choice>  
      <xs:element name="Type" type="Type" minOccurs="0" maxOccurs="unbounded" />  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="InheritanceCode" type="xs:string" use="optional" />  
    <xs:attribute name="IsInheritanceDefault" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Column">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="IsPrimaryKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsDbGenerated" type="xs:boolean" use="optional" />  
    <xs:attribute name="CanBeNull" type="xs:boolean" use="optional" />  
    <xs:attribute name="UpdateCheck" type="UpdateCheck" use="optional" />  
    <xs:attribute name="IsDiscriminator" type="xs:boolean" use="optional" />  
    <xs:attribute name="Expression" type="xs:string" use="optional" />  
    <xs:attribute name="IsVersion" type="xs:boolean" use="optional" />  
    <xs:attribute name="AutoSync" type="AutoSync" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Association">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Member" type="xs:string" use="required" />  
    <xs:attribute name="Storage" type="xs:string" use="optional" />  
    <xs:attribute name="ThisKey" type="xs:string" use="optional" />  
    <xs:attribute name="OtherKey" type="xs:string" use="optional" />  
    <xs:attribute name="IsForeignKey" type="xs:boolean" use="optional" />  
    <xs:attribute name="IsUnique" type="xs:boolean" use="optional" />  
    <xs:attribute name="DeleteRule" type="xs:string" use="optional" />  
    <xs:attribute name="DeleteOnNull" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Function">  
    <xs:sequence>  
      <xs:element name="Parameter" type="Parameter" minOccurs="0" maxOccurs="unbounded" />  
      <xs:choice>  
        <xs:element name="ElementType" type="Type" minOccurs="0" maxOccurs="unbounded" />  
        <xs:element name="Return" type="Return" minOccurs="0" maxOccurs="1" />  
      </xs:choice>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Method" type="xs:string" use="required" />  
    <xs:attribute name="IsComposable" type="xs:boolean" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Parameter">  
    <xs:attribute name="Name" type="xs:string" use="optional" />  
    <xs:attribute name="Parameter" type="xs:string" use="required" />  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
    <xs:attribute name="Direction" type="ParameterDirection" use="optional" />  
  </xs:complexType>  
  <xs:complexType name="Return">  
    <xs:attribute name="DbType" type="xs:string" use="optional" />  
  </xs:complexType>  
  <xs:simpleType name="UpdateCheck">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="WhenChanged" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="ParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In" />  
      <xs:enumeration value="Out" />  
      <xs:enumeration value="InOut" />  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:simpleType name="AutoSync">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Never" />  
      <xs:enumeration value="OnInsert" />  
      <xs:enumeration value="OnUpdate" />  
      <xs:enumeration value="Always" />  
      <xs:enumeration value="Default" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3907b-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="3907b-125">See also</span></span>

- [<span data-ttu-id="3907b-126">LINQ to SQL でのコード生成</span><span class="sxs-lookup"><span data-stu-id="3907b-126">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="3907b-127">参照</span><span class="sxs-lookup"><span data-stu-id="3907b-127">Reference</span></span>](reference.md)
- [<span data-ttu-id="3907b-128">方法: オブジェクト モデルを外部ファイルとして生成する</span><span class="sxs-lookup"><span data-stu-id="3907b-128">How to: Generate the Object Model as an External File</span></span>](how-to-generate-the-object-model-as-an-external-file.md)
