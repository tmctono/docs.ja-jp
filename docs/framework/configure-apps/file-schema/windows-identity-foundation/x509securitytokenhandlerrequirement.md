---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152451"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="34c39-101">\<>の要件を満たしています。</span><span class="sxs-lookup"><span data-stu-id="34c39-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="34c39-102">クラスまたは派生クラスの<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>オプションの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="34c39-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="34c39-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="34c39-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="34c39-104">&nbsp;&nbsp;[**\<>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="34c39-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="34c39-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<id構成>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="34c39-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="34c39-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="34c39-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="34c39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>を追加する**](add.md)</span><span class="sxs-lookup"><span data-stu-id="34c39-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="34c39-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>の要件を満>**</span><span class="sxs-lookup"><span data-stu-id="34c39-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34c39-109">構文</span><span class="sxs-lookup"><span data-stu-id="34c39-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34c39-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="34c39-110">Attributes and Elements</span></span>  
 <span data-ttu-id="34c39-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="34c39-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34c39-112">属性</span><span class="sxs-lookup"><span data-stu-id="34c39-112">Attributes</span></span>  
  
|<span data-ttu-id="34c39-113">属性</span><span class="sxs-lookup"><span data-stu-id="34c39-113">Attribute</span></span>|<span data-ttu-id="34c39-114">説明</span><span class="sxs-lookup"><span data-stu-id="34c39-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34c39-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="34c39-115">certificateValidationMode</span></span>|<span data-ttu-id="34c39-116">X.509 証明書に使用する検証モードを指定する<xref:System.ServiceModel.Security.X509CertificateValidationMode>値。</span><span class="sxs-lookup"><span data-stu-id="34c39-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="34c39-117">既定値は"ピアオーチェーントラスト" です。</span><span class="sxs-lookup"><span data-stu-id="34c39-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="34c39-118">ウィンドウズにマップします。</span><span class="sxs-lookup"><span data-stu-id="34c39-118">mapToWindows</span></span>|<span data-ttu-id="34c39-119">トークン ハンドラーが、入力方向の UPN 要求を使用して検証トークンを Windows アカウントにマップするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="34c39-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="34c39-120">既定値は "false" です。</span><span class="sxs-lookup"><span data-stu-id="34c39-120">The default is "false".</span></span>|  
|<span data-ttu-id="34c39-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="34c39-121">revocationMode</span></span>|<span data-ttu-id="34c39-122">X.509 証明書に使用する失効モードを指定する<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>値。</span><span class="sxs-lookup"><span data-stu-id="34c39-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="34c39-123">デフォルト値は「オンライン」です。</span><span class="sxs-lookup"><span data-stu-id="34c39-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="34c39-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="34c39-124">trustedStoreLocation</span></span>|<span data-ttu-id="34c39-125">X.509 証明書ストアを指定する<xref:System.Security.Cryptography.X509Certificates.StoreLocation>値。</span><span class="sxs-lookup"><span data-stu-id="34c39-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="34c39-126">デフォルト値は「ローカルマシン」です。</span><span class="sxs-lookup"><span data-stu-id="34c39-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="34c39-127">証明書検証ツール</span><span class="sxs-lookup"><span data-stu-id="34c39-127">certificateValidator</span></span>|<span data-ttu-id="34c39-128">から<xref:System.IdentityModel.Selectors.X509CertificateValidator>派生するカスタム型。</span><span class="sxs-lookup"><span data-stu-id="34c39-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="34c39-129">属性が`certificateValidationMode`"カスタム" の場合、この型のインスタンスは発行者証明書の検証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="34c39-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34c39-130">子要素</span><span class="sxs-lookup"><span data-stu-id="34c39-130">Child Elements</span></span>  
 <span data-ttu-id="34c39-131">なし</span><span class="sxs-lookup"><span data-stu-id="34c39-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34c39-132">親要素</span><span class="sxs-lookup"><span data-stu-id="34c39-132">Parent Elements</span></span>  
  
|<span data-ttu-id="34c39-133">要素</span><span class="sxs-lookup"><span data-stu-id="34c39-133">Element</span></span>|<span data-ttu-id="34c39-134">説明</span><span class="sxs-lookup"><span data-stu-id="34c39-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34c39-135">\<>を追加する</span><span class="sxs-lookup"><span data-stu-id="34c39-135">\<add></span></span>](add.md)|<span data-ttu-id="34c39-136">指定したセキュリティ トークン ハンドラーをトークン ハンドラー コレクションに追加します。</span><span class="sxs-lookup"><span data-stu-id="34c39-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="34c39-137">例</span><span class="sxs-lookup"><span data-stu-id="34c39-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
