---
title: <schemaImporterExtensions> の <add> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 89196b094d5631c9e243a51a718e53f9c06db20d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794980"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="7d55d-102">\<追加 > 要素の\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="7d55d-102">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="7d55d-103">XSD 型を .NET Framework 型に対応付けるために、<xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="7d55d-103">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="7d55d-104">構成ファイルの詳細については、「[構成ファイル スキーマ](../../../docs/framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d55d-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="7d55d-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d55d-105">\<configuration></span></span>  
<span data-ttu-id="7d55d-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7d55d-106">\<system.xml.serialization></span></span>  
<span data-ttu-id="7d55d-107">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7d55d-107">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="7d55d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="7d55d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d55d-109">構文</span><span class="sxs-lookup"><span data-stu-id="7d55d-109">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d55d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d55d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d55d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d55d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d55d-112">属性</span><span class="sxs-lookup"><span data-stu-id="7d55d-112">Attributes</span></span>  
  
|<span data-ttu-id="7d55d-113">属性</span><span class="sxs-lookup"><span data-stu-id="7d55d-113">Attribute</span></span>|<span data-ttu-id="7d55d-114">説明</span><span class="sxs-lookup"><span data-stu-id="7d55d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d55d-115">**name**</span><span class="sxs-lookup"><span data-stu-id="7d55d-115">**name**</span></span>|<span data-ttu-id="7d55d-116">インスタンスの検索に使用される簡易名。</span><span class="sxs-lookup"><span data-stu-id="7d55d-116">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="7d55d-117">**type**</span><span class="sxs-lookup"><span data-stu-id="7d55d-117">**type**</span></span>|<span data-ttu-id="7d55d-118">必須。</span><span class="sxs-lookup"><span data-stu-id="7d55d-118">Required.</span></span> <span data-ttu-id="7d55d-119">追加するスキーマ拡張クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7d55d-119">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="7d55d-120">**type** 属性の値は 1 行で指定し、完全修飾型名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d55d-120">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="7d55d-121">アセンブリをグローバル アセンブリ キャッシュ (GAC: Global Assembly Cache) に配置する場合は、バージョン、カルチャ、およびアセンブリの署名に使用した公開キーのトークンも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d55d-121">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d55d-122">子要素</span><span class="sxs-lookup"><span data-stu-id="7d55d-122">Child Elements</span></span>  
 <span data-ttu-id="7d55d-123">なし。</span><span class="sxs-lookup"><span data-stu-id="7d55d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d55d-124">親要素</span><span class="sxs-lookup"><span data-stu-id="7d55d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7d55d-125">要素</span><span class="sxs-lookup"><span data-stu-id="7d55d-125">Element</span></span>|<span data-ttu-id="7d55d-126">説明</span><span class="sxs-lookup"><span data-stu-id="7d55d-126">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d55d-127">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7d55d-127">\<schemaImporterExtensions></span></span>|<span data-ttu-id="7d55d-128"><xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7d55d-128">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7d55d-129">例</span><span class="sxs-lookup"><span data-stu-id="7d55d-129">Example</span></span>  
 <span data-ttu-id="7d55d-130">型を対応付けるときに XmlSchemaImporter が使用できる拡張の型を追加するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7d55d-130">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <schemaImporterExtensions>  
       <add name="contoso" type="System.Web.Mobile.MobileCapabilities,   
       System.Web.Mobile, Version=2.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a" />   
    </schemaImporterExtensions>  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d55d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d55d-131">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="7d55d-132">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="7d55d-132">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="7d55d-133">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="7d55d-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
