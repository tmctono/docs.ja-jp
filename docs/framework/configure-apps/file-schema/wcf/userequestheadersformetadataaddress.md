---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: a323e6da0eb173e303d70cc3b7309b898a805573
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172815"
---
# \<useRequestHeadersForMetadataAddress>

<span data-ttu-id="f7a0a-101">メタデータのアドレス情報を要求メッセージ ヘッダーから取得できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f7a0a-101">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**  
  
## <a name="syntax"></a><span data-ttu-id="f7a0a-102">構文</span><span class="sxs-lookup"><span data-stu-id="f7a0a-102">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7a0a-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f7a0a-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f7a0a-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f7a0a-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7a0a-105">属性</span><span class="sxs-lookup"><span data-stu-id="f7a0a-105">Attributes</span></span>  

 <span data-ttu-id="f7a0a-106">なし。</span><span class="sxs-lookup"><span data-stu-id="f7a0a-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7a0a-107">子要素</span><span class="sxs-lookup"><span data-stu-id="f7a0a-107">Child Elements</span></span>  
  
|<span data-ttu-id="f7a0a-108">要素</span><span class="sxs-lookup"><span data-stu-id="f7a0a-108">Element</span></span>|<span data-ttu-id="f7a0a-109">説明</span><span class="sxs-lookup"><span data-stu-id="f7a0a-109">Description</span></span>|  
|-------------|-----------------|  
|[\<defaultPorts>](defaultports.md)|<span data-ttu-id="f7a0a-110">クライアント アプリケーションがリッスンする既定の通信エンドポイントの一覧を表示する既定のポートのコレクション。</span><span class="sxs-lookup"><span data-stu-id="f7a0a-110">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7a0a-111">親要素</span><span class="sxs-lookup"><span data-stu-id="f7a0a-111">Parent Elements</span></span>  
  
|<span data-ttu-id="f7a0a-112">要素</span><span class="sxs-lookup"><span data-stu-id="f7a0a-112">Element</span></span>|<span data-ttu-id="f7a0a-113">説明</span><span class="sxs-lookup"><span data-stu-id="f7a0a-113">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f7a0a-114">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7a0a-114">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7a0a-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7a0a-115">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
