---
title: <schemaImporterExtensions> 要素
description: <schemaImporterExtensions> 要素は、XSD の型を .NET Framework の型にマッピングするために XmlSchemaImporter が使用する型を含みます。
ms.date: 03/30/2017
helpviewer_keywords:
- XML serialization, configuration
- schemaImporterExtensions element
- <schemaImporterExtensions> element
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
ms.openlocfilehash: c46c5cb6e01463723f0f2ce3873fb4a6ec0b4e60
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "84278403"
---
# <a name="schemaimporterextensions-element"></a><span data-ttu-id="49631-103">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="49631-103">\<schemaImporterExtensions> Element</span></span>
<span data-ttu-id="49631-104">XSD の型を .NET Framework の型にマッピングするために <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を含みます。</span><span class="sxs-lookup"><span data-stu-id="49631-104">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span> <span data-ttu-id="49631-105">構成ファイルの詳細については、「[構成ファイル スキーマ](../../framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49631-105">For more information about configuration files, see [Configuration File Schema](../../framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49631-106">構文</span><span class="sxs-lookup"><span data-stu-id="49631-106">Syntax</span></span>  
  
```xml  
<schemaImporterExtensions>  
    <!-- Add types -->  
</schemaImporterExtensions>  
```  
  
## <a name="child-elements"></a><span data-ttu-id="49631-107">子要素</span><span class="sxs-lookup"><span data-stu-id="49631-107">Child Elements</span></span>  
  
|<span data-ttu-id="49631-108">要素</span><span class="sxs-lookup"><span data-stu-id="49631-108">Element</span></span>|<span data-ttu-id="49631-109">説明</span><span class="sxs-lookup"><span data-stu-id="49631-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49631-110">\<schemaImporterExtensions> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="49631-110">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)|<span data-ttu-id="49631-111">マッピングを作成するために <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加します。</span><span class="sxs-lookup"><span data-stu-id="49631-111">Adds types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> to create mappings.</span></span>|  
  
## <a name="parent-elements"></a><span data-ttu-id="49631-112">親要素</span><span class="sxs-lookup"><span data-stu-id="49631-112">Parent Elements</span></span>  
  
|<span data-ttu-id="49631-113">要素</span><span class="sxs-lookup"><span data-stu-id="49631-113">Element</span></span>|<span data-ttu-id="49631-114">説明</span><span class="sxs-lookup"><span data-stu-id="49631-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="49631-115">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="49631-115">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="49631-116">XML シリアル化を制御する最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="49631-116">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="49631-117">例</span><span class="sxs-lookup"><span data-stu-id="49631-117">Example</span></span>  
 <span data-ttu-id="49631-118">XSD の型を .NET Framework の型にマッピングする際に <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加する方法を次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="49631-118">The following code example illustrates how to add types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =
        "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.xml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="49631-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="49631-119">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="49631-120">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="49631-120">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="49631-121">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="49631-121">\<dateTimeSerialization> Element</span></span>](datetimeserialization-element.md)
- [<span data-ttu-id="49631-122">\<schemaImporterExtensions> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="49631-122">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="49631-123">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="49631-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
