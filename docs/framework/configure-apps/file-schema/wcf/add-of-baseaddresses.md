---
title: <add> の <baseAddresses>
ms.date: 03/30/2017
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
ms.openlocfilehash: cd0ef5cc5f0f809bdafa23bd312e7e30fcdccc21
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181610"
---
# <a name="add-of-baseaddresses"></a><span data-ttu-id="6e119-102">\<add> の \<baseAddresses></span><span class="sxs-lookup"><span data-stu-id="6e119-102">\<add> of \<baseAddresses></span></span>

<span data-ttu-id="6e119-103">サービス ホストによって使用されるベース アドレスを指定する構成要素を表します。</span><span class="sxs-lookup"><span data-stu-id="6e119-103">Represents a configuration element that specifies the base addresses used by the service host.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<services>**](services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<service>**](service.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<host>**](host.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<baseAddresses>**](baseaddresses.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="6e119-104">構文</span><span class="sxs-lookup"><span data-stu-id="6e119-104">Syntax</span></span>  
  
```xml  
<add baseAddress="string" />
```  
  
## <a name="type"></a><span data-ttu-id="6e119-105">種類</span><span class="sxs-lookup"><span data-stu-id="6e119-105">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e119-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6e119-106">Attributes and Elements</span></span>  

 <span data-ttu-id="6e119-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e119-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e119-108">属性</span><span class="sxs-lookup"><span data-stu-id="6e119-108">Attributes</span></span>  
  
|<span data-ttu-id="6e119-109">属性</span><span class="sxs-lookup"><span data-stu-id="6e119-109">Attribute</span></span>|<span data-ttu-id="6e119-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="6e119-110">Description</span></span>|  
|---------------|-----------------|  
|`baseAddress`|<span data-ttu-id="6e119-111">サービス ホストによって使用されるベース アドレスを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="6e119-111">A string that specifies a base address used by the service host.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e119-112">子要素</span><span class="sxs-lookup"><span data-stu-id="6e119-112">Child Elements</span></span>  

 <span data-ttu-id="6e119-113">なし。</span><span class="sxs-lookup"><span data-stu-id="6e119-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e119-114">親要素</span><span class="sxs-lookup"><span data-stu-id="6e119-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6e119-115">要素</span><span class="sxs-lookup"><span data-stu-id="6e119-115">Element</span></span>|<span data-ttu-id="6e119-116">説明</span><span class="sxs-lookup"><span data-stu-id="6e119-116">Description</span></span>|  
|-------------|-----------------|  
|[\<baseAddresses>](baseaddresses.md)|<span data-ttu-id="6e119-117">`baseAddress` 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="6e119-117">A collection of `baseAddress` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e119-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e119-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>
- [<span data-ttu-id="6e119-119">ホスティング</span><span class="sxs-lookup"><span data-stu-id="6e119-119">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
