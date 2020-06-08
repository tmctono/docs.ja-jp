---
title: <schemaImporterExtensions> の <add> 要素
description: <add> 要素は、XSD の型を .NET Framework の型にマッピングするために XmlSchemaImporter クラスで使用される型を追加します。
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- <add> element for <schemaImporterExtensions> element
ms.assetid: c828a558-094b-441e-9065-790b87315fa0
ms.openlocfilehash: 6fd8113ad39a22c927035fca574151ae8f002685
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288330"
---
# <a name="add-element-for-schemaimporterextensions"></a><span data-ttu-id="e56bf-103">\<schemaImporterExtensions> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-103">\<add> Element for \<schemaImporterExtensions></span></span>
<span data-ttu-id="e56bf-104">XSD 型を .NET Framework 型に対応付けるために、<xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="e56bf-104">Adds types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping XSD types to .NET Framework types.</span></span> <span data-ttu-id="e56bf-105">構成ファイルの詳細については、「[構成ファイル スキーマ](../../framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e56bf-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
\<schemaImporterExtensions>  
\<add>  
  
## <a name="syntax"></a><span data-ttu-id="e56bf-106">構文</span><span class="sxs-lookup"><span data-stu-id="e56bf-106">Syntax</span></span>  
  
```xml  
<add name = "typeName" type="fully qualified type [,Version=version number] [,Culture=culture] [,PublicKeyToken= token]"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e56bf-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-107">Attributes and Elements</span></span>  
 <span data-ttu-id="e56bf-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e56bf-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e56bf-109">属性</span><span class="sxs-lookup"><span data-stu-id="e56bf-109">Attributes</span></span>  
  
|<span data-ttu-id="e56bf-110">属性</span><span class="sxs-lookup"><span data-stu-id="e56bf-110">Attribute</span></span>|<span data-ttu-id="e56bf-111">説明</span><span class="sxs-lookup"><span data-stu-id="e56bf-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e56bf-112">**name**</span><span class="sxs-lookup"><span data-stu-id="e56bf-112">**name**</span></span>|<span data-ttu-id="e56bf-113">インスタンスの検索に使用される簡易名。</span><span class="sxs-lookup"><span data-stu-id="e56bf-113">A simple name that is used to find the instance.</span></span>|  
|<span data-ttu-id="e56bf-114">**type**</span><span class="sxs-lookup"><span data-stu-id="e56bf-114">**type**</span></span>|<span data-ttu-id="e56bf-115">必須です。</span><span class="sxs-lookup"><span data-stu-id="e56bf-115">Required.</span></span> <span data-ttu-id="e56bf-116">追加するスキーマ拡張クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e56bf-116">Specifies the schema  extension class to add.</span></span> <span data-ttu-id="e56bf-117">**type** 属性の値は 1 行で指定し、完全修飾型名を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56bf-117">The **type** attribute value must be on one line, and include the fully qualified type name.</span></span> <span data-ttu-id="e56bf-118">アセンブリをグローバル アセンブリ キャッシュ (GAC: Global Assembly Cache) に配置する場合は、バージョン、カルチャ、およびアセンブリの署名に使用した公開キーのトークンも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="e56bf-118">When the assembly is placed in the Global Assembly Cache (GAC), it must also include the version, culture, and public key token of the signed assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e56bf-119">子要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-119">Child Elements</span></span>  
 <span data-ttu-id="e56bf-120">なし。</span><span class="sxs-lookup"><span data-stu-id="e56bf-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e56bf-121">親要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e56bf-122">要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-122">Element</span></span>|<span data-ttu-id="e56bf-123">説明</span><span class="sxs-lookup"><span data-stu-id="e56bf-123">Description</span></span>|  
|-------------|-----------------|  
|\<schemaImporterExtensions>|<span data-ttu-id="e56bf-124"><xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e56bf-124">Contains the types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e56bf-125">例</span><span class="sxs-lookup"><span data-stu-id="e56bf-125">Example</span></span>  
 <span data-ttu-id="e56bf-126">型を対応付けるときに XmlSchemaImporter が使用できる拡張の型を追加するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e56bf-126">The following code example adds an extension type that the XmlSchemaImporter can use when mapping types.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e56bf-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="e56bf-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- [<span data-ttu-id="e56bf-128">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-128">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="e56bf-129">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="e56bf-129">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
