---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399200"
---
# \<useRequestHeadersForMetadataAddress>
<span data-ttu-id="701e0-101">メタデータのアドレス情報を要求メッセージ ヘッダーから取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="701e0-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="701e0-102">構文</span><span class="sxs-lookup"><span data-stu-id="701e0-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="701e0-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="701e0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="701e0-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="701e0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="701e0-105">属性</span><span class="sxs-lookup"><span data-stu-id="701e0-105">Attributes</span></span>  
 <span data-ttu-id="701e0-106">なし。</span><span class="sxs-lookup"><span data-stu-id="701e0-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="701e0-107">子要素</span><span class="sxs-lookup"><span data-stu-id="701e0-107">Child Elements</span></span>  
  
|<span data-ttu-id="701e0-108">要素</span><span class="sxs-lookup"><span data-stu-id="701e0-108">Element</span></span>|<span data-ttu-id="701e0-109">説明</span><span class="sxs-lookup"><span data-stu-id="701e0-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="701e0-110">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="701e0-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="701e0-111">親要素</span><span class="sxs-lookup"><span data-stu-id="701e0-111">Parent Elements</span></span>  
  
|<span data-ttu-id="701e0-112">要素</span><span class="sxs-lookup"><span data-stu-id="701e0-112">Element</span></span>|<span data-ttu-id="701e0-113">説明</span><span class="sxs-lookup"><span data-stu-id="701e0-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="701e0-114">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="701e0-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="701e0-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="701e0-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
