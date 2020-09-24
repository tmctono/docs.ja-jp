---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: b8cb5075ba41bed5a22b152a231c7213b326a62f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153717"
---
# \<services>

<span data-ttu-id="bf1ec-101">サービスは、設定ファイルの `services` セクションで定義されます。</span><span class="sxs-lookup"><span data-stu-id="bf1ec-101">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="bf1ec-102">各サービスには、独自の `service` 設定セクションがあります。</span><span class="sxs-lookup"><span data-stu-id="bf1ec-102">Each service has its own `service` configuration section.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**  
  
## <a name="syntax"></a><span data-ttu-id="bf1ec-103">構文</span><span class="sxs-lookup"><span data-stu-id="bf1ec-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf1ec-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bf1ec-104">Attributes and Elements</span></span>  

 <span data-ttu-id="bf1ec-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf1ec-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf1ec-106">属性</span><span class="sxs-lookup"><span data-stu-id="bf1ec-106">Attributes</span></span>  

 <span data-ttu-id="bf1ec-107">None</span><span class="sxs-lookup"><span data-stu-id="bf1ec-107">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bf1ec-108">子要素</span><span class="sxs-lookup"><span data-stu-id="bf1ec-108">Child Elements</span></span>  
  
|<span data-ttu-id="bf1ec-109">要素</span><span class="sxs-lookup"><span data-stu-id="bf1ec-109">Element</span></span>|<span data-ttu-id="bf1ec-110">説明</span><span class="sxs-lookup"><span data-stu-id="bf1ec-110">Description</span></span>|  
|-------------|-----------------|  
|[\<service>](service.md)|<span data-ttu-id="bf1ec-111">サービス コントラクト、動作、および特定のサービスのエンドポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="bf1ec-111">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bf1ec-112">親要素</span><span class="sxs-lookup"><span data-stu-id="bf1ec-112">Parent Elements</span></span>  
  
|<span data-ttu-id="bf1ec-113">要素</span><span class="sxs-lookup"><span data-stu-id="bf1ec-113">Element</span></span>|<span data-ttu-id="bf1ec-114">説明</span><span class="sxs-lookup"><span data-stu-id="bf1ec-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="bf1ec-115">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="bf1ec-115">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf1ec-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf1ec-116">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
