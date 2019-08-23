---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923104"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="8811b-101">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="8811b-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="8811b-102">トークンハンドラーコレクションのハンドラーによって使用されるサービストークンリゾルバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="8811b-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8811b-103">サービストークンリゾルバーは、受信トークンとメッセージの暗号化トークンを解決するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8811b-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="8811b-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="8811b-104">\<system.identityModel></span></span>  
<span data-ttu-id="8811b-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="8811b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="8811b-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="8811b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8811b-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8811b-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="8811b-108">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="8811b-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8811b-109">構文</span><span class="sxs-lookup"><span data-stu-id="8811b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8811b-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="8811b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8811b-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="8811b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8811b-112">属性</span><span class="sxs-lookup"><span data-stu-id="8811b-112">Attributes</span></span>  
  
|<span data-ttu-id="8811b-113">属性</span><span class="sxs-lookup"><span data-stu-id="8811b-113">Attribute</span></span>|<span data-ttu-id="8811b-114">説明</span><span class="sxs-lookup"><span data-stu-id="8811b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8811b-115">型</span><span class="sxs-lookup"><span data-stu-id="8811b-115">type</span></span>|<span data-ttu-id="8811b-116">サービストークンリゾルバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="8811b-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="8811b-117">クラスから派生した型または型。<xref:System.IdentityModel.Selectors.SecurityTokenResolver> <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="8811b-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="8811b-118">`type`属性を指定する方法の詳細については、「[カスタム型参照]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8811b-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="8811b-119">必須。</span><span class="sxs-lookup"><span data-stu-id="8811b-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8811b-120">子要素</span><span class="sxs-lookup"><span data-stu-id="8811b-120">Child Elements</span></span>  
 <span data-ttu-id="8811b-121">なし</span><span class="sxs-lookup"><span data-stu-id="8811b-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8811b-122">親要素</span><span class="sxs-lookup"><span data-stu-id="8811b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="8811b-123">要素</span><span class="sxs-lookup"><span data-stu-id="8811b-123">Element</span></span>|<span data-ttu-id="8811b-124">説明</span><span class="sxs-lookup"><span data-stu-id="8811b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8811b-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8811b-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="8811b-126">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="8811b-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8811b-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="8811b-127">Remarks</span></span>  
 <span data-ttu-id="8811b-128">サービストークンリゾルバーを使用して、受信トークンとメッセージの暗号化トークンを解決できます。</span><span class="sxs-lookup"><span data-stu-id="8811b-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="8811b-129">これは、受信トークンの暗号化を解除するために使用する必要があるキーを取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8811b-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="8811b-130">`type`属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8811b-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="8811b-131">指定できる型は、また<xref:System.IdentityModel.Selectors.SecurityTokenResolver>は<xref:System.IdentityModel.Selectors.SecurityTokenResolver>クラスから派生したカスタム型のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="8811b-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="8811b-132">一部のトークンハンドラーでは、構成でサービストークンリゾルバーの設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="8811b-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="8811b-133">個々のトークンハンドラーの設定は、セキュリティトークンハンドラーコレクションで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8811b-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8811b-134">要素を、指定した[ \<>](identityconfiguration.md)要素の子要素として指定することは推奨されていませんが、旧バージョンとの互換性のためにサポートされています。 `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="8811b-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="8811b-135">要素の設定`<securityTokenHandlerConfiguration>`は、要素の設定`<identityConfiguration>`よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8811b-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8811b-136">例</span><span class="sxs-lookup"><span data-stu-id="8811b-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
