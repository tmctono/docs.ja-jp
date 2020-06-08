---
title: <dateTimeSerialization> 要素
description: この記事では、DateTime オブジェクトのシリアル化モードを決定する <dateTimeSerialization> 要素について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: a2684ab72c1fb109d711e333e01836d3399caf86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "84289643"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="c17b1-103">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="c17b1-104"><xref:System.DateTime> オブジェクトのシリアル化モードを決定します。</span><span class="sxs-lookup"><span data-stu-id="c17b1-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 \<configuration>  
\<dateTimeSerialization>  
  
## <a name="syntax"></a><span data-ttu-id="c17b1-105">構文</span><span class="sxs-lookup"><span data-stu-id="c17b1-105">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c17b1-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c17b1-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c17b1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c17b1-108">属性</span><span class="sxs-lookup"><span data-stu-id="c17b1-108">Attributes</span></span>  
  
|<span data-ttu-id="c17b1-109">属性</span><span class="sxs-lookup"><span data-stu-id="c17b1-109">Attributes</span></span>|<span data-ttu-id="c17b1-110">説明</span><span class="sxs-lookup"><span data-stu-id="c17b1-110">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="c17b1-111">任意。</span><span class="sxs-lookup"><span data-stu-id="c17b1-111">Optional.</span></span> <span data-ttu-id="c17b1-112">シリアル化モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="c17b1-112">Specifies the serialization mode.</span></span> <span data-ttu-id="c17b1-113"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 値のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="c17b1-113">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="c17b1-114">既定値は **RoundTrip** です。</span><span class="sxs-lookup"><span data-stu-id="c17b1-114">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c17b1-115">子要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-115">Child Elements</span></span>  
 <span data-ttu-id="c17b1-116">なし。</span><span class="sxs-lookup"><span data-stu-id="c17b1-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c17b1-117">親要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c17b1-118">要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-118">Element</span></span>|<span data-ttu-id="c17b1-119">説明</span><span class="sxs-lookup"><span data-stu-id="c17b1-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c17b1-120">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="c17b1-120">system.xml.serialization</span></span>|<span data-ttu-id="c17b1-121">XML シリアル化を制御する最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="c17b1-121">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c17b1-122">Remarks</span><span class="sxs-lookup"><span data-stu-id="c17b1-122">Remarks</span></span>  
 <span data-ttu-id="c17b1-123">.NET Framework の 1.0、1.1、2.0、およびそれ以降のバージョンで、このプロパティが **Local** に設定されている場合、<xref:System.DateTime> オブジェクトは常に現地時刻として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="c17b1-123">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="c17b1-124">つまり、ローカル タイム ゾーンの情報が、シリアル化されたデータに必ず組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="c17b1-124">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="c17b1-125">.NET Framework の以前のバージョンとの互換性を保証するには、このプロパティを **Local** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c17b1-125">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="c17b1-126">このプロパティが **Roundtrip** に設定されているバージョン 2.0 以降の .NET Framework では、<xref:System.DateTime> オブジェクトが調べられ、タイム ゾーンがローカル、UTC、または未指定のいずれであるかが特定されます。</span><span class="sxs-lookup"><span data-stu-id="c17b1-126">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="c17b1-127">その後、この特定された情報を保持する形で、<xref:System.DateTime> オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="c17b1-127">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="c17b1-128">これは既定の動作であり、.NET Framework の以前のバージョンと通信を行わない、すべての新しいアプリケーションで推奨されます。</span><span class="sxs-lookup"><span data-stu-id="c17b1-128">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c17b1-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c17b1-129">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="c17b1-130">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c17b1-130">Configuration File Schema</span></span>](../../framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c17b1-131">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-131">\<schemaImporterExtensions> Element</span></span>](schemaimporterextensions-element.md)
- [<span data-ttu-id="c17b1-132">\<schemaImporterExtensions> の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-132">\<add> Element for \<schemaImporterExtensions></span></span>](add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="c17b1-133">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="c17b1-133">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
