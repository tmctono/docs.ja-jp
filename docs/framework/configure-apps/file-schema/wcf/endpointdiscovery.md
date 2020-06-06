---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 98b1655f42b7b43604ed4ab9d66870ec204a9590
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398016"
---
# \<endpointDiscovery>
<span data-ttu-id="23df1-101">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="23df1-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="23df1-102">構文</span><span class="sxs-lookup"><span data-stu-id="23df1-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23df1-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="23df1-103">Attributes and Elements</span></span>  
 <span data-ttu-id="23df1-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="23df1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23df1-105">属性</span><span class="sxs-lookup"><span data-stu-id="23df1-105">Attributes</span></span>  
  
|<span data-ttu-id="23df1-106">属性</span><span class="sxs-lookup"><span data-stu-id="23df1-106">Attribute</span></span>|<span data-ttu-id="23df1-107">説明</span><span class="sxs-lookup"><span data-stu-id="23df1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23df1-108">enabled</span><span class="sxs-lookup"><span data-stu-id="23df1-108">enabled</span></span>|<span data-ttu-id="23df1-109">このエンドポイントで探索可能性が有効かどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="23df1-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="23df1-110">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="23df1-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23df1-111">子要素</span><span class="sxs-lookup"><span data-stu-id="23df1-111">Child Elements</span></span>  
  
|<span data-ttu-id="23df1-112">要素</span><span class="sxs-lookup"><span data-stu-id="23df1-112">Element</span></span>|<span data-ttu-id="23df1-113">Description</span><span class="sxs-lookup"><span data-stu-id="23df1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="23df1-114">エンドポイントのスコープ URI のコレクション。</span><span class="sxs-lookup"><span data-stu-id="23df1-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="23df1-115">複数の URI を 1 つのエンドポイントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="23df1-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="23df1-116">[\<extensions>](extensions.md)[/ \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="23df1-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="23df1-117">エンドポイントで発行されるカスタム メタデータを指定できる、XML 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="23df1-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="23df1-118">検索するインターフェイスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="23df1-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23df1-119">親要素</span><span class="sxs-lookup"><span data-stu-id="23df1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="23df1-120">要素</span><span class="sxs-lookup"><span data-stu-id="23df1-120">Element</span></span>|<span data-ttu-id="23df1-121">Description</span><span class="sxs-lookup"><span data-stu-id="23df1-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="23df1-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="23df1-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="23df1-123">解説</span><span class="sxs-lookup"><span data-stu-id="23df1-123">Remarks</span></span>  
 <span data-ttu-id="23df1-124">エンドポイントの動作構成に追加し、`enabled` 属性を `true` に設定すると、この構成要素の探索可能性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="23df1-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="23df1-125">また、子要素を使用して、 [\<scopes>](scopes.md) クエリ中にサービスエンドポイントをフィルター処理するために使用できるカスタムスコープ uri を指定したり、 [\<extensions>](extensions.md) 標準の探索可能なメタデータ (EPR、Contracttypename、Bindingname、Scope、ListenURI) と共に発行する必要があるカスタムメタデータを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="23df1-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="23df1-126">この構成要素は、探索可能性 [\<serviceDiscovery>](servicediscovery.md) のサービスレベルコントロールを提供する要素に依存します。</span><span class="sxs-lookup"><span data-stu-id="23df1-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="23df1-127">これは [\<serviceDiscovery>](servicediscovery.md) 、が構成内に存在しない場合に、この要素の設定が無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="23df1-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23df1-128">例</span><span class="sxs-lookup"><span data-stu-id="23df1-128">Example</span></span>  
 <span data-ttu-id="23df1-129">次の構成例では、フィルターのスコープと、エンドポイントで発行される拡張メタデータを指定しています。</span><span class="sxs-lookup"><span data-stu-id="23df1-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23df1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="23df1-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
