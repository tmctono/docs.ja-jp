---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152633"
---
# \<samlSecurityTokenRequirement>
<span data-ttu-id="d3f6f-101">クラス、クラス、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> またはこれらのクラスの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-101">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="d3f6f-102">クラスによって表さ <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> れます。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-102">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="d3f6f-103">構文</span><span class="sxs-lookup"><span data-stu-id="d3f6f-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3f6f-104">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d3f6f-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d3f6f-105">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3f6f-106">属性</span><span class="sxs-lookup"><span data-stu-id="d3f6f-106">Attributes</span></span>  
  
|<span data-ttu-id="d3f6f-107">属性</span><span class="sxs-lookup"><span data-stu-id="d3f6f-107">Attribute</span></span>|<span data-ttu-id="d3f6f-108">説明</span><span class="sxs-lookup"><span data-stu-id="d3f6f-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3f6f-109">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="d3f6f-109">mapToWindows</span></span>|<span data-ttu-id="d3f6f-110">受信 UPN 要求を使用して、トークンハンドラーが検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-110">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="d3f6f-111">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-111">The default is "false".</span></span>|  
|<span data-ttu-id="d3f6f-112">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="d3f6f-112">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="d3f6f-113"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 証明書に使用する失効モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-113">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="d3f6f-114">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-114">The default value is "Online".</span></span>|  
|<span data-ttu-id="d3f6f-115">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="d3f6f-115">issuerCertificateValidationMode</span></span>|<span data-ttu-id="d3f6f-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 証明書に使用する検証モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="d3f6f-117">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="d3f6f-118">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="d3f6f-118">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="d3f6f-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 証明書ストアを示す値です。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="d3f6f-120">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-120">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="d3f6f-121">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="d3f6f-121">issuerCertificateValidator</span></span>|<span data-ttu-id="d3f6f-122">から派生するカスタム型 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-122">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="d3f6f-123">`issuerCertificateValidationMode`属性が "Custom" の場合、この型のインスタンスは発行者の証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-123">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3f6f-124">子要素</span><span class="sxs-lookup"><span data-stu-id="d3f6f-124">Child Elements</span></span>  
  
|<span data-ttu-id="d3f6f-125">要素</span><span class="sxs-lookup"><span data-stu-id="d3f6f-125">Element</span></span>|<span data-ttu-id="d3f6f-126">Description</span><span class="sxs-lookup"><span data-stu-id="d3f6f-126">Description</span></span>|  
|-------------|-----------------|  
|[\<nameClaimType>](nameclaimtype.md)|<span data-ttu-id="d3f6f-127">プロパティを指定するクレームの種類を設定し <xref:System.Security.Principal.IIdentity.Name%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-127">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[\<roleClaimType>](roleclaimtype.md)|<span data-ttu-id="d3f6f-128"><xref:System.Security.Claims.ClaimsIdentity>トークンハンドラーのメソッドによって返されるオブジェクトのコレクション内でのロールの種類の要求を定義する要求の種類を指定し <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-128">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d3f6f-129">親要素</span><span class="sxs-lookup"><span data-stu-id="d3f6f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="d3f6f-130">要素</span><span class="sxs-lookup"><span data-stu-id="d3f6f-130">Element</span></span>|<span data-ttu-id="d3f6f-131">Description</span><span class="sxs-lookup"><span data-stu-id="d3f6f-131">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="d3f6f-132">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-132">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3f6f-133">解説</span><span class="sxs-lookup"><span data-stu-id="d3f6f-133">Remarks</span></span>  
 <span data-ttu-id="d3f6f-134">要素は、 `<samlSecurityTokenRequirement>` オブジェクトモデルのクラスによって表され、 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> `SamlSecurityTokenRequirement` またはでプロパティを構成するために使用され <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ます。</span><span class="sxs-lookup"><span data-stu-id="d3f6f-134">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3f6f-135">例</span><span class="sxs-lookup"><span data-stu-id="d3f6f-135">Example</span></span>  
  
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
