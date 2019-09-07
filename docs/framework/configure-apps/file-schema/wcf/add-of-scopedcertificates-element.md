---
title: <add> <scopedCertificates>要素
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398343"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="798d4-102">\<scopedCertificates > 要素\<の > の追加</span><span class="sxs-lookup"><span data-stu-id="798d4-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="798d4-103">範囲指定された証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="798d4-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
<span data-ttu-id="798d4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="798d4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="798d4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="798d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="798d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="798d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="798d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="798d4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<scopedCertificates >** ](scopedcertificates-element.md)</span><span class="sxs-lookup"><span data-stu-id="798d4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)</span></span>\
<span data-ttu-id="798d4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> の追加**</span><span class="sxs-lookup"><span data-stu-id="798d4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="798d4-113">構文</span><span class="sxs-lookup"><span data-stu-id="798d4-113">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="798d4-114">属性および要素</span><span class="sxs-lookup"><span data-stu-id="798d4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="798d4-115">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="798d4-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="798d4-116">属性</span><span class="sxs-lookup"><span data-stu-id="798d4-116">Attributes</span></span>  
  
|<span data-ttu-id="798d4-117">属性</span><span class="sxs-lookup"><span data-stu-id="798d4-117">Attribute</span></span>|<span data-ttu-id="798d4-118">説明</span><span class="sxs-lookup"><span data-stu-id="798d4-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="798d4-119">targetUri</span><span class="sxs-lookup"><span data-stu-id="798d4-119">targetUri</span></span>|<span data-ttu-id="798d4-120">文字列。</span><span class="sxs-lookup"><span data-stu-id="798d4-120">String.</span></span> <span data-ttu-id="798d4-121">証明書に関連付けられているサービスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="798d4-121">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="798d4-122">findValue</span><span class="sxs-lookup"><span data-stu-id="798d4-122">findValue</span></span>|<span data-ttu-id="798d4-123">文字列。</span><span class="sxs-lookup"><span data-stu-id="798d4-123">String.</span></span> <span data-ttu-id="798d4-124">検索対象の値。</span><span class="sxs-lookup"><span data-stu-id="798d4-124">The value to search for.</span></span>|  
|<span data-ttu-id="798d4-125">x509FindType</span><span class="sxs-lookup"><span data-stu-id="798d4-125">x509FindType</span></span>|<span data-ttu-id="798d4-126">列挙値。</span><span class="sxs-lookup"><span data-stu-id="798d4-126">Enumeration.</span></span> <span data-ttu-id="798d4-127">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="798d4-127">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="798d4-128">storeLocation</span><span class="sxs-lookup"><span data-stu-id="798d4-128">storeLocation</span></span>|<span data-ttu-id="798d4-129">列挙値。</span><span class="sxs-lookup"><span data-stu-id="798d4-129">Enumeration.</span></span> <span data-ttu-id="798d4-130">検索する 2 つの格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="798d4-130">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="798d4-131">storeName</span><span class="sxs-lookup"><span data-stu-id="798d4-131">storeName</span></span>|<span data-ttu-id="798d4-132">列挙値。</span><span class="sxs-lookup"><span data-stu-id="798d4-132">Enumeration.</span></span> <span data-ttu-id="798d4-133">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="798d4-133">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="798d4-134">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="798d4-134">findValue Attribute</span></span>  
  
|<span data-ttu-id="798d4-135">値</span><span class="sxs-lookup"><span data-stu-id="798d4-135">Value</span></span>|<span data-ttu-id="798d4-136">説明</span><span class="sxs-lookup"><span data-stu-id="798d4-136">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="798d4-137">String</span><span class="sxs-lookup"><span data-stu-id="798d4-137">String</span></span>|<span data-ttu-id="798d4-138">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="798d4-138">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="798d4-139">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="798d4-139">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="798d4-140">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="798d4-140">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="798d4-141">値</span><span class="sxs-lookup"><span data-stu-id="798d4-141">Value</span></span>|<span data-ttu-id="798d4-142">説明</span><span class="sxs-lookup"><span data-stu-id="798d4-142">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="798d4-143">列挙</span><span class="sxs-lookup"><span data-stu-id="798d4-143">Enumeration</span></span>|<span data-ttu-id="798d4-144">次の値が含まれます。FindByThumbprint、FindBySubjectName、Findbysubjectdistinguishedname です、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span><span class="sxs-lookup"><span data-stu-id="798d4-144">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="798d4-145">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="798d4-145">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="798d4-146">値</span><span class="sxs-lookup"><span data-stu-id="798d4-146">Value</span></span>|<span data-ttu-id="798d4-147">説明</span><span class="sxs-lookup"><span data-stu-id="798d4-147">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="798d4-148">列挙型</span><span class="sxs-lookup"><span data-stu-id="798d4-148">Enumeration</span></span>|<span data-ttu-id="798d4-149">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="798d4-149">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="798d4-150">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="798d4-150">storeName Attribute</span></span>  
  
|<span data-ttu-id="798d4-151">値</span><span class="sxs-lookup"><span data-stu-id="798d4-151">Value</span></span>|<span data-ttu-id="798d4-152">説明</span><span class="sxs-lookup"><span data-stu-id="798d4-152">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="798d4-153">列挙</span><span class="sxs-lookup"><span data-stu-id="798d4-153">Enumeration</span></span>|<span data-ttu-id="798d4-154">次の値が含まれます。アドレス帳、AuthRoot、CertificateAuthority、許可されていない、My、Root、TrustedPeople、Trustedpeople。</span><span class="sxs-lookup"><span data-stu-id="798d4-154">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="798d4-155">子要素</span><span class="sxs-lookup"><span data-stu-id="798d4-155">Child Elements</span></span>  
 <span data-ttu-id="798d4-156">なし。</span><span class="sxs-lookup"><span data-stu-id="798d4-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="798d4-157">親要素</span><span class="sxs-lookup"><span data-stu-id="798d4-157">Parent Elements</span></span>  
  
|<span data-ttu-id="798d4-158">要素</span><span class="sxs-lookup"><span data-stu-id="798d4-158">Element</span></span>|<span data-ttu-id="798d4-159">説明</span><span class="sxs-lookup"><span data-stu-id="798d4-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="798d4-160">\<scopedCertificates></span><span class="sxs-lookup"><span data-stu-id="798d4-160">\<scopedCertificates></span></span>](scopedcertificates-element.md)|<span data-ttu-id="798d4-161">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="798d4-161">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="798d4-162">Remarks</span><span class="sxs-lookup"><span data-stu-id="798d4-162">Remarks</span></span>  
 <span data-ttu-id="798d4-163">この要素を使用すると、クライアントは、通信するサービスの URL に基づいて、使用するサービス証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="798d4-163">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="798d4-164">これは、クライアントが複数のサービス (エンド サービスと中間セキュリティ トークン サービス) と通信している可能性がある発行済みトークンのシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="798d4-164">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="798d4-165">証明書に基づくメッセージ セキュリティを使用したバインドにおいて、この証明書を使用してサービスへのメッセージを暗号化します。サービスがクライアントへの応答に署名する際には、この証明書を使用することが要求されます。</span><span class="sxs-lookup"><span data-stu-id="798d4-165">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="798d4-166">バインディングにサービスの証明書が必要で、サービスの URL に対する特定の証明書が ScopedCertificates 内に存在しない場合は、既定の証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="798d4-166">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="798d4-167">詳細について[は、「How to:フェデレーションクライアント](../../../wcf/feature-details/how-to-create-a-federated-client.md)を作成します。</span><span class="sxs-lookup"><span data-stu-id="798d4-167">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="798d4-168">例</span><span class="sxs-lookup"><span data-stu-id="798d4-168">Example</span></span>  
 <span data-ttu-id="798d4-169">次の例は、コレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="798d4-169">The following example adds an X.509 certificate the collection.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <serviceCertificate>
          <scopedCertificates>
            <add targetUri="http://www.contoso.com"
                 findValue="www.Contoso.com"
                 storeLocation="LocalMachine"
                 storeName="Root"
                 x509FindType="FindByIssuerName" />
          </scopedCertificates>
        </serviceCertificate>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="798d4-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="798d4-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="798d4-171">方法: フェデレーションクライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="798d4-171">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="798d4-172">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="798d4-172">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="798d4-173">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="798d4-173">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="798d4-174">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="798d4-174">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
