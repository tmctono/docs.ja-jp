---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 3432d33c0cd65af03d2b1ac1302ca2c8ff3e0f43
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201643"
---
# \<allowAccounts>

Windows Communication Foundation (WCF) サービスをホストするプロセスのユーザーアカウントを指定する構成要素のコレクションが含まれており、共有サービスへの接続アクセスが許可されます。  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a>構文  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>属性および要素  

 以降のセクションでは、属性、子要素、および親要素について説明します。  
  
### <a name="attributes"></a>属性  

 なし。  
  
### <a name="child-elements"></a>子要素  
  
|属性|[説明]|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|WCF サービスをホストし、共有サービスへの接続アクセスが付与されているプロセスのユーザーアカウントを追加します。|  
  
### <a name="parent-elements"></a>親要素  
  
|要素|説明|  
|-------------|-----------------|  
|[\<net.pipe>](net-pipe.md) または [\<net.tcp>](net-tcp.md)|Net Pipe または TCP 共有サービスの構成設定を指定します。|  
  
## <a name="see-also"></a>関連項目

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
