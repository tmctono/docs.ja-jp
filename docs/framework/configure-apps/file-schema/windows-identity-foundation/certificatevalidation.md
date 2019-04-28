---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667354"
---
# <a name="certificatevalidation"></a><span data-ttu-id="7c9eb-101">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="7c9eb-101">\<certificateValidation></span></span>
<span data-ttu-id="7c9eb-102">トークン ハンドラーを使用して証明書の検証の設定を制御します。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="7c9eb-103">特定のハンドラーが、独自の検証ツールで構成されている場合、これらの設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="7c9eb-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="7c9eb-104">\<system.identityModel></span></span>  
<span data-ttu-id="7c9eb-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7c9eb-105">\<identityConfiguration></span></span>  
<span data-ttu-id="7c9eb-106">\<certificateValidation></span><span class="sxs-lookup"><span data-stu-id="7c9eb-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c9eb-107">構文</span><span class="sxs-lookup"><span data-stu-id="7c9eb-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c9eb-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7c9eb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7c9eb-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c9eb-110">属性</span><span class="sxs-lookup"><span data-stu-id="7c9eb-110">Attributes</span></span>  
  
|<span data-ttu-id="7c9eb-111">属性</span><span class="sxs-lookup"><span data-stu-id="7c9eb-111">Attribute</span></span>|<span data-ttu-id="7c9eb-112">説明</span><span class="sxs-lookup"><span data-stu-id="7c9eb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c9eb-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="7c9eb-113">certificateValidationMode</span></span>|<span data-ttu-id="7c9eb-114"><xref:System.ServiceModel.Security.X509CertificateValidationMode> X.509 証明書を使用する検証モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="7c9eb-115">既定値は、"PeerOrChainTrust"です。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="7c9eb-116">カスタム検証を指定するには、"Custom"には、この属性を設定し、検証を指定、 [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)要素。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="7c9eb-117">任意。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-117">Optional.</span></span>|  
|<span data-ttu-id="7c9eb-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="7c9eb-118">revocationMode</span></span>|<span data-ttu-id="7c9eb-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> X.509 証明書を使用する失効モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="7c9eb-120">既定値は、"Online"です。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-120">The default value is "Online".</span></span> <span data-ttu-id="7c9eb-121">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-121">Optional.</span></span>|  
|<span data-ttu-id="7c9eb-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="7c9eb-122">trustedStoreLocation</span></span>|<span data-ttu-id="7c9eb-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 証明書ストアを指定する値。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="7c9eb-124">既定値は、"LocalMachine"です。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="7c9eb-125">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c9eb-126">子要素</span><span class="sxs-lookup"><span data-stu-id="7c9eb-126">Child Elements</span></span>  
  
|<span data-ttu-id="7c9eb-127">要素</span><span class="sxs-lookup"><span data-stu-id="7c9eb-127">Element</span></span>|<span data-ttu-id="7c9eb-128">説明</span><span class="sxs-lookup"><span data-stu-id="7c9eb-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c9eb-129">\<certificateValidator></span><span class="sxs-lookup"><span data-stu-id="7c9eb-129">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="7c9eb-130">証明書の検証のカスタム型を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="7c9eb-131">場合にのみ、この型が使用される、`certificateValidationMode`の属性、 [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)要素が"Custom"に設定します。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7c9eb-132">親要素</span><span class="sxs-lookup"><span data-stu-id="7c9eb-132">Parent Elements</span></span>  
  
|<span data-ttu-id="7c9eb-133">要素</span><span class="sxs-lookup"><span data-stu-id="7c9eb-133">Element</span></span>|<span data-ttu-id="7c9eb-134">説明</span><span class="sxs-lookup"><span data-stu-id="7c9eb-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c9eb-135">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="7c9eb-135">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="7c9eb-136">サービス レベルの id の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="7c9eb-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="7c9eb-137">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="7c9eb-138">トークン ハンドラー コレクションのセキュリティの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c9eb-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="7c9eb-139">Remarks</span></span>  
 <span data-ttu-id="7c9eb-140">A`<certificateValidation>`下で、サービス レベルで要素を指定することができます、`<identityConfiguration>`要素またはセキュリティ トークン ハンドラー コレクション レベルの下で、`<securityTokenHandlerConfiguration>`要素。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="7c9eb-141">トークン ハンドラー コレクションの設定は、サービスに指定されているものをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="7c9eb-142">いくつかのトークン ハンドラーを使用すると、構成で証明書検証の設定を指定できます。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="7c9eb-143">個々 のトークン ハンドラーの設定は、サービス レベルとセキュリティ トークン ハンドラー コレクションの両方に指定されたオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="7c9eb-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c9eb-144">例</span><span class="sxs-lookup"><span data-stu-id="7c9eb-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
