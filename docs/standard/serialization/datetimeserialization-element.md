---
title: <dateTimeSerialization> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- dateTimeSerialization element
- XML serialization, configuration
- <dateTimeSerialization> element
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
ms.openlocfilehash: 180a4942dd4b701b56fe4788d5f8cd8607faaedd
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459265"
---
# <a name="datetimeserialization-element"></a><span data-ttu-id="aa2c5-102">\<dateTimeSerialization > 要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-102">\<dateTimeSerialization> Element</span></span>
<span data-ttu-id="aa2c5-103"><xref:System.DateTime> オブジェクトのシリアル化モードを決定します。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-103">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>  
  
 <span data-ttu-id="aa2c5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="aa2c5-104">\<configuration></span></span>  
<span data-ttu-id="aa2c5-105">\<dateTimeSerialization></span><span class="sxs-lookup"><span data-stu-id="aa2c5-105">\<dateTimeSerialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa2c5-106">構文</span><span class="sxs-lookup"><span data-stu-id="aa2c5-106">Syntax</span></span>  
  
```xml  
<dateTimeSerialization  
    mode = "Roundtrip|Local"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa2c5-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="aa2c5-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa2c5-109">属性</span><span class="sxs-lookup"><span data-stu-id="aa2c5-109">Attributes</span></span>  
  
|<span data-ttu-id="aa2c5-110">属性</span><span class="sxs-lookup"><span data-stu-id="aa2c5-110">Attributes</span></span>|<span data-ttu-id="aa2c5-111">説明</span><span class="sxs-lookup"><span data-stu-id="aa2c5-111">Description</span></span>|  
|----------------|-----------------|  
|`mode`|<span data-ttu-id="aa2c5-112">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-112">Optional.</span></span> <span data-ttu-id="aa2c5-113">シリアル化モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-113">Specifies the serialization mode.</span></span> <span data-ttu-id="aa2c5-114"><xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 値のいずれかに設定します。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-114">Set to one of the <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> values.</span></span> <span data-ttu-id="aa2c5-115">既定値は **RoundTrip** です。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-115">The default is **RoundTrip**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa2c5-116">子要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-116">Child Elements</span></span>  
 <span data-ttu-id="aa2c5-117">なし。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa2c5-118">親要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aa2c5-119">要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-119">Element</span></span>|<span data-ttu-id="aa2c5-120">説明</span><span class="sxs-lookup"><span data-stu-id="aa2c5-120">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa2c5-121">system.xml.serialization</span><span class="sxs-lookup"><span data-stu-id="aa2c5-121">system.xml.serialization</span></span>|<span data-ttu-id="aa2c5-122">XML シリアル化を制御する最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-122">The top-level element for controlling XML serialization.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa2c5-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="aa2c5-123">Remarks</span></span>  
 <span data-ttu-id="aa2c5-124">.NET Framework の 1.0、1.1、2.0、およびそれ以降のバージョンで、このプロパティが **Local** に設定されている場合、<xref:System.DateTime> オブジェクトは常に現地時刻として書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-124">In versions 1.0, 1.1, 2.0 and later versions of the .NET Framework, when this property is set to **Local**, <xref:System.DateTime> objects are always formatted as the local time.</span></span> <span data-ttu-id="aa2c5-125">つまり、ローカル タイム ゾーンの情報が、シリアル化されたデータに必ず組み込まれます。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-125">That is, local time zone information is always included with the serialized data.</span></span> <span data-ttu-id="aa2c5-126">.NET Framework の以前のバージョンとの互換性を保証するには、このプロパティを **Local** に設定します。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-126">Set this property to **Local** to ensure compatibility with older versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="aa2c5-127">このプロパティが **Roundtrip** に設定されているバージョン 2.0 以降の .NET Framework では、<xref:System.DateTime> オブジェクトが調べられ、タイム ゾーンがローカル、UTC、または未指定のいずれであるかが特定されます。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-127">In version 2.0 and later versions of the .NET Framework that have this property set to **Roundtrip**, <xref:System.DateTime> objects are examined to determine whether they are in the local, UTC, or an unspecified time zone.</span></span> <span data-ttu-id="aa2c5-128">その後、この特定された情報を保持する形で、<xref:System.DateTime> オブジェクトがシリアル化されます。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-128">The <xref:System.DateTime> objects are then serialized in such a way that this information is preserved.</span></span> <span data-ttu-id="aa2c5-129">これは既定の動作であり、.NET Framework の以前のバージョンと通信を行わない、すべての新しいアプリケーションで推奨されます。</span><span class="sxs-lookup"><span data-stu-id="aa2c5-129">This is the default behavior and is the recommended behavior for all new applications that do not communicate with older versions of the framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2c5-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa2c5-130">See also</span></span>

- <xref:System.DateTime>
- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="aa2c5-131">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="aa2c5-131">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="aa2c5-132">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-132">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- [<span data-ttu-id="aa2c5-133">\<Schema> Terextensions の要素を追加 \<</span><span class="sxs-lookup"><span data-stu-id="aa2c5-133">\<add> Element for \<schemaImporterExtensions></span></span>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)
- [<span data-ttu-id="aa2c5-134">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="aa2c5-134">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
