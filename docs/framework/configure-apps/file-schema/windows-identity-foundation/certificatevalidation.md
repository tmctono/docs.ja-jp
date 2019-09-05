---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252133"
---
# <a name="certificatevalidation"></a><span data-ttu-id="9cfde-101">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="9cfde-101">\<certificateValidation></span></span>
<span data-ttu-id="9cfde-102">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="9cfde-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="9cfde-103">特定のハンドラーが独自の検証コントロールを使用して構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="9cfde-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="9cfde-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9cfde-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9cfde-105">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="9cfde-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="9cfde-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="9cfde-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="9cfde-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateValidation >**</span><span class="sxs-lookup"><span data-stu-id="9cfde-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cfde-108">構文</span><span class="sxs-lookup"><span data-stu-id="9cfde-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cfde-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9cfde-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9cfde-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9cfde-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cfde-111">属性</span><span class="sxs-lookup"><span data-stu-id="9cfde-111">Attributes</span></span>  
  
|<span data-ttu-id="9cfde-112">属性</span><span class="sxs-lookup"><span data-stu-id="9cfde-112">Attribute</span></span>|<span data-ttu-id="9cfde-113">説明</span><span class="sxs-lookup"><span data-stu-id="9cfde-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cfde-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="9cfde-114">certificateValidationMode</span></span>|<span data-ttu-id="9cfde-115">X.509 証明書に使用する検証モードを指定する値。<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="9cfde-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9cfde-116">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="9cfde-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="9cfde-117">カスタム検証を指定するには、この属性を "custom" に設定し、 [ \<certificatevalidator >](certificatevalidator.md)要素を使用して検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="9cfde-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="9cfde-118">任意。</span><span class="sxs-lookup"><span data-stu-id="9cfde-118">Optional.</span></span>|  
|<span data-ttu-id="9cfde-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="9cfde-119">revocationMode</span></span>|<span data-ttu-id="9cfde-120">X.509 証明書に使用する失効モードを指定する値。<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="9cfde-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="9cfde-121">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="9cfde-121">The default value is "Online".</span></span> <span data-ttu-id="9cfde-122">任意。</span><span class="sxs-lookup"><span data-stu-id="9cfde-122">Optional.</span></span>|  
|<span data-ttu-id="9cfde-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="9cfde-123">trustedStoreLocation</span></span>|<span data-ttu-id="9cfde-124">X.509 証明書ストアを示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="9cfde-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="9cfde-125">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="9cfde-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="9cfde-126">任意。</span><span class="sxs-lookup"><span data-stu-id="9cfde-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cfde-127">子要素</span><span class="sxs-lookup"><span data-stu-id="9cfde-127">Child Elements</span></span>  
  
|<span data-ttu-id="9cfde-128">要素</span><span class="sxs-lookup"><span data-stu-id="9cfde-128">Element</span></span>|<span data-ttu-id="9cfde-129">説明</span><span class="sxs-lookup"><span data-stu-id="9cfde-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cfde-130">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="9cfde-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="9cfde-131">証明書の検証に使用するカスタムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cfde-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="9cfde-132">この型は、 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md)要素の属性が "Custom" に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="9cfde-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9cfde-133">親要素</span><span class="sxs-lookup"><span data-stu-id="9cfde-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9cfde-134">要素</span><span class="sxs-lookup"><span data-stu-id="9cfde-134">Element</span></span>|<span data-ttu-id="9cfde-135">説明</span><span class="sxs-lookup"><span data-stu-id="9cfde-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cfde-136">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="9cfde-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="9cfde-137">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9cfde-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="9cfde-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9cfde-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9cfde-139">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="9cfde-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cfde-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="9cfde-140">Remarks</span></span>  
 <span data-ttu-id="9cfde-141">要素は、要素の`<identityConfiguration>`下のサービスレベルで指定することも、 `<securityTokenHandlerConfiguration>`要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもできます。 `<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="9cfde-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="9cfde-142">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9cfde-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="9cfde-143">一部のトークンハンドラーでは、構成で証明書の検証設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9cfde-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="9cfde-144">個々のトークンハンドラーの設定は、サービスレベルとセキュリティトークンハンドラーコレクションの両方で指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9cfde-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cfde-145">例</span><span class="sxs-lookup"><span data-stu-id="9cfde-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
