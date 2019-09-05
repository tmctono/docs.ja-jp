---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 017309436660991c69da569e9cc4219e842ecaa3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251873"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="a8c94-101">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="a8c94-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="a8c94-102">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
<span data-ttu-id="a8c94-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8c94-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8c94-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a8c94-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a8c94-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a8c94-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a8c94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<securityTokenHandlers >**</span><span class="sxs-lookup"><span data-stu-id="a8c94-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8c94-107">構文</span><span class="sxs-lookup"><span data-stu-id="a8c94-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8c94-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a8c94-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a8c94-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8c94-110">属性</span><span class="sxs-lookup"><span data-stu-id="a8c94-110">Attributes</span></span>  
  
|<span data-ttu-id="a8c94-111">属性</span><span class="sxs-lookup"><span data-stu-id="a8c94-111">Attribute</span></span>|<span data-ttu-id="a8c94-112">説明</span><span class="sxs-lookup"><span data-stu-id="a8c94-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8c94-113">name</span><span class="sxs-lookup"><span data-stu-id="a8c94-113">name</span></span>|<span data-ttu-id="a8c94-114">トークンハンドラーコレクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="a8c94-115">フレームワークによって認識される値は、"ActAs" と "OnBehalfOf" だけです。</span><span class="sxs-lookup"><span data-stu-id="a8c94-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="a8c94-116">これらのいずれかの名前でトークンハンドラーコレクションが指定されている場合、ActAs または OnBehalfOf トークンをそれぞれ処理するときにコレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8c94-117">子要素</span><span class="sxs-lookup"><span data-stu-id="a8c94-117">Child Elements</span></span>  
  
|<span data-ttu-id="a8c94-118">要素</span><span class="sxs-lookup"><span data-stu-id="a8c94-118">Element</span></span>|<span data-ttu-id="a8c94-119">説明</span><span class="sxs-lookup"><span data-stu-id="a8c94-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8c94-120">\<add></span><span class="sxs-lookup"><span data-stu-id="a8c94-120">\<add></span></span>](add.md)|<span data-ttu-id="a8c94-121">トークンハンドラーコレクションにセキュリティトークンハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="a8c94-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="a8c94-122">\<clear></span></span>](clear.md)|<span data-ttu-id="a8c94-123">すべてのセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="a8c94-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="a8c94-124">\<remove></span></span>](remove.md)|<span data-ttu-id="a8c94-125">トークンハンドラーコレクションからセキュリティトークンハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="a8c94-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a8c94-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="a8c94-127">トークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8c94-128">親要素</span><span class="sxs-lookup"><span data-stu-id="a8c94-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a8c94-129">要素</span><span class="sxs-lookup"><span data-stu-id="a8c94-129">Element</span></span>|<span data-ttu-id="a8c94-130">説明</span><span class="sxs-lookup"><span data-stu-id="a8c94-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8c94-131">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="a8c94-131">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="a8c94-132">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8c94-133">Remarks</span><span class="sxs-lookup"><span data-stu-id="a8c94-133">Remarks</span></span>  
 <span data-ttu-id="a8c94-134">サービス構成では、セキュリティトークンハンドラーの1つ以上の名前付きコレクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="a8c94-135">`name`属性を使用して、コレクションの名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="a8c94-136">フレームワークによって処理される名前は、"ActAs" と "OnBehalfOf" だけです。</span><span class="sxs-lookup"><span data-stu-id="a8c94-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="a8c94-137">これらのコレクションにハンドラーが存在する場合は、 `ActAs` `OnBehalfOf`トークンの処理時に既定のハンドラーではなく、Security Token Service (STS) によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="a8c94-138">既定では<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>、コレクションには<xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>、 <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>、、、、、 、およびの各ハンドラー型が設定されます。<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="a8c94-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="a8c94-139">コレクションは、 `<add>` `<remove>`、、および`<clear>`の各要素を使用して変更できます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="a8c94-140">コレクション内に存在する特定の種類のハンドラーが1つだけであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8c94-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="a8c94-141">たとえば、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラスからハンドラーを派生させる場合、ハンドラーまたはが<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 1 つのコレクションで構成されていることがありますが、両方を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="a8c94-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="a8c94-142">コレクション内`<securityTokenHandlerConfiguration>`のハンドラーの構成設定を指定するには、要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="a8c94-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="a8c94-143">この要素によって指定された設定は、サービスで指定された設定よりも、ユーザー [ \<構成 >](identityconfiguration.md)要素を介してオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="a8c94-144">いくつかの組み込みハンドラー型を含む一部のハンドラーは、 `<add>`要素の子要素を通じて追加の構成をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="a8c94-145">ハンドラーに指定された設定は、コレクションまたはサービスで指定された同等の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a8c94-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
