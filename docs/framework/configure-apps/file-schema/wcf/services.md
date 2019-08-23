---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937203"
---
# <a name="services"></a><span data-ttu-id="4460d-101">\<services></span><span class="sxs-lookup"><span data-stu-id="4460d-101">\<services></span></span>
<span data-ttu-id="4460d-102">サービスは、設定ファイルの `services` セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="4460d-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="4460d-103">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="4460d-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="4460d-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4460d-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4460d-105">構文</span><span class="sxs-lookup"><span data-stu-id="4460d-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4460d-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4460d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="4460d-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4460d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4460d-108">属性</span><span class="sxs-lookup"><span data-stu-id="4460d-108">Attributes</span></span>  
 <span data-ttu-id="4460d-109">なし</span><span class="sxs-lookup"><span data-stu-id="4460d-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4460d-110">子要素</span><span class="sxs-lookup"><span data-stu-id="4460d-110">Child Elements</span></span>  
  
|<span data-ttu-id="4460d-111">要素</span><span class="sxs-lookup"><span data-stu-id="4460d-111">Element</span></span>|<span data-ttu-id="4460d-112">説明</span><span class="sxs-lookup"><span data-stu-id="4460d-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4460d-113">\<service></span><span class="sxs-lookup"><span data-stu-id="4460d-113">\<service></span></span>](service.md)|<span data-ttu-id="4460d-114">サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="4460d-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4460d-115">親要素</span><span class="sxs-lookup"><span data-stu-id="4460d-115">Parent Elements</span></span>  
  
|<span data-ttu-id="4460d-116">要素</span><span class="sxs-lookup"><span data-stu-id="4460d-116">Element</span></span>|<span data-ttu-id="4460d-117">説明</span><span class="sxs-lookup"><span data-stu-id="4460d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4460d-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4460d-118">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="4460d-119">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="4460d-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4460d-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4460d-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
