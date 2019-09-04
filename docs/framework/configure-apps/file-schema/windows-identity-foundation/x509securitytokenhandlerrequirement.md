---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251691"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="f847e-101">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="f847e-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="f847e-102"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>クラスまたは派生クラスのオプションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="f847e-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="f847e-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f847e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f847e-104">&nbsp;&nbsp;[ **\<システムの >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="f847e-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="f847e-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<構成 >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f847e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="f847e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="f847e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="f847e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> の追加**](add.md)</span><span class="sxs-lookup"><span data-stu-id="f847e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="f847e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<x509SecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="f847e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f847e-109">構文</span><span class="sxs-lookup"><span data-stu-id="f847e-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f847e-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f847e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f847e-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f847e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f847e-112">属性</span><span class="sxs-lookup"><span data-stu-id="f847e-112">Attributes</span></span>  
  
|<span data-ttu-id="f847e-113">属性</span><span class="sxs-lookup"><span data-stu-id="f847e-113">Attribute</span></span>|<span data-ttu-id="f847e-114">説明</span><span class="sxs-lookup"><span data-stu-id="f847e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f847e-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="f847e-115">certificateValidationMode</span></span>|<span data-ttu-id="f847e-116">X.509 証明書に使用する検証モードを指定する値。<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="f847e-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f847e-117">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="f847e-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="f847e-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="f847e-118">mapToWindows</span></span>|<span data-ttu-id="f847e-119">受信 UPN 要求を使用して、トークンハンドラーが検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f847e-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="f847e-120">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="f847e-120">The default is "false".</span></span>|  
|<span data-ttu-id="f847e-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="f847e-121">revocationMode</span></span>|<span data-ttu-id="f847e-122">X.509 証明書に使用する失効モードを指定する値。<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="f847e-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="f847e-123">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="f847e-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="f847e-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="f847e-124">trustedStoreLocation</span></span>|<span data-ttu-id="f847e-125">X.509 証明書ストアを示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="f847e-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="f847e-126">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="f847e-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="f847e-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="f847e-127">certificateValidator</span></span>|<span data-ttu-id="f847e-128">から<xref:System.IdentityModel.Selectors.X509CertificateValidator>派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="f847e-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="f847e-129">`certificateValidationMode`属性が "Custom" の場合、この型のインスタンスは発行者の証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="f847e-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f847e-130">子要素</span><span class="sxs-lookup"><span data-stu-id="f847e-130">Child Elements</span></span>  
 <span data-ttu-id="f847e-131">なし</span><span class="sxs-lookup"><span data-stu-id="f847e-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f847e-132">親要素</span><span class="sxs-lookup"><span data-stu-id="f847e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="f847e-133">要素</span><span class="sxs-lookup"><span data-stu-id="f847e-133">Element</span></span>|<span data-ttu-id="f847e-134">説明</span><span class="sxs-lookup"><span data-stu-id="f847e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f847e-135">\<add></span><span class="sxs-lookup"><span data-stu-id="f847e-135">\<add></span></span>](add.md)|<span data-ttu-id="f847e-136">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="f847e-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f847e-137">例</span><span class="sxs-lookup"><span data-stu-id="f847e-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
