---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: d0587ae942d1b0c7eb72bee830ca3ced76e4270c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190034"
---
# \<endpointExtensions>

このセクションは、コンピューターまたはアプリケーションの構成ファイルの拡張セクションに新たな標準エンドポイントを登録します。 このコレクションに標準エンドポイントを追加するには、`add` キーワードを使用し、要素の `type` 属性をエンドポイントの種類に設定して、`name` 属性を標準エンドポイントの名前に設定します。  
  
 次の例は、`add` 要素と `name` 属性を使用して、構成ファイルの `<endpointExtensions>` セクションに標準エンドポイントを追加します。  
  
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
  
 標準エンドポイントを追加すると、次の例に示すように、このエンドポイントを使用できます。 要素では、 [\<endpoint>](endpoint-element.md) 属性は、 `kind` セクションに登録されている標準エンドポイントの種類を指定し `<endpointExtensions>` ます。 属性は、 `endpointConfiguration` `name` セクション内の標準エンドポイントの構成要素の属性と同じになり `<standardEndpoints>` ます。  
  
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
