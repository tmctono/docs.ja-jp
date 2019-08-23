---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941955"
---
# <a name="audienceuris"></a><span data-ttu-id="18f5c-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="18f5c-101">\<audienceUris></span></span>
<span data-ttu-id="18f5c-102">証明書利用者 (RP) の許容される識別子である Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="18f5c-103">トークンは、許可されている対象ユーザーの Uri の1つを対象としている場合を除き、受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="18f5c-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="18f5c-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="18f5c-104">\<system.identityModel></span></span>  
<span data-ttu-id="18f5c-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="18f5c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="18f5c-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="18f5c-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="18f5c-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="18f5c-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="18f5c-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="18f5c-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f5c-109">構文</span><span class="sxs-lookup"><span data-stu-id="18f5c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18f5c-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="18f5c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="18f5c-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18f5c-112">属性</span><span class="sxs-lookup"><span data-stu-id="18f5c-112">Attributes</span></span>  
  
|<span data-ttu-id="18f5c-113">属性</span><span class="sxs-lookup"><span data-stu-id="18f5c-113">Attribute</span></span>|<span data-ttu-id="18f5c-114">説明</span><span class="sxs-lookup"><span data-stu-id="18f5c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18f5c-115">モード</span><span class="sxs-lookup"><span data-stu-id="18f5c-115">mode</span></span>|<span data-ttu-id="18f5c-116">対象ユーザーの制限を受信トークンに適用する必要があるかどうかを示す値です。<xref:System.IdentityModel.Selectors.AudienceUriMode></span><span class="sxs-lookup"><span data-stu-id="18f5c-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="18f5c-117">指定できる値は、"Always"、"Never"、および "BearerKeyOnly" です。</span><span class="sxs-lookup"><span data-stu-id="18f5c-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="18f5c-118">既定値は "Always" です。</span><span class="sxs-lookup"><span data-stu-id="18f5c-118">The default is "Always".</span></span> <span data-ttu-id="18f5c-119">任意。</span><span class="sxs-lookup"><span data-stu-id="18f5c-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18f5c-120">子要素</span><span class="sxs-lookup"><span data-stu-id="18f5c-120">Child Elements</span></span>  
  
|<span data-ttu-id="18f5c-121">要素</span><span class="sxs-lookup"><span data-stu-id="18f5c-121">Element</span></span>|<span data-ttu-id="18f5c-122">説明</span><span class="sxs-lookup"><span data-stu-id="18f5c-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="18f5c-123">`value`属性によって指定された URI を audienceUris コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="18f5c-124">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="18f5c-124">The `value` attribute is required.</span></span> <span data-ttu-id="18f5c-125">URI では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="18f5c-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="18f5c-126">AudienceUris コレクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="18f5c-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="18f5c-127">すべての識別子はコレクションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="18f5c-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="18f5c-128">`value`属性によって指定された URI を audienceUris コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="18f5c-129">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="18f5c-129">The `value` attribute is required.</span></span> <span data-ttu-id="18f5c-130">URI では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="18f5c-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18f5c-131">親要素</span><span class="sxs-lookup"><span data-stu-id="18f5c-131">Parent Elements</span></span>  
  
|<span data-ttu-id="18f5c-132">要素</span><span class="sxs-lookup"><span data-stu-id="18f5c-132">Element</span></span>|<span data-ttu-id="18f5c-133">説明</span><span class="sxs-lookup"><span data-stu-id="18f5c-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18f5c-134">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="18f5c-134">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="18f5c-135">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f5c-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="18f5c-136">Remarks</span></span>  
 <span data-ttu-id="18f5c-137">既定では、コレクションは空です。コレクション`<add>`を`<clear>`変更する`<remove>`には、、、およびの各要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="18f5c-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>オブジェクト<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>とオブジェクトは、audience uri コレクションの値を使用して、オブジェクトで<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>許可されている対象ユーザー uri 制限を構成します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="18f5c-139">要素は、 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection>クラスによって表されます。 `<audienceUris>`</span><span class="sxs-lookup"><span data-stu-id="18f5c-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="18f5c-140">コレクションに追加された個々の URI は、 <xref:System.IdentityModel.Configuration.AudienceUriElement>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="18f5c-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="18f5c-141">この`<audienceUris>`要素を、identity [ \<configuration >](identityconfiguration.md)要素の子要素として使用することは非推奨とされましたが、旧バージョンとの互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="18f5c-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="18f5c-142">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="18f5c-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18f5c-143">例</span><span class="sxs-lookup"><span data-stu-id="18f5c-143">Example</span></span>  
 <span data-ttu-id="18f5c-144">次の XML は、アプリケーションに対して許容される対象ユーザーの Uri を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="18f5c-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="18f5c-145">この例では、単一の URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="18f5c-145">This example configures a single URI.</span></span> <span data-ttu-id="18f5c-146">この URI にスコープが設定されているトークンは受け入れられ、それ以外はすべて拒否されます。</span><span class="sxs-lookup"><span data-stu-id="18f5c-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
