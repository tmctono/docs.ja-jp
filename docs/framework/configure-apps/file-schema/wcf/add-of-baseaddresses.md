---
title: <add> の <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: d75142209ad8706d0cad5ce188d9d991a5e881bc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850581"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="e8999-102">\<add> の \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="e8999-102">\<add> of \<baseAddresses></span></span>
<span data-ttu-id="e8999-103">サービス ホストによって使用されるベース アドレスを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="e8999-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="e8999-104">構文</span><span class="sxs-lookup"><span data-stu-id="e8999-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="e8999-105">Type</span><span class="sxs-lookup"><span data-stu-id="e8999-105">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8999-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8999-106">Attributes and Elements</span></span>  
 <span data-ttu-id="e8999-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8999-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8999-108">属性</span><span class="sxs-lookup"><span data-stu-id="e8999-108">Attributes</span></span>  
  
|<span data-ttu-id="e8999-109">属性</span><span class="sxs-lookup"><span data-stu-id="e8999-109">Attribute</span></span>|<span data-ttu-id="e8999-110">説明</span><span class="sxs-lookup"><span data-stu-id="e8999-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="e8999-111">サービス ホストによって使用されるベース アドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="e8999-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8999-112">子要素</span><span class="sxs-lookup"><span data-stu-id="e8999-112">Child Elements</span></span>  
 <span data-ttu-id="e8999-113">なし。</span><span class="sxs-lookup"><span data-stu-id="e8999-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e8999-114">親要素</span><span class="sxs-lookup"><span data-stu-id="e8999-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e8999-115">要素</span><span class="sxs-lookup"><span data-stu-id="e8999-115">Element</span></span>|<span data-ttu-id="e8999-116">Description</span><span class="sxs-lookup"><span data-stu-id="e8999-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="e8999-117">`baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="e8999-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8999-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8999-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="e8999-119">ホスティング</span><span class="sxs-lookup"><span data-stu-id="e8999-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
