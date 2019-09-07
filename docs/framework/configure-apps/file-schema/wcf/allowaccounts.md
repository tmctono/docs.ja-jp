---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398404"
---
# <a name="allowaccounts"></a><span data-ttu-id="dd51d-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="dd51d-101">\<allowAccounts></span></span>
<span data-ttu-id="dd51d-102">Windows Communication Foundation (WCF) サービスをホストするプロセスのユーザーアカウントを指定する構成要素のコレクションが含まれており、共有サービスへの接続アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="dd51d-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="dd51d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd51d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dd51d-104">&nbsp;&nbsp;[ **\<System.servicemodel. activation >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="dd51d-104">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="dd51d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<net.pipe >** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="dd51d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="dd51d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<allowAccounts >**</span><span class="sxs-lookup"><span data-stu-id="dd51d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd51d-107">構文</span><span class="sxs-lookup"><span data-stu-id="dd51d-107">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd51d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dd51d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd51d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd51d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd51d-110">属性</span><span class="sxs-lookup"><span data-stu-id="dd51d-110">Attributes</span></span>  
 <span data-ttu-id="dd51d-111">なし。</span><span class="sxs-lookup"><span data-stu-id="dd51d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd51d-112">子要素</span><span class="sxs-lookup"><span data-stu-id="dd51d-112">Child Elements</span></span>  
  
|<span data-ttu-id="dd51d-113">属性</span><span class="sxs-lookup"><span data-stu-id="dd51d-113">Attribute</span></span>|<span data-ttu-id="dd51d-114">説明</span><span class="sxs-lookup"><span data-stu-id="dd51d-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="dd51d-115">\<add></span><span class="sxs-lookup"><span data-stu-id="dd51d-115">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="dd51d-116">WCF サービスをホストし、共有サービスへの接続アクセスが付与されているプロセスのユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="dd51d-116">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd51d-117">親要素</span><span class="sxs-lookup"><span data-stu-id="dd51d-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dd51d-118">要素</span><span class="sxs-lookup"><span data-stu-id="dd51d-118">Element</span></span>|<span data-ttu-id="dd51d-119">説明</span><span class="sxs-lookup"><span data-stu-id="dd51d-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd51d-120">net.pipe > または[ \<](net-pipe.md) [ \<net.tcp >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="dd51d-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="dd51d-121">Net Pipe または TCP 共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd51d-121">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd51d-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="dd51d-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
