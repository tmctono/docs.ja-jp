---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152633"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="4f1d0-101">\<></span><span class="sxs-lookup"><span data-stu-id="4f1d0-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="4f1d0-102"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>クラス、<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>クラス、またはこれらのクラスのいずれかの派生クラスの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="4f1d0-103">クラスによって表<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>されます。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="4f1d0-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f1d0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f1d0-105">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="4f1d0-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="4f1d0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="4f1d0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="4f1d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="4f1d0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="4f1d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を追加する**](add.md)</span><span class="sxs-lookup"><span data-stu-id="4f1d0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="4f1d0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<要件>**</span><span class="sxs-lookup"><span data-stu-id="4f1d0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f1d0-110">構文</span><span class="sxs-lookup"><span data-stu-id="4f1d0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f1d0-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4f1d0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f1d0-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f1d0-113">属性</span><span class="sxs-lookup"><span data-stu-id="4f1d0-113">Attributes</span></span>  
  
|<span data-ttu-id="4f1d0-114">属性</span><span class="sxs-lookup"><span data-stu-id="4f1d0-114">Attribute</span></span>|<span data-ttu-id="4f1d0-115">説明</span><span class="sxs-lookup"><span data-stu-id="4f1d0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f1d0-116">ウィンドウズにマップします。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-116">mapToWindows</span></span>|<span data-ttu-id="4f1d0-117">トークン ハンドラーが、入力方向の UPN 要求を使用して検証トークンを Windows アカウントにマップするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="4f1d0-118">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-118">The default is "false".</span></span>|  
|<span data-ttu-id="4f1d0-119">発行者証明書失効モード</span><span class="sxs-lookup"><span data-stu-id="4f1d0-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="4f1d0-120">X.509 証明書に使用する失効モードを指定する<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>値。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="4f1d0-121">デフォルト値は「オンライン」です。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="4f1d0-122">証明書検証モードを発行します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="4f1d0-123">X.509 証明書に使用する検証モードを指定する<xref:System.ServiceModel.Security.X509CertificateValidationMode>値。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="4f1d0-124">既定値は"ピアオーチェーントラスト" です。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="4f1d0-125">発行者証明書信頼されたストアの場所</span><span class="sxs-lookup"><span data-stu-id="4f1d0-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="4f1d0-126">X.509 証明書ストアを指定する<xref:System.Security.Cryptography.X509Certificates.StoreLocation>値。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="4f1d0-127">デフォルト値は「ローカルマシン」です。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="4f1d0-128">発行者証明書検証ツール</span><span class="sxs-lookup"><span data-stu-id="4f1d0-128">issuerCertificateValidator</span></span>|<span data-ttu-id="4f1d0-129">から<xref:System.IdentityModel.Selectors.X509CertificateValidator>派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="4f1d0-130">属性が`issuerCertificateValidationMode`"カスタム" の場合、この型のインスタンスは発行者証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f1d0-131">子要素</span><span class="sxs-lookup"><span data-stu-id="4f1d0-131">Child Elements</span></span>  
  
|<span data-ttu-id="4f1d0-132">要素</span><span class="sxs-lookup"><span data-stu-id="4f1d0-132">Element</span></span>|<span data-ttu-id="4f1d0-133">説明</span><span class="sxs-lookup"><span data-stu-id="4f1d0-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f1d0-134">\<名前クレームタイプ></span><span class="sxs-lookup"><span data-stu-id="4f1d0-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="4f1d0-135">プロパティを指定するクレームの種類<xref:System.Security.Principal.IIdentity.Name%2A>を設定します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="4f1d0-136">\<ロールクレームタイプ></span><span class="sxs-lookup"><span data-stu-id="4f1d0-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="4f1d0-137">トークン ハンドラーのメソッドによって返されるオブジェクトのコレクション内の<xref:System.Security.Claims.ClaimsIdentity>ロールの種類の要求<xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A>を定義するクレームの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f1d0-138">親要素</span><span class="sxs-lookup"><span data-stu-id="4f1d0-138">Parent Elements</span></span>  
  
|<span data-ttu-id="4f1d0-139">要素</span><span class="sxs-lookup"><span data-stu-id="4f1d0-139">Element</span></span>|<span data-ttu-id="4f1d0-140">説明</span><span class="sxs-lookup"><span data-stu-id="4f1d0-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f1d0-141">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="4f1d0-141">\<add></span></span>](add.md)|<span data-ttu-id="4f1d0-142">指定したセキュリティ トークン ハンドラーをトークン ハンドラー コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f1d0-143">解説</span><span class="sxs-lookup"><span data-stu-id="4f1d0-143">Remarks</span></span>  
 <span data-ttu-id="4f1d0-144">要素`<samlSecurityTokenRequirement>`はオブジェクト モデルの<xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement>クラスによって表され、 または のプロパティを`SamlSecurityTokenRequirement`<xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>構成するために使用されます<xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>。</span><span class="sxs-lookup"><span data-stu-id="4f1d0-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f1d0-145">例</span><span class="sxs-lookup"><span data-stu-id="4f1d0-145">Example</span></span>  
  
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
