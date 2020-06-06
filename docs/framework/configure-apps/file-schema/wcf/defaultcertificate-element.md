---
title: <defaultCertificate> 要素
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400428"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="ae42b-102">\<defaultCertificate> 要素</span><span class="sxs-lookup"><span data-stu-id="ae42b-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="ae42b-103">ネゴシエーション プロトコル経由でサービスまたは STS が証明書を提供しないときに使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae42b-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="ae42b-104">構文</span><span class="sxs-lookup"><span data-stu-id="ae42b-104">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae42b-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ae42b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ae42b-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae42b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ae42b-107">属性</span><span class="sxs-lookup"><span data-stu-id="ae42b-107">Attributes</span></span>  
  
|<span data-ttu-id="ae42b-108">属性</span><span class="sxs-lookup"><span data-stu-id="ae42b-108">Attribute</span></span>|<span data-ttu-id="ae42b-109">説明</span><span class="sxs-lookup"><span data-stu-id="ae42b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ae42b-110">findValue</span><span class="sxs-lookup"><span data-stu-id="ae42b-110">findValue</span></span>|<span data-ttu-id="ae42b-111">文字列。</span><span class="sxs-lookup"><span data-stu-id="ae42b-111">String.</span></span> <span data-ttu-id="ae42b-112">検索する値。</span><span class="sxs-lookup"><span data-stu-id="ae42b-112">The value to search for.</span></span>|  
|<span data-ttu-id="ae42b-113">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ae42b-113">x509FindType</span></span>|<span data-ttu-id="ae42b-114">列挙値。</span><span class="sxs-lookup"><span data-stu-id="ae42b-114">Enumeration.</span></span> <span data-ttu-id="ae42b-115">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ae42b-115">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="ae42b-116">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ae42b-116">storeLocation</span></span>|<span data-ttu-id="ae42b-117">列挙値。</span><span class="sxs-lookup"><span data-stu-id="ae42b-117">Enumeration.</span></span> <span data-ttu-id="ae42b-118">検索する 2 つのシステム格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ae42b-118">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="ae42b-119">storeName</span><span class="sxs-lookup"><span data-stu-id="ae42b-119">storeName</span></span>|<span data-ttu-id="ae42b-120">列挙値。</span><span class="sxs-lookup"><span data-stu-id="ae42b-120">Enumeration.</span></span> <span data-ttu-id="ae42b-121">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="ae42b-121">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="ae42b-122">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="ae42b-122">findValue Attribute</span></span>  
  
|<span data-ttu-id="ae42b-123">値</span><span class="sxs-lookup"><span data-stu-id="ae42b-123">Value</span></span>|<span data-ttu-id="ae42b-124">説明</span><span class="sxs-lookup"><span data-stu-id="ae42b-124">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae42b-125">String</span><span class="sxs-lookup"><span data-stu-id="ae42b-125">String</span></span>|<span data-ttu-id="ae42b-126">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ae42b-126">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="ae42b-127">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae42b-127">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="ae42b-128">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="ae42b-128">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="ae42b-129">値</span><span class="sxs-lookup"><span data-stu-id="ae42b-129">Value</span></span>|<span data-ttu-id="ae42b-130">Description</span><span class="sxs-lookup"><span data-stu-id="ae42b-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae42b-131">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ae42b-131">Enumeration</span></span>|<span data-ttu-id="ae42b-132">値は、FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage、FindBySubjectKeyIdentifier です。</span><span class="sxs-lookup"><span data-stu-id="ae42b-132">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="ae42b-133">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="ae42b-133">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="ae42b-134">値</span><span class="sxs-lookup"><span data-stu-id="ae42b-134">Value</span></span>|<span data-ttu-id="ae42b-135">Description</span><span class="sxs-lookup"><span data-stu-id="ae42b-135">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae42b-136">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ae42b-136">Enumeration</span></span>|<span data-ttu-id="ae42b-137">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="ae42b-137">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="ae42b-138">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="ae42b-138">storeName Attribute</span></span>  
  
|<span data-ttu-id="ae42b-139">値</span><span class="sxs-lookup"><span data-stu-id="ae42b-139">Value</span></span>|<span data-ttu-id="ae42b-140">Description</span><span class="sxs-lookup"><span data-stu-id="ae42b-140">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ae42b-141">Enumeration</span><span class="sxs-lookup"><span data-stu-id="ae42b-141">Enumeration</span></span>|<span data-ttu-id="ae42b-142">値は、AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople、および TrustedPublisher です。</span><span class="sxs-lookup"><span data-stu-id="ae42b-142">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae42b-143">子要素</span><span class="sxs-lookup"><span data-stu-id="ae42b-143">Child Elements</span></span>  
 <span data-ttu-id="ae42b-144">なし。</span><span class="sxs-lookup"><span data-stu-id="ae42b-144">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ae42b-145">親要素</span><span class="sxs-lookup"><span data-stu-id="ae42b-145">Parent Elements</span></span>  
  
|<span data-ttu-id="ae42b-146">要素</span><span class="sxs-lookup"><span data-stu-id="ae42b-146">Element</span></span>|<span data-ttu-id="ae42b-147">Description</span><span class="sxs-lookup"><span data-stu-id="ae42b-147">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCertificate>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="ae42b-148">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae42b-148">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae42b-149">解説</span><span class="sxs-lookup"><span data-stu-id="ae42b-149">Remarks</span></span>  
 <span data-ttu-id="ae42b-150">証明書ベースのメッセージ セキュリティを使用するバインディングでは、この構成要素で指定された証明書を使用して、サービスへのメッセージが暗号化されます。この証明書は、サービスがクライアントへの応答に署名するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae42b-150">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="ae42b-151">この要素には、サービスで証明書が指定されていないときに使用する証明書を 1 つ格納できます。</span><span class="sxs-lookup"><span data-stu-id="ae42b-151">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae42b-152">例</span><span class="sxs-lookup"><span data-stu-id="ae42b-152">Example</span></span>  
 <span data-ttu-id="ae42b-153">次の例では、URI がで始まるエンドポイントに使用する証明書 `http://www.contoso.com` と、証明書ネゴシエーションを実行しない他のすべてのエンドポイントに使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="ae42b-153">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
```xml  
<serviceCertificate>
  <defaultCertificate findValue="www.contoso.com"
                      storeLocation="LocalMachine"
                      storeName="TrustedPeople"
                      x509FindType="FindByIssuerDistinguishedName" />
  <scopedCertificates>
    <add targetUri="http://www.contoso.com"
         findValue="www.contoso.com"
         storeLocation="LocalMachine"
         storeName="Root"
         x509FindType="FindByIssuerName" />
  </scopedCertificates>
  <authentication revocationMode="Online"
                  trustedStoreLocation="LocalMachine" />
</serviceCertificate>
```  
  
## <a name="see-also"></a><span data-ttu-id="ae42b-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae42b-154">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="ae42b-155">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="ae42b-155">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [\<authentication>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="ae42b-156">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ae42b-156">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="ae42b-157">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="ae42b-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
