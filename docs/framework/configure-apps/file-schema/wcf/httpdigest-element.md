---
title: <httpDigest> 要素
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 2ceefdd7fab82025e89ad08d8423d57524c2e4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925556"
---
# <a name="httpdigest-element"></a><span data-ttu-id="bab05-102">\<httpDigest > 要素</span><span class="sxs-lookup"><span data-stu-id="bab05-102">\<httpDigest> Element</span></span>
<span data-ttu-id="bab05-103">サービスに対するクライアントの認証時に使用されるダイジェスト型の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="bab05-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
 <span data-ttu-id="bab05-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bab05-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bab05-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="bab05-105">\<behaviors></span></span>  
<span data-ttu-id="bab05-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="bab05-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="bab05-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="bab05-107">\<behavior></span></span>  
<span data-ttu-id="bab05-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="bab05-108">\<clientCredentials></span></span>  
<span data-ttu-id="bab05-109">\<httpDigest ></span><span class="sxs-lookup"><span data-stu-id="bab05-109">\<httpDigest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bab05-110">構文</span><span class="sxs-lookup"><span data-stu-id="bab05-110">Syntax</span></span>  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bab05-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="bab05-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bab05-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="bab05-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bab05-113">属性</span><span class="sxs-lookup"><span data-stu-id="bab05-113">Attributes</span></span>  
  
|<span data-ttu-id="bab05-114">属性</span><span class="sxs-lookup"><span data-stu-id="bab05-114">Attribute</span></span>|<span data-ttu-id="bab05-115">説明</span><span class="sxs-lookup"><span data-stu-id="bab05-115">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="bab05-116">クライアントがサーバーと通信する偽装設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="bab05-116">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="bab05-117">クライアントが選択する偽装モードは、サーバーでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="bab05-117">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="bab05-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="bab05-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bab05-119">番号サーバーはクライアントの id と特権を取得できますが、クライアントの権限を借用することはできません。</span><span class="sxs-lookup"><span data-stu-id="bab05-119">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="bab05-120">偽造サーバーは、ローカルシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="bab05-120">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="bab05-121">-委任:サーバーは、リモートシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="bab05-121">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="bab05-122">非同期サーバーは、クライアントの権限を借用または識別できません。</span><span class="sxs-lookup"><span data-stu-id="bab05-122">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="bab05-123">存在偽装レベルが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="bab05-123">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="bab05-124">既定値は Identification です。</span><span class="sxs-lookup"><span data-stu-id="bab05-124">The default is Identification.</span></span> <span data-ttu-id="bab05-125">この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="bab05-125">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bab05-126">子要素</span><span class="sxs-lookup"><span data-stu-id="bab05-126">Child Elements</span></span>  
 <span data-ttu-id="bab05-127">なし</span><span class="sxs-lookup"><span data-stu-id="bab05-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bab05-128">親要素</span><span class="sxs-lookup"><span data-stu-id="bab05-128">Parent Elements</span></span>  
  
|<span data-ttu-id="bab05-129">要素</span><span class="sxs-lookup"><span data-stu-id="bab05-129">Element</span></span>|<span data-ttu-id="bab05-130">説明</span><span class="sxs-lookup"><span data-stu-id="bab05-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bab05-131">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="bab05-131">\<clientCredentials></span></span>](clientcredentials.md)|<span data-ttu-id="bab05-132">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="bab05-132">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bab05-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="bab05-133">Remarks</span></span>  
 <span data-ttu-id="bab05-134">ダイジェストは、アルゴリズムと入力セットを使用して決定されるハッシュです。</span><span class="sxs-lookup"><span data-stu-id="bab05-134">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="bab05-135">認証する側と認証される側はアルゴリズムに同意し、入力として使用されるデータを交換します。</span><span class="sxs-lookup"><span data-stu-id="bab05-135">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="bab05-136">クライアントはハッシュを計算して、サービスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="bab05-136">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="bab05-137">また、サービスもハッシュを計算して、値を比較します。</span><span class="sxs-lookup"><span data-stu-id="bab05-137">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="bab05-138">一致すると、クライアントが検証されます。</span><span class="sxs-lookup"><span data-stu-id="bab05-138">A match validates the client.</span></span>  
  
 <span data-ttu-id="bab05-139">この機能は、Windows の Active Directory およびインターネット インフォメーション サービス (IIS) と共に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bab05-139">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="bab05-140">詳細については、「 [IIS 6.0 でのダイジェスト認証](https://go.microsoft.com/fwlink/?LinkId=88443)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bab05-140">For more information, see [Digest Authentication in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88443).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bab05-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="bab05-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="bab05-142">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="bab05-142">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="bab05-143">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="bab05-143">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="bab05-144">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="bab05-144">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="bab05-145">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="bab05-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
