---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: e6524c18780c062c3b5b7dfc2509449cb208e270
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400432"
---
# <a name="datacontractserializer"></a><span data-ttu-id="e0988-102">dataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="e0988-102">dataContractSerializer</span></span>
<span data-ttu-id="e0988-103"><xref:System.Runtime.Serialization.DataContractSerializer> 用の設定データが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0988-103">Contains configuration data for the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
<span data-ttu-id="e0988-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e0988-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e0988-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e0988-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e0988-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e0988-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e0988-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e0988-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="e0988-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e0988-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="e0988-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dataContractSerializer >**</span><span class="sxs-lookup"><span data-stu-id="e0988-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0988-110">構文</span><span class="sxs-lookup"><span data-stu-id="e0988-110">Syntax</span></span>  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0988-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e0988-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e0988-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0988-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0988-113">属性</span><span class="sxs-lookup"><span data-stu-id="e0988-113">Attributes</span></span>  
  
|<span data-ttu-id="e0988-114">要素</span><span class="sxs-lookup"><span data-stu-id="e0988-114">Element</span></span>|<span data-ttu-id="e0988-115">説明</span><span class="sxs-lookup"><span data-stu-id="e0988-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0988-116">ignoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="e0988-116">ignoreExtensionDataObject</span></span>|<span data-ttu-id="e0988-117">エンドポイントがシリアル化または逆シリアル化されているときに、そのエンドポイントにより提供されるデータを無視するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="e0988-117">A Boolean value that specifies whether to ignore data supplied by the endpoint, when it is being serialized or deserialized.</span></span>|  
|<span data-ttu-id="e0988-118">maxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="e0988-118">maxItemsInObjectGraph</span></span>|<span data-ttu-id="e0988-119">シリアル化または逆シリアル化する項目の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e0988-119">An integer that specifies the maximum number of items to serialize or deserialize.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0988-120">子要素</span><span class="sxs-lookup"><span data-stu-id="e0988-120">Child Elements</span></span>  
 <span data-ttu-id="e0988-121">なし。</span><span class="sxs-lookup"><span data-stu-id="e0988-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0988-122">親要素</span><span class="sxs-lookup"><span data-stu-id="e0988-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e0988-123">要素</span><span class="sxs-lookup"><span data-stu-id="e0988-123">Element</span></span>|<span data-ttu-id="e0988-124">説明</span><span class="sxs-lookup"><span data-stu-id="e0988-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0988-125">\<behavior></span><span class="sxs-lookup"><span data-stu-id="e0988-125">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="e0988-126">エンドポイントの動作を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0988-126">Specifies an endpoint behavior.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0988-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="e0988-127">Remarks</span></span>  
 <span data-ttu-id="e0988-128">既知の型の詳細については、<xref:System.Runtime.Serialization.DataContractSerializer> のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0988-128">See the <xref:System.Runtime.Serialization.DataContractSerializer> documentation for more information about known types.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e0988-129">`<dataContractSerializer>` 動作要素が存在する場合は、構成ファイル内で `<enableWebScript>` 動作要素よりも前に出現する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0988-129">The `<dataContractSerializer>` behavior element (if present) should always appear before the `<enableWebScript>` behavior element in the configuration file.</span></span> <span data-ttu-id="e0988-130">それ以外の場合は、動作結果は未定義になります。</span><span class="sxs-lookup"><span data-stu-id="e0988-130">Otherwise, the resulting behavior is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0988-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0988-131">See also</span></span>

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [<span data-ttu-id="e0988-132">既知のデータ コントラクト型</span><span class="sxs-lookup"><span data-stu-id="e0988-132">Data Contract Known Types</span></span>](../../../wcf/feature-details/data-contract-known-types.md)
- [<span data-ttu-id="e0988-133">データ転送とシリアル化</span><span class="sxs-lookup"><span data-stu-id="e0988-133">Data Transfer and Serialization</span></span>](../../../wcf/feature-details/data-transfer-and-serialization.md)
