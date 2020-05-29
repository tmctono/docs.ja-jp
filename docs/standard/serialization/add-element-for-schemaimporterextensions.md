---
title: <schemaImporterExtensions> の <add> 要素
description: <add> 要素は、XSD の型を .NET Framework の型にマッピングするために XmlSchemaImporter クラスで使用される型を追加します。
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 401d1ba9cc2f97e93d7851f96f73b552e6ed6356
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378473"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="7dfae-103">\<schemaImporterExtensions>の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="7dfae-104">XSD 型を .NET Framework 型に対応付けるために、<xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="7dfae-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="7dfae-105">構成ファイルの詳細については、「[構成ファイル スキーマ](../../../docs/framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7dfae-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="7dfae-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7dfae-106">\<configuration></span></span>  
<span data-ttu-id="7dfae-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="7dfae-107">\<system.xml.serialization></span></span>  
<span data-ttu-id="7dfae-108">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7dfae-108">\<schemaImporterExtensions></span></span>  
<span data-ttu-id="7dfae-109">\<add></span><span class="sxs-lookup"><span data-stu-id="7dfae-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dfae-110">構文</span><span class="sxs-lookup"><span data-stu-id="7dfae-110">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dfae-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7dfae-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7dfae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dfae-113">属性</span><span class="sxs-lookup"><span data-stu-id="7dfae-113">Attributes</span></span>  
  
|<span data-ttu-id="7dfae-114">属性</span><span class="sxs-lookup"><span data-stu-id="7dfae-114">Attribute</span></span>|<span data-ttu-id="7dfae-115">説明</span><span class="sxs-lookup"><span data-stu-id="7dfae-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dfae-116">**name**</span><span class="sxs-lookup"><span data-stu-id="7dfae-116">**name**</span></span>|<span data-ttu-id="7dfae-117">インスタンスの検索に使用される簡易名。</span><span class="sxs-lookup"><span data-stu-id="7dfae-117">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="7dfae-118">**type**</span><span class="sxs-lookup"><span data-stu-id="7dfae-118">**type**</span></span>|<span data-ttu-id="7dfae-119">必須です。</span><span class="sxs-lookup"><span data-stu-id="7dfae-119">Required.</span></span> <span data-ttu-id="7dfae-120">追加するスキーマ拡張クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="7dfae-120">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="7dfae-121">**type** 属性の値は 1 行で指定し、完全修飾型名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dfae-121">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="7dfae-122">アセンブリをグローバル アセンブリ キャッシュ (GAC: Global Assembly Cache) に配置する場合は、バージョン、カルチャ、およびアセンブリの署名に使用した公開キーのトークンも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="7dfae-122">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dfae-123">子要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-123">Child Elements</span></span>  
 <span data-ttu-id="7dfae-124">なし。</span><span class="sxs-lookup"><span data-stu-id="7dfae-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dfae-125">親要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7dfae-126">要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-126">Element</span></span>|<span data-ttu-id="7dfae-127">説明</span><span class="sxs-lookup"><span data-stu-id="7dfae-127">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7dfae-128">\<schemaImporterExtensions></span><span class="sxs-lookup"><span data-stu-id="7dfae-128">\<schemaImporterExtensions></span></span>|<span data-ttu-id="7dfae-129"><xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7dfae-129">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7dfae-130">例</span><span class="sxs-lookup"><span data-stu-id="7dfae-130">Example</span></span>  
 <span data-ttu-id="7dfae-131">型を対応付けるときに XmlSchemaImporter が使用できる拡張の型を追加するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="7dfae-131">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7dfae-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="7dfae-132">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="7dfae-133">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-133">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="7dfae-134">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="7dfae-134">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
