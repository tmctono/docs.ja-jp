---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 12ac8d9a7b0ed584fb1308e56d197a03b1c53e51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700879"
---
# <a name="endpointextensions"></a><span data-ttu-id="fbe6f-101">\<endpointExtensions></span><span class="sxs-lookup"><span data-stu-id="fbe6f-101">\<endpointExtensions></span></span>
<span data-ttu-id="fbe6f-102">このセクションは、コンピューターまたはアプリケーションの構成ファイルの拡張セクションに新たな標準エンドポイントを登録します。</span><span class="sxs-lookup"><span data-stu-id="fbe6f-102">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="fbe6f-103">このコレクションに標準エンドポイントを追加するには、`add` キーワードを使用し、要素の `type` 属性をエンドポイントの種類に設定して、`name` 属性を標準エンドポイントの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="fbe6f-103">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="fbe6f-104">次の例は、`add` 要素と `name` 属性を使用して、構成ファイルの `<endpointExtensions>` セクションに標準エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="fbe6f-104">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <endpointExtensions>
      <add name="udpDiscoveryEndpoint"
           type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="fbe6f-105">標準エンドポイントを追加すると、次の例に示すように、このエンドポイントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fbe6f-105">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="fbe6f-106">[\<エンドポイント >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)要素、`kind`属性に登録されている標準エンドポイントの種類を指定します、`<endpointExtensions>`セクション。</span><span class="sxs-lookup"><span data-stu-id="fbe6f-106">In the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="fbe6f-107">`endpointConfiguration`属性は同じになります、`name`標準エンドポイントの構成要素の属性、`<standardEndpoints>`セクション。</span><span class="sxs-lookup"><span data-stu-id="fbe6f-107">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Service1">
      <endpoint kind="udpDiscoveryEndpoint"
                endpointConfiguration="udpConfig" />
    </service>
  </services>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
