---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152815"
---
# \<certificateReference>
<span data-ttu-id="1612f-101">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1612f-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="1612f-102">構文</span><span class="sxs-lookup"><span data-stu-id="1612f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1612f-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1612f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="1612f-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1612f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1612f-105">属性</span><span class="sxs-lookup"><span data-stu-id="1612f-105">Attributes</span></span>  
  
|<span data-ttu-id="1612f-106">属性</span><span class="sxs-lookup"><span data-stu-id="1612f-106">Attribute</span></span>|<span data-ttu-id="1612f-107">説明</span><span class="sxs-lookup"><span data-stu-id="1612f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1612f-108">storeName</span><span class="sxs-lookup"><span data-stu-id="1612f-108">storeName</span></span>|<span data-ttu-id="1612f-109">X.509 証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="1612f-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="1612f-110">既定値は "My" です。</span><span class="sxs-lookup"><span data-stu-id="1612f-110">The default is "My".</span></span> <span data-ttu-id="1612f-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1612f-111">Optional.</span></span>|  
|<span data-ttu-id="1612f-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="1612f-112">storeLocation</span></span>|<span data-ttu-id="1612f-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 証明書ストアの場所を示す値です。</span><span class="sxs-lookup"><span data-stu-id="1612f-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="1612f-114">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="1612f-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="1612f-115">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1612f-115">Optional.</span></span>|  
|<span data-ttu-id="1612f-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="1612f-116">x509FindType</span></span>|<span data-ttu-id="1612f-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>実行する検索の種類を示す値です。</span><span class="sxs-lookup"><span data-stu-id="1612f-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="1612f-118">既定値は "Findbysubjectdistinguishedname です" です。</span><span class="sxs-lookup"><span data-stu-id="1612f-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="1612f-119">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1612f-119">Optional.</span></span>|  
|<span data-ttu-id="1612f-120">findValue</span><span class="sxs-lookup"><span data-stu-id="1612f-120">findValue</span></span>|<span data-ttu-id="1612f-121">X.509 証明書ストアで検索する値。</span><span class="sxs-lookup"><span data-stu-id="1612f-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1612f-122">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1612f-122">Optional.</span></span>|  
|<span data-ttu-id="1612f-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="1612f-123">isChainIncluded</span></span>|<span data-ttu-id="1612f-124">証明書チェーンを使用して検証を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1612f-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="1612f-125">既定値は "true" です。検証は、証明書チェーンを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="1612f-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="1612f-126">省略可能。</span><span class="sxs-lookup"><span data-stu-id="1612f-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1612f-127">子要素</span><span class="sxs-lookup"><span data-stu-id="1612f-127">Child Elements</span></span>  
 <span data-ttu-id="1612f-128">なし</span><span class="sxs-lookup"><span data-stu-id="1612f-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1612f-129">親要素</span><span class="sxs-lookup"><span data-stu-id="1612f-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1612f-130">要素</span><span class="sxs-lookup"><span data-stu-id="1612f-130">Element</span></span>|<span data-ttu-id="1612f-131">Description</span><span class="sxs-lookup"><span data-stu-id="1612f-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="1612f-132">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="1612f-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1612f-133">解説</span><span class="sxs-lookup"><span data-stu-id="1612f-133">Remarks</span></span>  
 <span data-ttu-id="1612f-134">要素は、 `<certificateReference>` 証明書ストア内の x.509 証明書の検索と検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1612f-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="1612f-135">要素の子要素として指定されている場合は、 `<serviceCertificate>` トークンの暗号化と復号化に使用される x.509 証明書の場所と検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="1612f-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="1612f-136">`<certificateReference>`要素は、クラスによって表され <xref:System.ServiceModel.Configuration.CertificateReferenceElement> ます。</span><span class="sxs-lookup"><span data-stu-id="1612f-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
