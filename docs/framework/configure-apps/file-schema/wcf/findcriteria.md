---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: ce2b1fdd85e0454f901bac393e2f44ae0c6da43f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178148"
---
# \<findCriteria>

<span data-ttu-id="1c9af-101">探索サービスの検索にクライアント アプリケーションによって使用される基準を提供する構成要素。</span><span class="sxs-lookup"><span data-stu-id="1c9af-101">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="1c9af-102">基準は、(探しているサービスを指定する) 検索条件と (検索をどのくらい続けるかを指定する) 検索終了条件にグループ化できます。</span><span class="sxs-lookup"><span data-stu-id="1c9af-102">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dynamicEndpoint>**](dynamicendpoint.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<standardEndpoint>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<discoveryClientSettings>**](discoveryclientsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<findCriteria>**  
  
## <a name="syntax"></a><span data-ttu-id="1c9af-103">構文</span><span class="sxs-lookup"><span data-stu-id="1c9af-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c9af-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1c9af-104">Attributes and Elements</span></span>  

 <span data-ttu-id="1c9af-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c9af-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c9af-106">属性</span><span class="sxs-lookup"><span data-stu-id="1c9af-106">Attributes</span></span>  
  
|<span data-ttu-id="1c9af-107">属性</span><span class="sxs-lookup"><span data-stu-id="1c9af-107">Attribute</span></span>|<span data-ttu-id="1c9af-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="1c9af-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c9af-109">duration</span><span class="sxs-lookup"><span data-stu-id="1c9af-109">duration</span></span>|<span data-ttu-id="1c9af-110">ネットワーク上でサービスからの応答を待機する最長時間を指定する Timespan 値。</span><span class="sxs-lookup"><span data-stu-id="1c9af-110">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="1c9af-111">既定の時間は 20 秒です。</span><span class="sxs-lookup"><span data-stu-id="1c9af-111">The default duration is 20 seconds.</span></span>|  
|<span data-ttu-id="1c9af-112">maxResults</span><span class="sxs-lookup"><span data-stu-id="1c9af-112">maxResults</span></span>|<span data-ttu-id="1c9af-113">ネットワークまたはインターネット上で待機する、サービスから応答の最大数を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="1c9af-113">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="1c9af-114">`duration` 属性に指定した時間が経過する前に応答の最大数に達した場合、検索操作は終了します。</span><span class="sxs-lookup"><span data-stu-id="1c9af-114">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="1c9af-115">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="1c9af-115">scopeMatchBy</span></span>|<span data-ttu-id="1c9af-116">Probe メッセージのスコープをエンドポイントのスコープと一致させるときに使用する、一致のアルゴリズムを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="1c9af-116">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="1c9af-117">サポートされているスコープ一致規則は 5 つあります。</span><span class="sxs-lookup"><span data-stu-id="1c9af-117">There are five supported scope-matching rules.</span></span> <span data-ttu-id="1c9af-118">スコープ一致規則を指定しなかった場合は、`ScopeMatchByPrefix` が使用されます。</span><span class="sxs-lookup"><span data-stu-id="1c9af-118">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="1c9af-119">詳細については、「<xref:System.ServiceModel.Discovery.FindCriteria>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c9af-119">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c9af-120">子要素</span><span class="sxs-lookup"><span data-stu-id="1c9af-120">Child Elements</span></span>  
  
|<span data-ttu-id="1c9af-121">要素</span><span class="sxs-lookup"><span data-stu-id="1c9af-121">Element</span></span>|<span data-ttu-id="1c9af-122">説明</span><span class="sxs-lookup"><span data-stu-id="1c9af-122">Description</span></span>|  
|-------------|-----------------|  
|[\<contractTypeNames>](contracttypenames.md)|<span data-ttu-id="1c9af-123">ワークフローサービスコントラクト型の名前を含む構成要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c9af-123">A collection of configuration elements that contain the names of workflow service contract types.</span></span>|  
|<span data-ttu-id="1c9af-124">\<extensions> の \<findCriteria></span><span class="sxs-lookup"><span data-stu-id="1c9af-124">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="1c9af-125">拡張を提供する XML 要素オブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c9af-125">A collection of XML element objects that provide extensions.</span></span>|  
|[\<scopes>](scopes.md)|<span data-ttu-id="1c9af-126">特定のサービスを特定する検索操作の実行中に使用される絶対 URI を格納するオブジェクトのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c9af-126">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="1c9af-127">特定のサービスが見つかった場合、サービス URI とスコープ URI が一致します。複雑な一致を処理するスコープ規則が使用されることもあります。</span><span class="sxs-lookup"><span data-stu-id="1c9af-127">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c9af-128">親要素</span><span class="sxs-lookup"><span data-stu-id="1c9af-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1c9af-129">要素</span><span class="sxs-lookup"><span data-stu-id="1c9af-129">Element</span></span>|<span data-ttu-id="1c9af-130">説明</span><span class="sxs-lookup"><span data-stu-id="1c9af-130">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="1c9af-131">サービス探索プロセスにクライアントとして参加するためにアプリケーションが必要とする設定を格納します。</span><span class="sxs-lookup"><span data-stu-id="1c9af-131">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c9af-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c9af-132">See also</span></span>

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
