---
title: <xmlSerializer> 要素
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 2919e8d4c1af858973ff3d2b58b4d3bc4f925527
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018068"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="fbb22-102">\<xmlSerializer > 要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-102">\<xmlSerializer> Element</span></span>
<span data-ttu-id="fbb22-103"><xref:System.Xml.Serialization.XmlSerializer> の進行状況の追加チェックを行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-103">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="fbb22-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fbb22-104">\<configuration></span></span>  
<span data-ttu-id="fbb22-105">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="fbb22-105">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbb22-106">構文</span><span class="sxs-lookup"><span data-stu-id="fbb22-106">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true"|"false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbb22-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-107">Attributes and Elements</span></span>  
 <span data-ttu-id="fbb22-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbb22-109">属性</span><span class="sxs-lookup"><span data-stu-id="fbb22-109">Attributes</span></span>  
  
|<span data-ttu-id="fbb22-110">属性</span><span class="sxs-lookup"><span data-stu-id="fbb22-110">Attribute</span></span>|<span data-ttu-id="fbb22-111">説明</span><span class="sxs-lookup"><span data-stu-id="fbb22-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fbb22-112">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="fbb22-112">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="fbb22-113"><xref:System.Xml.Serialization.XmlSerializer> の進行状況をチェックするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-113">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="fbb22-114">属性は "true" または "false" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-114">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="fbb22-115">既定値は "true" です。</span><span class="sxs-lookup"><span data-stu-id="fbb22-115">The default is "true".</span></span>|  
|<span data-ttu-id="fbb22-116">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="fbb22-116">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="fbb22-117">C# コードをファイルに記述し、それをアセンブリにコンパイルすることによってアセンブリを生成する従来のシリアル化の生成を、<xref:System.Xml.Serialization.XmlSerializer> で使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-117">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="fbb22-118">既定値は **false** です。</span><span class="sxs-lookup"><span data-stu-id="fbb22-118">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fbb22-119">子要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-119">Child Elements</span></span>  
 <span data-ttu-id="fbb22-120">なし。</span><span class="sxs-lookup"><span data-stu-id="fbb22-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fbb22-121">親要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fbb22-122">要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-122">Element</span></span>|<span data-ttu-id="fbb22-123">説明</span><span class="sxs-lookup"><span data-stu-id="fbb22-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fbb22-124">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-124">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="fbb22-125"><xref:System.Xml.Serialization.XmlSerializer> クラスおよび <xref:System.Xml.Serialization.XmlSchemaImporter> クラスの構成設定を含みます。</span><span class="sxs-lookup"><span data-stu-id="fbb22-125">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbb22-126">Remarks</span><span class="sxs-lookup"><span data-stu-id="fbb22-126">Remarks</span></span>  
 <span data-ttu-id="fbb22-127">既定では、<xref:System.Xml.Serialization.XmlSerializer> は、信頼できないデータを逆シリアル化する際に、サービス拒否攻撃の可能性に対するセキュリティをさらに高めることができます。</span><span class="sxs-lookup"><span data-stu-id="fbb22-127">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="fbb22-128">これは、逆シリアル化中に無限ループを検出することにより行われます。</span><span class="sxs-lookup"><span data-stu-id="fbb22-128">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="fbb22-129">このような条件が検出された場合は、次のメッセージが、例外がスローされます。"内部エラー: 基になるストリーム化セキュリティの強化を逆シリアル化ができませんでした"。</span><span class="sxs-lookup"><span data-stu-id="fbb22-129">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="fbb22-130">このメッセージは、必ずしもサービス拒否攻撃を受けていることを示すわけではありません。</span><span class="sxs-lookup"><span data-stu-id="fbb22-130">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="fbb22-131">まれに、無限ループ検出機構で誤検出が発生し、適正な受信メッセージに対して例外がスローされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbb22-131">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="fbb22-132">特定のアプリケーションにおいて、セキュリティの強化によって適正なメッセージが拒否される場合は、**checkDeserializeAdvances** 属性を "false" に設定します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-132">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbb22-133">例</span><span class="sxs-lookup"><span data-stu-id="fbb22-133">Example</span></span>  
 <span data-ttu-id="fbb22-134">**checkDeserializeAdvances** 属性を "false" に設定するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fbb22-134">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fbb22-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbb22-135">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="fbb22-136">\<system.xml.serialization> 要素</span><span class="sxs-lookup"><span data-stu-id="fbb22-136">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="fbb22-137">XML シリアル化および SOAP シリアル化</span><span class="sxs-lookup"><span data-stu-id="fbb22-137">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
