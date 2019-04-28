---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 125baba917a49135aaa426df2cfa1a4dbe8ac1e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700911"
---
# <a name="endpointdiscovery"></a><span data-ttu-id="1c681-101">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="1c681-101">\<endpointDiscovery></span></span>
<span data-ttu-id="1c681-102">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="1c681-102">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
<span data-ttu-id="1c681-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1c681-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="1c681-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="1c681-104">\<behaviors></span></span>  
<span data-ttu-id="1c681-105">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="1c681-105">\<endpointBehaviors></span></span>  
<span data-ttu-id="1c681-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1c681-106">\<behavior></span></span>  
<span data-ttu-id="1c681-107">\<endpointDiscovery></span><span class="sxs-lookup"><span data-stu-id="1c681-107">\<endpointDiscovery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c681-108">構文</span><span class="sxs-lookup"><span data-stu-id="1c681-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c681-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1c681-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1c681-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1c681-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c681-111">属性</span><span class="sxs-lookup"><span data-stu-id="1c681-111">Attributes</span></span>  
  
|<span data-ttu-id="1c681-112">属性</span><span class="sxs-lookup"><span data-stu-id="1c681-112">Attribute</span></span>|<span data-ttu-id="1c681-113">説明</span><span class="sxs-lookup"><span data-stu-id="1c681-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c681-114">enabled</span><span class="sxs-lookup"><span data-stu-id="1c681-114">enabled</span></span>|<span data-ttu-id="1c681-115">このエンドポイントで見つけやすさが有効になっているかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="1c681-115">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="1c681-116">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1c681-116">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c681-117">子要素</span><span class="sxs-lookup"><span data-stu-id="1c681-117">Child Elements</span></span>  
  
|<span data-ttu-id="1c681-118">要素</span><span class="sxs-lookup"><span data-stu-id="1c681-118">Element</span></span>|<span data-ttu-id="1c681-119">説明</span><span class="sxs-lookup"><span data-stu-id="1c681-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c681-120">\<scopes></span><span class="sxs-lookup"><span data-stu-id="1c681-120">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="1c681-121">エンドポイントのスコープ URI のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c681-121">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="1c681-122">複数の URI を 1 つのエンドポイントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1c681-122">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="1c681-123">[\<拡張機能 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [の\<endpointDiscovery >]</span><span class="sxs-lookup"><span data-stu-id="1c681-123">[\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="1c681-124">エンドポイントで発行されるカスタム メタデータを指定できる、XML 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c681-124">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|<span data-ttu-id="1c681-125">\<types></span><span class="sxs-lookup"><span data-stu-id="1c681-125">\<types></span></span>|<span data-ttu-id="1c681-126">検索するインターフェイスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="1c681-126">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c681-127">親要素</span><span class="sxs-lookup"><span data-stu-id="1c681-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1c681-128">要素</span><span class="sxs-lookup"><span data-stu-id="1c681-128">Element</span></span>|<span data-ttu-id="1c681-129">説明</span><span class="sxs-lookup"><span data-stu-id="1c681-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c681-130">\<behavior></span><span class="sxs-lookup"><span data-stu-id="1c681-130">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1c681-131">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="1c681-131">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="1c681-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="1c681-132">Remarks</span></span>  
 <span data-ttu-id="1c681-133">エンドポイントの動作構成に追加し、`enabled` 属性を `true` に設定すると、この構成要素の探索可能性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="1c681-133">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="1c681-134">さらに、使用、 [\<スコープ >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)カスタム スコープ クエリ中にサービス エンドポイントのフィルター処理に使用できる Uri を指定する子要素だけでなく[\<拡張機能 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) (EPR、ContractTypeName、BindingName、スコープおよび ListenURI) は、標準の探索可能なメタデータと共に発行する必要のあるカスタム メタデータを指定する子要素。</span><span class="sxs-lookup"><span data-stu-id="1c681-134">In addition, you can use the [\<scopes>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="1c681-135">この構成要素に依存、 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)探索可能性のサービス レベルの制御を提供する要素。</span><span class="sxs-lookup"><span data-stu-id="1c681-135">This configuration element is dependent on the [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="1c681-136">場合、この要素の設定は無視されます、つまり[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)は、構成に存在しません。</span><span class="sxs-lookup"><span data-stu-id="1c681-136">This means that this element’s settings are ignored if [\<serviceDiscovery>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c681-137">例</span><span class="sxs-lookup"><span data-stu-id="1c681-137">Example</span></span>  
 <span data-ttu-id="1c681-138">次の構成例では、フィルターのスコープと、エンドポイントで発行される拡張メタデータを指定しています。</span><span class="sxs-lookup"><span data-stu-id="1c681-138">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1c681-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c681-139">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
