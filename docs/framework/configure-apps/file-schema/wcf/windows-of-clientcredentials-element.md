---
title: <windows> <clientCredentials>要素
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: 61ca99213f0b83a5af5df0184a8c1de405366288
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399128"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="4c899-102">\<clientCredentials > 要素\<の windows ></span><span class="sxs-lookup"><span data-stu-id="4c899-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="4c899-103">クライアントを表すために使用される Windows 資格情報の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c899-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
<span data-ttu-id="4c899-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c899-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c899-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4c899-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4c899-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4c899-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4c899-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4c899-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="4c899-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4c899-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="4c899-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="4c899-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="4c899-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windows >**</span><span class="sxs-lookup"><span data-stu-id="4c899-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windows>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c899-111">構文</span><span class="sxs-lookup"><span data-stu-id="4c899-111">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c899-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4c899-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4c899-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c899-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c899-114">属性</span><span class="sxs-lookup"><span data-stu-id="4c899-114">Attributes</span></span>  
  
|<span data-ttu-id="4c899-115">属性</span><span class="sxs-lookup"><span data-stu-id="4c899-115">Attribute</span></span>|<span data-ttu-id="4c899-116">説明</span><span class="sxs-lookup"><span data-stu-id="4c899-116">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="4c899-117">クライアントがサーバーと通信する偽装設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="4c899-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="4c899-118">クライアントが選択する偽装モードは、サーバーでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="4c899-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="4c899-119">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="4c899-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4c899-120">番号サーバーはクライアントの id と特権を取得できますが、クライアントの権限を借用することはできません。</span><span class="sxs-lookup"><span data-stu-id="4c899-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="4c899-121">偽造サーバーは、ローカルシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="4c899-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="4c899-122">-委任:サーバーは、リモートシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="4c899-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="4c899-123">非同期サーバーは、クライアントの権限を借用または識別できません。</span><span class="sxs-lookup"><span data-stu-id="4c899-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="4c899-124">存在偽装レベルが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="4c899-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="4c899-125">既定値は Identification です。</span><span class="sxs-lookup"><span data-stu-id="4c899-125">The default is Identification.</span></span> <span data-ttu-id="4c899-126">この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="4c899-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="4c899-127">このプロパティを `true` に設定すると、Kerberos 認証を利用できない場合、NTLM 認証にダウングレードできます。</span><span class="sxs-lookup"><span data-stu-id="4c899-127">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="4c899-128">このプロパティをに`false`設定すると、NTLM が使用されている場合に Windows Communication Foundation (WCF) がベストエフォートで例外をスローするようになります。</span><span class="sxs-lookup"><span data-stu-id="4c899-128">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="4c899-129">ただし、このプロパティを `false` に設定しても、ネットワーク経由で NTLM 資格情報が送信されなくなるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="4c899-129">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c899-130">子要素</span><span class="sxs-lookup"><span data-stu-id="4c899-130">Child Elements</span></span>  
 <span data-ttu-id="4c899-131">なし。</span><span class="sxs-lookup"><span data-stu-id="4c899-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c899-132">親要素</span><span class="sxs-lookup"><span data-stu-id="4c899-132">Parent Elements</span></span>  
  
|<span data-ttu-id="4c899-133">要素</span><span class="sxs-lookup"><span data-stu-id="4c899-133">Element</span></span>|<span data-ttu-id="4c899-134">説明</span><span class="sxs-lookup"><span data-stu-id="4c899-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c899-135">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="4c899-135">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="4c899-136">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="4c899-136">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c899-137">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c899-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="4c899-138">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4c899-138">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="4c899-139">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="4c899-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="4c899-140">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="4c899-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
