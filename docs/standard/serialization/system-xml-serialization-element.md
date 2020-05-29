---
title: <system.xml.serialization> 要素
description: この記事では、XML シリアル化を制御する最上位要素である <system.xml.serialization> 要素について説明します。
ms.date: 03/30/2017
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
ms.openlocfilehash: 1e66220004d561f937d03c506e6f30db4ccc635b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380112"
---
# <a name="systemxmlserialization-element"></a><span data-ttu-id="c457b-103">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-103">\<system.xml.serialization> Element</span></span>

<span data-ttu-id="c457b-104">XML シリアル化を制御する最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="c457b-104">The top-level element for controlling XML serialization.</span></span> <span data-ttu-id="c457b-105">構成ファイルの詳細については、「[構成ファイル スキーマ](../../../docs/framework/configure-apps/file-schema/index.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c457b-105">For more information about configuration files, see [Configuration File Schema](../../../docs/framework/configure-apps/file-schema/index.md).</span></span>

<span data-ttu-id="c457b-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c457b-106">\<configuration></span></span>\
<span data-ttu-id="c457b-107">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="c457b-107">\<system.xml.serialization></span></span>

## <a name="syntax"></a><span data-ttu-id="c457b-108">構文</span><span class="sxs-lookup"><span data-stu-id="c457b-108">Syntax</span></span>

```xml
<system.xml.serialization>
</system.xml.serialization>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c457b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c457b-109">Attributes and Elements</span></span>

<span data-ttu-id="c457b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c457b-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c457b-111">属性</span><span class="sxs-lookup"><span data-stu-id="c457b-111">Attributes</span></span>

<span data-ttu-id="c457b-112">なし。</span><span class="sxs-lookup"><span data-stu-id="c457b-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c457b-113">子要素</span><span class="sxs-lookup"><span data-stu-id="c457b-113">Child Elements</span></span>

|<span data-ttu-id="c457b-114">要素</span><span class="sxs-lookup"><span data-stu-id="c457b-114">Element</span></span>|<span data-ttu-id="c457b-115">説明</span><span class="sxs-lookup"><span data-stu-id="c457b-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c457b-116">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-116">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)|<span data-ttu-id="c457b-117"><xref:System.DateTime> オブジェクトのシリアル化モードを決定します。</span><span class="sxs-lookup"><span data-stu-id="c457b-117">Determines the serialization mode of <xref:System.DateTime> objects.</span></span>|
|[<span data-ttu-id="c457b-118">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-118">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<span data-ttu-id="c457b-119">XSD の型を .NET Framework の型にマッピングするために <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を含みます。</span><span class="sxs-lookup"><span data-stu-id="c457b-119">Contains types that are used by the <xref:System.Xml.Serialization.XmlSchemaImporter> for mapping of XSD types to .NET Framework types.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c457b-120">親要素</span><span class="sxs-lookup"><span data-stu-id="c457b-120">Parent Elements</span></span>

|<span data-ttu-id="c457b-121">要素</span><span class="sxs-lookup"><span data-stu-id="c457b-121">Element</span></span>|<span data-ttu-id="c457b-122">説明</span><span class="sxs-lookup"><span data-stu-id="c457b-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c457b-123">\<configuration> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-123">\<configuration> Element</span></span>](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="c457b-124">共通言語ランタイムおよび .NET Framework アプリケーションで使用されるすべての構成ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="c457b-124">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="example"></a><span data-ttu-id="c457b-125">例</span><span class="sxs-lookup"><span data-stu-id="c457b-125">Example</span></span>

<span data-ttu-id="c457b-126">次のコード例は、<xref:System.DateTime> オブジェクトのシリアル化モードを指定し、XSD の型を .NET Framework の型にマッピングするために <xref:System.Xml.Serialization.XmlSchemaImporter> によって使用される型を追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c457b-126">The following code example illustrates how to specify the serialization mode of a <xref:System.DateTime> object, and the addition of types used by the <xref:System.Xml.Serialization.XmlSchemaImporter> when mapping XSD types to .NET Framework types.</span></span>

```xml
<system.xml.serialization>
    <xmlSerializer checkDeserializeAdvances="false" />
    <dateTimeSerialization mode = "Local" />
    <schemaImporterExtensions>
        <add
        name = "MobileCapabilities"
        type = "System.Web.Mobile.MobileCapabilities,
        System.Web.Mobile, Version=2.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f6f11d40a3a" />
    </schemaImporterExtensions>
</system.xml.serialization>
```

## <a name="see-also"></a><span data-ttu-id="c457b-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="c457b-127">See also</span></span>

- <xref:System.Xml.Serialization.XmlSchemaImporter>
- <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>
- [<span data-ttu-id="c457b-128">構成ファイル スキーマ</span><span class="sxs-lookup"><span data-stu-id="c457b-128">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="c457b-129">\<dateTimeSerialization> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-129">\<dateTimeSerialization> Element</span></span>](../../../docs/standard/serialization/datetimeserialization-element.md)
- [<span data-ttu-id="c457b-130">\<schemaImporterExtensions> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-130">\<schemaImporterExtensions> Element</span></span>](../../../docs/standard/serialization/schemaimporterextensions-element.md)
- <span data-ttu-id="c457b-131">[\<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)の \<add> 要素</span><span class="sxs-lookup"><span data-stu-id="c457b-131">[\<add> Element for \<schemaImporterExtensions>](../../../docs/standard/serialization/add-element-for-schemaimporterextensions.md)</span></span>
