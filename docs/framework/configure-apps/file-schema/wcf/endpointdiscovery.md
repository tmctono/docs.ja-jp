---
title: <endpointDiscovery>
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: 621c742e3bb06ce91fa5a6b8951351295f73df9e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185809"
---
# \<endpointDiscovery>

<span data-ttu-id="ee3f4-101">エンドポイントのさまざまな探索設定を指定します (探索可能性、スコープ、メタデータに対するカスタム拡張など)。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-101">Specifies the various discovery settings for an endpoint, such as its discoverability, scopes, and any custom extensions to its metadata.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointDiscovery>**  
  
## <a name="syntax"></a><span data-ttu-id="ee3f4-102">構文</span><span class="sxs-lookup"><span data-stu-id="ee3f4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee3f4-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ee3f4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="ee3f4-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee3f4-105">属性</span><span class="sxs-lookup"><span data-stu-id="ee3f4-105">Attributes</span></span>  
  
|<span data-ttu-id="ee3f4-106">属性</span><span class="sxs-lookup"><span data-stu-id="ee3f4-106">Attribute</span></span>|<span data-ttu-id="ee3f4-107">説明</span><span class="sxs-lookup"><span data-stu-id="ee3f4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee3f4-108">enabled</span><span class="sxs-lookup"><span data-stu-id="ee3f4-108">enabled</span></span>|<span data-ttu-id="ee3f4-109">このエンドポイントで探索可能性が有効かどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-109">A Boolean value that specifies whether discoverability is enabled on this endpoint.</span></span> <span data-ttu-id="ee3f4-110">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-110">The default is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee3f4-111">子要素</span><span class="sxs-lookup"><span data-stu-id="ee3f4-111">Child Elements</span></span>  
  
|<span data-ttu-id="ee3f4-112">要素</span><span class="sxs-lookup"><span data-stu-id="ee3f4-112">Element</span></span>|<span data-ttu-id="ee3f4-113">説明</span><span class="sxs-lookup"><span data-stu-id="ee3f4-113">Description</span></span>|  
|-------------|-----------------|  
|[\<scopes>](scopes.md)|<span data-ttu-id="ee3f4-114">エンドポイントのスコープ URI のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-114">A collection of scope URIs for the endpoint.</span></span> <span data-ttu-id="ee3f4-115">複数の URI を 1 つのエンドポイントに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-115">More than one scope Uris can be associated with a single endpoint.</span></span>|  
|<span data-ttu-id="ee3f4-116">[\<extensions>](extensions.md) [/ \<endpointDiscovery> ]</span><span class="sxs-lookup"><span data-stu-id="ee3f4-116">[\<extensions>](extensions.md) [of \<endpointDiscovery>]</span></span>|<span data-ttu-id="ee3f4-117">エンドポイントで発行されるカスタム メタデータを指定できる、XML 要素のコレクション。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-117">A collection of XML elements that allows you to specify custom metadata to be published for an endpoint.</span></span>|  
|\<types>|<span data-ttu-id="ee3f4-118">検索するインターフェイスのコレクション。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-118">A collection of interfaces to search for.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee3f4-119">親要素</span><span class="sxs-lookup"><span data-stu-id="ee3f4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ee3f4-120">要素</span><span class="sxs-lookup"><span data-stu-id="ee3f4-120">Element</span></span>|<span data-ttu-id="ee3f4-121">説明</span><span class="sxs-lookup"><span data-stu-id="ee3f4-121">Description</span></span>|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="ee3f4-122">動作の要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-122">Specifies a behavior element.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="ee3f4-123">解説</span><span class="sxs-lookup"><span data-stu-id="ee3f4-123">Remarks</span></span>  

 <span data-ttu-id="ee3f4-124">エンドポイントの動作構成に追加し、`enabled` 属性を `true` に設定すると、この構成要素の探索可能性が有効になります。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-124">When added to the endpoint’s behavior configuration and with the `enabled` attribute set to `true`, this configuration element enables its discoverability.</span></span> <span data-ttu-id="ee3f4-125">また、子要素を使用して、 [\<scopes>](scopes.md) クエリ中にサービスエンドポイントをフィルター処理するために使用できるカスタムスコープ uri を指定したり、 [\<extensions>](extensions.md) 標準の探索可能なメタデータ (EPR、Contracttypename、Bindingname、Scope、ListenURI) と共に発行する必要があるカスタムメタデータを指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-125">In addition, you can use the [\<scopes>](scopes.md)child element to specifying custom scope Uris that can be used to filter service endpoints during query, as well as the [\<extensions>](extensions.md) child element to specify custom metadata that should be published along with the standard discoverable metadata (EPR, ContractTypeName, BindingName, Scope and ListenURI).</span></span>  
  
 <span data-ttu-id="ee3f4-126">この構成要素は、探索可能性 [\<serviceDiscovery>](servicediscovery.md) のサービスレベルコントロールを提供する要素に依存します。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-126">This configuration element is dependent on the [\<serviceDiscovery>](servicediscovery.md) element that provides the service level control of discoverability.</span></span> <span data-ttu-id="ee3f4-127">これは [\<serviceDiscovery>](servicediscovery.md) 、が構成内に存在しない場合に、この要素の設定が無視されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-127">This means that this element’s settings are ignored if [\<serviceDiscovery>](servicediscovery.md) is not present in the configuration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee3f4-128">例</span><span class="sxs-lookup"><span data-stu-id="ee3f4-128">Example</span></span>  

 <span data-ttu-id="ee3f4-129">次の構成例では、フィルターのスコープと、エンドポイントで発行される拡張メタデータを指定しています。</span><span class="sxs-lookup"><span data-stu-id="ee3f4-129">The following configuration example specifies filtering scopes and extension metadata to be published for an endpoint.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ee3f4-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee3f4-130">See also</span></span>

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
