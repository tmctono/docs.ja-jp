---
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: e24dae47171f741af064ca2eaa822928690acf6e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400451"
---
# <a name="datacontractserializer"></a><span data-ttu-id="8fa1d-101">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8fa1d-101">\<dataContractSerializer></span></span>
<span data-ttu-id="8fa1d-102"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-102">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="8fa1d-103">この要素は、2 つの異なる階層で使用されます。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-103">This element occurs in two different hierarchies.</span></span> <span data-ttu-id="8fa1d-104">1 つは以下の「スキーマの階層」に示したもので、もう 1 つは「解説」に記載しています。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-104">One is listed the following Schema Hierarchy section and the other is listed in the Remarks section.</span></span>  
  
<span data-ttu-id="8fa1d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8fa1d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8fa1d-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8fa1d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8fa1d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8fa1d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="8fa1d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8fa1d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="8fa1d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="8fa1d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="8fa1d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="8fa1d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fa1d-111">構文</span><span class="sxs-lookup"><span data-stu-id="8fa1d-111">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8fa1d-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8fa1d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8fa1d-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8fa1d-114">属性</span><span class="sxs-lookup"><span data-stu-id="8fa1d-114">Attributes</span></span>  
  
|<span data-ttu-id="8fa1d-115">要素</span><span class="sxs-lookup"><span data-stu-id="8fa1d-115">Element</span></span>|<span data-ttu-id="8fa1d-116">説明</span><span class="sxs-lookup"><span data-stu-id="8fa1d-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8fa1d-117">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="8fa1d-117">ignoreExtensionDataObject</span></span>|<span data-ttu-id="8fa1d-118">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-118">A Boolean value that specifies whether to ignore data supplied by the endpoint when it is being serialized or deserialized.</span></span> <span data-ttu-id="8fa1d-119">この属性は、`<dataContractSerializer>` 要素の下の `<behavior>` でのみ設定可能です。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-119">This attribute is settable only on the `<dataContractSerializer>` under the `<behavior>` element.</span></span>|  
|<span data-ttu-id="8fa1d-120">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="8fa1d-120">maxItemsInObjectGraph</span></span>|<span data-ttu-id="8fa1d-121">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-121">An integer that specifies the maximum number of items to serialize or deserialize.</span></span> <span data-ttu-id="8fa1d-122">この属性は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-122">This attribute is 65536.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8fa1d-123">子要素</span><span class="sxs-lookup"><span data-stu-id="8fa1d-123">Child Elements</span></span>  
 <span data-ttu-id="8fa1d-124">なし。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8fa1d-125">親要素</span><span class="sxs-lookup"><span data-stu-id="8fa1d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8fa1d-126">要素</span><span class="sxs-lookup"><span data-stu-id="8fa1d-126">Element</span></span>|<span data-ttu-id="8fa1d-127">説明</span><span class="sxs-lookup"><span data-stu-id="8fa1d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8fa1d-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8fa1d-128">\<behavior></span></span>](behavior-of-servicebehaviors.md)|<span data-ttu-id="8fa1d-129">サービスの動作設定のコレクション。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-129">A collection of settings for the behavior of a service.</span></span>|  
|[<span data-ttu-id="8fa1d-130">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="8fa1d-130">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)|<span data-ttu-id="8fa1d-131"><xref:System.Runtime.Serialization> 名前空間セクションのルート要素を表し、<xref:System.Runtime.Serialization.DataContractSerializer> のオプションを設定するための要素を含みます。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-131">Represents the root element for the <xref:System.Runtime.Serialization> namespace section and contains elements for setting options of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fa1d-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="8fa1d-132">Remarks</span></span>  
 <span data-ttu-id="8fa1d-133">このトピックの冒頭で述べたように、これは\<X509Extension > 要素が発生する2番目の階層です。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-133">As stated in the Introduction of this topic, this is the second hierarchy in which the \<X509Extension> element occurs.</span></span>  
  
 [<span data-ttu-id="8fa1d-134">\<system.runtime.serialization ></span><span class="sxs-lookup"><span data-stu-id="8fa1d-134">\<system.runtime.serialization></span></span>](system-runtime-serialization.md)  
  
 [<span data-ttu-id="8fa1d-135">\<dataContractSerializer ></span><span class="sxs-lookup"><span data-stu-id="8fa1d-135">\<dataContractSerializer></span></span>](datacontractserializer-element.md)  
  
 <span data-ttu-id="8fa1d-136">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fa1d-136">For more information about known types, see <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa1d-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fa1d-137">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="8fa1d-138">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="8fa1d-138">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="8fa1d-139">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="8fa1d-139">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
