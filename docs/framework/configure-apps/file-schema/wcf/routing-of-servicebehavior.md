---
title: <routing> の <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: 73a610056f94efe144705968eaf97c8314c1ae0d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934197"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="15433-102">\<serviceBehavior > の\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="15433-102">\<routing> of \<serviceBehavior></span></span>
<span data-ttu-id="15433-103">ルーティング構成の動的な変更を可能にするルーティング サービスへの実行時アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="15433-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="15433-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="15433-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="15433-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="15433-105">\<behaviors></span></span>  
<span data-ttu-id="15433-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="15433-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="15433-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15433-107">\<behavior></span></span>  
<span data-ttu-id="15433-108">\<ルーティング ></span><span class="sxs-lookup"><span data-stu-id="15433-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15433-109">構文</span><span class="sxs-lookup"><span data-stu-id="15433-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15433-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="15433-110">Attributes and Elements</span></span>  
 <span data-ttu-id="15433-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="15433-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15433-112">属性</span><span class="sxs-lookup"><span data-stu-id="15433-112">Attributes</span></span>  
  
|<span data-ttu-id="15433-113">属性</span><span class="sxs-lookup"><span data-stu-id="15433-113">Attribute</span></span>|<span data-ttu-id="15433-114">説明</span><span class="sxs-lookup"><span data-stu-id="15433-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15433-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="15433-115">filterTable</span></span>|<span data-ttu-id="15433-116">ルーティング サービスによって評価されるフィルターを含むルーティング テーブルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="15433-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="15433-117">この値は、 `name` [filtertables > セクションの filterTable > 要素の属性と一致している必要があります。 \<](filtertables.md) [ \<](filtertable.md)</span><span class="sxs-lookup"><span data-stu-id="15433-117">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="15433-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="15433-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="15433-119">フィルターがメッセージの本文とヘッダーの両方を調べるか、ヘッダーのみを調べるかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="15433-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="15433-120">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="15433-120">The default is `true`.</span></span>|  
|<span data-ttu-id="15433-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="15433-121">soapProcessingEnabled</span></span>|<span data-ttu-id="15433-122">SOAP 処理を実行するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="15433-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15433-123">子要素</span><span class="sxs-lookup"><span data-stu-id="15433-123">Child Elements</span></span>  
 <span data-ttu-id="15433-124">なし。</span><span class="sxs-lookup"><span data-stu-id="15433-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15433-125">親要素</span><span class="sxs-lookup"><span data-stu-id="15433-125">Parent Elements</span></span>  
  
|<span data-ttu-id="15433-126">要素</span><span class="sxs-lookup"><span data-stu-id="15433-126">Element</span></span>|<span data-ttu-id="15433-127">説明</span><span class="sxs-lookup"><span data-stu-id="15433-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15433-128">\<behavior></span><span class="sxs-lookup"><span data-stu-id="15433-128">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="15433-129">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="15433-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15433-130">Remarks</span><span class="sxs-lookup"><span data-stu-id="15433-130">Remarks</span></span>  
 <span data-ttu-id="15433-131">サービスの動作構成に追加すると、この構成要素により、サービスのルーティングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="15433-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="15433-132">この要素には、サービスで使用される実際のルーティング テーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="15433-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="15433-133">この構成セクションを使用すると、配置パターンの変更時にルーティング設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="15433-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="15433-134">実行時には、新しいルーティング設定を使用した独自のルーティング拡張を登録できます。ルーティング サービスは (開始時に適用されていた規則に関係なく) 更新済みの構成情報を使用して新たなメッセージとセッションにサービスを提供します。ただし、インフライトのメッセージやセッションには以前の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="15433-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="15433-135">このようにして、実行時において、セッション セーフでリサイクルの程度を抑えた状態でのルーティング サービスの再構成が可能となります。</span><span class="sxs-lookup"><span data-stu-id="15433-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
