---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: a6a8185297e1345de9fa20c7d4d0dffbdcd8620f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185393"
---
# \<x509SecurityTokenHandlerRequirement>

<span data-ttu-id="e90f9-101">クラスまたは派生クラスのオプションの構成を提供 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> します。</span><span class="sxs-lookup"><span data-stu-id="e90f9-101">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**  
  
## <a name="syntax"></a><span data-ttu-id="e90f9-102">構文</span><span class="sxs-lookup"><span data-stu-id="e90f9-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e90f9-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e90f9-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e90f9-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e90f9-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e90f9-105">属性</span><span class="sxs-lookup"><span data-stu-id="e90f9-105">Attributes</span></span>  
  
|<span data-ttu-id="e90f9-106">属性</span><span class="sxs-lookup"><span data-stu-id="e90f9-106">Attribute</span></span>|<span data-ttu-id="e90f9-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="e90f9-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e90f9-108">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="e90f9-108">certificateValidationMode</span></span>|<span data-ttu-id="e90f9-109"><xref:System.ServiceModel.Security.X509CertificateValidationMode>X.509 証明書に使用する検証モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="e90f9-109">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e90f9-110">既定値は "PeerOrChainTrust" です。</span><span class="sxs-lookup"><span data-stu-id="e90f9-110">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="e90f9-111">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="e90f9-111">mapToWindows</span></span>|<span data-ttu-id="e90f9-112">受信 UPN 要求を使用して、トークンハンドラーが検証トークンを Windows アカウントにマップする必要があるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e90f9-112">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="e90f9-113">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="e90f9-113">The default is "false".</span></span>|  
|<span data-ttu-id="e90f9-114">revocationMode</span><span class="sxs-lookup"><span data-stu-id="e90f9-114">revocationMode</span></span>|<span data-ttu-id="e90f9-115"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>X.509 証明書に使用する失効モードを指定する値。</span><span class="sxs-lookup"><span data-stu-id="e90f9-115">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="e90f9-116">既定値は "Online" です。</span><span class="sxs-lookup"><span data-stu-id="e90f9-116">The default value is "Online".</span></span>|  
|<span data-ttu-id="e90f9-117">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="e90f9-117">trustedStoreLocation</span></span>|<span data-ttu-id="e90f9-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 証明書ストアを示す値です。</span><span class="sxs-lookup"><span data-stu-id="e90f9-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="e90f9-119">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="e90f9-119">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="e90f9-120">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="e90f9-120">certificateValidator</span></span>|<span data-ttu-id="e90f9-121">から派生するカスタム型 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 。</span><span class="sxs-lookup"><span data-stu-id="e90f9-121">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="e90f9-122">`certificateValidationMode`属性が "Custom" の場合、この型のインスタンスは発行者の証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e90f9-122">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e90f9-123">子要素</span><span class="sxs-lookup"><span data-stu-id="e90f9-123">Child Elements</span></span>  

 <span data-ttu-id="e90f9-124">None</span><span class="sxs-lookup"><span data-stu-id="e90f9-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e90f9-125">親要素</span><span class="sxs-lookup"><span data-stu-id="e90f9-125">Parent Elements</span></span>  
  
|<span data-ttu-id="e90f9-126">要素</span><span class="sxs-lookup"><span data-stu-id="e90f9-126">Element</span></span>|<span data-ttu-id="e90f9-127">説明</span><span class="sxs-lookup"><span data-stu-id="e90f9-127">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add.md)|<span data-ttu-id="e90f9-128">指定されたセキュリティトークンハンドラーをトークンハンドラーコレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="e90f9-128">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e90f9-129">例</span><span class="sxs-lookup"><span data-stu-id="e90f9-129">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
