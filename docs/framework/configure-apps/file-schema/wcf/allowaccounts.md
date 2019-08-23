---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926599"
---
# <a name="allowaccounts"></a><span data-ttu-id="cefc5-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="cefc5-101">\<allowAccounts></span></span>
<span data-ttu-id="cefc5-102">Windows Communication Foundation (WCF) サービスをホストするプロセスのユーザーアカウントを指定する構成要素のコレクションが含まれており、共有サービスへの接続アクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="cefc5-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="cefc5-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="cefc5-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cefc5-104">構文</span><span class="sxs-lookup"><span data-stu-id="cefc5-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cefc5-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cefc5-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cefc5-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cefc5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cefc5-107">属性</span><span class="sxs-lookup"><span data-stu-id="cefc5-107">Attributes</span></span>  
 <span data-ttu-id="cefc5-108">なし。</span><span class="sxs-lookup"><span data-stu-id="cefc5-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cefc5-109">子要素</span><span class="sxs-lookup"><span data-stu-id="cefc5-109">Child Elements</span></span>  
  
|<span data-ttu-id="cefc5-110">属性</span><span class="sxs-lookup"><span data-stu-id="cefc5-110">Attribute</span></span>|<span data-ttu-id="cefc5-111">説明</span><span class="sxs-lookup"><span data-stu-id="cefc5-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="cefc5-112">\<add></span><span class="sxs-lookup"><span data-stu-id="cefc5-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="cefc5-113">WCF サービスをホストし、共有サービスへの接続アクセスが付与されているプロセスのユーザーアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="cefc5-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cefc5-114">親要素</span><span class="sxs-lookup"><span data-stu-id="cefc5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="cefc5-115">要素</span><span class="sxs-lookup"><span data-stu-id="cefc5-115">Element</span></span>|<span data-ttu-id="cefc5-116">説明</span><span class="sxs-lookup"><span data-stu-id="cefc5-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cefc5-117">net.pipe > または[ \<](net-pipe.md) [ \<net.tcp >](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="cefc5-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="cefc5-118">Net Pipe または TCP 共有サービスの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="cefc5-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cefc5-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="cefc5-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
