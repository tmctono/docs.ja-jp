---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c21e5186b8afdf8c72cbfc605af94c95bc2bc0d5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201379"
---
# \<certificateReference>

<span data-ttu-id="0e1a4-101">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-101">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**  
  
## <a name="syntax"></a><span data-ttu-id="0e1a4-102">構文</span><span class="sxs-lookup"><span data-stu-id="0e1a4-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e1a4-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="0e1a4-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0e1a4-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e1a4-105">属性</span><span class="sxs-lookup"><span data-stu-id="0e1a4-105">Attributes</span></span>  
  
|<span data-ttu-id="0e1a4-106">属性</span><span class="sxs-lookup"><span data-stu-id="0e1a4-106">Attribute</span></span>|<span data-ttu-id="0e1a4-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="0e1a4-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0e1a4-108">storeName</span><span class="sxs-lookup"><span data-stu-id="0e1a4-108">storeName</span></span>|<span data-ttu-id="0e1a4-109">X.509 証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-109">The name of the X.509 certificate store.</span></span> <span data-ttu-id="0e1a4-110">既定値は "My" です。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-110">The default is "My".</span></span> <span data-ttu-id="0e1a4-111">省略可能。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-111">Optional.</span></span>|  
|<span data-ttu-id="0e1a4-112">storeLocation</span><span class="sxs-lookup"><span data-stu-id="0e1a4-112">storeLocation</span></span>|<span data-ttu-id="0e1a4-113"><xref:System.Security.Cryptography.X509Certificates.StoreLocation>X.509 証明書ストアの場所を示す値です。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-113">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="0e1a4-114">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-114">The default value is "LocalMachine".</span></span> <span data-ttu-id="0e1a4-115">省略可能。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-115">Optional.</span></span>|  
|<span data-ttu-id="0e1a4-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="0e1a4-116">x509FindType</span></span>|<span data-ttu-id="0e1a4-117"><xref:System.Security.Cryptography.X509Certificates.X509FindType>実行する検索の種類を示す値です。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-117">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="0e1a4-118">既定値は "Findbysubjectdistinguishedname です" です。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-118">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="0e1a4-119">省略可能。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-119">Optional.</span></span>|  
|<span data-ttu-id="0e1a4-120">findValue</span><span class="sxs-lookup"><span data-stu-id="0e1a4-120">findValue</span></span>|<span data-ttu-id="0e1a4-121">X.509 証明書ストアで検索する値。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-121">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="0e1a4-122">省略可能。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-122">Optional.</span></span>|  
|<span data-ttu-id="0e1a4-123">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="0e1a4-123">isChainIncluded</span></span>|<span data-ttu-id="0e1a4-124">証明書チェーンを使用して検証を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-124">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="0e1a4-125">既定値は "true" です。検証は、証明書チェーンを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-125">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="0e1a4-126">省略可能。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e1a4-127">子要素</span><span class="sxs-lookup"><span data-stu-id="0e1a4-127">Child Elements</span></span>  

 <span data-ttu-id="0e1a4-128">None</span><span class="sxs-lookup"><span data-stu-id="0e1a4-128">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e1a4-129">親要素</span><span class="sxs-lookup"><span data-stu-id="0e1a4-129">Parent Elements</span></span>  
  
|<span data-ttu-id="0e1a4-130">要素</span><span class="sxs-lookup"><span data-stu-id="0e1a4-130">Element</span></span>|<span data-ttu-id="0e1a4-131">説明</span><span class="sxs-lookup"><span data-stu-id="0e1a4-131">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate.md)|<span data-ttu-id="0e1a4-132">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-132">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e1a4-133">解説</span><span class="sxs-lookup"><span data-stu-id="0e1a4-133">Remarks</span></span>  

 <span data-ttu-id="0e1a4-134">要素は、 `<certificateReference>` 証明書ストア内の x.509 証明書の検索と検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-134">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="0e1a4-135">要素の子要素として指定されている場合は、 `<serviceCertificate>` トークンの暗号化と復号化に使用される x.509 証明書の場所と検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-135">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="0e1a4-136">`<certificateReference>`要素は、クラスによって表され <xref:System.ServiceModel.Configuration.CertificateReferenceElement> ます。</span><span class="sxs-lookup"><span data-stu-id="0e1a4-136">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
