---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925887"
---
# <a name="defaultports"></a><span data-ttu-id="20922-101">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="20922-101">\<defaultPorts></span></span>
<span data-ttu-id="20922-102">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="20922-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="20922-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="20922-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="20922-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="20922-104">\<behaviors></span></span>  
<span data-ttu-id="20922-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="20922-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="20922-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="20922-106">\<behavior></span></span>  
<span data-ttu-id="20922-107">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="20922-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="20922-108">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="20922-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20922-109">構文</span><span class="sxs-lookup"><span data-stu-id="20922-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20922-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="20922-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20922-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="20922-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20922-112">属性</span><span class="sxs-lookup"><span data-stu-id="20922-112">Attributes</span></span>  
 <span data-ttu-id="20922-113">なし。</span><span class="sxs-lookup"><span data-stu-id="20922-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20922-114">子要素</span><span class="sxs-lookup"><span data-stu-id="20922-114">Child Elements</span></span>  
  
|<span data-ttu-id="20922-115">要素</span><span class="sxs-lookup"><span data-stu-id="20922-115">Element</span></span>|<span data-ttu-id="20922-116">説明</span><span class="sxs-lookup"><span data-stu-id="20922-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20922-117">\<defaultports の\<> を追加し ></span><span class="sxs-lookup"><span data-stu-id="20922-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="20922-118">クライアント アプリケーションがリッスンする既定の通信エンドポイント。</span><span class="sxs-lookup"><span data-stu-id="20922-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20922-119">親要素</span><span class="sxs-lookup"><span data-stu-id="20922-119">Parent Elements</span></span>  
  
|<span data-ttu-id="20922-120">要素</span><span class="sxs-lookup"><span data-stu-id="20922-120">Element</span></span>|<span data-ttu-id="20922-121">説明</span><span class="sxs-lookup"><span data-stu-id="20922-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20922-122">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="20922-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="20922-123">既定のポートの一覧。</span><span class="sxs-lookup"><span data-stu-id="20922-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20922-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="20922-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
