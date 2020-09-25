---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 583fef7eb364c39890b3f9304770b383c1ea6d2a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183508"
---
# \<certificateValidation>

<span data-ttu-id="47d78-101">トークンハンドラーが証明書を検証するために使用する設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="47d78-101">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="47d78-102">特定のハンドラーが独自の検証コントロールを使用して構成されている場合、これらの設定はオーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="47d78-102">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**  
  
## <a name="syntax"></a><span data-ttu-id="47d78-103">構文</span><span class="sxs-lookup"><span data-stu-id="47d78-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47d78-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="47d78-104">Attributes and Elements</span></span>  

 <span data-ttu-id="47d78-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="47d78-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47d78-106">属性</span><span class="sxs-lookup"><span data-stu-id="47d78-106">Attributes</span></span>  
  
|<span data-ttu-id="47d78-107">属性</span><span class="sxs-lookup"><span data-stu-id="47d78-107">Attribute</span></span>|<span data-ttu-id="47d78-108">[説明]</span><span class="sxs-lookup"><span data-stu-id="47d78-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47d78-109">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="47d78-109">certificateValidationMode</span></span>|<span data-ttu-id="47d78-110"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 証明書に使用する検証モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="47d78-110">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="47d78-111">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="47d78-111">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="47d78-112">カスタム検証を指定するには、この属性を "Custom" に設定し、要素を使用して検証コントロールを指定し [\<certificateValidator>](certificatevalidator.md) ます。</span><span class="sxs-lookup"><span data-stu-id="47d78-112">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="47d78-113">省略可能。</span><span class="sxs-lookup"><span data-stu-id="47d78-113">Optional.</span></span>|  
|<span data-ttu-id="47d78-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="47d78-114">revocationMode</span></span>|<span data-ttu-id="47d78-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 証明書に使用する失効モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="47d78-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="47d78-116">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="47d78-116">The default value is "Online".</span></span> <span data-ttu-id="47d78-117">省略可能。</span><span class="sxs-lookup"><span data-stu-id="47d78-117">Optional.</span></span>|  
|<span data-ttu-id="47d78-118">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="47d78-118">trustedStoreLocation</span></span>|<span data-ttu-id="47d78-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 証明書ストアを示す値です。</span><span class="sxs-lookup"><span data-stu-id="47d78-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="47d78-120">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="47d78-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="47d78-121">省略可能。</span><span class="sxs-lookup"><span data-stu-id="47d78-121">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47d78-122">子要素</span><span class="sxs-lookup"><span data-stu-id="47d78-122">Child Elements</span></span>  
  
|<span data-ttu-id="47d78-123">要素</span><span class="sxs-lookup"><span data-stu-id="47d78-123">Element</span></span>|<span data-ttu-id="47d78-124">説明</span><span class="sxs-lookup"><span data-stu-id="47d78-124">Description</span></span>|  
|-------------|-----------------|  
|[\<certificateValidator>](certificatevalidator.md)|<span data-ttu-id="47d78-125">証明書の検証に使用するカスタムの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="47d78-125">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="47d78-126">この型は `certificateValidationMode` 、要素の属性 [\<certificateValidation>](certificatevalidation.md) が "Custom" に設定されている場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="47d78-126">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47d78-127">親要素</span><span class="sxs-lookup"><span data-stu-id="47d78-127">Parent Elements</span></span>  
  
|<span data-ttu-id="47d78-128">要素</span><span class="sxs-lookup"><span data-stu-id="47d78-128">Element</span></span>|<span data-ttu-id="47d78-129">説明</span><span class="sxs-lookup"><span data-stu-id="47d78-129">Description</span></span>|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|<span data-ttu-id="47d78-130">サービスレベルの id 設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="47d78-130">Specifies service-level identity settings.</span></span>|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="47d78-131">セキュリティトークンハンドラーのコレクションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="47d78-131">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47d78-132">解説</span><span class="sxs-lookup"><span data-stu-id="47d78-132">Remarks</span></span>  

 <span data-ttu-id="47d78-133">要素は `<certificateValidation>` 、要素の下のサービスレベルで指定することも、 `<identityConfiguration>` 要素の下のセキュリティトークンハンドラーコレクションレベルで指定することもでき `<securityTokenHandlerConfiguration>` ます。</span><span class="sxs-lookup"><span data-stu-id="47d78-133">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="47d78-134">トークンハンドラーコレクションの設定は、サービスで指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="47d78-134">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="47d78-135">一部のトークンハンドラーでは、構成で証明書の検証設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="47d78-135">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="47d78-136">個々のトークンハンドラーの設定は、サービスレベルとセキュリティトークンハンドラーコレクションの両方で指定された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="47d78-136">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47d78-137">例</span><span class="sxs-lookup"><span data-stu-id="47d78-137">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
