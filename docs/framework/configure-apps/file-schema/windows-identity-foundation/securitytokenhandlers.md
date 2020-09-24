---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: d892fbd802ed366ca7af9b85fbf5c23d4d27e0f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157006"
---
# \<securityTokenHandlers>

<span data-ttu-id="fcbe1-101">エンドポイントに登録されているセキュリティトークンハンドラーのコレクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-101">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlers>**  
  
## <a name="syntax"></a><span data-ttu-id="fcbe1-102">構文</span><span class="sxs-lookup"><span data-stu-id="fcbe1-102">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcbe1-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="fcbe1-103">Attributes and Elements</span></span>  

 <span data-ttu-id="fcbe1-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcbe1-105">属性</span><span class="sxs-lookup"><span data-stu-id="fcbe1-105">Attributes</span></span>  
  
|<span data-ttu-id="fcbe1-106">属性</span><span class="sxs-lookup"><span data-stu-id="fcbe1-106">Attribute</span></span>|<span data-ttu-id="fcbe1-107">説明</span><span class="sxs-lookup"><span data-stu-id="fcbe1-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcbe1-108">name</span><span class="sxs-lookup"><span data-stu-id="fcbe1-108">name</span></span>|<span data-ttu-id="fcbe1-109">トークンハンドラーコレクションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-109">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="fcbe1-110">フレームワークによって認識される値は、"ActAs" と "OnBehalfOf" だけです。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-110">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="fcbe1-111">これらのいずれかの名前でトークンハンドラーコレクションが指定されている場合、ActAs または OnBehalfOf トークンをそれぞれ処理するときにコレクションが使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-111">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcbe1-112">子要素</span><span class="sxs-lookup"><span data-stu-id="fcbe1-112">Child Elements</span></span>  
  
|<span data-ttu-id="fcbe1-113">要素</span><span class="sxs-lookup"><span data-stu-id="fcbe1-113">Element</span></span>|<span data-ttu-id="fcbe1-114">説明</span><span class="sxs-lookup"><span data-stu-id="fcbe1-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="fcbe1-115">トークンハンドラーコレクションにセキュリティトークンハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-115">Adds a security token handler to the token handler collection.</span></span>|  
|[\<clear>](clear.md)|<span data-ttu-id="fcbe1-116">すべてのセキュリティトークンハンドラーをトークンハンドラーコレクションから削除します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-116">Clears all security token handlers from the token handler collection.</span></span>|  
|[\<remove>](remove.md)|<span data-ttu-id="fcbe1-117">トークンハンドラーコレクションからセキュリティトークンハンドラーを削除します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-117">Removes a security token handler from the token handler collection.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="fcbe1-118">トークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-118">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcbe1-119">親要素</span><span class="sxs-lookup"><span data-stu-id="fcbe1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fcbe1-120">要素</span><span class="sxs-lookup"><span data-stu-id="fcbe1-120">Element</span></span>|<span data-ttu-id="fcbe1-121">説明</span><span class="sxs-lookup"><span data-stu-id="fcbe1-121">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="fcbe1-122">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcbe1-123">解説</span><span class="sxs-lookup"><span data-stu-id="fcbe1-123">Remarks</span></span>  

 <span data-ttu-id="fcbe1-124">サービス構成では、セキュリティトークンハンドラーの1つ以上の名前付きコレクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-124">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="fcbe1-125">属性を使用して、コレクションの名前を指定でき `name` ます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-125">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="fcbe1-126">フレームワークによって処理される名前は、"ActAs" と "OnBehalfOf" だけです。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-126">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="fcbe1-127">これらのコレクションにハンドラーが存在する場合は、トークンの処理時に既定のハンドラーではなく、Security Token Service (STS) によって使用され `ActAs` `OnBehalfOf` ます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-127">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="fcbe1-128">既定では、コレクションには、、、、、、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler> <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 、および <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler> の各ハンドラー型が設定されます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-128">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="fcbe1-129">コレクションは、、、およびの各要素を使用して変更でき `<add>` `<remove>` `<clear>` ます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-129">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="fcbe1-130">コレクション内に存在する特定の種類のハンドラーが1つだけであることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-130">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="fcbe1-131">たとえば、クラスからハンドラーを派生させる場合、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ハンドラーまたはが <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 1 つのコレクションで構成されていることがありますが、両方を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-131">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="fcbe1-132">`<securityTokenHandlerConfiguration>`コレクション内のハンドラーの構成設定を指定するには、要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-132">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="fcbe1-133">この要素によって指定された設定は、サービスで指定された設定よりも要素を介してオーバーライドされ [\<identityConfiguration>](identityconfiguration.md) ます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-133">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="fcbe1-134">いくつかの組み込みハンドラー型を含む一部のハンドラーは、要素の子要素を通じて追加の構成をサポートでき `<add>` ます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-134">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="fcbe1-135">ハンドラーに指定された設定は、コレクションまたはサービスで指定された同等の設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="fcbe1-135">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
