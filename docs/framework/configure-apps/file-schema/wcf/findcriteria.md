---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: 44e068ee205bc5e04382164e7ab00716b2c07dcf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855160"
---
# <a name="findcriteria"></a><span data-ttu-id="e8fd8-101">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="e8fd8-101">\<findCriteria></span></span>
<span data-ttu-id="e8fd8-102">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="e8fd8-103">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
<span data-ttu-id="e8fd8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8fd8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e8fd8-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e8fd8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e8fd8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="e8fd8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="e8fd8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dynamicEndpoint >** ](dynamicendpoint.md)</span><span class="sxs-lookup"><span data-stu-id="e8fd8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)</span></span>\
<span data-ttu-id="e8fd8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<standardEndpoint >** </span><span class="sxs-lookup"><span data-stu-id="e8fd8-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**</span></span>\
<span data-ttu-id="e8fd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<discoveryClientSettings >** ](discoveryclientsettings.md)</span><span class="sxs-lookup"><span data-stu-id="e8fd8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)</span></span>\
<span data-ttu-id="e8fd8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<findCriteria >**</span><span class="sxs-lookup"><span data-stu-id="e8fd8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fd8-111">構文</span><span class="sxs-lookup"><span data-stu-id="e8fd8-111">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8fd8-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e8fd8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e8fd8-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8fd8-114">属性</span><span class="sxs-lookup"><span data-stu-id="e8fd8-114">Attributes</span></span>  
  
|<span data-ttu-id="e8fd8-115">属性</span><span class="sxs-lookup"><span data-stu-id="e8fd8-115">Attribute</span></span>|<span data-ttu-id="e8fd8-116">説明</span><span class="sxs-lookup"><span data-stu-id="e8fd8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e8fd8-117">duration</span><span class="sxs-lookup"><span data-stu-id="e8fd8-117">duration</span></span>|<span data-ttu-id="e8fd8-118">ネットワーク上でサービスからの応答を待機する最長時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-118">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="e8fd8-119">既定の時間は 20 秒です。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-119">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="e8fd8-120">maxResults</span><span class="sxs-lookup"><span data-stu-id="e8fd8-120">maxResults</span></span>|<span data-ttu-id="e8fd8-121">ネットワークまたはインターネット上で待機する、サービスから応答の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-121">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="e8fd8-122">`duration` 属性に指定した時間が経過する前に応答の最大数に達した場合、検索操作は終了します。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-122">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="e8fd8-123">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="e8fd8-123">scopeMatchBy</span></span>|<span data-ttu-id="e8fd8-124">Probe メッセージのスコープをエンドポイントのスコープと一致させるときに使用する、一致のアルゴリズムを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-124">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="e8fd8-125">サポートされているスコープ一致規則は 5 つあります。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-125">There are five supported scope-matching rules.</span></span> <span data-ttu-id="e8fd8-126">スコープ一致規則を指定しなかった場合は、`ScopeMatchByPrefix` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-126">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="e8fd8-127">詳細については、「<xref:System.ServiceModel.Discovery.FindCriteria>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-127">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8fd8-128">子要素</span><span class="sxs-lookup"><span data-stu-id="e8fd8-128">Child Elements</span></span>  
  
|<span data-ttu-id="e8fd8-129">要素</span><span class="sxs-lookup"><span data-stu-id="e8fd8-129">Element</span></span>|<span data-ttu-id="e8fd8-130">説明</span><span class="sxs-lookup"><span data-stu-id="e8fd8-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8fd8-131">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="e8fd8-131">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="e8fd8-132">ワークフローサービスコントラクト型の名前を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-132">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="e8fd8-133">\<findcriteria の\<> 拡張機能 ></span><span class="sxs-lookup"><span data-stu-id="e8fd8-133">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="e8fd8-134">拡張を提供する XML 要素オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-134">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="e8fd8-135">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="e8fd8-135">\<scopes></span></span>](scopes.md)|<span data-ttu-id="e8fd8-136">特定のサービスを特定する検索操作の実行中に使用される絶対 URI を格納するオブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-136">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="e8fd8-137">特定のサービスが見つかった場合、サービス URI とスコープ URI が一致します。複雑な一致を処理するスコープ規則が使用されることもあります。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-137">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8fd8-138">親要素</span><span class="sxs-lookup"><span data-stu-id="e8fd8-138">Parent Elements</span></span>  
  
|<span data-ttu-id="e8fd8-139">要素</span><span class="sxs-lookup"><span data-stu-id="e8fd8-139">Element</span></span>|<span data-ttu-id="e8fd8-140">説明</span><span class="sxs-lookup"><span data-stu-id="e8fd8-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8fd8-141">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="e8fd8-141">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="e8fd8-142">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="e8fd8-142">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8fd8-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8fd8-143">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
