---
title: <system.xml.serialization> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: f41e3811fc6bab8a354f75f46b0ac79c0ce42f99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018087"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="f5793-102">\<system.xml.serialization > 要素</span><span class="sxs-lookup"><span data-stu-id="f5793-102">\<system.xml.serialization> Element</span></span>
<span data-ttu-id="f5793-103">XML シリアル化を制御する最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="f5793-103">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="f5793-104">構成ファイルの詳細については、「[構成ファイル スキーマ](../../../docs/framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5793-104">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
 <span data-ttu-id="f5793-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f5793-105">\<configuration></span></span>  
<span data-ttu-id="f5793-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="f5793-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5793-107">構文</span><span class="sxs-lookup"><span data-stu-id="f5793-107">Syntax</span></span>  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5793-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5793-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f5793-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5793-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5793-110">属性</span><span class="sxs-lookup"><span data-stu-id="f5793-110">Attributes</span></span>  
 <span data-ttu-id="f5793-111">なし。</span><span class="sxs-lookup"><span data-stu-id="f5793-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f5793-112">子要素</span><span class="sxs-lookup"><span data-stu-id="f5793-112">Child Elements</span></span>  
  
|<span data-ttu-id="f5793-113">要素</span><span class="sxs-lookup"><span data-stu-id="f5793-113">Element</span></span>|<span data-ttu-id="f5793-114">説明</span><span class="sxs-lookup"><span data-stu-id="f5793-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5793-115">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="f5793-115">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="f5793-116"><xref:System.DateTime> オブジェクトのシリアル化モードを決定します。</span><span class="sxs-lookup"><span data-stu-id="f5793-116">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|  
|[<span data-ttu-id="f5793-117">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="f5793-117">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="f5793-118">XSD の型を .NET Framework の型にマッピングするために <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を含みます。</span><span class="sxs-lookup"><span data-stu-id="f5793-118">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5793-119">親要素</span><span class="sxs-lookup"><span data-stu-id="f5793-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f5793-120">要素</span><span class="sxs-lookup"><span data-stu-id="f5793-120">Element</span></span>|<span data-ttu-id="f5793-121">説明</span><span class="sxs-lookup"><span data-stu-id="f5793-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5793-122">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="f5793-122">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="f5793-123">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="f5793-123">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5793-124">例</span><span class="sxs-lookup"><span data-stu-id="f5793-124">Example</span></span>  
 <span data-ttu-id="f5793-125">次のコード例は、<xref:System.DateTime> オブジェクトのシリアル化モードを指定し、XSD の型を .NET Framework の型にマッピングするために <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f5793-125">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5793-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="f5793-126">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="f5793-127">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="f5793-127">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f5793-128">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="f5793-128">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="f5793-129">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="f5793-129">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="f5793-130">\<追加 > 要素の\<schemaImporterExtensions ></span><span class="sxs-lookup"><span data-stu-id="f5793-130">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
