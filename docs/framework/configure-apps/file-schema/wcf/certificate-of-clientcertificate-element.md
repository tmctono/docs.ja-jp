---
title: <certificate> <clientCertificate>要素
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400543"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="3cc66-102">\<証明書 > の\<clientCertificate > 要素</span><span class="sxs-lookup"><span data-stu-id="3cc66-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="3cc66-103">メッセージの署名と暗号化に使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
<span data-ttu-id="3cc66-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3cc66-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3cc66-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="3cc66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="3cc66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="3cc66-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="3cc66-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCertificate >** ](clientcertificate-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3cc66-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)</span></span>\
<span data-ttu-id="3cc66-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<証明書の >**</span><span class="sxs-lookup"><span data-stu-id="3cc66-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cc66-112">構文</span><span class="sxs-lookup"><span data-stu-id="3cc66-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cc66-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3cc66-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3cc66-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cc66-115">属性</span><span class="sxs-lookup"><span data-stu-id="3cc66-115">Attributes</span></span>  
  
|<span data-ttu-id="3cc66-116">属性</span><span class="sxs-lookup"><span data-stu-id="3cc66-116">Attribute</span></span>|<span data-ttu-id="3cc66-117">説明</span><span class="sxs-lookup"><span data-stu-id="3cc66-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="3cc66-118">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="3cc66-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="3cc66-119">属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc66-119">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="3cc66-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="3cc66-121">クライアントがサーバーの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-121">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="3cc66-122">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cc66-123">-LocalMachine: ローカル マシンに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="3cc66-124">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="3cc66-125">既定は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="3cc66-126">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="3cc66-127">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cc66-128">-AddressBook:他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="3cc66-129">-   AuthRoot:サード パーティ証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="3cc66-130">-証明機関:中間証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-130">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="3cc66-131">-許可されていません。失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="3cc66-132">-My:個人用証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="3cc66-133">ルート:信頼されたルート証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="3cc66-134">-TrustedPeople:直接信頼されたユーザーとリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-134">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="3cc66-135">-TrustedPublisher:直接信頼された発行者の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="3cc66-135">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="3cc66-136">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="3cc66-137">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="3cc66-138">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3cc66-139">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="3cc66-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="3cc66-140">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="3cc66-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="3cc66-141">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3cc66-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="3cc66-142">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="3cc66-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="3cc66-143">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="3cc66-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="3cc66-144">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="3cc66-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="3cc66-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="3cc66-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="3cc66-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="3cc66-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="3cc66-147">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="3cc66-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="3cc66-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="3cc66-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="3cc66-149">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="3cc66-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="3cc66-150">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="3cc66-150">-   FindByExtension</span></span><br /><span data-ttu-id="3cc66-151">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="3cc66-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="3cc66-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="3cc66-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="3cc66-153">`findValue` 属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc66-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="3cc66-154">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="3cc66-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cc66-155">子要素</span><span class="sxs-lookup"><span data-stu-id="3cc66-155">Child Elements</span></span>  
 <span data-ttu-id="3cc66-156">なし。</span><span class="sxs-lookup"><span data-stu-id="3cc66-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3cc66-157">親要素</span><span class="sxs-lookup"><span data-stu-id="3cc66-157">Parent Elements</span></span>  
  
|<span data-ttu-id="3cc66-158">要素</span><span class="sxs-lookup"><span data-stu-id="3cc66-158">Element</span></span>|<span data-ttu-id="3cc66-159">説明</span><span class="sxs-lookup"><span data-stu-id="3cc66-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3cc66-160">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="3cc66-160">\<clientCertificate></span></span>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="3cc66-161">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cc66-161">Remarks</span></span>  
 <span data-ttu-id="3cc66-162">`<certificate>` 要素は、サービスがクライアントと安全に通信するために、サービスが前もってクライアントの証明書を持っている必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-162">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="3cc66-163">このような状況は、双方向通信パターンを使用する場合に生じます。</span><span class="sxs-lookup"><span data-stu-id="3cc66-163">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="3cc66-164">より一般的な要求/応答パターンでは、クライアントは自身の証明書を要求に含め、サービスはそれを使用してクライアントへの応答を暗号化し、署名します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-164">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="3cc66-165">一方、双方向通信パターンでは、サービスにはクライアントからの要求が来ないので、クライアントの証明書をあらかじめ取得することで、クライアント宛のメッセージのセキュリティを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc66-165">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="3cc66-166">このため、クライアントの証明書を帯域外のネゴシエーションで取得し、この要素を使用して証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cc66-166">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="3cc66-167">双方向サービスの詳細については、次を参照してください。[方法。双方向コントラクトを作成する](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-167">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cc66-168">例</span><span class="sxs-lookup"><span data-stu-id="3cc66-168">Example</span></span>  
 <span data-ttu-id="3cc66-169">次のコードは、`<authentication>` 要素の適切な X.509 証明書とカスタム検証タイプの検索方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-169">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="myServiceBehavior">
    <clientCertificate>
      <certificate findValue="www.cohowinery.com"
                   storeLocation="CurrentUser"
                   storeName="TrustedPeople"
                   x509FindType="FindByIssuerName" />
      <authentication customCertificateValidatorType="MyTypes.Coho"
                      certificateValidationMode="Custom"
                      revocationMode="Offline"
                      includeWindowsGroups="false"
                      mapClientCertificateToWindowsAccount="true" />
    </clientCertificate>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="3cc66-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="3cc66-170">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="3cc66-171">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="3cc66-171">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3cc66-172">方法: カスタム証明書の検証を使用するサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="3cc66-172">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="3cc66-173">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="3cc66-173">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
