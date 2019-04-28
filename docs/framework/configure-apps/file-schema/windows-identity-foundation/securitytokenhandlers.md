---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: a5af3893ab72d23c2b3814569decfc50431b8e55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793836"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="929a7-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="929a7-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="929a7-102">エンドポイントに登録されているセキュリティ トークン ハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="929a7-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="929a7-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="929a7-103">\<system.identityModel></span></span>  
<span data-ttu-id="929a7-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="929a7-104">\<identityConfiguration></span></span>  
<span data-ttu-id="929a7-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="929a7-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929a7-106">構文</span><span class="sxs-lookup"><span data-stu-id="929a7-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="929a7-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="929a7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="929a7-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="929a7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="929a7-109">属性</span><span class="sxs-lookup"><span data-stu-id="929a7-109">Attributes</span></span>  
  
|<span data-ttu-id="929a7-110">属性</span><span class="sxs-lookup"><span data-stu-id="929a7-110">Attribute</span></span>|<span data-ttu-id="929a7-111">説明</span><span class="sxs-lookup"><span data-stu-id="929a7-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="929a7-112">name</span><span class="sxs-lookup"><span data-stu-id="929a7-112">name</span></span>|<span data-ttu-id="929a7-113">トークン ハンドラー コレクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="929a7-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="929a7-114">フレームワークによって認識される唯一の値は、"ActAs"と"OnBehalfOf"です。</span><span class="sxs-lookup"><span data-stu-id="929a7-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="929a7-115">トークン ハンドラー コレクションにこれらの名前のいずれかを指定する場合、コレクションをそれぞれトークン ActAs または OnBehalfOf を処理するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="929a7-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="929a7-116">子要素</span><span class="sxs-lookup"><span data-stu-id="929a7-116">Child Elements</span></span>  
  
|<span data-ttu-id="929a7-117">要素</span><span class="sxs-lookup"><span data-stu-id="929a7-117">Element</span></span>|<span data-ttu-id="929a7-118">説明</span><span class="sxs-lookup"><span data-stu-id="929a7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="929a7-119">\<add></span><span class="sxs-lookup"><span data-stu-id="929a7-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="929a7-120">トークン ハンドラー コレクションには、セキュリティ トークン ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="929a7-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="929a7-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="929a7-121">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="929a7-122">トークン ハンドラー コレクションからすべてのセキュリティ トークン ハンドラーをクリアします。</span><span class="sxs-lookup"><span data-stu-id="929a7-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="929a7-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="929a7-123">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="929a7-124">トークン ハンドラー コレクションからセキュリティ トークン ハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="929a7-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="929a7-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="929a7-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="929a7-126">トークン ハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="929a7-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="929a7-127">親要素</span><span class="sxs-lookup"><span data-stu-id="929a7-127">Parent Elements</span></span>  
  
|<span data-ttu-id="929a7-128">要素</span><span class="sxs-lookup"><span data-stu-id="929a7-128">Element</span></span>|<span data-ttu-id="929a7-129">説明</span><span class="sxs-lookup"><span data-stu-id="929a7-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="929a7-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="929a7-130">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="929a7-131">サービス レベルの id の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="929a7-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="929a7-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="929a7-132">Remarks</span></span>  
 <span data-ttu-id="929a7-133">サービス構成では、セキュリティ トークン ハンドラーの 1 つまたは複数の名前付きコレクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="929a7-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="929a7-134">使用してコレクションの名前を指定することができます、`name`属性。</span><span class="sxs-lookup"><span data-stu-id="929a7-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="929a7-135">フレームワークを処理する唯一の名前とは、"ActAs"と"OnBehalfOf"です。</span><span class="sxs-lookup"><span data-stu-id="929a7-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="929a7-136">ハンドラーは、これらのコレクションに存在する場合で使用されるセキュリティ トークン サービス (STS)、既定のハンドラーではなく処理するときに`ActAs`と`OnBehalfOf`トークンです。</span><span class="sxs-lookup"><span data-stu-id="929a7-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="929a7-137">既定では、コレクションは、次の種類のハンドラーで設定されます: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>、および<xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>します。</span><span class="sxs-lookup"><span data-stu-id="929a7-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="929a7-138">使用して、コレクションを変更することができます、 `<add>`、 `<remove>`、および`<clear>`要素。</span><span class="sxs-lookup"><span data-stu-id="929a7-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="929a7-139">特定の型の 1 つのハンドラーのみがコレクションに存在することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="929a7-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="929a7-140">たとえば、次のハンドラーからの派生、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラスか、ハンドラーまたは<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>両方ではなく 1 つのコレクションで構成することがあります。</span><span class="sxs-lookup"><span data-stu-id="929a7-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="929a7-141">使用して、`<securityTokenHandlerConfiguration>`要素をコレクション内で、ハンドラーの構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="929a7-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="929a7-142">この要素で指定された設定をオーバーライドを通じてサービスに指定されている、 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素。</span><span class="sxs-lookup"><span data-stu-id="929a7-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="929a7-143">いくつかのハンドラー (いくつかの組み込みハンドラー型を含む) の子要素を追加の構成をサポートできる、`<add>`要素。</span><span class="sxs-lookup"><span data-stu-id="929a7-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="929a7-144">ハンドラーで指定した設定では、コレクションまたはサービスに指定した同等の設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="929a7-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
