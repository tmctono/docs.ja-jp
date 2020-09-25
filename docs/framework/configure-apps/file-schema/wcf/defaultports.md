---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 08ca8a2bfcf5b905152f7e64a45cbae4992a7b78
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192374"
---
# \<defaultPorts>

<span data-ttu-id="ffcf1-101">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ffcf1-101">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultPorts>**  
  
## <a name="syntax"></a><span data-ttu-id="ffcf1-102">構文</span><span class="sxs-lookup"><span data-stu-id="ffcf1-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffcf1-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ffcf1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ffcf1-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ffcf1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffcf1-105">属性</span><span class="sxs-lookup"><span data-stu-id="ffcf1-105">Attributes</span></span>  

 <span data-ttu-id="ffcf1-106">なし。</span><span class="sxs-lookup"><span data-stu-id="ffcf1-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ffcf1-107">子要素</span><span class="sxs-lookup"><span data-stu-id="ffcf1-107">Child Elements</span></span>  
  
|<span data-ttu-id="ffcf1-108">要素</span><span class="sxs-lookup"><span data-stu-id="ffcf1-108">Element</span></span>|<span data-ttu-id="ffcf1-109">説明</span><span class="sxs-lookup"><span data-stu-id="ffcf1-109">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffcf1-110">\<defaultPorts> の \<add></span><span class="sxs-lookup"><span data-stu-id="ffcf1-110">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="ffcf1-111">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="ffcf1-111">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ffcf1-112">親要素</span><span class="sxs-lookup"><span data-stu-id="ffcf1-112">Parent Elements</span></span>  
  
|<span data-ttu-id="ffcf1-113">要素</span><span class="sxs-lookup"><span data-stu-id="ffcf1-113">Element</span></span>|<span data-ttu-id="ffcf1-114">説明</span><span class="sxs-lookup"><span data-stu-id="ffcf1-114">Description</span></span>|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|<span data-ttu-id="ffcf1-115">既定のポートの一覧。</span><span class="sxs-lookup"><span data-stu-id="ffcf1-115">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffcf1-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="ffcf1-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
