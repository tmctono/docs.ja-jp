---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941929"
---
# <a name="certificatereference"></a><span data-ttu-id="4fc82-101">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="4fc82-101">\<certificateReference></span></span>
<span data-ttu-id="4fc82-102">証明書ストアの x.509 証明書を検索して検証するために使用する設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc82-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="4fc82-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="4fc82-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="4fc82-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="4fc82-104">\<federationConfiguration></span></span>  
<span data-ttu-id="4fc82-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="4fc82-105">\<serviceCertificate></span></span>  
<span data-ttu-id="4fc82-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="4fc82-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc82-107">構文</span><span class="sxs-lookup"><span data-stu-id="4fc82-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fc82-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4fc82-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4fc82-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4fc82-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fc82-110">属性</span><span class="sxs-lookup"><span data-stu-id="4fc82-110">Attributes</span></span>  
  
|<span data-ttu-id="4fc82-111">属性</span><span class="sxs-lookup"><span data-stu-id="4fc82-111">Attribute</span></span>|<span data-ttu-id="4fc82-112">説明</span><span class="sxs-lookup"><span data-stu-id="4fc82-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4fc82-113">storeName</span><span class="sxs-lookup"><span data-stu-id="4fc82-113">storeName</span></span>|<span data-ttu-id="4fc82-114">X.509 証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="4fc82-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="4fc82-115">既定値は "My" です。</span><span class="sxs-lookup"><span data-stu-id="4fc82-115">The default is "My".</span></span> <span data-ttu-id="4fc82-116">任意。</span><span class="sxs-lookup"><span data-stu-id="4fc82-116">Optional.</span></span>|  
|<span data-ttu-id="4fc82-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="4fc82-117">storeLocation</span></span>|<span data-ttu-id="4fc82-118">X.509 証明書ストアの場所を示す値です。<xref:System.Security.Cryptography.X509Certificates.StoreLocation></span><span class="sxs-lookup"><span data-stu-id="4fc82-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="4fc82-119">既定値は "LocalMachine" です。</span><span class="sxs-lookup"><span data-stu-id="4fc82-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="4fc82-120">任意。</span><span class="sxs-lookup"><span data-stu-id="4fc82-120">Optional.</span></span>|  
|<span data-ttu-id="4fc82-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="4fc82-121">x509FindType</span></span>|<span data-ttu-id="4fc82-122">実行する検索の種類を示す値です。<xref:System.Security.Cryptography.X509Certificates.X509FindType></span><span class="sxs-lookup"><span data-stu-id="4fc82-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="4fc82-123">既定値は "Findbysubjectdistinguishedname です" です。</span><span class="sxs-lookup"><span data-stu-id="4fc82-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="4fc82-124">任意。</span><span class="sxs-lookup"><span data-stu-id="4fc82-124">Optional.</span></span>|  
|<span data-ttu-id="4fc82-125">findValue</span><span class="sxs-lookup"><span data-stu-id="4fc82-125">findValue</span></span>|<span data-ttu-id="4fc82-126">X.509 証明書ストアで検索する値。</span><span class="sxs-lookup"><span data-stu-id="4fc82-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="4fc82-127">任意。</span><span class="sxs-lookup"><span data-stu-id="4fc82-127">Optional.</span></span>|  
|<span data-ttu-id="4fc82-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="4fc82-128">isChainIncluded</span></span>|<span data-ttu-id="4fc82-129">証明書チェーンを使用して検証を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc82-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="4fc82-130">既定値は "true" です。検証は、証明書チェーンを使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="4fc82-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="4fc82-131">任意。</span><span class="sxs-lookup"><span data-stu-id="4fc82-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fc82-132">子要素</span><span class="sxs-lookup"><span data-stu-id="4fc82-132">Child Elements</span></span>  
 <span data-ttu-id="4fc82-133">なし</span><span class="sxs-lookup"><span data-stu-id="4fc82-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4fc82-134">親要素</span><span class="sxs-lookup"><span data-stu-id="4fc82-134">Parent Elements</span></span>  
  
|<span data-ttu-id="4fc82-135">要素</span><span class="sxs-lookup"><span data-stu-id="4fc82-135">Element</span></span>|<span data-ttu-id="4fc82-136">説明</span><span class="sxs-lookup"><span data-stu-id="4fc82-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4fc82-137">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="4fc82-137">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="4fc82-138">トークンの暗号化と復号化に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="4fc82-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4fc82-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="4fc82-139">Remarks</span></span>  
 <span data-ttu-id="4fc82-140">要素`<certificateReference>`は、証明書ストア内の x.509 証明書の検索と検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc82-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="4fc82-141">`<serviceCertificate>`要素の子要素として指定されている場合は、トークンの暗号化と復号化に使用される x.509 証明書の場所と検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="4fc82-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="4fc82-142">要素は、 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>クラスによって表されます。 `<certificateReference>`</span><span class="sxs-lookup"><span data-stu-id="4fc82-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
