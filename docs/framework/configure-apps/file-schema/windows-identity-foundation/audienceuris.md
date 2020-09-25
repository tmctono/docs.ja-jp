---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: c9787d8e0d8d66494bbf2dbd0e24ff39178a4cde
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189904"
---
# \<audienceUris>

<span data-ttu-id="57648-101">証明書利用者 (RP) の許容される識別子である Uri のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="57648-101">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="57648-102">トークンは、許可されている対象 URI の 1 つに範囲が設定されていない限り、受け入れられません。</span><span class="sxs-lookup"><span data-stu-id="57648-102">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**  
  
## <a name="syntax"></a><span data-ttu-id="57648-103">構文</span><span class="sxs-lookup"><span data-stu-id="57648-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57648-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="57648-104">Attributes and Elements</span></span>  

 <span data-ttu-id="57648-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="57648-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57648-106">属性</span><span class="sxs-lookup"><span data-stu-id="57648-106">Attributes</span></span>  
  
|<span data-ttu-id="57648-107">属性</span><span class="sxs-lookup"><span data-stu-id="57648-107">Attribute</span></span>|<span data-ttu-id="57648-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="57648-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="57648-109">mode</span><span class="sxs-lookup"><span data-stu-id="57648-109">mode</span></span>|<span data-ttu-id="57648-110"><xref:System.IdentityModel.Selectors.AudienceUriMode>対象ユーザーの制限を受信トークンに適用する必要があるかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="57648-110">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="57648-111">指定できる値は、"Always"、"Never"、および "BearerKeyOnly" です。</span><span class="sxs-lookup"><span data-stu-id="57648-111">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="57648-112">既定値は "Always" です。</span><span class="sxs-lookup"><span data-stu-id="57648-112">The default is "Always".</span></span> <span data-ttu-id="57648-113">省略可能。</span><span class="sxs-lookup"><span data-stu-id="57648-113">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57648-114">子要素</span><span class="sxs-lookup"><span data-stu-id="57648-114">Child Elements</span></span>  
  
|<span data-ttu-id="57648-115">要素</span><span class="sxs-lookup"><span data-stu-id="57648-115">Element</span></span>|<span data-ttu-id="57648-116">説明</span><span class="sxs-lookup"><span data-stu-id="57648-116">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="57648-117">属性によって指定された URI を `value` audienceUris コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="57648-117">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="57648-118">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="57648-118">The `value` attribute is required.</span></span> <span data-ttu-id="57648-119">URI では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="57648-119">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="57648-120">AudienceUris コレクションをクリアします。</span><span class="sxs-lookup"><span data-stu-id="57648-120">Clears the audienceUris collection.</span></span> <span data-ttu-id="57648-121">すべての識別子はコレクションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="57648-121">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="57648-122">属性によって指定された URI を `value` audienceUris コレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="57648-122">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="57648-123">`value` 属性は必須です。</span><span class="sxs-lookup"><span data-stu-id="57648-123">The `value` attribute is required.</span></span> <span data-ttu-id="57648-124">URI では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="57648-124">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="57648-125">親要素</span><span class="sxs-lookup"><span data-stu-id="57648-125">Parent Elements</span></span>  
  
|<span data-ttu-id="57648-126">要素</span><span class="sxs-lookup"><span data-stu-id="57648-126">Element</span></span>|<span data-ttu-id="57648-127">説明</span><span class="sxs-lookup"><span data-stu-id="57648-127">Description</span></span>|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="57648-128">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="57648-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57648-129">解説</span><span class="sxs-lookup"><span data-stu-id="57648-129">Remarks</span></span>  

 <span data-ttu-id="57648-130">既定では、コレクションは空です。 `<add>`コレクションを `<clear>` 変更するには、、、およびの各要素を使用し `<remove>` ます。</span><span class="sxs-lookup"><span data-stu-id="57648-130">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="57648-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> オブジェクトと <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> オブジェクトは、AUDIENCE uri コレクションの値を使用して、オブジェクトで許可されている対象ユーザー uri 制限を構成し <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> ます。</span><span class="sxs-lookup"><span data-stu-id="57648-131"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="57648-132">`<audienceUris>`要素は、クラスによって表され <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> ます。</span><span class="sxs-lookup"><span data-stu-id="57648-132">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="57648-133">コレクションに追加された個々の URI は、クラスによって表され <xref:System.IdentityModel.Configuration.AudienceUriElement> ます。</span><span class="sxs-lookup"><span data-stu-id="57648-133">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57648-134">要素の `<audienceUris>` 子要素としての要素の使用は [\<identityConfiguration>](identityconfiguration.md) 非推奨とされましたが、旧バージョンとの互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="57648-134">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="57648-135">要素の設定は、要素の設定 `<securityTokenHandlerConfiguration>` よりも優先さ `<identityConfiguration>` れます。</span><span class="sxs-lookup"><span data-stu-id="57648-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57648-136">例</span><span class="sxs-lookup"><span data-stu-id="57648-136">Example</span></span>  

 <span data-ttu-id="57648-137">次の XML は、アプリケーションに対して許容される対象ユーザーの Uri を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="57648-137">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="57648-138">この例では、単一の URI を構成します。</span><span class="sxs-lookup"><span data-stu-id="57648-138">This example configures a single URI.</span></span> <span data-ttu-id="57648-139">この URI にスコープが設定されているトークンは受け入れられ、それ以外はすべて拒否されます。</span><span class="sxs-lookup"><span data-stu-id="57648-139">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
