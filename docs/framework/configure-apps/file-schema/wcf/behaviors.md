---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: 914fa04c9aff0c287913104cd9bedc570c473330
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201487"
---
# \<behaviors>

<span data-ttu-id="aa7c6-101">この要素は、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-101">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="aa7c6-102">各コレクションは、エンドポイントとサービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-102">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="aa7c6-103">各動作要素は、その一意の `name` 属性で識別されます。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-103">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="aa7c6-104">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-104">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="aa7c6-105">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-105">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**  
  
## <a name="syntax"></a><span data-ttu-id="aa7c6-106">構文</span><span class="sxs-lookup"><span data-stu-id="aa7c6-106">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa7c6-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="aa7c6-107">Attributes and Elements</span></span>  

 <span data-ttu-id="aa7c6-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa7c6-109">属性</span><span class="sxs-lookup"><span data-stu-id="aa7c6-109">Attributes</span></span>  

 <span data-ttu-id="aa7c6-110">None</span><span class="sxs-lookup"><span data-stu-id="aa7c6-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa7c6-111">子要素</span><span class="sxs-lookup"><span data-stu-id="aa7c6-111">Child Elements</span></span>  
  
|<span data-ttu-id="aa7c6-112">要素</span><span class="sxs-lookup"><span data-stu-id="aa7c6-112">Element</span></span>|<span data-ttu-id="aa7c6-113">説明</span><span class="sxs-lookup"><span data-stu-id="aa7c6-113">Description</span></span>|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|<span data-ttu-id="aa7c6-114">この構成セクションは、特定のエンドポイントに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-114">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[\<serviceBehaviors>](servicebehaviors.md)|<span data-ttu-id="aa7c6-115">この構成セクションは、特定のサービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-115">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa7c6-116">親要素</span><span class="sxs-lookup"><span data-stu-id="aa7c6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="aa7c6-117">要素</span><span class="sxs-lookup"><span data-stu-id="aa7c6-117">Element</span></span>|<span data-ttu-id="aa7c6-118">説明</span><span class="sxs-lookup"><span data-stu-id="aa7c6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="aa7c6-119">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa7c6-120">解説</span><span class="sxs-lookup"><span data-stu-id="aa7c6-120">Remarks</span></span>  

 <span data-ttu-id="aa7c6-121">`<remove>` 要素を使用して、コレクションから特定の動作を削除できます。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-121">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="aa7c6-122">これを行うには、`name` 要素の `<remove>` 属性に、削除する動作の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-122">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="aa7c6-123">また、`<clear>` 要素を使用してコレクションの内容をすべて消去し、動作コレクションの初期値を確実に空にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="aa7c6-123">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa7c6-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa7c6-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="aa7c6-125">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="aa7c6-125">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="aa7c6-126">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="aa7c6-126">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="aa7c6-127">クライアントのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="aa7c6-127">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="aa7c6-128">サービスのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="aa7c6-128">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="aa7c6-129">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="aa7c6-129">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
