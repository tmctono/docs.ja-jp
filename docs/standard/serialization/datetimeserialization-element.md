---
title: <dateTimeSerialization> 要素
description: この記事では、DateTime オブジェクトのシリアル化モードを決定する <dateTimeSerialization> 要素について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 652a88e25f59cd905e47ef71351e47e67f375286
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375826"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="ab4cb-103">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-103">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="ab4cb-104"><xref:System.DateTime> オブジェクトのシリアル化モードを決定します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-104">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="ab4cb-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ab4cb-105">\<configuration></span></span>  
<span data-ttu-id="ab4cb-106">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="ab4cb-106">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab4cb-107">構文</span><span class="sxs-lookup"><span data-stu-id="ab4cb-107">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ab4cb-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ab4cb-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ab4cb-110">属性</span><span class="sxs-lookup"><span data-stu-id="ab4cb-110">Attributes</span></span>  
  
|<span data-ttu-id="ab4cb-111">属性</span><span class="sxs-lookup"><span data-stu-id="ab4cb-111">Attributes</span></span>|<span data-ttu-id="ab4cb-112">説明</span><span class="sxs-lookup"><span data-stu-id="ab4cb-112">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="ab4cb-113">任意。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-113">Optional.</span></span> <span data-ttu-id="ab4cb-114">シリアル化モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-114">Specifies the serialization mode.</span></span> <span data-ttu-id="ab4cb-115"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 値のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-115">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="ab4cb-116">既定値は **RoundTrip** です。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-116">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ab4cb-117">子要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-117">Child Elements</span></span>  
 <span data-ttu-id="ab4cb-118">なし。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ab4cb-119">親要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ab4cb-120">要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-120">Element</span></span>|<span data-ttu-id="ab4cb-121">説明</span><span class="sxs-lookup"><span data-stu-id="ab4cb-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab4cb-122">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="ab4cb-122">system.xml.serialization</span></span>|<span data-ttu-id="ab4cb-123">XML シリアル化を制御する最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-123">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab4cb-124">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab4cb-124">Remarks</span></span>  
 <span data-ttu-id="ab4cb-125">.NET Framework の 1.0、1.1、2.0、およびそれ以降のバージョンで、このプロパティが **Local** に設定されている場合、<xref:System.DateTime> オブジェクトは常に現地時刻として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-125">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="ab4cb-126">つまり、ローカル タイム ゾーンの情報が、シリアル化されたデータに必ず組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-126">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="ab4cb-127">.NET Framework の以前のバージョンとの互換性を保証するには、このプロパティを **Local** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-127">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ab4cb-128">このプロパティが **Roundtrip** に設定されているバージョン 2.0 以降の .NET Framework では、<xref:System.DateTime> オブジェクトが調べられ、タイム ゾーンがローカル、UTC、または未指定のいずれであるかが特定されます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-128">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="ab4cb-129">その後、この特定された情報を保持する形で、<xref:System.DateTime> オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-129">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="ab4cb-130">これは既定の動作であり、.NET Framework の以前のバージョンと通信を行わない、すべての新しいアプリケーションで推奨されます。</span><span class="sxs-lookup"><span data-stu-id="ab4cb-130">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4cb-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ab4cb-131">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="ab4cb-132">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="ab4cb-132">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ab4cb-133">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-133">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- <span data-ttu-id="ab4cb-134">[\<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-134">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>
- [<span data-ttu-id="ab4cb-135">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="ab4cb-135">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
