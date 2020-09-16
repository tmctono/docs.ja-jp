---
title: <httpDigest> 要素
ms.date: 03/30/2017
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
ms.openlocfilehash: 0ffaba218d31a77407c598f8b7fa0260daa4e39c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556903"
---
# <a name="httpdigest-element"></a><span data-ttu-id="61f75-102">\<httpDigest> 要素</span><span class="sxs-lookup"><span data-stu-id="61f75-102">\<httpDigest> Element</span></span>
<span data-ttu-id="61f75-103">サービスに対するクライアントの認証時に使用されるダイジェスト型の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="61f75-103">Specifies a digest type credential used when authenticating the client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpDigest>**  
  
## <a name="syntax"></a><span data-ttu-id="61f75-104">構文</span><span class="sxs-lookup"><span data-stu-id="61f75-104">Syntax</span></span>  
  
```xml  
<httpDigest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61f75-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="61f75-105">Attributes and Elements</span></span>  
 <span data-ttu-id="61f75-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="61f75-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61f75-107">属性</span><span class="sxs-lookup"><span data-stu-id="61f75-107">Attributes</span></span>  
  
|<span data-ttu-id="61f75-108">属性</span><span class="sxs-lookup"><span data-stu-id="61f75-108">Attribute</span></span>|<span data-ttu-id="61f75-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="61f75-109">Description</span></span>|  
|---------------|-----------------|  
|`impersonationLevel`|<span data-ttu-id="61f75-110">クライアントがサーバーと通信する偽装設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="61f75-110">Sets the impersonation preference that the client communicates to the server.</span></span> <span data-ttu-id="61f75-111">クライアントが選択する偽装モードは、サーバーでは適用されません。</span><span class="sxs-lookup"><span data-stu-id="61f75-111">The impersonation mode that the client selects is not enforced on the server.</span></span> <span data-ttu-id="61f75-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="61f75-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="61f75-113">-識別: サーバーはクライアントの id と特権を取得できますが、クライアントの権限を借用することはできません。</span><span class="sxs-lookup"><span data-stu-id="61f75-113">-   Identification: The server can get the identity and privileges of the client, but cannot impersonate the client.</span></span><br /><span data-ttu-id="61f75-114">-権限借用: サーバーは、ローカルシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="61f75-114">-   Impersonation: The server can impersonate the client's security context on the local system.</span></span><br /><span data-ttu-id="61f75-115">-委任: サーバーは、リモートシステム上のクライアントのセキュリティコンテキストを偽装できます。</span><span class="sxs-lookup"><span data-stu-id="61f75-115">-   Delegation: The server can impersonate the client's security context on remote systems.</span></span><br /><span data-ttu-id="61f75-116">-Anonymous: サーバーはクライアントの権限を借用または識別できません。</span><span class="sxs-lookup"><span data-stu-id="61f75-116">-   Anonymous: The server cannot impersonate or identify the client.</span></span><br /><span data-ttu-id="61f75-117">-None: 偽装レベルが割り当てられていません。</span><span class="sxs-lookup"><span data-stu-id="61f75-117">-   None: An impersonation level is not assigned.</span></span><br /><br /> <span data-ttu-id="61f75-118">既定値は Identification です。</span><span class="sxs-lookup"><span data-stu-id="61f75-118">The default is Identification.</span></span> <span data-ttu-id="61f75-119">この属性は <xref:System.Security.Principal.TokenImpersonationLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="61f75-119">This attribute is of type <xref:System.Security.Principal.TokenImpersonationLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61f75-120">子要素</span><span class="sxs-lookup"><span data-stu-id="61f75-120">Child Elements</span></span>  
 <span data-ttu-id="61f75-121">なし</span><span class="sxs-lookup"><span data-stu-id="61f75-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61f75-122">親要素</span><span class="sxs-lookup"><span data-stu-id="61f75-122">Parent Elements</span></span>  
  
|<span data-ttu-id="61f75-123">要素</span><span class="sxs-lookup"><span data-stu-id="61f75-123">Element</span></span>|<span data-ttu-id="61f75-124">説明</span><span class="sxs-lookup"><span data-stu-id="61f75-124">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="61f75-125">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="61f75-125">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61f75-126">注釈</span><span class="sxs-lookup"><span data-stu-id="61f75-126">Remarks</span></span>  
 <span data-ttu-id="61f75-127">ダイジェストは、アルゴリズムと入力セットを使用して決定されるハッシュです。</span><span class="sxs-lookup"><span data-stu-id="61f75-127">A digest is a hash determined by using an algorithm and a set of inputs.</span></span> <span data-ttu-id="61f75-128">認証する側と認証される側はアルゴリズムに同意し、入力として使用されるデータを交換します。</span><span class="sxs-lookup"><span data-stu-id="61f75-128">The authenticator and the authenticated agree upon an algorithm and exchange the data used as inputs.</span></span> <span data-ttu-id="61f75-129">クライアントはハッシュを計算して、サービスに送信できます。</span><span class="sxs-lookup"><span data-stu-id="61f75-129">The client can calculate the hash and send it to the service.</span></span> <span data-ttu-id="61f75-130">また、サービスもハッシュを計算して、値を比較します。</span><span class="sxs-lookup"><span data-stu-id="61f75-130">The service also calculates the hash and compares the values.</span></span> <span data-ttu-id="61f75-131">一致すると、クライアントが検証されます。</span><span class="sxs-lookup"><span data-stu-id="61f75-131">A match validates the client.</span></span>  
  
 <span data-ttu-id="61f75-132">この機能は、Windows の Active Directory およびインターネット インフォメーション サービス (IIS) と共に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="61f75-132">This feature must be enabled with Active Directory on Windows and Internet Information Services (IIS).</span></span> <span data-ttu-id="61f75-133">詳細については、「 [IIS 6.0 でのダイジェスト認証](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="61f75-133">For more information, see [Digest Authentication in IIS 6.0](/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f75-134">関連項目</span><span class="sxs-lookup"><span data-stu-id="61f75-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>
- <xref:System.ServiceModel.Configuration.HttpDigestClientElement>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential>
- [<span data-ttu-id="61f75-135">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="61f75-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="61f75-136">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="61f75-136">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="61f75-137">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="61f75-137">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="61f75-138">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="61f75-138">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
