---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 2851820460a34d62175929b48ad57914df557059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945176"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="b8994-101">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b8994-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="b8994-102"><xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>クラスまたは派生クラスのオプションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="b8994-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="b8994-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b8994-103">\<system.identityModel></span></span>  
<span data-ttu-id="b8994-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b8994-104">\<identityConfiguration></span></span>  
<span data-ttu-id="b8994-105">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="b8994-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b8994-106">\<add></span><span class="sxs-lookup"><span data-stu-id="b8994-106">\<add></span></span>  
<span data-ttu-id="b8994-107">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="b8994-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8994-108">構文</span><span class="sxs-lookup"><span data-stu-id="b8994-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8994-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b8994-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b8994-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8994-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8994-111">属性</span><span class="sxs-lookup"><span data-stu-id="b8994-111">Attributes</span></span>  
  
|<span data-ttu-id="b8994-112">属性</span><span class="sxs-lookup"><span data-stu-id="b8994-112">Attribute</span></span>|<span data-ttu-id="b8994-113">説明</span><span class="sxs-lookup"><span data-stu-id="b8994-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8994-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="b8994-114">certificateValidationMode</span></span>|<span data-ttu-id="b8994-115">X.509 証明書に使用する検証モードを指定する値。<xref:System.ServiceModel.Security.X509CertificateValidationMode></span><span class="sxs-lookup"><span data-stu-id="b8994-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b8994-116">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="b8994-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="b8994-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="b8994-117">mapToWindows</span></span>|<span data-ttu-id="b8994-118">受信 UPN 要求を使用して、トークンハンドラーが検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8994-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="b8994-119">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="b8994-119">The default is "false".</span></span>|  
|<span data-ttu-id="b8994-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="b8994-120">revocationMode</span></span>|<span data-ttu-id="b8994-121">X.509 証明書に使用する失効モードを指定する値。<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode></span><span class="sxs-lookup"><span data-stu-id="b8994-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="b8994-122">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="b8994-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="b8994-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="b8994-123">trustedStoreLocation</span></span>|<span data-ttu-id="b8994-124">X.509 証明書ストアを示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="b8994-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="b8994-125">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="b8994-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="b8994-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="b8994-126">certificateValidator</span></span>|<span data-ttu-id="b8994-127">から<xref:System.IdentityModel.Selectors.X509CertificateValidator>派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="b8994-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="b8994-128">`certificateValidationMode`属性が "Custom" の場合、この型のインスタンスは発行者の証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8994-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8994-129">子要素</span><span class="sxs-lookup"><span data-stu-id="b8994-129">Child Elements</span></span>  
 <span data-ttu-id="b8994-130">なし</span><span class="sxs-lookup"><span data-stu-id="b8994-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b8994-131">親要素</span><span class="sxs-lookup"><span data-stu-id="b8994-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b8994-132">要素</span><span class="sxs-lookup"><span data-stu-id="b8994-132">Element</span></span>|<span data-ttu-id="b8994-133">説明</span><span class="sxs-lookup"><span data-stu-id="b8994-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8994-134">\<add></span><span class="sxs-lookup"><span data-stu-id="b8994-134">\<add></span></span>](add.md)|<span data-ttu-id="b8994-135">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="b8994-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b8994-136">例</span><span class="sxs-lookup"><span data-stu-id="b8994-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
