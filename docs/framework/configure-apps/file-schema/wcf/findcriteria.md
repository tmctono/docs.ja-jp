---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eb8ff3905f7696f4c71a79e31db1b8f82c9f0d3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925590"
---
# <a name="findcriteria"></a><span data-ttu-id="c0d1b-101">\<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="c0d1b-101">\<findCriteria></span></span>
<span data-ttu-id="c0d1b-102">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-102">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="c0d1b-103">条件は、検索条件 (探しているサービスを指定します) にグループ化し、終了条件 (検索の最後の長さ) を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-103">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="c0d1b-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c0d1b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c0d1b-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="c0d1b-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0d1b-106">構文</span><span class="sxs-lookup"><span data-stu-id="c0d1b-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0d1b-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c0d1b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c0d1b-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0d1b-109">属性</span><span class="sxs-lookup"><span data-stu-id="c0d1b-109">Attributes</span></span>  
  
|<span data-ttu-id="c0d1b-110">属性</span><span class="sxs-lookup"><span data-stu-id="c0d1b-110">Attribute</span></span>|<span data-ttu-id="c0d1b-111">説明</span><span class="sxs-lookup"><span data-stu-id="c0d1b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c0d1b-112">duration</span><span class="sxs-lookup"><span data-stu-id="c0d1b-112">duration</span></span>|<span data-ttu-id="c0d1b-113">ネットワーク上でサービスからの応答を待機する最長時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-113">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="c0d1b-114">既定の時間は 20 秒です。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-114">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="c0d1b-115">maxResults</span><span class="sxs-lookup"><span data-stu-id="c0d1b-115">maxResults</span></span>|<span data-ttu-id="c0d1b-116">ネットワークまたはインターネット上で待機する、サービスから応答の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-116">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="c0d1b-117">`duration` 属性に指定した時間が経過する前に応答の最大数に達した場合、検索操作は終了します。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-117">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="c0d1b-118">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="c0d1b-118">scopeMatchBy</span></span>|<span data-ttu-id="c0d1b-119">Probe メッセージのスコープをエンドポイントのスコープと一致させるときに使用する、一致のアルゴリズムを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-119">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="c0d1b-120">サポートされているスコープ一致規則は 5 つあります。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-120">There are five supported scope-matching rules.</span></span> <span data-ttu-id="c0d1b-121">スコープ一致規則を指定しなかった場合は、`ScopeMatchByPrefix` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-121">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="c0d1b-122">詳細については、「<xref:System.ServiceModel.Discovery.FindCriteria>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-122">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c0d1b-123">子要素</span><span class="sxs-lookup"><span data-stu-id="c0d1b-123">Child Elements</span></span>  
  
|<span data-ttu-id="c0d1b-124">要素</span><span class="sxs-lookup"><span data-stu-id="c0d1b-124">Element</span></span>|<span data-ttu-id="c0d1b-125">説明</span><span class="sxs-lookup"><span data-stu-id="c0d1b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0d1b-126">\<contractTypeNames></span><span class="sxs-lookup"><span data-stu-id="c0d1b-126">\<contractTypeNames></span></span>](contracttypenames.md)|<span data-ttu-id="c0d1b-127">ワークフローサービスコントラクト型の名前を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-127">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="c0d1b-128">\<findcriteria の\<> 拡張機能 ></span><span class="sxs-lookup"><span data-stu-id="c0d1b-128">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="c0d1b-129">拡張を提供する XML 要素オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-129">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="c0d1b-130">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="c0d1b-130">\<scopes></span></span>](scopes.md)|<span data-ttu-id="c0d1b-131">特定のサービスを特定する検索操作の実行中に使用される絶対 URI を格納するオブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-131">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="c0d1b-132">特定のサービスが見つかった場合、サービス URI とスコープ URI が一致します。複雑な一致を処理するスコープ規則が使用されることもあります。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-132">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0d1b-133">親要素</span><span class="sxs-lookup"><span data-stu-id="c0d1b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="c0d1b-134">要素</span><span class="sxs-lookup"><span data-stu-id="c0d1b-134">Element</span></span>|<span data-ttu-id="c0d1b-135">説明</span><span class="sxs-lookup"><span data-stu-id="c0d1b-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0d1b-136">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="c0d1b-136">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="c0d1b-137">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="c0d1b-137">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0d1b-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0d1b-138">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
