---
title: <behaviors>
ms.date: 03/30/2017
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
ms.openlocfilehash: bcdd26f038b343040d81b0add83bf166a5e3151f
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74139694"
---
# <a name="behaviors"></a><span data-ttu-id="cad2d-101">\<の動作 ></span><span class="sxs-lookup"><span data-stu-id="cad2d-101">\<behaviors></span></span>
<span data-ttu-id="cad2d-102">この要素は、`endpointBehaviors` と`serviceBehaviors` という 2 つの子コレクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="cad2d-102">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="cad2d-103">各コレクションは、エンドポイントとサービスによって使用されるそれぞれの動作要素を定義します。</span><span class="sxs-lookup"><span data-stu-id="cad2d-103">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="cad2d-104">各動作要素は、その一意の `name` 属性で識別されます。</span><span class="sxs-lookup"><span data-stu-id="cad2d-104">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="cad2d-105">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cad2d-105">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="cad2d-106">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad2d-106">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
<span data-ttu-id="cad2d-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cad2d-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cad2d-108">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="cad2d-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cad2d-109">&nbsp;&nbsp;&nbsp;&nbsp; **\<の動作 >**</span><span class="sxs-lookup"><span data-stu-id="cad2d-109">&nbsp;&nbsp;&nbsp;&nbsp;**\<behaviors>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad2d-110">構文</span><span class="sxs-lookup"><span data-stu-id="cad2d-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
  </serviceBehaviors>
  <endpointBehaviors>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cad2d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cad2d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cad2d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cad2d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cad2d-113">属性</span><span class="sxs-lookup"><span data-stu-id="cad2d-113">Attributes</span></span>  
 <span data-ttu-id="cad2d-114">None</span><span class="sxs-lookup"><span data-stu-id="cad2d-114">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cad2d-115">子要素</span><span class="sxs-lookup"><span data-stu-id="cad2d-115">Child Elements</span></span>  
  
|<span data-ttu-id="cad2d-116">要素</span><span class="sxs-lookup"><span data-stu-id="cad2d-116">Element</span></span>|<span data-ttu-id="cad2d-117">説明</span><span class="sxs-lookup"><span data-stu-id="cad2d-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cad2d-118">endpointBehaviors > の \<</span><span class="sxs-lookup"><span data-stu-id="cad2d-118">\<endpointBehaviors></span></span>](endpointbehaviors.md)|<span data-ttu-id="cad2d-119">この構成セクションは、特定のエンドポイントに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="cad2d-119">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="cad2d-120">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cad2d-120">\<serviceBehaviors></span></span>](servicebehaviors.md)|<span data-ttu-id="cad2d-121">この構成セクションは、特定のサービスに対して定義されたすべての動作を表します。</span><span class="sxs-lookup"><span data-stu-id="cad2d-121">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cad2d-122">親要素</span><span class="sxs-lookup"><span data-stu-id="cad2d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cad2d-123">要素</span><span class="sxs-lookup"><span data-stu-id="cad2d-123">Element</span></span>|<span data-ttu-id="cad2d-124">説明</span><span class="sxs-lookup"><span data-stu-id="cad2d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cad2d-125">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cad2d-125">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="cad2d-126">すべての Windows Communication Foundation (WCF) 構成要素のルート要素です。</span><span class="sxs-lookup"><span data-stu-id="cad2d-126">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cad2d-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="cad2d-127">Remarks</span></span>  
 <span data-ttu-id="cad2d-128">`<remove>` 要素を使用して、コレクションから特定の動作を削除できます。</span><span class="sxs-lookup"><span data-stu-id="cad2d-128">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="cad2d-129">これを行うには、`name` 要素の `<remove>` 属性に、削除する動作の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="cad2d-129">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="cad2d-130">また、`<clear>` 要素を使用してコレクションの内容をすべて消去し、動作コレクションの初期値を確実に空にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cad2d-130">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cad2d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="cad2d-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.BehaviorsSection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>
- [<span data-ttu-id="cad2d-132">動作を使用したランタイムの構成と拡張</span><span class="sxs-lookup"><span data-stu-id="cad2d-132">Configuring and Extending the Runtime with Behaviors</span></span>](../../../wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
- [<span data-ttu-id="cad2d-133">クライアントの動作の構成</span><span class="sxs-lookup"><span data-stu-id="cad2d-133">Configuring Client Behaviors</span></span>](../../../wcf/configuring-client-behaviors.md)
- [<span data-ttu-id="cad2d-134">クライアントのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="cad2d-134">Specifying Client Run-Time Behavior</span></span>](../../../wcf/specifying-client-run-time-behavior.md)
- [<span data-ttu-id="cad2d-135">サービスのランタイム動作の指定</span><span class="sxs-lookup"><span data-stu-id="cad2d-135">Specifying Service Run-Time Behavior</span></span>](../../../wcf/specifying-service-run-time-behavior.md)
- [<span data-ttu-id="cad2d-136">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="cad2d-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
