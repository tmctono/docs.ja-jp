---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398404"
---
# \<allowAccounts>
<span data-ttu-id="e0ff0-101">Windows Communication Foundation (WCF) サービスをホストするプロセスのユーザーアカウントを指定する構成要素のコレクションが含まれており、共有サービスへの接続アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="e0ff0-101">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**  
  
## <a name="syntax"></a><span data-ttu-id="e0ff0-102">構文</span><span class="sxs-lookup"><span data-stu-id="e0ff0-102">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0ff0-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e0ff0-103">Attributes and Elements</span></span>  
 <span data-ttu-id="e0ff0-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0ff0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0ff0-105">属性</span><span class="sxs-lookup"><span data-stu-id="e0ff0-105">Attributes</span></span>  
 <span data-ttu-id="e0ff0-106">なし。</span><span class="sxs-lookup"><span data-stu-id="e0ff0-106">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e0ff0-107">子要素</span><span class="sxs-lookup"><span data-stu-id="e0ff0-107">Child Elements</span></span>  
  
|<span data-ttu-id="e0ff0-108">属性</span><span class="sxs-lookup"><span data-stu-id="e0ff0-108">Attribute</span></span>|<span data-ttu-id="e0ff0-109">説明</span><span class="sxs-lookup"><span data-stu-id="e0ff0-109">Description</span></span>|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|<span data-ttu-id="e0ff0-110">WCF サービスをホストし、共有サービスへの接続アクセスが付与されているプロセスのユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="e0ff0-110">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e0ff0-111">親要素</span><span class="sxs-lookup"><span data-stu-id="e0ff0-111">Parent Elements</span></span>  
  
|<span data-ttu-id="e0ff0-112">要素</span><span class="sxs-lookup"><span data-stu-id="e0ff0-112">Element</span></span>|<span data-ttu-id="e0ff0-113">Description</span><span class="sxs-lookup"><span data-stu-id="e0ff0-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0ff0-114">[\<net.pipe>](net-pipe.md)もしくは[\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="e0ff0-114">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="e0ff0-115">Net Pipe または TCP 共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0ff0-115">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0ff0-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="e0ff0-116">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
