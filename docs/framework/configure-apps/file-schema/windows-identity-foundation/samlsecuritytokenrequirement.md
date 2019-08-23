---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942486"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="d2f94-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d2f94-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="d2f94-102">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="d2f94-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="d2f94-103"><xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="d2f94-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="d2f94-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="d2f94-104">\<system.identityModel></span></span>  
<span data-ttu-id="d2f94-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="d2f94-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d2f94-106">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="d2f94-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="d2f94-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d2f94-107">\<add></span></span>  
<span data-ttu-id="d2f94-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="d2f94-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2f94-109">構文</span><span class="sxs-lookup"><span data-stu-id="d2f94-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2f94-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d2f94-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d2f94-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d2f94-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2f94-112">属性</span><span class="sxs-lookup"><span data-stu-id="d2f94-112">Attributes</span></span>  
  
|<span data-ttu-id="d2f94-113">属性</span><span class="sxs-lookup"><span data-stu-id="d2f94-113">Attribute</span></span>|<span data-ttu-id="d2f94-114">説明</span><span class="sxs-lookup"><span data-stu-id="d2f94-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2f94-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="d2f94-115">mapToWindows</span></span>|<span data-ttu-id="d2f94-116">受信 UPN 要求を使用して、トークンハンドラーが検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d2f94-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="d2f94-117">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="d2f94-117">The default is "false".</span></span>|  
|<span data-ttu-id="d2f94-118">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="d2f94-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="d2f94-119">X.509 証明書に使用する失効モードを指定する値。<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="d2f94-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="d2f94-120">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="d2f94-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="d2f94-121">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="d2f94-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="d2f94-122">X.509 証明書に使用する検証モードを指定する値。<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="d2f94-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="d2f94-123">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="d2f94-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="d2f94-124">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="d2f94-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="d2f94-125">X.509 証明書ストアを示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="d2f94-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="d2f94-126">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="d2f94-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="d2f94-127">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="d2f94-127">issuerCertificateValidator</span></span>|<span data-ttu-id="d2f94-128">から<xref:System.IdentityModel.Selectors.X509CertificateValidator>派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="d2f94-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="d2f94-129">`issuerCertificateValidationMode`属性が "Custom" の場合、この型のインスタンスは発行者の証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d2f94-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2f94-130">子要素</span><span class="sxs-lookup"><span data-stu-id="d2f94-130">Child Elements</span></span>  
  
|<span data-ttu-id="d2f94-131">要素</span><span class="sxs-lookup"><span data-stu-id="d2f94-131">Element</span></span>|<span data-ttu-id="d2f94-132">説明</span><span class="sxs-lookup"><span data-stu-id="d2f94-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2f94-133">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="d2f94-133">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="d2f94-134"><xref:System.Security.Principal.IIdentity.Name%2A>プロパティを指定するクレームの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="d2f94-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="d2f94-135">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="d2f94-135">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="d2f94-136">トークンハンドラーの<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>メソッドによって返されるオブジェクトのコレクション内でのロールの種類の要求を定義する要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="d2f94-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2f94-137">親要素</span><span class="sxs-lookup"><span data-stu-id="d2f94-137">Parent Elements</span></span>  
  
|<span data-ttu-id="d2f94-138">要素</span><span class="sxs-lookup"><span data-stu-id="d2f94-138">Element</span></span>|<span data-ttu-id="d2f94-139">説明</span><span class="sxs-lookup"><span data-stu-id="d2f94-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2f94-140">\<add></span><span class="sxs-lookup"><span data-stu-id="d2f94-140">\<add></span></span>](add.md)|<span data-ttu-id="d2f94-141">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d2f94-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2f94-142">Remarks</span><span class="sxs-lookup"><span data-stu-id="d2f94-142">Remarks</span></span>  
 <span data-ttu-id="d2f94-143">`SamlSecurityTokenRequirement` <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>要素は、オブジェクトモデルの<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>クラスによって表され、またはでプロパティを構成するために使用されます。 `<samlSecurityTokenRequirement>`</span><span class="sxs-lookup"><span data-stu-id="d2f94-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2f94-144">例</span><span class="sxs-lookup"><span data-stu-id="d2f94-144">Example</span></span>  
  
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
