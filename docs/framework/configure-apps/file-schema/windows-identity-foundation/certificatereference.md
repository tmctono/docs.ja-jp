---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152815"
---
# <a name="certificatereference"></a><span data-ttu-id="6d74e-101">\<証明書リファレンス></span><span class="sxs-lookup"><span data-stu-id="6d74e-101">\<certificateReference></span></span>
<span data-ttu-id="6d74e-102">証明書ストア内の X.509 証明書を検索および検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d74e-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="6d74e-103">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6d74e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6d74e-104">&nbsp;&nbsp;[**\<サービス>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="6d74e-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="6d74e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<フェデレーション構成>**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6d74e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="6d74e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<サービス証明書>**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="6d74e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="6d74e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<証明書参照>**</span><span class="sxs-lookup"><span data-stu-id="6d74e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d74e-108">構文</span><span class="sxs-lookup"><span data-stu-id="6d74e-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d74e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6d74e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6d74e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d74e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d74e-111">属性</span><span class="sxs-lookup"><span data-stu-id="6d74e-111">Attributes</span></span>  
  
|<span data-ttu-id="6d74e-112">属性</span><span class="sxs-lookup"><span data-stu-id="6d74e-112">Attribute</span></span>|<span data-ttu-id="6d74e-113">説明</span><span class="sxs-lookup"><span data-stu-id="6d74e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6d74e-114">storeName</span><span class="sxs-lookup"><span data-stu-id="6d74e-114">storeName</span></span>|<span data-ttu-id="6d74e-115">X.509 証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="6d74e-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="6d74e-116">デフォルトは "My" です。</span><span class="sxs-lookup"><span data-stu-id="6d74e-116">The default is "My".</span></span> <span data-ttu-id="6d74e-117">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6d74e-117">Optional.</span></span>|  
|<span data-ttu-id="6d74e-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="6d74e-118">storeLocation</span></span>|<span data-ttu-id="6d74e-119">X.509 証明書ストアの場所を指定する<xref:System.Security.Cryptography.X509Certificates.StoreLocation>値。</span><span class="sxs-lookup"><span data-stu-id="6d74e-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="6d74e-120">デフォルト値は「ローカルマシン」です。</span><span class="sxs-lookup"><span data-stu-id="6d74e-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="6d74e-121">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6d74e-121">Optional.</span></span>|  
|<span data-ttu-id="6d74e-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="6d74e-122">x509FindType</span></span>|<span data-ttu-id="6d74e-123">実行<xref:System.Security.Cryptography.X509Certificates.X509FindType>される検索の種類を指定する値。</span><span class="sxs-lookup"><span data-stu-id="6d74e-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="6d74e-124">デフォルトは「識別名を見つける」です。</span><span class="sxs-lookup"><span data-stu-id="6d74e-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="6d74e-125">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6d74e-125">Optional.</span></span>|  
|<span data-ttu-id="6d74e-126">findValue</span><span class="sxs-lookup"><span data-stu-id="6d74e-126">findValue</span></span>|<span data-ttu-id="6d74e-127">X.509 証明書ストアで検索する値。</span><span class="sxs-lookup"><span data-stu-id="6d74e-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="6d74e-128">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6d74e-128">Optional.</span></span>|  
|<span data-ttu-id="6d74e-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="6d74e-129">isChainIncluded</span></span>|<span data-ttu-id="6d74e-130">証明書チェーンを使用して検証を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6d74e-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="6d74e-131">デフォルトは "true" です。検証は、証明書チェーンを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="6d74e-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="6d74e-132">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6d74e-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6d74e-133">子要素</span><span class="sxs-lookup"><span data-stu-id="6d74e-133">Child Elements</span></span>  
 <span data-ttu-id="6d74e-134">なし</span><span class="sxs-lookup"><span data-stu-id="6d74e-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6d74e-135">親要素</span><span class="sxs-lookup"><span data-stu-id="6d74e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6d74e-136">要素</span><span class="sxs-lookup"><span data-stu-id="6d74e-136">Element</span></span>|<span data-ttu-id="6d74e-137">説明</span><span class="sxs-lookup"><span data-stu-id="6d74e-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6d74e-138">\<サービス証明書></span><span class="sxs-lookup"><span data-stu-id="6d74e-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="6d74e-139">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="6d74e-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d74e-140">解説</span><span class="sxs-lookup"><span data-stu-id="6d74e-140">Remarks</span></span>  
 <span data-ttu-id="6d74e-141">この`<certificateReference>`要素は、証明書ストア内の X.509 証明書を検索して検証するために使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d74e-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="6d74e-142">`<serviceCertificate>`要素の子要素として指定すると、トークンの暗号化と復号化に使用される X.509 証明書の場所と検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="6d74e-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="6d74e-143">要素`<certificateReference>`は<xref:System.ServiceModel.Configuration.CertificateReferenceElement>クラスによって表されます。</span><span class="sxs-lookup"><span data-stu-id="6d74e-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
