---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252169"
---
# <a name="audienceuris"></a><span data-ttu-id="531e3-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="531e3-101">\<audienceUris></span></span>
<span data-ttu-id="531e3-102">証明書利用者 (RP) の許容される識別子である Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="531e3-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="531e3-103">トークンは、許可されている対象ユーザーの Uri の1つを対象としている場合を除き、受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="531e3-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="531e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="531e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="531e3-105">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="531e3-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="531e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="531e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="531e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="531e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="531e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="531e3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="531e3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<audienceUris >**</span><span class="sxs-lookup"><span data-stu-id="531e3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="531e3-110">構文</span><span class="sxs-lookup"><span data-stu-id="531e3-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="531e3-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="531e3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="531e3-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="531e3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="531e3-113">属性</span><span class="sxs-lookup"><span data-stu-id="531e3-113">Attributes</span></span>  
  
|<span data-ttu-id="531e3-114">属性</span><span class="sxs-lookup"><span data-stu-id="531e3-114">Attribute</span></span>|<span data-ttu-id="531e3-115">説明</span><span class="sxs-lookup"><span data-stu-id="531e3-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="531e3-116">モード</span><span class="sxs-lookup"><span data-stu-id="531e3-116">mode</span></span>|<span data-ttu-id="531e3-117">対象ユーザーの制限を受信トークンに適用する必要があるかどうかを示す値です。<xref:System.IdentityModel.Selectors.AudienceUriMode></span><span class="sxs-lookup"><span data-stu-id="531e3-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="531e3-118">指定できる値は、"Always"、"Never"、および "BearerKeyOnly" です。</span><span class="sxs-lookup"><span data-stu-id="531e3-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="531e3-119">既定値は "Always" です。</span><span class="sxs-lookup"><span data-stu-id="531e3-119">The default is "Always".</span></span> <span data-ttu-id="531e3-120">任意。</span><span class="sxs-lookup"><span data-stu-id="531e3-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="531e3-121">子要素</span><span class="sxs-lookup"><span data-stu-id="531e3-121">Child Elements</span></span>  
  
|<span data-ttu-id="531e3-122">要素</span><span class="sxs-lookup"><span data-stu-id="531e3-122">Element</span></span>|<span data-ttu-id="531e3-123">説明</span><span class="sxs-lookup"><span data-stu-id="531e3-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="531e3-124">`value`属性によって指定された URI を audienceUris コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="531e3-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="531e3-125">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="531e3-125">The `value` attribute is required.</span></span> <span data-ttu-id="531e3-126">URI では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="531e3-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="531e3-127">AudienceUris コレクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="531e3-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="531e3-128">すべての識別子はコレクションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="531e3-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="531e3-129">`value`属性によって指定された URI を audienceUris コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="531e3-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="531e3-130">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="531e3-130">The `value` attribute is required.</span></span> <span data-ttu-id="531e3-131">URI では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="531e3-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="531e3-132">親要素</span><span class="sxs-lookup"><span data-stu-id="531e3-132">Parent Elements</span></span>  
  
|<span data-ttu-id="531e3-133">要素</span><span class="sxs-lookup"><span data-stu-id="531e3-133">Element</span></span>|<span data-ttu-id="531e3-134">説明</span><span class="sxs-lookup"><span data-stu-id="531e3-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="531e3-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="531e3-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="531e3-136">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="531e3-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="531e3-137">Remarks</span><span class="sxs-lookup"><span data-stu-id="531e3-137">Remarks</span></span>  
 <span data-ttu-id="531e3-138">既定では、コレクションは空です。コレクション`<add>`を`<clear>`変更する`<remove>`には、、、およびの各要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="531e3-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="531e3-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>オブジェクト<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>とオブジェクトは、audience uri コレクションの値を使用して、オブジェクトで<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>許可されている対象ユーザー uri 制限を構成します。</span><span class="sxs-lookup"><span data-stu-id="531e3-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="531e3-140">要素は、 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection>クラスによって表されます。 `<audienceUris>`</span><span class="sxs-lookup"><span data-stu-id="531e3-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="531e3-141">コレクションに追加された個々の URI は、 <xref:System.IdentityModel.Configuration.AudienceUriElement>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="531e3-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="531e3-142">この`<audienceUris>`要素を、identity [ \<configuration >](identityconfiguration.md)要素の子要素として使用することは非推奨とされましたが、旧バージョンとの互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="531e3-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="531e3-143">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="531e3-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="531e3-144">例</span><span class="sxs-lookup"><span data-stu-id="531e3-144">Example</span></span>  
 <span data-ttu-id="531e3-145">次の XML は、アプリケーションに対して許容される対象ユーザーの Uri を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="531e3-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="531e3-146">この例では、単一の URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="531e3-146">This example configures a single URI.</span></span> <span data-ttu-id="531e3-147">この URI にスコープが設定されているトークンは受け入れられ、それ以外はすべて拒否されます。</span><span class="sxs-lookup"><span data-stu-id="531e3-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
