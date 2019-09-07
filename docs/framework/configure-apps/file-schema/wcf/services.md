---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 1f9cb6c95fa14a5b8a55cc561699e2a07e1dc80c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399595"
---
# <a name="services"></a><span data-ttu-id="e00d3-101">\<services></span><span class="sxs-lookup"><span data-stu-id="e00d3-101">\<services></span></span>
<span data-ttu-id="e00d3-102">サービスは、設定ファイルの `services` セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e00d3-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e00d3-103">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="e00d3-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="e00d3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e00d3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e00d3-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e00d3-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e00d3-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<サービス >**</span><span class="sxs-lookup"><span data-stu-id="e00d3-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
## <a name="syntax"></a><span data-ttu-id="e00d3-107">構文</span><span class="sxs-lookup"><span data-stu-id="e00d3-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e00d3-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e00d3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e00d3-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e00d3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e00d3-110">属性</span><span class="sxs-lookup"><span data-stu-id="e00d3-110">Attributes</span></span>  
 <span data-ttu-id="e00d3-111">なし</span><span class="sxs-lookup"><span data-stu-id="e00d3-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e00d3-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e00d3-112">Child Elements</span></span>  
  
|<span data-ttu-id="e00d3-113">要素</span><span class="sxs-lookup"><span data-stu-id="e00d3-113">Element</span></span>|<span data-ttu-id="e00d3-114">説明</span><span class="sxs-lookup"><span data-stu-id="e00d3-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e00d3-115">\<service></span><span class="sxs-lookup"><span data-stu-id="e00d3-115">\<service></span></span>](service.md)|<span data-ttu-id="e00d3-116">サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="e00d3-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e00d3-117">親要素</span><span class="sxs-lookup"><span data-stu-id="e00d3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e00d3-118">要素</span><span class="sxs-lookup"><span data-stu-id="e00d3-118">Element</span></span>|<span data-ttu-id="e00d3-119">説明</span><span class="sxs-lookup"><span data-stu-id="e00d3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e00d3-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e00d3-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="e00d3-121">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e00d3-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e00d3-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="e00d3-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
