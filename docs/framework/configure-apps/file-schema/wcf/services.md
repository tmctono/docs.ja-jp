---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168078"
---
# <a name="services"></a><span data-ttu-id="e1521-101">\<services></span><span class="sxs-lookup"><span data-stu-id="e1521-101">\<services></span></span>
<span data-ttu-id="e1521-102">サービスは、設定ファイルの `services` セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="e1521-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="e1521-103">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="e1521-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="e1521-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e1521-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1521-105">構文</span><span class="sxs-lookup"><span data-stu-id="e1521-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1521-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e1521-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e1521-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1521-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1521-108">属性</span><span class="sxs-lookup"><span data-stu-id="e1521-108">Attributes</span></span>  
 <span data-ttu-id="e1521-109">なし</span><span class="sxs-lookup"><span data-stu-id="e1521-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e1521-110">子要素</span><span class="sxs-lookup"><span data-stu-id="e1521-110">Child Elements</span></span>  
  
|<span data-ttu-id="e1521-111">要素</span><span class="sxs-lookup"><span data-stu-id="e1521-111">Element</span></span>|<span data-ttu-id="e1521-112">説明</span><span class="sxs-lookup"><span data-stu-id="e1521-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1521-113">\<service></span><span class="sxs-lookup"><span data-stu-id="e1521-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="e1521-114">サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="e1521-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e1521-115">親要素</span><span class="sxs-lookup"><span data-stu-id="e1521-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e1521-116">要素</span><span class="sxs-lookup"><span data-stu-id="e1521-116">Element</span></span>|<span data-ttu-id="e1521-117">説明</span><span class="sxs-lookup"><span data-stu-id="e1521-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e1521-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e1521-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="e1521-119">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="e1521-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e1521-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1521-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
