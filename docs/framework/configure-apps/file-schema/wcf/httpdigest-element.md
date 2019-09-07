---
title: <httpDigest> 要素
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: f392ebf4eeb6a008952fd4d5ef4e301e57f6eb31
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397992"
---
# <a name="httpdigest-element"></a><span data-ttu-id="91e47-102">\<httpDigest > 要素</span><span class="sxs-lookup"><span data-stu-id="91e47-102">\<httpDigest> Element</span></span>
<span data-ttu-id="91e47-103">サービスに対するクライアントの認証時に使用されるダイジェスト型の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="91e47-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
<span data-ttu-id="91e47-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91e47-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91e47-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="91e47-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="91e47-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91e47-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="91e47-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91e47-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="91e47-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="91e47-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="91e47-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="91e47-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="91e47-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpDigest >**</span><span class="sxs-lookup"><span data-stu-id="91e47-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91e47-111">構文</span><span class="sxs-lookup"><span data-stu-id="91e47-111">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91e47-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="91e47-112">Attributes and Elements</span></span>  
 <span data-ttu-id="91e47-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="91e47-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91e47-114">属性</span><span class="sxs-lookup"><span data-stu-id="91e47-114">Attributes</span></span>  
  
|<span data-ttu-id="91e47-115">属性</span><span class="sxs-lookup"><span data-stu-id="91e47-115">Attribute</span></span>|<span data-ttu-id="91e47-116">説明</span><span class="sxs-lookup"><span data-stu-id="91e47-116">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="91e47-117">クライアントがサーバーと通信する偽装設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="91e47-117">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="91e47-118">クライアントが選択する偽装モードは、サーバーでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="91e47-118">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="91e47-119">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="91e47-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="91e47-120">番号サーバーはクライアントの id と特権を取得できますが、クライアントの権限を借用することはできません。</span><span class="sxs-lookup"><span data-stu-id="91e47-120">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="91e47-121">偽造サーバーは、ローカルシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="91e47-121">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="91e47-122">-委任:サーバーは、リモートシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="91e47-122">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="91e47-123">非同期サーバーは、クライアントの権限を借用または識別できません。</span><span class="sxs-lookup"><span data-stu-id="91e47-123">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="91e47-124">存在偽装レベルが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="91e47-124">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="91e47-125">既定値は Identification です。</span><span class="sxs-lookup"><span data-stu-id="91e47-125">The default is Identification.</span></span> <span data-ttu-id="91e47-126">この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="91e47-126">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91e47-127">子要素</span><span class="sxs-lookup"><span data-stu-id="91e47-127">Child Elements</span></span>  
 <span data-ttu-id="91e47-128">なし</span><span class="sxs-lookup"><span data-stu-id="91e47-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91e47-129">親要素</span><span class="sxs-lookup"><span data-stu-id="91e47-129">Parent Elements</span></span>  
  
|<span data-ttu-id="91e47-130">要素</span><span class="sxs-lookup"><span data-stu-id="91e47-130">Element</span></span>|<span data-ttu-id="91e47-131">説明</span><span class="sxs-lookup"><span data-stu-id="91e47-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91e47-132">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="91e47-132">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="91e47-133">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="91e47-133">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91e47-134">Remarks</span><span class="sxs-lookup"><span data-stu-id="91e47-134">Remarks</span></span>  
 <span data-ttu-id="91e47-135">ダイジェストは、アルゴリズムと入力セットを使用して決定されるハッシュです。</span><span class="sxs-lookup"><span data-stu-id="91e47-135">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="91e47-136">認証する側と認証される側はアルゴリズムに同意し、入力として使用されるデータを交換します。</span><span class="sxs-lookup"><span data-stu-id="91e47-136">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="91e47-137">クライアントはハッシュを計算して、サービスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="91e47-137">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="91e47-138">また、サービスもハッシュを計算して、値を比較します。</span><span class="sxs-lookup"><span data-stu-id="91e47-138">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="91e47-139">一致すると、クライアントが検証されます。</span><span class="sxs-lookup"><span data-stu-id="91e47-139">A match validates the client.</span></span>  
  
 <span data-ttu-id="91e47-140">この機能は、Windows の Active Directory およびインターネット インフォメーション サービス (IIS) と共に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="91e47-140">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="91e47-141">詳細については、「 [IIS 6.0 でのダイジェスト認証](https://go.microsoft.com/fwlink/?LinkId=88443)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91e47-141">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91e47-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="91e47-142">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="91e47-143">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="91e47-143">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="91e47-144">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="91e47-144">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="91e47-145">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="91e47-145">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="91e47-146">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="91e47-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
