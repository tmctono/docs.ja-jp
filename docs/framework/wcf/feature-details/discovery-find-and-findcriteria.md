---
title: 探索検索と FindCriteria
ms.date: 03/30/2017
ms.assetid: 99016fa4-1778-495b-b4cc-0e22fbec42c6
ms.openlocfilehash: 6efbfe34bbe5b15696d247c291f1d88006a53a36
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345782"
---
# <a name="discovery-find-and-findcriteria"></a><span data-ttu-id="8955e-102">探索検索と FindCriteria</span><span class="sxs-lookup"><span data-stu-id="8955e-102">Discovery Find and FindCriteria</span></span>
<span data-ttu-id="8955e-103">探索検索操作は、1 つ以上のサービスを探索するためにクライアントによって開始される操作であり、探索における主要なアクションの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="8955e-103">A discovery find operation is initiated by a client to discover one or more services and is one of the main actions in discovery.</span></span> <span data-ttu-id="8955e-104">検索を実行すると、WS-Discovery Probe メッセージがネットワークを介して送信されます。</span><span class="sxs-lookup"><span data-stu-id="8955e-104">Performing a find sends a WS-Discovery Probe message over the network.</span></span> <span data-ttu-id="8955e-105">指定された条件に一致するサービスは、WS-Discovery ProbeMatch メッセージを使用して応答します。</span><span class="sxs-lookup"><span data-stu-id="8955e-105">Services that match the criteria specified reply with WS-Discovery ProbeMatch messages.</span></span> <span data-ttu-id="8955e-106">探索メッセージの詳細については、次を参照してください。、 [Ws-discovery 仕様](https://go.microsoft.com/fwlink/?LinkID=122347)します。</span><span class="sxs-lookup"><span data-stu-id="8955e-106">For more information about discovery messages, see the [WS-Discovery specification](https://go.microsoft.com/fwlink/?LinkID=122347).</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="8955e-107">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="8955e-107">DiscoveryClient</span></span>  
 <span data-ttu-id="8955e-108"><xref:System.ServiceModel.Discovery.DiscoveryClient> クラスは、検索操作を実行するメカニズムを提供し、探索クライアントの操作を簡単に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8955e-108">The <xref:System.ServiceModel.Discovery.DiscoveryClient> class provides the mechanism to perform find operations and makes performing discovery client operations easy.</span></span> <span data-ttu-id="8955e-109">このクラスには、(ブロックする) 同期検索を実行する <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> メソッドと、ブロックしない非同期検索を実行する <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> メソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8955e-109">It contains a <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method, which performs a (blocking) synchronous find, and a <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method, which initiates a non-blocking asynchronous find.</span></span> <span data-ttu-id="8955e-110">どちらのメソッドも <xref:System.ServiceModel.Discovery.FindCriteria> パラメーターを使用し、<xref:System.ServiceModel.Discovery.FindResponse> オブジェクトを介してユーザーに結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="8955e-110">Both methods take a <xref:System.ServiceModel.Discovery.FindCriteria> parameter, and provide results to the user through a <xref:System.ServiceModel.Discovery.FindResponse> object.</span></span>  
  
## <a name="findcriteria"></a><span data-ttu-id="8955e-111">FindCriteria</span><span class="sxs-lookup"><span data-stu-id="8955e-111">FindCriteria</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria> <span data-ttu-id="8955e-112">探しているサービスの種類を指定するには、検索条件にグループ化することができ、検索 (検索持続期間)、終了条件をいくつかのプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8955e-112">has several properties, which can be grouped into search criteria, which specify what services you are looking for, and find termination criteria (how long the search should last).</span></span> <span data-ttu-id="8955e-113"><xref:System.ServiceModel.Discovery.FindCriteria> には、複数の検索条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8955e-113">A <xref:System.ServiceModel.Discovery.FindCriteria> can contain multiple search criteria.</span></span> <span data-ttu-id="8955e-114">既定では、サービスがすべての条件に一致する必要があり、そうでない場合は、サービスがそれ自体を一致サービスと見なしません。</span><span class="sxs-lookup"><span data-stu-id="8955e-114">By default, the service has to match all of the components otherwise it does not consider itself a matching service.</span></span> <span data-ttu-id="8955e-115">条件の一部にのみ一致するサービスを検索する場合は、サービスにカスタムの検索ロジックを実装するか、複数のクエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="8955e-115">If you want to find services that only match some of the criteria, you can implement custom find logic on the service or you can use multiple queries.</span></span>  
  
 <span data-ttu-id="8955e-116">検索条件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8955e-116">Search criteria include:</span></span>  
  
-   <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement> <span data-ttu-id="8955e-117">-省略可能。</span><span class="sxs-lookup"><span data-stu-id="8955e-117">- Optional.</span></span> <span data-ttu-id="8955e-118">検索対象のサービスのコントラクト名、およびサービスの検索に通常使用される条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="8955e-118">The contract name of the service being searched for and the criteria typically used when searching for a service.</span></span> <span data-ttu-id="8955e-119">複数のコントラクト名が指定されると、すべてのコントラクトに一致するサービス エンドポイントのみが応答します。</span><span class="sxs-lookup"><span data-stu-id="8955e-119">If more than one contract name is specified, only service endpoints matching ALL contracts reply.</span></span> <span data-ttu-id="8955e-120">Wcf エンドポイントのみをサポートできること 1 つのコントラクトに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8955e-120">Note that in WCF an endpoint can only support one contract.</span></span>  
  
-   <xref:System.ServiceModel.Discovery.Configuration.ScopeElement> <span data-ttu-id="8955e-121">-省略可能。</span><span class="sxs-lookup"><span data-stu-id="8955e-121">- Optional.</span></span> <span data-ttu-id="8955e-122">Scopes は、個々のサービス エンドポイントの分類に使用される絶対 URI です。</span><span class="sxs-lookup"><span data-stu-id="8955e-122">Scopes are absolute URIs that are used to categorize individual service endpoints.</span></span> <span data-ttu-id="8955e-123">複数のエンドポイントが同じコントラクトを公開し、これらのエンドポイントのサブセットを検索する手段が必要な場合は、これを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8955e-123">You may want to use this in scenarios where multiple endpoints expose the same contract and you want a way to search for a subset of the endpoints.</span></span> <span data-ttu-id="8955e-124">複数のスコープが指定されると、すべてのスコープに一致するサービス エンドポイントのみが応答します。</span><span class="sxs-lookup"><span data-stu-id="8955e-124">If more than one scope is specified, only service endpoints matching ALL scopes reply.</span></span>  
  
-   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchBy%2A> <span data-ttu-id="8955e-125">-Probe メッセージをエンドポイントのスコープに一致するときに使用する一致アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="8955e-125">- Specifies the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span> <span data-ttu-id="8955e-126">サポートされているスコープ一致規則は、次の 5 つです。</span><span class="sxs-lookup"><span data-stu-id="8955e-126">There are five supported scope-matching rules:</span></span>  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByExact?displayProperty=nameWithType> <span data-ttu-id="8955e-127">大文字の基本的な文字列比較を実行します。</span><span class="sxs-lookup"><span data-stu-id="8955e-127">does a basic case-sensitive string comparison.</span></span>  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix?displayProperty=nameWithType> <span data-ttu-id="8955e-128">区切られたセグメント単位で一致する「/」。</span><span class="sxs-lookup"><span data-stu-id="8955e-128">matches by segments separated by "/".</span></span> <span data-ttu-id="8955e-129">検索する`http://contoso/building1`スコープを持つサービスに一致`http://contoso/building/floor1`します。</span><span class="sxs-lookup"><span data-stu-id="8955e-129">A search for `http://contoso/building1` matches a service with scope `http://contoso/building/floor1`.</span></span> <span data-ttu-id="8955e-130">一致しないので注意`http://contoso/building100`最後の 2 つのセグメントが一致しないためです。</span><span class="sxs-lookup"><span data-stu-id="8955e-130">Note that it does not match `http://contoso/building100` because the last two segments do not match.</span></span>  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByLdap?displayProperty=nameWithType> <span data-ttu-id="8955e-131">LDAP URL を使用してセグメント単位でスコープに一致します。</span><span class="sxs-lookup"><span data-stu-id="8955e-131">matches scopes by segments using an LDAP URL.</span></span>  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByUuid?displayProperty=nameWithType> <span data-ttu-id="8955e-132">正確に UUID 文字列を使用したスコープと一致します。</span><span class="sxs-lookup"><span data-stu-id="8955e-132">matches scopes exactly using a UUID string.</span></span>  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByNone?displayProperty=nameWithType> <span data-ttu-id="8955e-133">スコープが指定されていないサービスだけと一致します。</span><span class="sxs-lookup"><span data-stu-id="8955e-133">matches only those services that do not specify a scope.</span></span>  
  
     <span data-ttu-id="8955e-134">スコープ一致規則が指定されていない場合は、<xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix> が使用されます。</span><span class="sxs-lookup"><span data-stu-id="8955e-134">If a scope-matching rule is not specified, <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix> is used.</span></span>  
  
 <span data-ttu-id="8955e-135">終了条件は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8955e-135">Termination criteria include:</span></span>  
  
1. <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> <span data-ttu-id="8955e-136">-ネットワーク上のサービスから応答を待機する最大時間。</span><span class="sxs-lookup"><span data-stu-id="8955e-136">- The maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="8955e-137">既定の時間は 20 秒です。</span><span class="sxs-lookup"><span data-stu-id="8955e-137">The default duration is 20 seconds.</span></span>  
  
2. <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> <span data-ttu-id="8955e-138">-待機する応答の最大数。</span><span class="sxs-lookup"><span data-stu-id="8955e-138">- The maximum number of replies to wait for.</span></span> <span data-ttu-id="8955e-139"><xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> が経過する前に <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> 応答が受信された場合は、検出操作が終了します。</span><span class="sxs-lookup"><span data-stu-id="8955e-139">If <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> replies are received before <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed, the find operation ends.</span></span>  
  
## <a name="findresponse"></a><span data-ttu-id="8955e-140">FindResponse</span><span class="sxs-lookup"><span data-stu-id="8955e-140">FindResponse</span></span>  
 <xref:System.ServiceModel.Discovery.FindResponse> <span data-ttu-id="8955e-141"><xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A>コレクション プロパティをネットワーク上のサービスを照合することによって送信された応答が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8955e-141">has an <xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A> collection property that contains any replies sent by matching services on the network.</span></span> <span data-ttu-id="8955e-142">応答したサービスがない場合、このコレクションは空です。</span><span class="sxs-lookup"><span data-stu-id="8955e-142">If no services replied, the collection is empty.</span></span> <span data-ttu-id="8955e-143">1 つ以上のサービスが応答した場合、各応答は <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> オブジェクトに格納されます。これには、アドレスやコントラクトなど、サービスについての追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8955e-143">If one or more services replied, each reply is stored in an <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> object, which contains the address, contract, and some additional information about the service.</span></span>  
  
 <span data-ttu-id="8955e-144">次の例は、コードで検索操作を実行する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="8955e-144">The following example shows how to perform a find operation in code.</span></span>  
  
```  
// Create DiscoveryClient  
DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
// Create FindCriteria  
FindCriteria findCriteria = new FindCriteria(typeof(IPrinterService));  
findCriteria.Scopes.Add(new Uri("http://www.contoso.com/building1/floor1"));  
findCriteria.Duration = TimeSpan.FromSeconds(10);   
  
// Find ICalculatorService endpoints              
FindResponse findResponse = discoveryClient.Find(findCriteria);  
  
Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8955e-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="8955e-145">See also</span></span>

- [<span data-ttu-id="8955e-146">WCF Discovery の概要</span><span class="sxs-lookup"><span data-stu-id="8955e-146">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="8955e-147">探索クライアント チャネルの使用</span><span class="sxs-lookup"><span data-stu-id="8955e-147">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)
- [<span data-ttu-id="8955e-148">スコープを使用した探索</span><span class="sxs-lookup"><span data-stu-id="8955e-148">Discovery with Scopes</span></span>](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [<span data-ttu-id="8955e-149">Basic</span><span class="sxs-lookup"><span data-stu-id="8955e-149">Basic</span></span>](../../../../docs/framework/wcf/samples/basic-sample.md)
