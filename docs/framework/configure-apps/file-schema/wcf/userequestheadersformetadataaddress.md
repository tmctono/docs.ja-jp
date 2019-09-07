---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399200"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="efc6d-101">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="efc6d-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="efc6d-102">メタデータのアドレス情報を要求メッセージ ヘッダーから取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="efc6d-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="efc6d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="efc6d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="efc6d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="efc6d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="efc6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efc6d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="efc6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efc6d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="efc6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="efc6d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="efc6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<useRequestHeadersForMetadataAddress >**</span><span class="sxs-lookup"><span data-stu-id="efc6d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc6d-109">構文</span><span class="sxs-lookup"><span data-stu-id="efc6d-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efc6d-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="efc6d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="efc6d-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="efc6d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efc6d-112">属性</span><span class="sxs-lookup"><span data-stu-id="efc6d-112">Attributes</span></span>  
 <span data-ttu-id="efc6d-113">なし。</span><span class="sxs-lookup"><span data-stu-id="efc6d-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="efc6d-114">子要素</span><span class="sxs-lookup"><span data-stu-id="efc6d-114">Child Elements</span></span>  
  
|<span data-ttu-id="efc6d-115">要素</span><span class="sxs-lookup"><span data-stu-id="efc6d-115">Element</span></span>|<span data-ttu-id="efc6d-116">説明</span><span class="sxs-lookup"><span data-stu-id="efc6d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efc6d-117">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="efc6d-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="efc6d-118">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="efc6d-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="efc6d-119">親要素</span><span class="sxs-lookup"><span data-stu-id="efc6d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="efc6d-120">要素</span><span class="sxs-lookup"><span data-stu-id="efc6d-120">Element</span></span>|<span data-ttu-id="efc6d-121">説明</span><span class="sxs-lookup"><span data-stu-id="efc6d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efc6d-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="efc6d-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="efc6d-123">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="efc6d-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efc6d-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="efc6d-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
