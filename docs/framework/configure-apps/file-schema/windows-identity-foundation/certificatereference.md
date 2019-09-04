---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252141"
---
# <a name="certificatereference"></a><span data-ttu-id="f42d1-101">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="f42d1-101">\<certificateReference></span></span>
<span data-ttu-id="f42d1-102">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f42d1-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="f42d1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f42d1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f42d1-104">&nbsp;&nbsp;[ **\<> のシステム**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="f42d1-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="f42d1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f42d1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="f42d1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="f42d1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="f42d1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateReference >**</span><span class="sxs-lookup"><span data-stu-id="f42d1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f42d1-108">構文</span><span class="sxs-lookup"><span data-stu-id="f42d1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f42d1-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f42d1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f42d1-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f42d1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f42d1-111">属性</span><span class="sxs-lookup"><span data-stu-id="f42d1-111">Attributes</span></span>  
  
|<span data-ttu-id="f42d1-112">属性</span><span class="sxs-lookup"><span data-stu-id="f42d1-112">Attribute</span></span>|<span data-ttu-id="f42d1-113">説明</span><span class="sxs-lookup"><span data-stu-id="f42d1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f42d1-114">storeName</span><span class="sxs-lookup"><span data-stu-id="f42d1-114">storeName</span></span>|<span data-ttu-id="f42d1-115">X.509 証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="f42d1-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="f42d1-116">既定値は "My" です。</span><span class="sxs-lookup"><span data-stu-id="f42d1-116">The default is "My".</span></span> <span data-ttu-id="f42d1-117">任意。</span><span class="sxs-lookup"><span data-stu-id="f42d1-117">Optional.</span></span>|  
|<span data-ttu-id="f42d1-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="f42d1-118">storeLocation</span></span>|<span data-ttu-id="f42d1-119">X.509 証明書ストアの場所を示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="f42d1-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="f42d1-120">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="f42d1-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="f42d1-121">任意。</span><span class="sxs-lookup"><span data-stu-id="f42d1-121">Optional.</span></span>|  
|<span data-ttu-id="f42d1-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="f42d1-122">x509FindType</span></span>|<span data-ttu-id="f42d1-123">実行する検索の種類を示す値です。<xref:System.Security.Cryptography.X509Certificates.X509FindType></span><span class="sxs-lookup"><span data-stu-id="f42d1-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="f42d1-124">既定値は "Findbysubjectdistinguishedname です" です。</span><span class="sxs-lookup"><span data-stu-id="f42d1-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="f42d1-125">任意。</span><span class="sxs-lookup"><span data-stu-id="f42d1-125">Optional.</span></span>|  
|<span data-ttu-id="f42d1-126">findValue</span><span class="sxs-lookup"><span data-stu-id="f42d1-126">findValue</span></span>|<span data-ttu-id="f42d1-127">X.509 証明書ストアで検索する値。</span><span class="sxs-lookup"><span data-stu-id="f42d1-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f42d1-128">任意。</span><span class="sxs-lookup"><span data-stu-id="f42d1-128">Optional.</span></span>|  
|<span data-ttu-id="f42d1-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="f42d1-129">isChainIncluded</span></span>|<span data-ttu-id="f42d1-130">証明書チェーンを使用して検証を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f42d1-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="f42d1-131">既定値は "true" です。検証は、証明書チェーンを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="f42d1-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="f42d1-132">任意。</span><span class="sxs-lookup"><span data-stu-id="f42d1-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f42d1-133">子要素</span><span class="sxs-lookup"><span data-stu-id="f42d1-133">Child Elements</span></span>  
 <span data-ttu-id="f42d1-134">なし</span><span class="sxs-lookup"><span data-stu-id="f42d1-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f42d1-135">親要素</span><span class="sxs-lookup"><span data-stu-id="f42d1-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f42d1-136">要素</span><span class="sxs-lookup"><span data-stu-id="f42d1-136">Element</span></span>|<span data-ttu-id="f42d1-137">説明</span><span class="sxs-lookup"><span data-stu-id="f42d1-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f42d1-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="f42d1-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="f42d1-139">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="f42d1-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f42d1-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="f42d1-140">Remarks</span></span>  
 <span data-ttu-id="f42d1-141">要素`<certificateReference>`は、証明書ストア内の x.509 証明書の検索と検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f42d1-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="f42d1-142">`<serviceCertificate>`要素の子要素として指定されている場合は、トークンの暗号化と復号化に使用される x.509 証明書の場所と検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f42d1-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="f42d1-143">要素は、 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>クラスによって表されます。 `<certificateReference>`</span><span class="sxs-lookup"><span data-stu-id="f42d1-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
