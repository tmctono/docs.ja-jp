---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: e2b92b88c3e2a8abb14f58af90aab6e2e58ce14a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557295"
---
# \<byteStreamMessageEncoding>
文字エンコーディングを指定するオプションを使用し、メッセージ エンコーディングをバイト ストリームとして指定します。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a>構文  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a>属性および要素  
 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  
  
|属性|説明|  
|---------------|-----------------|  
|messageVersion|バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。 このプロパティは、<xref:System.ServiceModel.Channels.MessageVersion.None%2A> のメッセージ バージョン値にのみ設定できます。 バイト ストリーム メッセージ エンコーダーは、他のメッセージ バージョンをサポートしません。<br /><br /> この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。|  
  
### <a name="child-elements"></a>子要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。 この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|カスタム バインドのすべてのバインド機能を定義します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [メッセージ エンコーディング](message-encoding.md)
- [メッセージ エンコーダーを選択する](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [バインド](../../../wcf/bindings.md)
- [バインディングの拡張](../../../wcf/extending/extending-bindings.md)
- [カスタム バインディング](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
