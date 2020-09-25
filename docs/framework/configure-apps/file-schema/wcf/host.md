---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: 524226cbb826486def18c1b3b66c5b4a3c456dec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185679"
---
# \<host>

<span data-ttu-id="6917b-101">サービス ホストの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6917b-101">Specifies settings for a service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**  
  
## <a name="syntax"></a><span data-ttu-id="6917b-102">構文</span><span class="sxs-lookup"><span data-stu-id="6917b-102">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="6917b-103">種類</span><span class="sxs-lookup"><span data-stu-id="6917b-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6917b-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6917b-104">Attributes and Elements</span></span>  

 <span data-ttu-id="6917b-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6917b-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6917b-106">属性</span><span class="sxs-lookup"><span data-stu-id="6917b-106">Attributes</span></span>  

 <span data-ttu-id="6917b-107">なし。</span><span class="sxs-lookup"><span data-stu-id="6917b-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6917b-108">子要素</span><span class="sxs-lookup"><span data-stu-id="6917b-108">Child Elements</span></span>  
  
|<span data-ttu-id="6917b-109">要素</span><span class="sxs-lookup"><span data-stu-id="6917b-109">Element</span></span>|<span data-ttu-id="6917b-110">説明</span><span class="sxs-lookup"><span data-stu-id="6917b-110">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="6917b-111">サービス ホストによって使用されるベース アドレスを指定する `baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="6917b-111">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[\<timeOuts>](timeouts.md)|<span data-ttu-id="6917b-112">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="6917b-112">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6917b-113">親要素</span><span class="sxs-lookup"><span data-stu-id="6917b-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6917b-114">要素</span><span class="sxs-lookup"><span data-stu-id="6917b-114">Element</span></span>|<span data-ttu-id="6917b-115">説明</span><span class="sxs-lookup"><span data-stu-id="6917b-115">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="6917b-116">Windows Communication Foundation (WCF) サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6917b-116">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6917b-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="6917b-117">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="6917b-118">ホスティング</span><span class="sxs-lookup"><span data-stu-id="6917b-118">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
