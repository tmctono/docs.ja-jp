---
title: <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: f758fc8e0934f56f9593246497d8aba5084c4a79
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673512"
---
# <a name="allowedaudienceuris"></a><span data-ttu-id="6dc31-101">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="6dc31-101">\<allowedAudienceUris></span></span>
<span data-ttu-id="6dc31-102"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-102">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="6dc31-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6dc31-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="6dc31-104">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="6dc31-104">\<behaviors></span></span>  
<span data-ttu-id="6dc31-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="6dc31-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="6dc31-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6dc31-106">\<behavior></span></span>  
<span data-ttu-id="6dc31-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="6dc31-107">\<serviceCredentials></span></span>  
<span data-ttu-id="6dc31-108">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="6dc31-108">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="6dc31-109">\<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="6dc31-109">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6dc31-110">構文</span><span class="sxs-lookup"><span data-stu-id="6dc31-110">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6dc31-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6dc31-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6dc31-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6dc31-113">属性</span><span class="sxs-lookup"><span data-stu-id="6dc31-113">Attributes</span></span>  
 <span data-ttu-id="6dc31-114">なし。</span><span class="sxs-lookup"><span data-stu-id="6dc31-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6dc31-115">子要素</span><span class="sxs-lookup"><span data-stu-id="6dc31-115">Child Elements</span></span>  
  
|<span data-ttu-id="6dc31-116">要素</span><span class="sxs-lookup"><span data-stu-id="6dc31-116">Element</span></span>|<span data-ttu-id="6dc31-117">説明</span><span class="sxs-lookup"><span data-stu-id="6dc31-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dc31-118">\<add></span><span class="sxs-lookup"><span data-stu-id="6dc31-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="6dc31-119"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-119">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6dc31-120">親要素</span><span class="sxs-lookup"><span data-stu-id="6dc31-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6dc31-121">要素</span><span class="sxs-lookup"><span data-stu-id="6dc31-121">Element</span></span>|<span data-ttu-id="6dc31-122">説明</span><span class="sxs-lookup"><span data-stu-id="6dc31-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6dc31-123">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="6dc31-123">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="6dc31-124">サービス資格情報として発行されるトークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-124">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6dc31-125">Remarks</span><span class="sxs-lookup"><span data-stu-id="6dc31-125">Remarks</span></span>  
 <span data-ttu-id="6dc31-126">このコレクションは、<xref:System.IdentityModel.Tokens.SamlSecurityToken> セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を利用するフェデレーション アプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dc31-126">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="6dc31-127">STS がセキュリティ トークンを発行する場合、このセキュリティ トークンに <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> を追加して、セキュリティ トークンの提供先となる Web サービスの URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6dc31-127">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="6dc31-128">これにより、受け取り側 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> Web サービスは、次のようにしてこのチェックが行われるように指定することで、発行されたセキュリティ トークンがこの Web サービスを対象としていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6dc31-128">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="6dc31-129">`audienceUriMode` の `<issuedTokenAuthentication>` 属性を <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> または <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> に設定します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-129">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="6dc31-130">このコレクションに URI を追加して、有効な URI のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-130">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="6dc31-131">詳細については、「 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6dc31-131">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="6dc31-132">この構成要素の使用に関する詳細については、次を参照してください。[方法。フェデレーション サービスで資格情報を構成](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-132">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dc31-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="6dc31-133">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [<span data-ttu-id="6dc31-134">\<issuedTokenAuthentication></span><span class="sxs-lookup"><span data-stu-id="6dc31-134">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="6dc31-135">\<add></span><span class="sxs-lookup"><span data-stu-id="6dc31-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)
- [<span data-ttu-id="6dc31-136">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="6dc31-136">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="6dc31-137">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6dc31-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6dc31-138">方法: フェデレーション サービスで資格情報を構成します。</span><span class="sxs-lookup"><span data-stu-id="6dc31-138">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
