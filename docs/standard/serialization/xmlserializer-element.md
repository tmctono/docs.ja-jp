---
title: <xmlSerializer> 要素
description: <xmlSerializer> 要素は、XmlSerializer の進行状況の追加チェックを行うかどうかを指定します。
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 68037959893ec307a896ea86d21e40a9d7aa824c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380031"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="fdf95-103">\<xmlSerializer> 要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="fdf95-104"><xref:System.Xml.Serialization.XmlSerializer> の進行状況の追加チェックを行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="fdf95-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fdf95-105">\<configuration></span></span>  
<span data-ttu-id="fdf95-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fdf95-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf95-107">構文</span><span class="sxs-lookup"><span data-stu-id="fdf95-107">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fdf95-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-108">Attributes and Elements</span></span>  
 <span data-ttu-id="fdf95-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fdf95-110">属性</span><span class="sxs-lookup"><span data-stu-id="fdf95-110">Attributes</span></span>  
  
|<span data-ttu-id="fdf95-111">属性</span><span class="sxs-lookup"><span data-stu-id="fdf95-111">Attribute</span></span>|<span data-ttu-id="fdf95-112">説明</span><span class="sxs-lookup"><span data-stu-id="fdf95-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fdf95-113">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="fdf95-113">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="fdf95-114"><xref:System.Xml.Serialization.XmlSerializer> の進行状況をチェックするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-114">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="fdf95-115">属性は "true" または "false" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-115">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="fdf95-116">既定値は "true" です。</span><span class="sxs-lookup"><span data-stu-id="fdf95-116">The default is "true".</span></span>|  
|<span data-ttu-id="fdf95-117">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="fdf95-117">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="fdf95-118">C# コードをファイルに記述し、それをアセンブリにコンパイルすることによってアセンブリを生成する従来のシリアル化の生成を、<xref:System.Xml.Serialization.XmlSerializer> で使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-118">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="fdf95-119">既定値は **false** です。</span><span class="sxs-lookup"><span data-stu-id="fdf95-119">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fdf95-120">子要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-120">Child Elements</span></span>  
 <span data-ttu-id="fdf95-121">なし。</span><span class="sxs-lookup"><span data-stu-id="fdf95-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fdf95-122">親要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fdf95-123">要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-123">Element</span></span>|<span data-ttu-id="fdf95-124">説明</span><span class="sxs-lookup"><span data-stu-id="fdf95-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fdf95-125">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-125">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="fdf95-126"><xref:System.Xml.Serialization.XmlSerializer> クラスおよび <xref:System.Xml.Serialization.XmlSchemaImporter> クラスの構成設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="fdf95-126">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdf95-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="fdf95-127">Remarks</span></span>  
 <span data-ttu-id="fdf95-128">既定では、<xref:System.Xml.Serialization.XmlSerializer> は、信頼できないデータを逆シリアル化する際に、サービス拒否攻撃の可能性に対するセキュリティをさらに高めることができます。</span><span class="sxs-lookup"><span data-stu-id="fdf95-128">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="fdf95-129">これは、逆シリアル化中に無限ループを検出することにより行われます。</span><span class="sxs-lookup"><span data-stu-id="fdf95-129">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="fdf95-130">このような状態が検出されると、例外がスローされ、次のメッセージが表示されます。"内部エラー: 基になるストリームで逆シリアル化を継続できませんでした。"</span><span class="sxs-lookup"><span data-stu-id="fdf95-130">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="fdf95-131">このメッセージは、必ずしもサービス拒否攻撃を受けていることを示すわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fdf95-131">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="fdf95-132">まれに、無限ループ検出機構で誤検出が発生し、適正な受信メッセージに対して例外がスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fdf95-132">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="fdf95-133">特定のアプリケーションにおいて、セキュリティの強化によって適正なメッセージが拒否される場合は、**checkDeserializeAdvances** 属性を "false" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-133">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf95-134">例</span><span class="sxs-lookup"><span data-stu-id="fdf95-134">Example</span></span>  
 <span data-ttu-id="fdf95-135">**checkDeserializeAdvances** 属性を "false" に設定するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fdf95-135">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdf95-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="fdf95-136">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="fdf95-137">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="fdf95-137">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="fdf95-138">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="fdf95-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
