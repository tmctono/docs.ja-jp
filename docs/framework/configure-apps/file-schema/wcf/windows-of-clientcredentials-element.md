---
title: <windows> <clientCredentials>要素
ms.date: 03/30/2017
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
ms.openlocfilehash: e9f0ed9879cc42ea25b83e6b626139a40a593112
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940309"
---
# <a name="windows-of-clientcredentials-element"></a><span data-ttu-id="a6915-102">\<clientCredentials > 要素\<の windows ></span><span class="sxs-lookup"><span data-stu-id="a6915-102">\<windows> of \<clientCredentials> Element</span></span>
<span data-ttu-id="a6915-103">クライアントを表すために使用される Windows 資格情報の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6915-103">Specifies the settings for a Windows credential to be used to represent the client.</span></span>  
  
 <span data-ttu-id="a6915-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a6915-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a6915-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="a6915-105">\<behaviors></span></span>  
<span data-ttu-id="a6915-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="a6915-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="a6915-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a6915-107">\<behavior></span></span>  
<span data-ttu-id="a6915-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a6915-108">\<clientCredentials></span></span>  
<span data-ttu-id="a6915-109">\<windows ></span><span class="sxs-lookup"><span data-stu-id="a6915-109">\<windows></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6915-110">構文</span><span class="sxs-lookup"><span data-stu-id="a6915-110">Syntax</span></span>  
  
```xml  
<windows allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"
         allowNtlm="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6915-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a6915-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a6915-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6915-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6915-113">属性</span><span class="sxs-lookup"><span data-stu-id="a6915-113">Attributes</span></span>  
  
|<span data-ttu-id="a6915-114">属性</span><span class="sxs-lookup"><span data-stu-id="a6915-114">Attribute</span></span>|<span data-ttu-id="a6915-115">説明</span><span class="sxs-lookup"><span data-stu-id="a6915-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedImpersonationLevel`|<span data-ttu-id="a6915-116">クライアントがサーバーと通信する偽装設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="a6915-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="a6915-117">クライアントが選択する偽装モードは、サーバーでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="a6915-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="a6915-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="a6915-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a6915-119">番号サーバーはクライアントの id と特権を取得できますが、クライアントの権限を借用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a6915-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="a6915-120">偽造サーバーは、ローカルシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="a6915-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="a6915-121">-委任:サーバーは、リモートシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="a6915-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="a6915-122">非同期サーバーは、クライアントの権限を借用または識別できません。</span><span class="sxs-lookup"><span data-stu-id="a6915-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="a6915-123">存在偽装レベルが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="a6915-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="a6915-124">既定値は Identification です。</span><span class="sxs-lookup"><span data-stu-id="a6915-124">The default is Identification.</span></span> <span data-ttu-id="a6915-125">この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="a6915-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
|`allowNtlm`|<span data-ttu-id="a6915-126">このプロパティを `true` に設定すると、Kerberos 認証を利用できない場合、NTLM 認証にダウングレードできます。</span><span class="sxs-lookup"><span data-stu-id="a6915-126">Setting this property to `true` allows authentication to downgrade to NTLM if Kerberos is not available.</span></span><br /><br /> <span data-ttu-id="a6915-127">このプロパティをに`false`設定すると、NTLM が使用されている場合に Windows Communication Foundation (WCF) がベストエフォートで例外をスローするようになります。</span><span class="sxs-lookup"><span data-stu-id="a6915-127">Setting this property to `false` causes Windows Communication Foundation (WCF) to make a best-effort to throw an exception if NTLM is used.</span></span> <span data-ttu-id="a6915-128">ただし、このプロパティを `false` に設定しても、ネットワーク経由で NTLM 資格情報が送信されなくなるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="a6915-128">Note that setting this property to `false` may not prevent NTLM credentials from being sent over the wire.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6915-129">子要素</span><span class="sxs-lookup"><span data-stu-id="a6915-129">Child Elements</span></span>  
 <span data-ttu-id="a6915-130">なし。</span><span class="sxs-lookup"><span data-stu-id="a6915-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a6915-131">親要素</span><span class="sxs-lookup"><span data-stu-id="a6915-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a6915-132">要素</span><span class="sxs-lookup"><span data-stu-id="a6915-132">Element</span></span>|<span data-ttu-id="a6915-133">説明</span><span class="sxs-lookup"><span data-stu-id="a6915-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6915-134">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="a6915-134">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="a6915-135">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6915-135">Specifies the credentials used to authenticate the client to the service.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a6915-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6915-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>
- <xref:System.ServiceModel.Security.WindowsClientCredential>
- [<span data-ttu-id="a6915-137">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a6915-137">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="a6915-138">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="a6915-138">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="a6915-139">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a6915-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
