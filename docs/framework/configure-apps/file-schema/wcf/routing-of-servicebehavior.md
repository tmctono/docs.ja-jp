---
title: <routing> の <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 0998f4fc61de7099879ba6e122eed1e64588baec
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397730"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="f5ceb-102">\<serviceBehavior > の\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="f5ceb-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="f5ceb-103">ルーティング構成の動的な変更を可能にするルーティング サービスへの実行時アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
<span data-ttu-id="f5ceb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5ceb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5ceb-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f5ceb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f5ceb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f5ceb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f5ceb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f5ceb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="f5ceb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f5ceb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="f5ceb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<ルーティング >**</span><span class="sxs-lookup"><span data-stu-id="f5ceb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5ceb-110">構文</span><span class="sxs-lookup"><span data-stu-id="f5ceb-110">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String"
               routeOnHeadersOnly="Boolean"
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5ceb-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f5ceb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5ceb-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5ceb-113">属性</span><span class="sxs-lookup"><span data-stu-id="f5ceb-113">Attributes</span></span>  
  
|<span data-ttu-id="f5ceb-114">属性</span><span class="sxs-lookup"><span data-stu-id="f5ceb-114">Attribute</span></span>|<span data-ttu-id="f5ceb-115">説明</span><span class="sxs-lookup"><span data-stu-id="f5ceb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5ceb-116">filterTable</span><span class="sxs-lookup"><span data-stu-id="f5ceb-116">filterTable</span></span>|<span data-ttu-id="f5ceb-117">ルーティング サービスによって評価されるフィルターを含むルーティング テーブルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-117">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="f5ceb-118">この値は、 `name` [filtertables > セクションの filterTable > 要素の属性と一致している必要があります。 \<](filtertables.md) [ \<](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="f5ceb-118">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="f5ceb-119">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="f5ceb-119">routeOnHeaderOnly</span></span>|<span data-ttu-id="f5ceb-120">フィルターがメッセージの本文とヘッダーの両方を調べるか、ヘッダーのみを調べるかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-120">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="f5ceb-121">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-121">The default is `true`.</span></span>|  
|<span data-ttu-id="f5ceb-122">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="f5ceb-122">soapProcessingEnabled</span></span>|<span data-ttu-id="f5ceb-123">SOAP 処理を実行するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-123">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5ceb-124">子要素</span><span class="sxs-lookup"><span data-stu-id="f5ceb-124">Child Elements</span></span>  
 <span data-ttu-id="f5ceb-125">なし。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5ceb-126">親要素</span><span class="sxs-lookup"><span data-stu-id="f5ceb-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f5ceb-127">要素</span><span class="sxs-lookup"><span data-stu-id="f5ceb-127">Element</span></span>|<span data-ttu-id="f5ceb-128">説明</span><span class="sxs-lookup"><span data-stu-id="f5ceb-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5ceb-129">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f5ceb-129">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="f5ceb-130">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-130">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5ceb-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="f5ceb-131">Remarks</span></span>  
 <span data-ttu-id="f5ceb-132">サービスの動作構成に追加すると、この構成要素により、サービスのルーティングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-132">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="f5ceb-133">この要素には、サービスで使用される実際のルーティング テーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-133">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="f5ceb-134">この構成セクションを使用すると、配置パターンの変更時にルーティング設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-134">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="f5ceb-135">実行時には、新しいルーティング設定を使用した独自のルーティング拡張を登録できます。ルーティング サービスは (開始時に適用されていた規則に関係なく) 更新済みの構成情報を使用して新たなメッセージとセッションにサービスを提供します。ただし、インフライトのメッセージやセッションには以前の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-135">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="f5ceb-136">このようにして、実行時において、セッション セーフでリサイクルの程度を抑えた状態でのルーティング サービスの再構成が可能となります。</span><span class="sxs-lookup"><span data-stu-id="f5ceb-136">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
