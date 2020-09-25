---
title: <windows><clientCredentials>要素の
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 115e1822659c04ee37a7364f7b25616b52dc5efe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177827"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="1001f-102">\<windows>\<clientCredentials>要素の</span><span class="sxs-lookup"><span data-stu-id="1001f-102">\<windows> of \<clientCredentials> Element</span></span>

<span data-ttu-id="1001f-103">クライアントを表すために使用される Windows 資格情報の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1001f-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**  
  
## <a name="syntax"></a><span data-ttu-id="1001f-104">構文</span><span class="sxs-lookup"><span data-stu-id="1001f-104">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1001f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1001f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1001f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1001f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1001f-107">属性</span><span class="sxs-lookup"><span data-stu-id="1001f-107">Attributes</span></span>  
  
|<span data-ttu-id="1001f-108">属性</span><span class="sxs-lookup"><span data-stu-id="1001f-108">Attribute</span></span>|<span data-ttu-id="1001f-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="1001f-109">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="1001f-110">クライアントがサーバーと通信する偽装設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="1001f-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="1001f-111">クライアントが選択する偽装モードは、サーバーでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="1001f-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="1001f-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1001f-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1001f-113">-識別: サーバーはクライアントの id と特権を取得できますが、クライアントの権限を借用することはできません。</span><span class="sxs-lookup"><span data-stu-id="1001f-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="1001f-114">-権限借用: サーバーは、ローカルシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="1001f-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="1001f-115">-委任: サーバーは、リモートシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="1001f-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="1001f-116">-Anonymous: サーバーはクライアントの権限を借用または識別できません。</span><span class="sxs-lookup"><span data-stu-id="1001f-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="1001f-117">-None: 偽装レベルが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="1001f-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="1001f-118">既定値は Identification です。</span><span class="sxs-lookup"><span data-stu-id="1001f-118">The default is Identification.</span></span> <span data-ttu-id="1001f-119">この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="1001f-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="1001f-120">このプロパティを `true` に設定すると、Kerberos 認証を利用できない場合、NTLM 認証にダウングレードできます。</span><span class="sxs-lookup"><span data-stu-id="1001f-120">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="1001f-121">このプロパティをに設定する `false` と、NTLM が使用されている場合に Windows Communication Foundation (WCF) がベストエフォートで例外をスローするようになります。</span><span class="sxs-lookup"><span data-stu-id="1001f-121">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="1001f-122">ただし、このプロパティを `false` に設定しても、ネットワーク経由で NTLM 資格情報が送信されなくなるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="1001f-122">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1001f-123">子要素</span><span class="sxs-lookup"><span data-stu-id="1001f-123">Child Elements</span></span>  

 <span data-ttu-id="1001f-124">なし。</span><span class="sxs-lookup"><span data-stu-id="1001f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1001f-125">親要素</span><span class="sxs-lookup"><span data-stu-id="1001f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="1001f-126">要素</span><span class="sxs-lookup"><span data-stu-id="1001f-126">Element</span></span>|<span data-ttu-id="1001f-127">説明</span><span class="sxs-lookup"><span data-stu-id="1001f-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="1001f-128">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="1001f-128">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1001f-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="1001f-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="1001f-130">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1001f-130">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="1001f-131">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="1001f-131">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="1001f-132">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="1001f-132">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
