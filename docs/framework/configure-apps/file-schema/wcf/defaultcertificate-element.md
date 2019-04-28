---
title: <defaultCertificate> 要素
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: c94531d10b7c0ef5ca0ee1f2d5683d0a259a2537
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644462"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="93af4-102">\<defaultCertificate > 要素</span><span class="sxs-lookup"><span data-stu-id="93af4-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="93af4-103">ネゴシエーション プロトコル経由でサービスまたは STS が証明書を提供しないときに使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="93af4-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
 <span data-ttu-id="93af4-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="93af4-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="93af4-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="93af4-105">\<behaviors></span></span>  
<span data-ttu-id="93af4-106">endpointBehaviors セクション</span><span class="sxs-lookup"><span data-stu-id="93af4-106">endpointBehaviors section</span></span>  
<span data-ttu-id="93af4-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="93af4-107">\<behavior></span></span>  
<span data-ttu-id="93af4-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="93af4-108">\<clientCredentials></span></span>  
<span data-ttu-id="93af4-109">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="93af4-109">\<serviceCertificate></span></span>  
<span data-ttu-id="93af4-110">\<defaultCertificate></span><span class="sxs-lookup"><span data-stu-id="93af4-110">\<defaultCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93af4-111">構文</span><span class="sxs-lookup"><span data-stu-id="93af4-111">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93af4-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="93af4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="93af4-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="93af4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93af4-114">属性</span><span class="sxs-lookup"><span data-stu-id="93af4-114">Attributes</span></span>  
  
|<span data-ttu-id="93af4-115">属性</span><span class="sxs-lookup"><span data-stu-id="93af4-115">Attribute</span></span>|<span data-ttu-id="93af4-116">説明</span><span class="sxs-lookup"><span data-stu-id="93af4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93af4-117">findValue</span><span class="sxs-lookup"><span data-stu-id="93af4-117">findValue</span></span>|<span data-ttu-id="93af4-118">文字列。</span><span class="sxs-lookup"><span data-stu-id="93af4-118">String.</span></span> <span data-ttu-id="93af4-119">検索対象の値。</span><span class="sxs-lookup"><span data-stu-id="93af4-119">The value to search for.</span></span>|  
|<span data-ttu-id="93af4-120">x509FindType</span><span class="sxs-lookup"><span data-stu-id="93af4-120">x509FindType</span></span>|<span data-ttu-id="93af4-121">列挙値。</span><span class="sxs-lookup"><span data-stu-id="93af4-121">Enumeration.</span></span> <span data-ttu-id="93af4-122">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="93af4-122">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="93af4-123">storeLocation</span><span class="sxs-lookup"><span data-stu-id="93af4-123">storeLocation</span></span>|<span data-ttu-id="93af4-124">列挙値。</span><span class="sxs-lookup"><span data-stu-id="93af4-124">Enumeration.</span></span> <span data-ttu-id="93af4-125">検索する 2 つのシステム格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="93af4-125">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="93af4-126">storeName</span><span class="sxs-lookup"><span data-stu-id="93af4-126">storeName</span></span>|<span data-ttu-id="93af4-127">列挙値。</span><span class="sxs-lookup"><span data-stu-id="93af4-127">Enumeration.</span></span> <span data-ttu-id="93af4-128">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="93af4-128">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="93af4-129">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="93af4-129">findValue Attribute</span></span>  
  
|<span data-ttu-id="93af4-130">値</span><span class="sxs-lookup"><span data-stu-id="93af4-130">Value</span></span>|<span data-ttu-id="93af4-131">説明</span><span class="sxs-lookup"><span data-stu-id="93af4-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93af4-132">String</span><span class="sxs-lookup"><span data-stu-id="93af4-132">String</span></span>|<span data-ttu-id="93af4-133">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="93af4-133">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="93af4-134">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93af4-134">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="93af4-135">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="93af4-135">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="93af4-136">値</span><span class="sxs-lookup"><span data-stu-id="93af4-136">Value</span></span>|<span data-ttu-id="93af4-137">説明</span><span class="sxs-lookup"><span data-stu-id="93af4-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93af4-138">列挙</span><span class="sxs-lookup"><span data-stu-id="93af4-138">Enumeration</span></span>|<span data-ttu-id="93af4-139">次の値が含まれます。FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage、findbysubjectkeyidentifier です。</span><span class="sxs-lookup"><span data-stu-id="93af4-139">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="93af4-140">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="93af4-140">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="93af4-141">値</span><span class="sxs-lookup"><span data-stu-id="93af4-141">Value</span></span>|<span data-ttu-id="93af4-142">説明</span><span class="sxs-lookup"><span data-stu-id="93af4-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93af4-143">列挙型</span><span class="sxs-lookup"><span data-stu-id="93af4-143">Enumeration</span></span>|<span data-ttu-id="93af4-144">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="93af4-144">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="93af4-145">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="93af4-145">storeName Attribute</span></span>  
  
|<span data-ttu-id="93af4-146">値</span><span class="sxs-lookup"><span data-stu-id="93af4-146">Value</span></span>|<span data-ttu-id="93af4-147">説明</span><span class="sxs-lookup"><span data-stu-id="93af4-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="93af4-148">列挙</span><span class="sxs-lookup"><span data-stu-id="93af4-148">Enumeration</span></span>|<span data-ttu-id="93af4-149">次の値が含まれます。AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople、および TrustedPublisher です。</span><span class="sxs-lookup"><span data-stu-id="93af4-149">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93af4-150">子要素</span><span class="sxs-lookup"><span data-stu-id="93af4-150">Child Elements</span></span>  
 <span data-ttu-id="93af4-151">なし。</span><span class="sxs-lookup"><span data-stu-id="93af4-151">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93af4-152">親要素</span><span class="sxs-lookup"><span data-stu-id="93af4-152">Parent Elements</span></span>  
  
|<span data-ttu-id="93af4-153">要素</span><span class="sxs-lookup"><span data-stu-id="93af4-153">Element</span></span>|<span data-ttu-id="93af4-154">説明</span><span class="sxs-lookup"><span data-stu-id="93af4-154">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="93af4-155">\<serviceCertificate></span><span class="sxs-lookup"><span data-stu-id="93af4-155">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="93af4-156">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="93af4-156">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93af4-157">Remarks</span><span class="sxs-lookup"><span data-stu-id="93af4-157">Remarks</span></span>  
 <span data-ttu-id="93af4-158">証明書ベースのメッセージ セキュリティを使用するバインディングでは、この構成要素で指定された証明書を使用して、サービスへのメッセージが暗号化されます。この証明書は、サービスがクライアントへの応答に署名するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="93af4-158">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="93af4-159">この要素には、サービスで証明書が指定されていないときに使用する証明書を 1 つ格納できます。</span><span class="sxs-lookup"><span data-stu-id="93af4-159">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93af4-160">例</span><span class="sxs-lookup"><span data-stu-id="93af4-160">Example</span></span>  
 <span data-ttu-id="93af4-161">次の例の URI が始まるエンドポイントに対して使用する証明書を指定する`http://www.contoso.com`と証明書ネゴシエーションを実行しない他のすべてのエンドポイントに使用する証明書。</span><span class="sxs-lookup"><span data-stu-id="93af4-161">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="93af4-162">関連項目</span><span class="sxs-lookup"><span data-stu-id="93af4-162">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="93af4-163">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="93af4-163">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="93af4-164">\<authentication></span><span class="sxs-lookup"><span data-stu-id="93af4-164">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="93af4-165">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="93af4-165">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="93af4-166">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="93af4-166">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
