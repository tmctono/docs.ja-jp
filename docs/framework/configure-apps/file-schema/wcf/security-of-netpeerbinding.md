---
title: <security> の <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 543c57d6b2dba1ff5934b49e0e219cf2e5cad153
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170026"
---
# <a name="security-of-netpeerbinding"></a>\<security> の \<netPeerBinding>

[\<netPeerTcpBinding>](netpeertcpbinding.md)使用される認証の種類とメッセージトランスポートに使用されるセキュリティを含む、のセキュリティ設定を定義します。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>構文  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a>属性および要素  

 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|[説明]|  
|---------------|-----------------|  
|mode|省略可能。 このバインディングで構成されたピアが使用するセキュリティの種類を指定します。 既定値は `Message` です。 この属性は <xref:System.ServiceModel.SecurityMode> 型です。|  
  
## <a name="mode-attribute"></a>mode 属性  
  
|値|[説明]|  
|-----------|-----------------|  
|Message|SOAP セキュリティにより、認証、整合性、および機密性が実現します。|  
|None|セキュリティを無効にします。|  
|トランスポート|セキュリティは、HTTPS を使用して確保されます。|  
|TransportWithMessageCredential|HTTPS により、認証および機密性が実現します。 SOAP メッセージには、豊富な資格情報の種類が用意されています。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|このバインディングで構成されたピアが送信するセキュリティで保護されたメッセージのトランスポートの型を定義します。 この要素は <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 型です。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|のすべてのバインディング機能を定義 [\<netPeerTcpBinding>](netpeertcpbinding.md) します。|  
  
## <a name="remarks"></a>解説  

 セキュリティは、メッセージ固有にすることも、トランスポート固有にすることもできます。  
  
## <a name="see-also"></a>関連項目

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [サービスおよびクライアントのセキュリティ保護](../../../wcf/feature-details/securing-services-and-clients.md)
- [資格情報の種類の選択](../../../wcf/feature-details/selecting-a-credential-type.md)
- [バインド](../../../wcf/bindings.md)
- [システムが提供するバインディングの構成](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [サービスとクライアントを構成するためのバインディングの使用](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
