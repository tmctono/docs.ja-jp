---
title: <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 9b3ed6b39f1743249925d5b6d9a47845c87983bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850208"
---
# \<baseAddresses>
<span data-ttu-id="81dbf-101">自己ホスト環境でのサービス ホストのベース アドレスである `baseAddress` 要素のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="81dbf-101">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="81dbf-102">ベース アドレスが存在すると、そのベース アドレスに関連したアドレスを使用してエンドポイントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="81dbf-102">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<baseAddresses>**  
  
## <a name="syntax"></a><span data-ttu-id="81dbf-103">構文</span><span class="sxs-lookup"><span data-stu-id="81dbf-103">Syntax</span></span>  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a><span data-ttu-id="81dbf-104">Type</span><span class="sxs-lookup"><span data-stu-id="81dbf-104">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81dbf-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="81dbf-105">Attributes and Elements</span></span>  
 <span data-ttu-id="81dbf-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="81dbf-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81dbf-107">属性</span><span class="sxs-lookup"><span data-stu-id="81dbf-107">Attributes</span></span>  
 <span data-ttu-id="81dbf-108">なし。</span><span class="sxs-lookup"><span data-stu-id="81dbf-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="81dbf-109">子要素</span><span class="sxs-lookup"><span data-stu-id="81dbf-109">Child Elements</span></span>  
  
|<span data-ttu-id="81dbf-110">要素</span><span class="sxs-lookup"><span data-stu-id="81dbf-110">Element</span></span>|<span data-ttu-id="81dbf-111">説明</span><span class="sxs-lookup"><span data-stu-id="81dbf-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-of-baseaddresses.md)|<span data-ttu-id="81dbf-112">サービス ホストによって使用されるベース アドレスを指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="81dbf-112">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81dbf-113">親要素</span><span class="sxs-lookup"><span data-stu-id="81dbf-113">Parent Elements</span></span>  
  
|<span data-ttu-id="81dbf-114">要素</span><span class="sxs-lookup"><span data-stu-id="81dbf-114">Element</span></span>|<span data-ttu-id="81dbf-115">説明</span><span class="sxs-lookup"><span data-stu-id="81dbf-115">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="81dbf-116">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="81dbf-116">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81dbf-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="81dbf-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="81dbf-118">ホスティング</span><span class="sxs-lookup"><span data-stu-id="81dbf-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
