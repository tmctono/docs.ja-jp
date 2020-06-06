---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b9c67ac03f0eb73a2a4cdd43ab48fe12871a1cc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854969"
---
# \<timeOuts>
<span data-ttu-id="a4d0b-101">サービス ホストを開くまたは閉じるまでに待機できる期間を指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="a4d0b-101">Represents a configuration element that specifies the interval of time allowed for the service host to open or close.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<timeOuts>**  
  
## <a name="syntax"></a><span data-ttu-id="a4d0b-102">構文</span><span class="sxs-lookup"><span data-stu-id="a4d0b-102">Syntax</span></span>  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4d0b-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a4d0b-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a4d0b-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a4d0b-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4d0b-105">属性</span><span class="sxs-lookup"><span data-stu-id="a4d0b-105">Attributes</span></span>  
  
|<span data-ttu-id="a4d0b-106">属性</span><span class="sxs-lookup"><span data-stu-id="a4d0b-106">Attribute</span></span>|<span data-ttu-id="a4d0b-107">説明</span><span class="sxs-lookup"><span data-stu-id="a4d0b-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="a4d0b-108">サービス ホストを閉じるまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="a4d0b-108">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to close.</span></span>|  
|`openTimeout`|<span data-ttu-id="a4d0b-109">サービス ホストを開くまでに待機できる期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="a4d0b-109">A <xref:System.TimeSpan> value that specifies the interval of time allowed for the service host to open.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4d0b-110">子要素</span><span class="sxs-lookup"><span data-stu-id="a4d0b-110">Child Elements</span></span>  
 <span data-ttu-id="a4d0b-111">なし。</span><span class="sxs-lookup"><span data-stu-id="a4d0b-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4d0b-112">親要素</span><span class="sxs-lookup"><span data-stu-id="a4d0b-112">Parent Elements</span></span>  
  
|<span data-ttu-id="a4d0b-113">要素</span><span class="sxs-lookup"><span data-stu-id="a4d0b-113">Element</span></span>|<span data-ttu-id="a4d0b-114">Description</span><span class="sxs-lookup"><span data-stu-id="a4d0b-114">Description</span></span>|  
|-------------|-----------------|  
|[\<host>](host.md)|<span data-ttu-id="a4d0b-115">サービス ホストの設定を指定する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="a4d0b-115">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4d0b-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="a4d0b-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [<span data-ttu-id="a4d0b-117">ホスティング</span><span class="sxs-lookup"><span data-stu-id="a4d0b-117">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
