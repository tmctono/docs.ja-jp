---
title: <add><scopedCertificates>要素の
ms.date: 03/30/2017
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
ms.openlocfilehash: b00a342108beca69a906fbf6212915768e98778f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398343"
---
# <a name="add-of-scopedcertificates-element"></a><span data-ttu-id="22e5f-102">\<add>\<scopedCertificates>要素の</span><span class="sxs-lookup"><span data-stu-id="22e5f-102">\<add> of \<scopedCertificates> Element</span></span>
<span data-ttu-id="22e5f-103">範囲指定された証明書のコレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-103">Adds an X.509 certificate to the collection of scoped certificates.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<scopedCertificates>**](scopedcertificates-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="22e5f-104">構文</span><span class="sxs-lookup"><span data-stu-id="22e5f-104">Syntax</span></span>  
  
```xml  
<add findValue="String"
     storeLocation="CurrentUser/LocalMachine"
     storeName=" CurrentUser/LocalMachine"
     targetUri="string"
     x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22e5f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="22e5f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="22e5f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22e5f-107">属性</span><span class="sxs-lookup"><span data-stu-id="22e5f-107">Attributes</span></span>  
  
|<span data-ttu-id="22e5f-108">属性</span><span class="sxs-lookup"><span data-stu-id="22e5f-108">Attribute</span></span>|<span data-ttu-id="22e5f-109">説明</span><span class="sxs-lookup"><span data-stu-id="22e5f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22e5f-110">targetUri</span><span class="sxs-lookup"><span data-stu-id="22e5f-110">targetUri</span></span>|<span data-ttu-id="22e5f-111">文字列。</span><span class="sxs-lookup"><span data-stu-id="22e5f-111">String.</span></span> <span data-ttu-id="22e5f-112">証明書に関連付けられているサービスの URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-112">Specifies the URI of the service associated with the certificate.</span></span>|  
|<span data-ttu-id="22e5f-113">findValue</span><span class="sxs-lookup"><span data-stu-id="22e5f-113">findValue</span></span>|<span data-ttu-id="22e5f-114">文字列。</span><span class="sxs-lookup"><span data-stu-id="22e5f-114">String.</span></span> <span data-ttu-id="22e5f-115">検索する値。</span><span class="sxs-lookup"><span data-stu-id="22e5f-115">The value to search for.</span></span>|  
|<span data-ttu-id="22e5f-116">x509FindType</span><span class="sxs-lookup"><span data-stu-id="22e5f-116">x509FindType</span></span>|<span data-ttu-id="22e5f-117">列挙値。</span><span class="sxs-lookup"><span data-stu-id="22e5f-117">Enumeration.</span></span> <span data-ttu-id="22e5f-118">検索する証明書フィールドのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="22e5f-118">One of the certificate fields to search.</span></span>|  
|<span data-ttu-id="22e5f-119">storeLocation</span><span class="sxs-lookup"><span data-stu-id="22e5f-119">storeLocation</span></span>|<span data-ttu-id="22e5f-120">列挙値。</span><span class="sxs-lookup"><span data-stu-id="22e5f-120">Enumeration.</span></span> <span data-ttu-id="22e5f-121">検索する 2 つの格納場所のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="22e5f-121">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="22e5f-122">storeName</span><span class="sxs-lookup"><span data-stu-id="22e5f-122">storeName</span></span>|<span data-ttu-id="22e5f-123">列挙値。</span><span class="sxs-lookup"><span data-stu-id="22e5f-123">Enumeration.</span></span> <span data-ttu-id="22e5f-124">検索するシステム ストアのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="22e5f-124">One of the system stores to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="22e5f-125">findValue 属性</span><span class="sxs-lookup"><span data-stu-id="22e5f-125">findValue Attribute</span></span>  
  
|<span data-ttu-id="22e5f-126">値</span><span class="sxs-lookup"><span data-stu-id="22e5f-126">Value</span></span>|<span data-ttu-id="22e5f-127">説明</span><span class="sxs-lookup"><span data-stu-id="22e5f-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22e5f-128">String</span><span class="sxs-lookup"><span data-stu-id="22e5f-128">String</span></span>|<span data-ttu-id="22e5f-129">値は、検索されるフィールド (X509FindType 属性により指定される) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="22e5f-129">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="22e5f-130">たとえば、サムプリント検索する場合、値は 16 進数の文字列にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e5f-130">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="22e5f-131">x509FindType 属性</span><span class="sxs-lookup"><span data-stu-id="22e5f-131">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="22e5f-132">値</span><span class="sxs-lookup"><span data-stu-id="22e5f-132">Value</span></span>|<span data-ttu-id="22e5f-133">Description</span><span class="sxs-lookup"><span data-stu-id="22e5f-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22e5f-134">Enumeration</span><span class="sxs-lookup"><span data-stu-id="22e5f-134">Enumeration</span></span>|<span data-ttu-id="22e5f-135">値は、FindByThumbprint、FindBySubjectName、FindBySubjectDistinguishedName、FindByIssuerName、FindByIssuerDistinguishedName、FindBySerialNumber、FindByTimeValid、FindByTimeNotYetValid、FindBySerialNumber、FindByTimeExpired、FindByTemplateName、FindByApplicationPolicy、FindByCertificatePolicy、FindByExtension、FindByKeyUsage、FindBySubjectKeyIdentifier です。</span><span class="sxs-lookup"><span data-stu-id="22e5f-135">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="22e5f-136">storeLocation 属性</span><span class="sxs-lookup"><span data-stu-id="22e5f-136">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="22e5f-137">値</span><span class="sxs-lookup"><span data-stu-id="22e5f-137">Value</span></span>|<span data-ttu-id="22e5f-138">Description</span><span class="sxs-lookup"><span data-stu-id="22e5f-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22e5f-139">Enumeration</span><span class="sxs-lookup"><span data-stu-id="22e5f-139">Enumeration</span></span>|<span data-ttu-id="22e5f-140">CurrentUser または LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="22e5f-140">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="22e5f-141">storeName 属性</span><span class="sxs-lookup"><span data-stu-id="22e5f-141">storeName Attribute</span></span>  
  
|<span data-ttu-id="22e5f-142">値</span><span class="sxs-lookup"><span data-stu-id="22e5f-142">Value</span></span>|<span data-ttu-id="22e5f-143">Description</span><span class="sxs-lookup"><span data-stu-id="22e5f-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22e5f-144">Enumeration</span><span class="sxs-lookup"><span data-stu-id="22e5f-144">Enumeration</span></span>|<span data-ttu-id="22e5f-145">値は、AddressBook、AuthRoot、CertificateAuthority、Disallowed、My、Root、TrustedPeople、および TrustedPublisher です。</span><span class="sxs-lookup"><span data-stu-id="22e5f-145">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22e5f-146">子要素</span><span class="sxs-lookup"><span data-stu-id="22e5f-146">Child Elements</span></span>  
 <span data-ttu-id="22e5f-147">なし。</span><span class="sxs-lookup"><span data-stu-id="22e5f-147">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22e5f-148">親要素</span><span class="sxs-lookup"><span data-stu-id="22e5f-148">Parent Elements</span></span>  
  
|<span data-ttu-id="22e5f-149">要素</span><span class="sxs-lookup"><span data-stu-id="22e5f-149">Element</span></span>|<span data-ttu-id="22e5f-150">Description</span><span class="sxs-lookup"><span data-stu-id="22e5f-150">Description</span></span>|  
|-------------|-----------------|  
|[\<scopedCertificates>](scopedcertificates-element.md)|<span data-ttu-id="22e5f-151">認証用の (範囲指定された) 特定のサービスにより提供される X.509 証明書のコレクションを表します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-151">Represents a collection of X.509 certificates provided by specific services (scoped) for authentication.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22e5f-152">解説</span><span class="sxs-lookup"><span data-stu-id="22e5f-152">Remarks</span></span>  
 <span data-ttu-id="22e5f-153">この要素を使用すると、クライアントは、通信するサービスの URL に基づいて、使用するサービス証明書を構成できます。</span><span class="sxs-lookup"><span data-stu-id="22e5f-153">This element enables the client to configure a service certificate to use based on the URL of the service it communicates with.</span></span> <span data-ttu-id="22e5f-154">これは、クライアントが複数のサービス (エンド サービスと中間セキュリティ トークン サービス) と通信している可能性がある発行済みトークンのシナリオで特に便利です。</span><span class="sxs-lookup"><span data-stu-id="22e5f-154">This is especially useful in issued token scenarios where a client can be communicating to multiple services (the end service as well as intermediary security token services).</span></span> <span data-ttu-id="22e5f-155">証明書に基づくメッセージ セキュリティを使用したバインドにおいて、この証明書を使用してサービスへのメッセージを暗号化します。サービスがクライアントへの応答に署名する際には、この証明書を使用することが要求されます。</span><span class="sxs-lookup"><span data-stu-id="22e5f-155">For bindings that use certificate-based message security, this certificate is used to encrypt messages to the service, and is expected to be used by the service for signing replies to the client.</span></span>  
  
 <span data-ttu-id="22e5f-156">バインディングにサービスの証明書が必要で、サービスの URL に対する特定の証明書が ScopedCertificates 内に存在しない場合は、既定の証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="22e5f-156">If a binding requires a certificate for the service and no specific certificate for the service URL is found in the ScopedCertificates, the default certificate is used.</span></span>  
  
 <span data-ttu-id="22e5f-157">詳細については、「[方法: フェデレーションクライアントを作成](../../../wcf/feature-details/how-to-create-a-federated-client.md)する」の「スコープ付き証明書」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e5f-157">For more information, see the "Scoped Certificates" section of [How to: Create a Federated Client](../../../wcf/feature-details/how-to-create-a-federated-client.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22e5f-158">例</span><span class="sxs-lookup"><span data-stu-id="22e5f-158">Example</span></span>  
 <span data-ttu-id="22e5f-159">次の例は、コレクションに X.509 証明書を追加します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-159">The following example adds an X.509 certificate the collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22e5f-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e5f-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>
- <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>
- [<span data-ttu-id="22e5f-161">方法: フェデレーション クライアントを作成する</span><span class="sxs-lookup"><span data-stu-id="22e5f-161">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="22e5f-162">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="22e5f-162">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="22e5f-163">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="22e5f-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="22e5f-164">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="22e5f-164">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
