---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152581"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="40924-101">\<></span><span class="sxs-lookup"><span data-stu-id="40924-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="40924-102">トークン ハンドラー コレクション内のハンドラーによって使用されるサービス トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="40924-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="40924-103">サービス トークン リゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="40924-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="40924-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="40924-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="40924-105">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="40924-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="40924-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="40924-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="40924-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="40924-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="40924-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="40924-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="40924-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>**</span><span class="sxs-lookup"><span data-stu-id="40924-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40924-110">構文</span><span class="sxs-lookup"><span data-stu-id="40924-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40924-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="40924-111">Attributes and Elements</span></span>  
 <span data-ttu-id="40924-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="40924-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40924-113">属性</span><span class="sxs-lookup"><span data-stu-id="40924-113">Attributes</span></span>  
  
|<span data-ttu-id="40924-114">属性</span><span class="sxs-lookup"><span data-stu-id="40924-114">Attribute</span></span>|<span data-ttu-id="40924-115">説明</span><span class="sxs-lookup"><span data-stu-id="40924-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40924-116">type</span><span class="sxs-lookup"><span data-stu-id="40924-116">type</span></span>|<span data-ttu-id="40924-117">サービス トークン リゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="40924-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="40924-118"><xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラスから派生する<xref:System.IdentityModel.Selectors.SecurityTokenResolver>型または型。</span><span class="sxs-lookup"><span data-stu-id="40924-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="40924-119">`type`属性の指定方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40924-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="40924-120">必須。</span><span class="sxs-lookup"><span data-stu-id="40924-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40924-121">子要素</span><span class="sxs-lookup"><span data-stu-id="40924-121">Child Elements</span></span>  
 <span data-ttu-id="40924-122">なし</span><span class="sxs-lookup"><span data-stu-id="40924-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40924-123">親要素</span><span class="sxs-lookup"><span data-stu-id="40924-123">Parent Elements</span></span>  
  
|<span data-ttu-id="40924-124">要素</span><span class="sxs-lookup"><span data-stu-id="40924-124">Element</span></span>|<span data-ttu-id="40924-125">説明</span><span class="sxs-lookup"><span data-stu-id="40924-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40924-126">\<></span><span class="sxs-lookup"><span data-stu-id="40924-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="40924-127">セキュリティ トークン ハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="40924-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40924-128">解説</span><span class="sxs-lookup"><span data-stu-id="40924-128">Remarks</span></span>  
 <span data-ttu-id="40924-129">サービス トークン リゾルバーを使用して、受信トークンとメッセージの暗号化トークンを解決できます。</span><span class="sxs-lookup"><span data-stu-id="40924-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="40924-130">これは、受信トークンの暗号化を解除するために使用するキーを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="40924-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="40924-131">属性を指定する`type`必要があります。</span><span class="sxs-lookup"><span data-stu-id="40924-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="40924-132">指定する型は、<xref:System.IdentityModel.Selectors.SecurityTokenResolver><xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラスから派生するカスタム型のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="40924-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="40924-133">一部のトークン ハンドラーでは、構成でサービス トークン リゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="40924-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="40924-134">個々のトークン ハンドラーの設定は、セキュリティ トークン ハンドラーコレクションで指定された設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="40924-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40924-135">要素を`<serviceTokenResolver>` [ \<identityConfiguration>](identityconfiguration.md)要素の子要素として指定することは非推奨になりましたが、下位互換性のために引き続きサポートされています。</span><span class="sxs-lookup"><span data-stu-id="40924-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="40924-136">要素の設定`<securityTokenHandlerConfiguration>`は、要素上の`<identityConfiguration>`設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="40924-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40924-137">例</span><span class="sxs-lookup"><span data-stu-id="40924-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
