---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 5cb64c54067ba695f67d86c0026db77ebbe7d5ee
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919051"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="a7e99-101">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="a7e99-101">\<endpointDiscovery></span></span>
<span data-ttu-id="a7e99-102">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="a7e99-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="a7e99-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a7e99-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a7e99-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="a7e99-104">\<behaviors></span></span>  
<span data-ttu-id="a7e99-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a7e99-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="a7e99-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a7e99-106">\<behavior></span></span>  
<span data-ttu-id="a7e99-107">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="a7e99-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e99-108">構文</span><span class="sxs-lookup"><span data-stu-id="a7e99-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7e99-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a7e99-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a7e99-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7e99-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7e99-111">属性</span><span class="sxs-lookup"><span data-stu-id="a7e99-111">Attributes</span></span>  
  
|<span data-ttu-id="a7e99-112">属性</span><span class="sxs-lookup"><span data-stu-id="a7e99-112">Attribute</span></span>|<span data-ttu-id="a7e99-113">説明</span><span class="sxs-lookup"><span data-stu-id="a7e99-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7e99-114">enabled</span><span class="sxs-lookup"><span data-stu-id="a7e99-114">enabled</span></span>|<span data-ttu-id="a7e99-115">このエンドポイントで探索可能性が有効かどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="a7e99-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="a7e99-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="a7e99-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7e99-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a7e99-117">Child Elements</span></span>  
  
|<span data-ttu-id="a7e99-118">要素</span><span class="sxs-lookup"><span data-stu-id="a7e99-118">Element</span></span>|<span data-ttu-id="a7e99-119">説明</span><span class="sxs-lookup"><span data-stu-id="a7e99-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7e99-120">\<スコープ ></span><span class="sxs-lookup"><span data-stu-id="a7e99-120">\<scopes></span></span>](scopes.md)|<span data-ttu-id="a7e99-121">エンドポイントのスコープ URI のコレクション。</span><span class="sxs-lookup"><span data-stu-id="a7e99-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="a7e99-122">複数の URI を 1 つのエンドポイントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a7e99-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="a7e99-123">拡張機能 > [ endpointdiscovery>]\< [ \<](extensions.md)</span><span class="sxs-lookup"><span data-stu-id="a7e99-123">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="a7e99-124">エンドポイントで発行されるカスタム メタデータを指定できる、XML 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="a7e99-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="a7e99-125">\<型 ></span><span class="sxs-lookup"><span data-stu-id="a7e99-125">\<types></span></span>|<span data-ttu-id="a7e99-126">検索するインターフェイスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="a7e99-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7e99-127">親要素</span><span class="sxs-lookup"><span data-stu-id="a7e99-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a7e99-128">要素</span><span class="sxs-lookup"><span data-stu-id="a7e99-128">Element</span></span>|<span data-ttu-id="a7e99-129">説明</span><span class="sxs-lookup"><span data-stu-id="a7e99-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7e99-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a7e99-130">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a7e99-131">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7e99-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="a7e99-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="a7e99-132">Remarks</span></span>  
 <span data-ttu-id="a7e99-133">エンドポイントの動作構成に追加し、`enabled` 属性を `true` に設定すると、この構成要素の探索可能性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="a7e99-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="a7e99-134">さらに、 [ \<スコープ >](scopes.md)子要素を使用して、クエリ[ \<](extensions.md)中にサービスエンドポイントをフィルター処理するために使用できるカスタムスコープ uri と、カスタムを指定する拡張 > 子要素を指定することができます。標準の探索可能なメタデータと共に公開する必要があるメタデータ (EPR、ContractTypeName、BindingName、Scope、ListenURI)。</span><span class="sxs-lookup"><span data-stu-id="a7e99-134">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="a7e99-135">この構成要素は、 [ \<](servicediscovery.md)サービスレベルの探索可能性を提供する servicediscovery > 要素に依存します。</span><span class="sxs-lookup"><span data-stu-id="a7e99-135">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="a7e99-136">これは、 [ \<servicediscovery >](servicediscovery.md)が構成内に存在しない場合に、この要素の設定が無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7e99-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7e99-137">例</span><span class="sxs-lookup"><span data-stu-id="a7e99-137">Example</span></span>  
 <span data-ttu-id="a7e99-138">次の構成例では、フィルターのスコープと、エンドポイントで発行される拡張メタデータを指定しています。</span><span class="sxs-lookup"><span data-stu-id="a7e99-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
```xml  
<services>
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding"
              address="calculator"
              contract="ICalculatorService"
              behaviorConfiguration="calculatorEndpointBehavior" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDiscovery />
    </behavior>
  </serviceBehaviors>
  <endpointBehaviors>
    <behavior name="calculatorEndpointBehavior">
      <endpointDiscovery enabled="true">
        <scopes>
          <add scope="http://contoso/test1" />
          <add scope="http://contoso/test2" />
        </scopes>
        <extensions>
          <e:Publisher xmlns:e="http://example.org">
            <e:Name>The Example Organization</e:Name>
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>
            <e:Contact>support@example.org</e:Contact>
          </e:Publisher>
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>
        </extensions>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="a7e99-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7e99-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
