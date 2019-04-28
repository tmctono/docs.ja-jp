---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750749"
---
# <a name="audienceuris"></a><span data-ttu-id="7da56-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="7da56-101">\<audienceUris></span></span>
<span data-ttu-id="7da56-102">利用者 (RP) の許容可能な識別子 Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="7da56-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="7da56-103">許可された対象 Uri のいずれかのスコープがない限り、トークンは受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="7da56-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="7da56-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7da56-104">\<system.identityModel></span></span>  
<span data-ttu-id="7da56-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7da56-105">\<identityConfiguration></span></span>  
<span data-ttu-id="7da56-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="7da56-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="7da56-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="7da56-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="7da56-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="7da56-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7da56-109">構文</span><span class="sxs-lookup"><span data-stu-id="7da56-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7da56-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7da56-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7da56-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7da56-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7da56-112">属性</span><span class="sxs-lookup"><span data-stu-id="7da56-112">Attributes</span></span>  
  
|<span data-ttu-id="7da56-113">属性</span><span class="sxs-lookup"><span data-stu-id="7da56-113">Attribute</span></span>|<span data-ttu-id="7da56-114">説明</span><span class="sxs-lookup"><span data-stu-id="7da56-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7da56-115">モード</span><span class="sxs-lookup"><span data-stu-id="7da56-115">mode</span></span>|<span data-ttu-id="7da56-116"><xref:System.IdentityModel.Selectors.AudienceUriMode>受信トークンに対象者制限を適用するかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="7da56-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="7da56-117">使用可能な値は、「常に」、"Never"、"BearerKeyOnly"。</span><span class="sxs-lookup"><span data-stu-id="7da56-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="7da56-118">既定では 常にです"。</span><span class="sxs-lookup"><span data-stu-id="7da56-118">The default is "Always".</span></span> <span data-ttu-id="7da56-119">任意。</span><span class="sxs-lookup"><span data-stu-id="7da56-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7da56-120">子要素</span><span class="sxs-lookup"><span data-stu-id="7da56-120">Child Elements</span></span>  
  
|<span data-ttu-id="7da56-121">要素</span><span class="sxs-lookup"><span data-stu-id="7da56-121">Element</span></span>|<span data-ttu-id="7da56-122">説明</span><span class="sxs-lookup"><span data-stu-id="7da56-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="7da56-123">指定された URI を追加、 `value` audienceUris のコレクションに属性します。</span><span class="sxs-lookup"><span data-stu-id="7da56-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="7da56-124">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="7da56-124">The `value` attribute is required.</span></span> <span data-ttu-id="7da56-125">URI は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="7da56-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="7da56-126">AudienceUris のコレクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="7da56-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="7da56-127">すべての識別子は、コレクションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="7da56-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="7da56-128">指定された URI を削除、 `value` audienceUris のコレクションから属性。</span><span class="sxs-lookup"><span data-stu-id="7da56-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="7da56-129">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="7da56-129">The `value` attribute is required.</span></span> <span data-ttu-id="7da56-130">URI は、大文字小文字を区別します。</span><span class="sxs-lookup"><span data-stu-id="7da56-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7da56-131">親要素</span><span class="sxs-lookup"><span data-stu-id="7da56-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7da56-132">要素</span><span class="sxs-lookup"><span data-stu-id="7da56-132">Element</span></span>|<span data-ttu-id="7da56-133">説明</span><span class="sxs-lookup"><span data-stu-id="7da56-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7da56-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="7da56-134">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="7da56-135">トークン ハンドラー コレクションのセキュリティの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="7da56-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7da56-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="7da56-136">Remarks</span></span>  
 <span data-ttu-id="7da56-137">既定では、コレクションが空です。使用して、 `<add>`、 `<clear>`、および`<remove>`コレクションを変更する要素。</span><span class="sxs-lookup"><span data-stu-id="7da56-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="7da56-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>オブジェクトでいずれかを構成する対象ユーザー URI のコレクション内の値が対象ユーザー URI 制限を許可されている使用<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="7da56-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="7da56-139">`<audienceUris>`要素が表される、<xref:System.IdentityModel.Configuration.AudienceUriElementCollection>クラス。</span><span class="sxs-lookup"><span data-stu-id="7da56-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="7da56-140">によって表されるコレクションに追加された個々 の URI、<xref:System.IdentityModel.Configuration.AudienceUriElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="7da56-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7da56-141">使用、`<audienceUris>`要素の子要素として、 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素は非推奨とされましたが、旧バージョンとの互換性もサポートします。</span><span class="sxs-lookup"><span data-stu-id="7da56-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="7da56-142">上の設定、`<securityTokenHandlerConfiguration>`要素のオーバーライド、`<identityConfiguration>`要素。</span><span class="sxs-lookup"><span data-stu-id="7da56-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7da56-143">例</span><span class="sxs-lookup"><span data-stu-id="7da56-143">Example</span></span>  
 <span data-ttu-id="7da56-144">次の XML では、アプリケーションの許容される対象ユーザー Uri を構成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7da56-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="7da56-145">この例では、単一の URI を設定します。</span><span class="sxs-lookup"><span data-stu-id="7da56-145">This example configures a single URI.</span></span> <span data-ttu-id="7da56-146">この URI のスコープのトークンが受け付けられます、他のすべてのユーザーは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="7da56-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
