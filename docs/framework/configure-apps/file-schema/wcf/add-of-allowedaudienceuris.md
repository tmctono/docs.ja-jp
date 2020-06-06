---
title: <add> の <allowedAudienceUris>
ms.date: 03/30/2017
ms.assetid: 4e7b7637-e0ea-4a91-988f-6b6ef28d9fc3
ms.openlocfilehash: e15cb2d3e525d39a321bbe9760ddb8d72b02fffa
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398356"
---
# <a name="add-of-allowedaudienceuris"></a><span data-ttu-id="5230c-102">\<add> の \<allowedAudienceUris></span><span class="sxs-lookup"><span data-stu-id="5230c-102">\<add> of \<allowedAudienceUris></span></span>
<span data-ttu-id="5230c-103"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI を追加します。</span><span class="sxs-lookup"><span data-stu-id="5230c-103">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenAuthentication>**](issuedtokenauthentication-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowedAudienceUris>**](allowedaudienceuris.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="5230c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5230c-104">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>
  <add allowedAudienceUri="String" />
</allowedAudienceUris>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5230c-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5230c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5230c-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5230c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5230c-107">属性</span><span class="sxs-lookup"><span data-stu-id="5230c-107">Attributes</span></span>  
  
|<span data-ttu-id="5230c-108">属性</span><span class="sxs-lookup"><span data-stu-id="5230c-108">Attribute</span></span>|<span data-ttu-id="5230c-109">説明</span><span class="sxs-lookup"><span data-stu-id="5230c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5230c-110">allowedAudienceUri</span><span class="sxs-lookup"><span data-stu-id="5230c-110">allowedAudienceUri</span></span>|<span data-ttu-id="5230c-111"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI を含む文字列です。</span><span class="sxs-lookup"><span data-stu-id="5230c-111">A string that contains a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5230c-112">子要素</span><span class="sxs-lookup"><span data-stu-id="5230c-112">Child Elements</span></span>  
 <span data-ttu-id="5230c-113">なし。</span><span class="sxs-lookup"><span data-stu-id="5230c-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5230c-114">親要素</span><span class="sxs-lookup"><span data-stu-id="5230c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="5230c-115">要素</span><span class="sxs-lookup"><span data-stu-id="5230c-115">Element</span></span>|<span data-ttu-id="5230c-116">Description</span><span class="sxs-lookup"><span data-stu-id="5230c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<allowedAudienceUris>](allowedaudienceuris.md)|<span data-ttu-id="5230c-117"><xref:System.IdentityModel.Tokens.SamlSecurityToken> インスタンスにより有効と見なされるように、<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> セキュリティ トークンのターゲットとなる URI のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="5230c-117">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5230c-118">解説</span><span class="sxs-lookup"><span data-stu-id="5230c-118">Remarks</span></span>  
 <span data-ttu-id="5230c-119">このコレクションは、<xref:System.IdentityModel.Tokens.SamlSecurityToken> セキュリティ トークンを発行するセキュリティ トークン サービス (STS) を利用するフェデレーション アプリケーションで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5230c-119">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="5230c-120">STS がセキュリティ トークンを発行する場合、このセキュリティ トークンに <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> を追加して、セキュリティ トークンの提供先となる Web サービスの URI を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5230c-120">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="5230c-121">これにより、受け取り側 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> Web サービスは、次のようにしてこのチェックが行われるように指定することで、発行されたセキュリティ トークンがこの Web サービスを対象としていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5230c-121">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
- <span data-ttu-id="5230c-122">`audienceUriMode` の `<issuedTokenAuthentication>` 属性を <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> または <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly> に設定します。</span><span class="sxs-lookup"><span data-stu-id="5230c-122">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
- <span data-ttu-id="5230c-123">このコレクションに URI を追加して、有効な URI のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="5230c-123">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="5230c-124">詳細については、「<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5230c-124">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="5230c-125">この構成要素の使用方法の詳細については、「[方法: フェデレーションサービスで資格情報を構成する](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5230c-125">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5230c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="5230c-126">See also</span></span>

- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>
- <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>
- <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>
- <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>
- [\<allowedAudienceUris>](allowedaudienceuris.md)
- [\<issuedTokenAuthentication>](issuedtokenauthentication-of-servicecredentials.md)
- [<span data-ttu-id="5230c-127">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="5230c-127">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="5230c-128">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="5230c-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5230c-129">方法: フェデレーション サービスで資格情報を設定する</span><span class="sxs-lookup"><span data-stu-id="5230c-129">How to: Configure Credentials on a Federation Service</span></span>](../../../wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
