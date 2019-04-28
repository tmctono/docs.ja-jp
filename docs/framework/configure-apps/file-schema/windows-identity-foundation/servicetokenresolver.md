---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793810"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="5be01-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="5be01-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="5be01-102">トークン ハンドラー コレクションのハンドラーによって使用されるサービス トークン リゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="5be01-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="5be01-103">サービス トークン リゾルバーを使用して、受信トークンおよびメッセージの暗号化トークンを解決します。</span><span class="sxs-lookup"><span data-stu-id="5be01-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="5be01-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5be01-104">\<system.identityModel></span></span>  
<span data-ttu-id="5be01-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5be01-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5be01-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="5be01-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="5be01-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="5be01-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="5be01-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="5be01-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be01-109">構文</span><span class="sxs-lookup"><span data-stu-id="5be01-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be01-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5be01-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5be01-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5be01-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be01-112">属性</span><span class="sxs-lookup"><span data-stu-id="5be01-112">Attributes</span></span>  
  
|<span data-ttu-id="5be01-113">属性</span><span class="sxs-lookup"><span data-stu-id="5be01-113">Attribute</span></span>|<span data-ttu-id="5be01-114">説明</span><span class="sxs-lookup"><span data-stu-id="5be01-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5be01-115">種類</span><span class="sxs-lookup"><span data-stu-id="5be01-115">type</span></span>|<span data-ttu-id="5be01-116">サービス トークン リゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="5be01-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="5be01-117">いずれか、<xref:System.IdentityModel.Selectors.SecurityTokenResolver>型または型から派生した、<xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラス。</span><span class="sxs-lookup"><span data-stu-id="5be01-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="5be01-118">詳細を指定する方法については、`type`属性を [カスタム型の参照] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5be01-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="5be01-119">必須。</span><span class="sxs-lookup"><span data-stu-id="5be01-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be01-120">子要素</span><span class="sxs-lookup"><span data-stu-id="5be01-120">Child Elements</span></span>  
 <span data-ttu-id="5be01-121">なし</span><span class="sxs-lookup"><span data-stu-id="5be01-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5be01-122">親要素</span><span class="sxs-lookup"><span data-stu-id="5be01-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5be01-123">要素</span><span class="sxs-lookup"><span data-stu-id="5be01-123">Element</span></span>|<span data-ttu-id="5be01-124">説明</span><span class="sxs-lookup"><span data-stu-id="5be01-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be01-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="5be01-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="5be01-126">トークン ハンドラー コレクションのセキュリティの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="5be01-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5be01-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="5be01-127">Remarks</span></span>  
 <span data-ttu-id="5be01-128">着信トークンおよびメッセージの暗号化トークンを解決するのには、サービス トークン リゾルバーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5be01-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="5be01-129">着信トークン暗号化解除に使用されるキーの取得に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5be01-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="5be01-130">指定する必要があります、`type`属性。</span><span class="sxs-lookup"><span data-stu-id="5be01-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="5be01-131">指定された型には、いずれかを指定できる<xref:System.IdentityModel.Selectors.SecurityTokenResolver>またはカスタム型から派生した、<xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラス。</span><span class="sxs-lookup"><span data-stu-id="5be01-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="5be01-132">いくつかのトークン ハンドラーを使用すると、構成でサービス トークン リゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5be01-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="5be01-133">セキュリティ トークン ハンドラー コレクションの指定された個々 のトークン ハンドラーの設定をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5be01-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5be01-134">指定する、`<serviceTokenResolver>`要素の子要素として、 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)要素は非推奨とされましたが、旧バージョンとの互換性もサポートします。</span><span class="sxs-lookup"><span data-stu-id="5be01-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="5be01-135">上の設定、`<securityTokenHandlerConfiguration>`要素のオーバーライド、`<identityConfiguration>`要素。</span><span class="sxs-lookup"><span data-stu-id="5be01-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5be01-136">例</span><span class="sxs-lookup"><span data-stu-id="5be01-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
