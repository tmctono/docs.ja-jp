---
title: <routing> の <serviceBehavior>
ms.date: 03/30/2017
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
ms.openlocfilehash: cd53b720bad5752189f1c30d9e4acd3a66830396
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150883"
---
# <a name="routing-of-servicebehavior"></a><span data-ttu-id="716b7-102">\<routing> の \<serviceBehavior></span><span class="sxs-lookup"><span data-stu-id="716b7-102">\<routing> of \<serviceBehavior></span></span>

<span data-ttu-id="716b7-103">ルーティング構成の動的な変更を可能にするルーティング サービスへの実行時アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="716b7-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**  
  
## <a name="syntax"></a><span data-ttu-id="716b7-104">構文</span><span class="sxs-lookup"><span data-stu-id="716b7-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="716b7-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="716b7-105">Attributes and Elements</span></span>  

 <span data-ttu-id="716b7-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="716b7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="716b7-107">属性</span><span class="sxs-lookup"><span data-stu-id="716b7-107">Attributes</span></span>  
  
|<span data-ttu-id="716b7-108">属性</span><span class="sxs-lookup"><span data-stu-id="716b7-108">Attribute</span></span>|<span data-ttu-id="716b7-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="716b7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="716b7-110">filterTable</span><span class="sxs-lookup"><span data-stu-id="716b7-110">filterTable</span></span>|<span data-ttu-id="716b7-111">ルーティング サービスによって評価されるフィルターを含むルーティング テーブルの名前を指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="716b7-111">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="716b7-112">この値は `name` 、セクション内の要素の属性と一致している必要があり [\<filterTable>](filtertable.md) [\<filterTables>](filtertables.md) ます。</span><span class="sxs-lookup"><span data-stu-id="716b7-112">This value must match the `name` attribute of a [\<filterTable>](filtertable.md) element in the [\<filterTables>](filtertables.md) section.</span></span>|  
|<span data-ttu-id="716b7-113">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="716b7-113">routeOnHeaderOnly</span></span>|<span data-ttu-id="716b7-114">フィルターがメッセージの本文とヘッダーの両方を調べるか、ヘッダーのみを調べるかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="716b7-114">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="716b7-115">既定では、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="716b7-115">The default is `true`.</span></span>|  
|<span data-ttu-id="716b7-116">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="716b7-116">soapProcessingEnabled</span></span>|<span data-ttu-id="716b7-117">SOAP 処理を実行するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="716b7-117">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="716b7-118">子要素</span><span class="sxs-lookup"><span data-stu-id="716b7-118">Child Elements</span></span>  

 <span data-ttu-id="716b7-119">なし。</span><span class="sxs-lookup"><span data-stu-id="716b7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="716b7-120">親要素</span><span class="sxs-lookup"><span data-stu-id="716b7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="716b7-121">要素</span><span class="sxs-lookup"><span data-stu-id="716b7-121">Element</span></span>|<span data-ttu-id="716b7-122">説明</span><span class="sxs-lookup"><span data-stu-id="716b7-122">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="716b7-123">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="716b7-123">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="716b7-124">解説</span><span class="sxs-lookup"><span data-stu-id="716b7-124">Remarks</span></span>  

 <span data-ttu-id="716b7-125">サービスの動作構成に追加すると、この構成要素により、サービスのルーティングが有効になります。</span><span class="sxs-lookup"><span data-stu-id="716b7-125">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="716b7-126">この要素には、サービスで使用される実際のルーティング テーブルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="716b7-126">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="716b7-127">この構成セクションを使用すると、配置パターンの変更時にルーティング設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="716b7-127">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="716b7-128">実行時には、新しいルーティング設定を使用した独自のルーティング拡張を登録できます。ルーティング サービスは (開始時に適用されていた規則に関係なく) 更新済みの構成情報を使用して新たなメッセージとセッションにサービスを提供します。ただし、インフライトのメッセージやセッションには以前の規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="716b7-128">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="716b7-129">このようにして、実行時において、セッション セーフでリサイクルの程度を抑えた状態でのルーティング サービスの再構成が可能となります。</span><span class="sxs-lookup"><span data-stu-id="716b7-129">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
