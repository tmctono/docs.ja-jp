---
title: <host>
ms.date: 03/30/2017
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
ms.openlocfilehash: b764bc21e9c4555b39c3d096212b6e6bcabb62ff
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855214"
---
# <a name="host"></a><span data-ttu-id="325fa-101">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="325fa-101">\<host></span></span>
<span data-ttu-id="325fa-102">サービス ホストの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="325fa-102">Specifies settings for a service host.</span></span>  
  
<span data-ttu-id="325fa-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="325fa-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="325fa-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="325fa-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="325fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="325fa-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="325fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="325fa-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="325fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ホスト >**</span><span class="sxs-lookup"><span data-stu-id="325fa-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<host>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325fa-108">構文</span><span class="sxs-lookup"><span data-stu-id="325fa-108">Syntax</span></span>  
  
```xml  
<host>
  <baseAddresses>
    <add baseAddress="string" />
  </baseAddresses>
  <timeOuts closeTimeout="TimeSpan"
            openTimeout="TimeSpan" />
</host>
```  
  
## <a name="type"></a><span data-ttu-id="325fa-109">型</span><span class="sxs-lookup"><span data-stu-id="325fa-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="325fa-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="325fa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="325fa-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="325fa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="325fa-112">属性</span><span class="sxs-lookup"><span data-stu-id="325fa-112">Attributes</span></span>  
 <span data-ttu-id="325fa-113">なし。</span><span class="sxs-lookup"><span data-stu-id="325fa-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="325fa-114">子要素</span><span class="sxs-lookup"><span data-stu-id="325fa-114">Child Elements</span></span>  
  
|<span data-ttu-id="325fa-115">要素</span><span class="sxs-lookup"><span data-stu-id="325fa-115">Element</span></span>|<span data-ttu-id="325fa-116">説明</span><span class="sxs-lookup"><span data-stu-id="325fa-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="325fa-117">\<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="325fa-117">\<baseAddresses></span></span>](baseaddresses.md)|<span data-ttu-id="325fa-118">サービス ホストによって使用されるベース アドレスを指定する `baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="325fa-118">A collection of `baseAddress` elements that specifies the base addresses used by the service host.</span></span>|  
|[<span data-ttu-id="325fa-119">\<timeOuts></span><span class="sxs-lookup"><span data-stu-id="325fa-119">\<timeOuts></span></span>](timeouts.md)|<span data-ttu-id="325fa-120">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素。</span><span class="sxs-lookup"><span data-stu-id="325fa-120">A configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="325fa-121">親要素</span><span class="sxs-lookup"><span data-stu-id="325fa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="325fa-122">要素</span><span class="sxs-lookup"><span data-stu-id="325fa-122">Element</span></span>|<span data-ttu-id="325fa-123">説明</span><span class="sxs-lookup"><span data-stu-id="325fa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="325fa-124">\<service></span><span class="sxs-lookup"><span data-stu-id="325fa-124">\<service></span></span>](service.md)|<span data-ttu-id="325fa-125">Windows Communication Foundation (WCF) サービスの設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="325fa-125">Specifies the settings for a Windows Communication Foundation (WCF) service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="325fa-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="325fa-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="325fa-127">ホスティング</span><span class="sxs-lookup"><span data-stu-id="325fa-127">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
