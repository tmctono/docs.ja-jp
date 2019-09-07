---
title: <defaultCertificate> 要素
ms.date: 03/30/2017
ms.assetid: f1ddf364-9a00-45d3-b989-ff381c154ce6
ms.openlocfilehash: cce236bf80fa00f01a3b5f4680d975f83fde0c16
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400428"
---
# <a name="defaultcertificate-element"></a><span data-ttu-id="43036-102">\<defaultCertificate > 要素</span><span class="sxs-lookup"><span data-stu-id="43036-102">\<defaultCertificate> Element</span></span>
<span data-ttu-id="43036-103">ネゴシエーション プロトコル経由でサービスまたは STS が証明書を提供しないときに使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="43036-103">Specifies an X.509 certificate to be used when a service or STS does not provide one via a negotiation protocol.</span></span>  
  
<span data-ttu-id="43036-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43036-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43036-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="43036-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="43036-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="43036-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="43036-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="43036-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="43036-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="43036-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="43036-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="43036-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="43036-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="43036-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="43036-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<defaultCertificate >**</span><span class="sxs-lookup"><span data-stu-id="43036-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<defaultCertificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43036-112">構文</span><span class="sxs-lookup"><span data-stu-id="43036-112">Syntax</span></span>  
  
```xml  
<defaultCertificate findValue="String"
                    storeLocation=" CurrentUser/LocalMachine"
                    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                    x509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialiNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43036-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="43036-113">Attributes and Elements</span></span>  
 <span data-ttu-id="43036-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="43036-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43036-115">属性</span><span class="sxs-lookup"><span data-stu-id="43036-115">Attributes</span></span>  
  
|<span data-ttu-id="43036-116">属性</span><span class="sxs-lookup"><span data-stu-id="43036-116">Attribute</span></span>|<span data-ttu-id="43036-117">説明</span><span class="sxs-lookup"><span data-stu-id="43036-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43036-118">findValue</span><span class="sxs-lookup"><span data-stu-id="43036-118">findValue</span></span>|<span data-ttu-id="43036-119">文字列。</span><span class="sxs-lookup"><span data-stu-id="43036-119">String.</span></span> <span data-ttu-id="43036-120">検索対象の値。</span><span class="sxs-lookup"><span data-stu-id="43036-120">The value to search for.</span></span>|  
|<span data-ttu-id="43036-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="43036-121">x509FindType</span></span>|<span data-ttu-id="43036-122">列挙値。</span><span class="sxs-lookup"><span data-stu-id="43036-122">Enumeration.</span></span> <span data-ttu-id="43036-123">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="43036-123">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="43036-124">storeLocation</span><span class="sxs-lookup"><span data-stu-id="43036-124">storeLocation</span></span>|<span data-ttu-id="43036-125">列挙値。</span><span class="sxs-lookup"><span data-stu-id="43036-125">Enumeration.</span></span> <span data-ttu-id="43036-126">検索する 2 つのシステム格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="43036-126">One of the two system store locations to search.</span></span>|  
|<span data-ttu-id="43036-127">storeName</span><span class="sxs-lookup"><span data-stu-id="43036-127">storeName</span></span>|<span data-ttu-id="43036-128">列挙値。</span><span class="sxs-lookup"><span data-stu-id="43036-128">Enumeration.</span></span> <span data-ttu-id="43036-129">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="43036-129">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="43036-130">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="43036-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="43036-131">値</span><span class="sxs-lookup"><span data-stu-id="43036-131">Value</span></span>|<span data-ttu-id="43036-132">説明</span><span class="sxs-lookup"><span data-stu-id="43036-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="43036-133">String</span><span class="sxs-lookup"><span data-stu-id="43036-133">String</span></span>|<span data-ttu-id="43036-134">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="43036-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="43036-135">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43036-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="43036-136">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="43036-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="43036-137">値</span><span class="sxs-lookup"><span data-stu-id="43036-137">Value</span></span>|<span data-ttu-id="43036-138">説明</span><span class="sxs-lookup"><span data-stu-id="43036-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="43036-139">列挙</span><span class="sxs-lookup"><span data-stu-id="43036-139">Enumeration</span></span>|<span data-ttu-id="43036-140">次の値が含まれます。FindByThumbprint、FindBySubjectName、Findbysubjectdistinguishedname です、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="43036-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="43036-141">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="43036-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="43036-142">値</span><span class="sxs-lookup"><span data-stu-id="43036-142">Value</span></span>|<span data-ttu-id="43036-143">説明</span><span class="sxs-lookup"><span data-stu-id="43036-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="43036-144">列挙型</span><span class="sxs-lookup"><span data-stu-id="43036-144">Enumeration</span></span>|<span data-ttu-id="43036-145">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="43036-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="43036-146">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="43036-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="43036-147">値</span><span class="sxs-lookup"><span data-stu-id="43036-147">Value</span></span>|<span data-ttu-id="43036-148">説明</span><span class="sxs-lookup"><span data-stu-id="43036-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="43036-149">列挙</span><span class="sxs-lookup"><span data-stu-id="43036-149">Enumeration</span></span>|<span data-ttu-id="43036-150">次の値が含まれます。アドレス帳、AuthRoot、CertificateAuthority、許可されていない、My、Root、TrustedPeople、Trustedpeople。</span><span class="sxs-lookup"><span data-stu-id="43036-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43036-151">子要素</span><span class="sxs-lookup"><span data-stu-id="43036-151">Child Elements</span></span>  
 <span data-ttu-id="43036-152">なし。</span><span class="sxs-lookup"><span data-stu-id="43036-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43036-153">親要素</span><span class="sxs-lookup"><span data-stu-id="43036-153">Parent Elements</span></span>  
  
|<span data-ttu-id="43036-154">要素</span><span class="sxs-lookup"><span data-stu-id="43036-154">Element</span></span>|<span data-ttu-id="43036-155">説明</span><span class="sxs-lookup"><span data-stu-id="43036-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43036-156">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="43036-156">\<serviceCertificate></span></span>](servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="43036-157">クライアントに対してサービスを認証する際に使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="43036-157">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43036-158">Remarks</span><span class="sxs-lookup"><span data-stu-id="43036-158">Remarks</span></span>  
 <span data-ttu-id="43036-159">証明書ベースのメッセージ セキュリティを使用するバインディングでは、この構成要素で指定された証明書を使用して、サービスへのメッセージが暗号化されます。この証明書は、サービスがクライアントへの応答に署名するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="43036-159">For bindings that use certificate-based message security, certificate specified by this configuration element is used to encrypt messages to the service and is expected to be used by the service for signing replies to the client.</span></span> <span data-ttu-id="43036-160">この要素には、サービスで証明書が指定されていないときに使用する証明書を 1 つ格納できます。</span><span class="sxs-lookup"><span data-stu-id="43036-160">It stores a single certificate to be used when no certificate is specified by a service.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43036-161">例</span><span class="sxs-lookup"><span data-stu-id="43036-161">Example</span></span>  
 <span data-ttu-id="43036-162">次の例では、URI がで`http://www.contoso.com`始まるエンドポイントに使用する証明書と、証明書ネゴシエーションを実行しない他のすべてのエンドポイントに使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="43036-162">The following example specifies a certificate to use for endpoints whose URI begins with `http://www.contoso.com` and a certificate to use for all other endpoints that do not perform certificate negotiation.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="43036-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="43036-163">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509DefaultServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.DefaultCertificate%2A>
- [<span data-ttu-id="43036-164">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="43036-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="43036-165">\<authentication></span><span class="sxs-lookup"><span data-stu-id="43036-165">\<authentication></span></span>](authentication-of-clientcertificate-element.md)
- [<span data-ttu-id="43036-166">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="43036-166">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="43036-167">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="43036-167">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
