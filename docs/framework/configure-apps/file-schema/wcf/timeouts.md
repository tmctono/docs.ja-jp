---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854969"
---
# <a name="timeouts"></a><span data-ttu-id="44367-101">\<タイムアウト ></span><span class="sxs-lookup"><span data-stu-id="44367-101">\<timeOuts></span></span>
<span data-ttu-id="44367-102">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="44367-102">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
<span data-ttu-id="44367-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44367-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44367-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44367-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44367-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](services.md)</span><span class="sxs-lookup"><span data-stu-id="44367-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)</span></span>\
<span data-ttu-id="44367-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<サービス >** ](service.md)</span><span class="sxs-lookup"><span data-stu-id="44367-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)</span></span>\
<span data-ttu-id="44367-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ホスト >** ](host.md)</span><span class="sxs-lookup"><span data-stu-id="44367-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)</span></span>\
<span data-ttu-id="44367-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<タイムアウト >**</span><span class="sxs-lookup"><span data-stu-id="44367-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44367-109">構文</span><span class="sxs-lookup"><span data-stu-id="44367-109">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44367-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="44367-110">Attributes and Elements</span></span>  
 <span data-ttu-id="44367-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="44367-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44367-112">属性</span><span class="sxs-lookup"><span data-stu-id="44367-112">Attributes</span></span>  
  
|<span data-ttu-id="44367-113">属性</span><span class="sxs-lookup"><span data-stu-id="44367-113">Attribute</span></span>|<span data-ttu-id="44367-114">説明</span><span class="sxs-lookup"><span data-stu-id="44367-114">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="44367-115">サービス ホストを閉じるまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="44367-115">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="44367-116">サービス ホストを開くまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="44367-116">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44367-117">子要素</span><span class="sxs-lookup"><span data-stu-id="44367-117">Child Elements</span></span>  
 <span data-ttu-id="44367-118">なし。</span><span class="sxs-lookup"><span data-stu-id="44367-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44367-119">親要素</span><span class="sxs-lookup"><span data-stu-id="44367-119">Parent Elements</span></span>  
  
|<span data-ttu-id="44367-120">要素</span><span class="sxs-lookup"><span data-stu-id="44367-120">Element</span></span>|<span data-ttu-id="44367-121">説明</span><span class="sxs-lookup"><span data-stu-id="44367-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44367-122">\<ホスト ></span><span class="sxs-lookup"><span data-stu-id="44367-122">\<host></span></span>](host.md)|<span data-ttu-id="44367-123">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="44367-123">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44367-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="44367-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="44367-125">ホスティング</span><span class="sxs-lookup"><span data-stu-id="44367-125">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
