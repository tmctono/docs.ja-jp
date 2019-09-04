---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251904"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="f9b5b-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="f9b5b-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="f9b5b-102">クラス、 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="f9b5b-103"><xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="f9b5b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f9b5b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f9b5b-105">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f9b5b-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f9b5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f9b5b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f9b5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="f9b5b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="f9b5b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add.md)</span><span class="sxs-lookup"><span data-stu-id="f9b5b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="f9b5b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<samlSecurityTokenRequirement >**</span><span class="sxs-lookup"><span data-stu-id="f9b5b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b5b-110">構文</span><span class="sxs-lookup"><span data-stu-id="f9b5b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9b5b-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f9b5b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f9b5b-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9b5b-113">属性</span><span class="sxs-lookup"><span data-stu-id="f9b5b-113">Attributes</span></span>  
  
|<span data-ttu-id="f9b5b-114">属性</span><span class="sxs-lookup"><span data-stu-id="f9b5b-114">Attribute</span></span>|<span data-ttu-id="f9b5b-115">説明</span><span class="sxs-lookup"><span data-stu-id="f9b5b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9b5b-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="f9b5b-116">mapToWindows</span></span>|<span data-ttu-id="f9b5b-117">受信 UPN 要求を使用して、トークンハンドラーが検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="f9b5b-118">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-118">The default is "false".</span></span>|  
|<span data-ttu-id="f9b5b-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="f9b5b-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="f9b5b-120">X.509 証明書に使用する失効モードを指定する値。<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="f9b5b-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f9b5b-121">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="f9b5b-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f9b5b-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="f9b5b-123">X.509 証明書に使用する検証モードを指定する値。<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="f9b5b-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f9b5b-124">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="f9b5b-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f9b5b-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="f9b5b-126">X.509 証明書ストアを示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="f9b5b-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="f9b5b-127">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="f9b5b-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="f9b5b-128">issuerCertificateValidator</span></span>|<span data-ttu-id="f9b5b-129">から<xref:System.IdentityModel.Selectors.X509CertificateValidator>派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="f9b5b-130">`issuerCertificateValidationMode`属性が "Custom" の場合、この型のインスタンスは発行者の証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9b5b-131">子要素</span><span class="sxs-lookup"><span data-stu-id="f9b5b-131">Child Elements</span></span>  
  
|<span data-ttu-id="f9b5b-132">要素</span><span class="sxs-lookup"><span data-stu-id="f9b5b-132">Element</span></span>|<span data-ttu-id="f9b5b-133">説明</span><span class="sxs-lookup"><span data-stu-id="f9b5b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9b5b-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="f9b5b-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="f9b5b-135"><xref:System.Security.Principal.IIdentity.Name%2A>プロパティを指定するクレームの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="f9b5b-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="f9b5b-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="f9b5b-137">トークンハンドラーの<xref:System.Security.Claims.ClaimsIdentity> <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>メソッドによって返されるオブジェクトのコレクション内でのロールの種類の要求を定義する要求の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9b5b-138">親要素</span><span class="sxs-lookup"><span data-stu-id="f9b5b-138">Parent Elements</span></span>  
  
|<span data-ttu-id="f9b5b-139">要素</span><span class="sxs-lookup"><span data-stu-id="f9b5b-139">Element</span></span>|<span data-ttu-id="f9b5b-140">説明</span><span class="sxs-lookup"><span data-stu-id="f9b5b-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9b5b-141">\<add></span><span class="sxs-lookup"><span data-stu-id="f9b5b-141">\<add></span></span>](add.md)|<span data-ttu-id="f9b5b-142">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f9b5b-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9b5b-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="f9b5b-143">Remarks</span></span>  
 <span data-ttu-id="f9b5b-144">`SamlSecurityTokenRequirement` <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>要素は、オブジェクトモデルの<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>クラスによって表され、またはでプロパティを構成するために使用されます。 `<samlSecurityTokenRequirement>`</span><span class="sxs-lookup"><span data-stu-id="f9b5b-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9b5b-145">例</span><span class="sxs-lookup"><span data-stu-id="f9b5b-145">Example</span></span>  
  
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
