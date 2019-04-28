---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: e1b8acd48ee185b3c6c50f70321bb9ca66e8e02b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793862"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="298e6-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="298e6-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="298e6-102">構成を提供、<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>クラス、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、またはこれらのクラスのいずれかの派生クラス。</span><span class="sxs-lookup"><span data-stu-id="298e6-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="298e6-103">によって表される、<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>クラス。</span><span class="sxs-lookup"><span data-stu-id="298e6-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="298e6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="298e6-104">\<system.identityModel></span></span>  
<span data-ttu-id="298e6-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="298e6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="298e6-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="298e6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="298e6-107">\<add></span><span class="sxs-lookup"><span data-stu-id="298e6-107">\<add></span></span>  
<span data-ttu-id="298e6-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="298e6-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="298e6-109">構文</span><span class="sxs-lookup"><span data-stu-id="298e6-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="298e6-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="298e6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="298e6-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="298e6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="298e6-112">属性</span><span class="sxs-lookup"><span data-stu-id="298e6-112">Attributes</span></span>  
  
|<span data-ttu-id="298e6-113">属性</span><span class="sxs-lookup"><span data-stu-id="298e6-113">Attribute</span></span>|<span data-ttu-id="298e6-114">説明</span><span class="sxs-lookup"><span data-stu-id="298e6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="298e6-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="298e6-115">mapToWindows</span></span>|<span data-ttu-id="298e6-116">トークン ハンドラーが、入力方向の UPN 要求を使用して、検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="298e6-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="298e6-117">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="298e6-117">The default is "false".</span></span>|  
|<span data-ttu-id="298e6-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="298e6-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="298e6-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> X.509 証明書を使用する失効モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="298e6-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="298e6-120">既定値は、"Online"です。</span><span class="sxs-lookup"><span data-stu-id="298e6-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="298e6-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="298e6-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="298e6-122"><xref:System.ServiceModel.Security.X509CertificateValidationMode> X.509 証明書を使用する検証モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="298e6-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="298e6-123">既定値は、"PeerOrChainTrust"です。</span><span class="sxs-lookup"><span data-stu-id="298e6-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="298e6-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="298e6-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="298e6-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 証明書ストアを指定する値。</span><span class="sxs-lookup"><span data-stu-id="298e6-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="298e6-126">既定値は、"LocalMachine"です。</span><span class="sxs-lookup"><span data-stu-id="298e6-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="298e6-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="298e6-127">issuerCertificateValidator</span></span>|<span data-ttu-id="298e6-128">派生したカスタム型<xref:System.IdentityModel.Selectors.X509CertificateValidator>します。</span><span class="sxs-lookup"><span data-stu-id="298e6-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="298e6-129">場合、`issuerCertificateValidationMode`属性が"Custom"は、この型のインスタンスが発行者証明書の検証に使用します。</span><span class="sxs-lookup"><span data-stu-id="298e6-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="298e6-130">子要素</span><span class="sxs-lookup"><span data-stu-id="298e6-130">Child Elements</span></span>  
  
|<span data-ttu-id="298e6-131">要素</span><span class="sxs-lookup"><span data-stu-id="298e6-131">Element</span></span>|<span data-ttu-id="298e6-132">説明</span><span class="sxs-lookup"><span data-stu-id="298e6-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="298e6-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="298e6-133">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="298e6-134">設定を指定するクレームの種類、<xref:System.Security.Principal.IIdentity.Name%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="298e6-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="298e6-135">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="298e6-135">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="298e6-136">コレクション内のロールの種類の要求を定義する要求の種類を指定します<xref:System.Security.Claims.ClaimsIdentity>によって返されるオブジェクト、<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>トークン ハンドラーのメソッド。</span><span class="sxs-lookup"><span data-stu-id="298e6-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="298e6-137">親要素</span><span class="sxs-lookup"><span data-stu-id="298e6-137">Parent Elements</span></span>  
  
|<span data-ttu-id="298e6-138">要素</span><span class="sxs-lookup"><span data-stu-id="298e6-138">Element</span></span>|<span data-ttu-id="298e6-139">説明</span><span class="sxs-lookup"><span data-stu-id="298e6-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="298e6-140">\<add></span><span class="sxs-lookup"><span data-stu-id="298e6-140">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="298e6-141">トークン ハンドラー コレクションには、指定したセキュリティ トークン ハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="298e6-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="298e6-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="298e6-142">Remarks</span></span>  
 <span data-ttu-id="298e6-143">`<samlSecurityTokenRequirement>`要素が表される、<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>オブジェクト モデルのクラスを構成するために使用、`SamlSecurityTokenRequirement`プロパティを<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>または<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>します。</span><span class="sxs-lookup"><span data-stu-id="298e6-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="298e6-144">例</span><span class="sxs-lookup"><span data-stu-id="298e6-144">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
