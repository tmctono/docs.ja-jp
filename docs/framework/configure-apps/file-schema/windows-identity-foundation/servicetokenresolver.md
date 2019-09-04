---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251847"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="87e7b-101">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="87e7b-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="87e7b-102">トークンハンドラーコレクションのハンドラーによって使用されるサービストークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="87e7b-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="87e7b-103">サービストークンリゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87e7b-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="87e7b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="87e7b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="87e7b-105">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="87e7b-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="87e7b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="87e7b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="87e7b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="87e7b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="87e7b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlerConfiguration >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="87e7b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="87e7b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<serviceTokenResolver >**</span><span class="sxs-lookup"><span data-stu-id="87e7b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e7b-110">構文</span><span class="sxs-lookup"><span data-stu-id="87e7b-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87e7b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="87e7b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="87e7b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="87e7b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87e7b-113">属性</span><span class="sxs-lookup"><span data-stu-id="87e7b-113">Attributes</span></span>  
  
|<span data-ttu-id="87e7b-114">属性</span><span class="sxs-lookup"><span data-stu-id="87e7b-114">Attribute</span></span>|<span data-ttu-id="87e7b-115">説明</span><span class="sxs-lookup"><span data-stu-id="87e7b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87e7b-116">型</span><span class="sxs-lookup"><span data-stu-id="87e7b-116">type</span></span>|<span data-ttu-id="87e7b-117">サービストークンリゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="87e7b-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="87e7b-118">クラスから派生した型または型。<xref:System.IdentityModel.Selectors.SecurityTokenResolver> <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="87e7b-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="87e7b-119">`type`属性を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87e7b-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="87e7b-120">必須。</span><span class="sxs-lookup"><span data-stu-id="87e7b-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87e7b-121">子要素</span><span class="sxs-lookup"><span data-stu-id="87e7b-121">Child Elements</span></span>  
 <span data-ttu-id="87e7b-122">なし</span><span class="sxs-lookup"><span data-stu-id="87e7b-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="87e7b-123">親要素</span><span class="sxs-lookup"><span data-stu-id="87e7b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="87e7b-124">要素</span><span class="sxs-lookup"><span data-stu-id="87e7b-124">Element</span></span>|<span data-ttu-id="87e7b-125">説明</span><span class="sxs-lookup"><span data-stu-id="87e7b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87e7b-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="87e7b-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="87e7b-127">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="87e7b-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87e7b-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="87e7b-128">Remarks</span></span>  
 <span data-ttu-id="87e7b-129">サービストークンリゾルバーを使用して、受信トークンとメッセージの暗号化トークンを解決できます。</span><span class="sxs-lookup"><span data-stu-id="87e7b-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="87e7b-130">これは、受信トークンの暗号化を解除するために使用する必要があるキーを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="87e7b-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="87e7b-131">`type`属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87e7b-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="87e7b-132">指定できる型は、また<xref:System.IdentityModel.Selectors.SecurityTokenResolver>は<xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラスから派生したカスタム型のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="87e7b-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="87e7b-133">一部のトークンハンドラーでは、構成でサービストークンリゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="87e7b-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="87e7b-134">個々のトークンハンドラーの設定は、セキュリティトークンハンドラーコレクションで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="87e7b-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87e7b-135">要素を、指定した[ \<>](identityconfiguration.md)要素の子要素として指定することは推奨されていませんが、旧バージョンとの互換性のためにサポートされています。 `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="87e7b-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="87e7b-136">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="87e7b-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87e7b-137">例</span><span class="sxs-lookup"><span data-stu-id="87e7b-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 