---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 89ebad118c1c9210357d8fd281c9216b7f64b450
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398069"
---
# <a name="defaultports"></a><span data-ttu-id="d8adc-101">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="d8adc-101">\<defaultPorts></span></span>
<span data-ttu-id="d8adc-102">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="d8adc-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="d8adc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d8adc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d8adc-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d8adc-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d8adc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d8adc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d8adc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d8adc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="d8adc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d8adc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="d8adc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<useRequestHeadersForMetadataAddress >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="d8adc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="d8adc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultPorts >**</span><span class="sxs-lookup"><span data-stu-id="d8adc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8adc-110">構文</span><span class="sxs-lookup"><span data-stu-id="d8adc-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8adc-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d8adc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d8adc-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8adc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8adc-113">属性</span><span class="sxs-lookup"><span data-stu-id="d8adc-113">Attributes</span></span>  
 <span data-ttu-id="d8adc-114">なし。</span><span class="sxs-lookup"><span data-stu-id="d8adc-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8adc-115">子要素</span><span class="sxs-lookup"><span data-stu-id="d8adc-115">Child Elements</span></span>  
  
|<span data-ttu-id="d8adc-116">要素</span><span class="sxs-lookup"><span data-stu-id="d8adc-116">Element</span></span>|<span data-ttu-id="d8adc-117">説明</span><span class="sxs-lookup"><span data-stu-id="d8adc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8adc-118">\<defaultports の\<> を追加し ></span><span class="sxs-lookup"><span data-stu-id="d8adc-118">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="d8adc-119">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="d8adc-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8adc-120">親要素</span><span class="sxs-lookup"><span data-stu-id="d8adc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d8adc-121">要素</span><span class="sxs-lookup"><span data-stu-id="d8adc-121">Element</span></span>|<span data-ttu-id="d8adc-122">説明</span><span class="sxs-lookup"><span data-stu-id="d8adc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8adc-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d8adc-123">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="d8adc-124">既定のポートの一覧。</span><span class="sxs-lookup"><span data-stu-id="d8adc-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8adc-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d8adc-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
