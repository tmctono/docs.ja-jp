---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 678e5c705181c55257b1ddb853690ada60ecd17a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942459"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="dda5e-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dda5e-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="dda5e-102">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="dda5e-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="dda5e-103">\<system.identityModel></span></span>  
<span data-ttu-id="dda5e-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dda5e-104">\<identityConfiguration></span></span>  
<span data-ttu-id="dda5e-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="dda5e-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda5e-106">構文</span><span class="sxs-lookup"><span data-stu-id="dda5e-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dda5e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="dda5e-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dda5e-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dda5e-109">属性</span><span class="sxs-lookup"><span data-stu-id="dda5e-109">Attributes</span></span>  
  
|<span data-ttu-id="dda5e-110">属性</span><span class="sxs-lookup"><span data-stu-id="dda5e-110">Attribute</span></span>|<span data-ttu-id="dda5e-111">説明</span><span class="sxs-lookup"><span data-stu-id="dda5e-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dda5e-112">name</span><span class="sxs-lookup"><span data-stu-id="dda5e-112">name</span></span>|<span data-ttu-id="dda5e-113">トークンハンドラーコレクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="dda5e-114">フレームワークによって認識される値は、"ActAs" と "OnBehalfOf" だけです。</span><span class="sxs-lookup"><span data-stu-id="dda5e-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="dda5e-115">これらのいずれかの名前でトークンハンドラーコレクションが指定されている場合、ActAs または OnBehalfOf トークンをそれぞれ処理するときにコレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dda5e-116">子要素</span><span class="sxs-lookup"><span data-stu-id="dda5e-116">Child Elements</span></span>  
  
|<span data-ttu-id="dda5e-117">要素</span><span class="sxs-lookup"><span data-stu-id="dda5e-117">Element</span></span>|<span data-ttu-id="dda5e-118">説明</span><span class="sxs-lookup"><span data-stu-id="dda5e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dda5e-119">\<add></span><span class="sxs-lookup"><span data-stu-id="dda5e-119">\<add></span></span>](add.md)|<span data-ttu-id="dda5e-120">トークンハンドラーコレクションにセキュリティトークンハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="dda5e-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="dda5e-121">\<clear></span></span>](clear.md)|<span data-ttu-id="dda5e-122">すべてのセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="dda5e-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="dda5e-123">\<remove></span></span>](remove.md)|<span data-ttu-id="dda5e-124">トークンハンドラーコレクションからセキュリティトークンハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="dda5e-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="dda5e-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="dda5e-126">トークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dda5e-127">親要素</span><span class="sxs-lookup"><span data-stu-id="dda5e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dda5e-128">要素</span><span class="sxs-lookup"><span data-stu-id="dda5e-128">Element</span></span>|<span data-ttu-id="dda5e-129">説明</span><span class="sxs-lookup"><span data-stu-id="dda5e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dda5e-130">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="dda5e-130">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="dda5e-131">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dda5e-132">Remarks</span><span class="sxs-lookup"><span data-stu-id="dda5e-132">Remarks</span></span>  
 <span data-ttu-id="dda5e-133">サービス構成では、セキュリティトークンハンドラーの1つ以上の名前付きコレクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="dda5e-134">`name`属性を使用して、コレクションの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="dda5e-135">フレームワークによって処理される名前は、"ActAs" と "OnBehalfOf" だけです。</span><span class="sxs-lookup"><span data-stu-id="dda5e-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="dda5e-136">これらのコレクションにハンドラーが存在する場合は、 `ActAs` `OnBehalfOf`トークンの処理時に既定のハンドラーではなく、Security Token Service (STS) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="dda5e-137">既定では<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>、コレクションには<xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>、、、、、 、およびの各ハンドラー型が設定されます。<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="dda5e-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="dda5e-138">コレクションは、 `<add>` `<remove>`、、および`<clear>`の各要素を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="dda5e-139">コレクション内に存在する特定の種類のハンドラーが1つだけであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dda5e-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="dda5e-140">たとえば、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラスからハンドラーを派生させる場合、ハンドラーまたはが<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 1 つのコレクションで構成されていることがありますが、両方を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="dda5e-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="dda5e-141">コレクション内`<securityTokenHandlerConfiguration>`のハンドラーの構成設定を指定するには、要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="dda5e-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="dda5e-142">この要素によって指定された設定は、サービスで指定された設定よりも、ユーザー [ \<構成 >](identityconfiguration.md)要素を介してオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="dda5e-143">いくつかの組み込みハンドラー型を含む一部のハンドラーは、 `<add>`要素の子要素を通じて追加の構成をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="dda5e-144">ハンドラーに指定された設定は、コレクションまたはサービスで指定された同等の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="dda5e-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
