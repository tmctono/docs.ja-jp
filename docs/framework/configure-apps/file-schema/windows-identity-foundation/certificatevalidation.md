---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941917"
---
# <a name="certificatevalidation"></a><span data-ttu-id="71167-101">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="71167-101">\<certificateValidation></span></span>
<span data-ttu-id="71167-102">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="71167-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="71167-103">特定のハンドラーが独自の検証コントロールを使用して構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="71167-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="71167-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="71167-104">\<system.identityModel></span></span>  
<span data-ttu-id="71167-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="71167-105">\<identityConfiguration></span></span>  
<span data-ttu-id="71167-106">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="71167-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71167-107">構文</span><span class="sxs-lookup"><span data-stu-id="71167-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71167-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="71167-108">Attributes and Elements</span></span>  
 <span data-ttu-id="71167-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="71167-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71167-110">属性</span><span class="sxs-lookup"><span data-stu-id="71167-110">Attributes</span></span>  
  
|<span data-ttu-id="71167-111">属性</span><span class="sxs-lookup"><span data-stu-id="71167-111">Attribute</span></span>|<span data-ttu-id="71167-112">説明</span><span class="sxs-lookup"><span data-stu-id="71167-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71167-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="71167-113">certificateValidationMode</span></span>|<span data-ttu-id="71167-114">X.509 証明書に使用する検証モードを指定する値。<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="71167-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="71167-115">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="71167-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="71167-116">カスタム検証を指定するには、この属性を "custom" に設定し、 [ \<certificatevalidator >](certificatevalidator.md)要素を使用して検証コントロールを指定します。</span><span class="sxs-lookup"><span data-stu-id="71167-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="71167-117">任意。</span><span class="sxs-lookup"><span data-stu-id="71167-117">Optional.</span></span>|  
|<span data-ttu-id="71167-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="71167-118">revocationMode</span></span>|<span data-ttu-id="71167-119">X.509 証明書に使用する失効モードを指定する値。<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="71167-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="71167-120">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="71167-120">The default value is "Online".</span></span> <span data-ttu-id="71167-121">任意。</span><span class="sxs-lookup"><span data-stu-id="71167-121">Optional.</span></span>|  
|<span data-ttu-id="71167-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="71167-122">trustedStoreLocation</span></span>|<span data-ttu-id="71167-123">X.509 証明書ストアを示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="71167-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="71167-124">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="71167-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="71167-125">任意。</span><span class="sxs-lookup"><span data-stu-id="71167-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71167-126">子要素</span><span class="sxs-lookup"><span data-stu-id="71167-126">Child Elements</span></span>  
  
|<span data-ttu-id="71167-127">要素</span><span class="sxs-lookup"><span data-stu-id="71167-127">Element</span></span>|<span data-ttu-id="71167-128">説明</span><span class="sxs-lookup"><span data-stu-id="71167-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71167-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="71167-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="71167-130">証明書の検証に使用するカスタムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="71167-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="71167-131">この型は、 `certificateValidationMode` [ \<certificatevalidation >](certificatevalidation.md)要素の属性が "Custom" に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="71167-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71167-132">親要素</span><span class="sxs-lookup"><span data-stu-id="71167-132">Parent Elements</span></span>  
  
|<span data-ttu-id="71167-133">要素</span><span class="sxs-lookup"><span data-stu-id="71167-133">Element</span></span>|<span data-ttu-id="71167-134">説明</span><span class="sxs-lookup"><span data-stu-id="71167-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71167-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="71167-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="71167-136">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="71167-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="71167-137">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="71167-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="71167-138">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="71167-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71167-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="71167-139">Remarks</span></span>  
 <span data-ttu-id="71167-140">要素は、要素の`<identityConfiguration>`下のサービスレベルで指定することも、 `<securityTokenHandlerConfiguration>`要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもできます。 `<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="71167-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="71167-141">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="71167-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="71167-142">一部のトークンハンドラーでは、構成で証明書の検証設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="71167-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="71167-143">個々のトークンハンドラーの設定は、サービスレベルとセキュリティトークンハンドラーコレクションの両方で指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="71167-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71167-144">例</span><span class="sxs-lookup"><span data-stu-id="71167-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
