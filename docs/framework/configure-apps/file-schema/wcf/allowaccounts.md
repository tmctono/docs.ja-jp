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

<span data-ttu-id="9ee37-101">Windows Communication Foundation (WCF) サービスをホストするプロセスのユーザーアカウントを指定する構成要素のコレクションが含まれており、共有サービスへの接続アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="9ee37-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="9ee37-102">構文</span><span class="sxs-lookup"><span data-stu-id="9ee37-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ee37-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9ee37-103">Attributes and Elements</span></span>  

 <span data-ttu-id="9ee37-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ee37-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ee37-105">属性</span><span class="sxs-lookup"><span data-stu-id="9ee37-105">Attributes</span></span>  

 <span data-ttu-id="9ee37-106">なし。</span><span class="sxs-lookup"><span data-stu-id="9ee37-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ee37-107">子要素</span><span class="sxs-lookup"><span data-stu-id="9ee37-107">Child Elements</span></span>  
  
|<span data-ttu-id="9ee37-108">属性</span><span class="sxs-lookup"><span data-stu-id="9ee37-108">Attribute</span></span>|<span data-ttu-id="9ee37-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="9ee37-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="9ee37-110">WCF サービスをホストし、共有サービスへの接続アクセスが付与されているプロセスのユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="9ee37-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ee37-111">親要素</span><span class="sxs-lookup"><span data-stu-id="9ee37-111">Parent Elements</span></span>  
  
|<span data-ttu-id="9ee37-112">要素</span><span class="sxs-lookup"><span data-stu-id="9ee37-112">Element</span></span>|<span data-ttu-id="9ee37-113">説明</span><span class="sxs-lookup"><span data-stu-id="9ee37-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ee37-114">[\<net.pipe>](net-pipe.md) または [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="9ee37-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="9ee37-115">Net Pipe または TCP 共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9ee37-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ee37-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="9ee37-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
