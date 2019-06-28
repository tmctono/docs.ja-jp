---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423024"
---
# <a name="certificatereference"></a><span data-ttu-id="26155-101">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="26155-101">\<certificateReference></span></span>
<span data-ttu-id="26155-102">検索して、証明書ストアに X.509 証明書の検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="26155-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="26155-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="26155-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="26155-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="26155-104">\<federationConfiguration></span></span>  
<span data-ttu-id="26155-105">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="26155-105">\<serviceCertificate></span></span>  
<span data-ttu-id="26155-106">\<certificateReference></span><span class="sxs-lookup"><span data-stu-id="26155-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26155-107">構文</span><span class="sxs-lookup"><span data-stu-id="26155-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26155-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="26155-108">Attributes and Elements</span></span>  
 <span data-ttu-id="26155-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="26155-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26155-110">属性</span><span class="sxs-lookup"><span data-stu-id="26155-110">Attributes</span></span>  
  
|<span data-ttu-id="26155-111">属性</span><span class="sxs-lookup"><span data-stu-id="26155-111">Attribute</span></span>|<span data-ttu-id="26155-112">説明</span><span class="sxs-lookup"><span data-stu-id="26155-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26155-113">storeName</span><span class="sxs-lookup"><span data-stu-id="26155-113">storeName</span></span>|<span data-ttu-id="26155-114">X.509 証明書ストアの名前。</span><span class="sxs-lookup"><span data-stu-id="26155-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="26155-115">既定値は"My"です。</span><span class="sxs-lookup"><span data-stu-id="26155-115">The default is "My".</span></span> <span data-ttu-id="26155-116">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26155-116">Optional.</span></span>|  
|<span data-ttu-id="26155-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="26155-117">storeLocation</span></span>|<span data-ttu-id="26155-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 証明書ストアの場所を指定する値。</span><span class="sxs-lookup"><span data-stu-id="26155-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="26155-119">既定値は、"LocalMachine"です。</span><span class="sxs-lookup"><span data-stu-id="26155-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="26155-120">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26155-120">Optional.</span></span>|  
|<span data-ttu-id="26155-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="26155-121">x509FindType</span></span>|<span data-ttu-id="26155-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType>を実行する検索の種類を指定する値。</span><span class="sxs-lookup"><span data-stu-id="26155-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="26155-123">既定値は、「findbysubjectdistinguishedname です」です。</span><span class="sxs-lookup"><span data-stu-id="26155-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="26155-124">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26155-124">Optional.</span></span>|  
|<span data-ttu-id="26155-125">findValue</span><span class="sxs-lookup"><span data-stu-id="26155-125">findValue</span></span>|<span data-ttu-id="26155-126">X.509 証明書ストアで検索する値。</span><span class="sxs-lookup"><span data-stu-id="26155-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="26155-127">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26155-127">Optional.</span></span>|  
|<span data-ttu-id="26155-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="26155-128">isChainIncluded</span></span>|<span data-ttu-id="26155-129">証明書チェーンを使用して検証を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="26155-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="26155-130">既定値は"true"になります。証明書チェーンを使用して検証します。</span><span class="sxs-lookup"><span data-stu-id="26155-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="26155-131">省略可能です。</span><span class="sxs-lookup"><span data-stu-id="26155-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26155-132">子要素</span><span class="sxs-lookup"><span data-stu-id="26155-132">Child Elements</span></span>  
 <span data-ttu-id="26155-133">なし</span><span class="sxs-lookup"><span data-stu-id="26155-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26155-134">親要素</span><span class="sxs-lookup"><span data-stu-id="26155-134">Parent Elements</span></span>  
  
|<span data-ttu-id="26155-135">要素</span><span class="sxs-lookup"><span data-stu-id="26155-135">Element</span></span>|<span data-ttu-id="26155-136">説明</span><span class="sxs-lookup"><span data-stu-id="26155-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26155-137">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="26155-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="26155-138">暗号化し、トークン暗号化解除に使用される証明書を構成します。</span><span class="sxs-lookup"><span data-stu-id="26155-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26155-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="26155-139">Remarks</span></span>  
 <span data-ttu-id="26155-140">`<certificateReference>`要素を検索し、証明書ストアに X.509 証明書の検証に使用される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="26155-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="26155-141">子要素として指定されている場合、`<serviceCertificate>`の暗号化し、トークン暗号化解除に使用される X.509 証明書の場所と検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="26155-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="26155-142">`<certificateReference>`要素が表される、<xref:System.ServiceModel.Configuration.CertificateReferenceElement>クラス。</span><span class="sxs-lookup"><span data-stu-id="26155-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
