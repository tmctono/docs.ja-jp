---
title: <certificate><clientCertificate>要素の
ms.date: 03/30/2017
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
ms.openlocfilehash: d0c4ef9d3657d2dfa787feb3576beda09d1997a3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400543"
---
# <a name="certificate-of-clientcertificate-element"></a><span data-ttu-id="150fc-102">\<certificate>\<clientCertificate>要素の</span><span class="sxs-lookup"><span data-stu-id="150fc-102">\<certificate> of \<clientCertificate> Element</span></span>
<span data-ttu-id="150fc-103">メッセージの署名と暗号化に使用される X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="150fc-103">Specifies an X.509 certificate used to sign and encrypt messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCertificate>**](clientcertificate-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="150fc-104">構文</span><span class="sxs-lookup"><span data-stu-id="150fc-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="150fc-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="150fc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="150fc-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="150fc-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="150fc-107">属性</span><span class="sxs-lookup"><span data-stu-id="150fc-107">Attributes</span></span>  
  
|<span data-ttu-id="150fc-108">属性</span><span class="sxs-lookup"><span data-stu-id="150fc-108">Attribute</span></span>|<span data-ttu-id="150fc-109">説明</span><span class="sxs-lookup"><span data-stu-id="150fc-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="150fc-110">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="150fc-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="150fc-111">属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="150fc-111">The type contained in the attribute must satisfy the requirements of the specified X509FindType.</span></span> <span data-ttu-id="150fc-112">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="150fc-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="150fc-113">クライアントがサーバーの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="150fc-113">Specifies the location of the X.509 certificate store that the client uses to validate the server’s certificate against.</span></span> <span data-ttu-id="150fc-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="150fc-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="150fc-115">-LocalMachine: ローカルコンピューターに割り当てられた証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="150fc-116">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="150fc-117">既定値は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="150fc-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="150fc-118">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="150fc-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="150fc-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="150fc-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="150fc-120">-アドレス帳: 他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="150fc-121">-AuthRoot: サードパーティ証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="150fc-122">-Microsoft-windows-certificationauthority: 中間証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-122">-   CertificationAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="150fc-123">-許可されていません: 失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="150fc-124">-My: 個人証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="150fc-125">-Root: 信頼されたルート証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="150fc-126">-TrustedPeople: 直接信頼されている人間とリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-126">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="150fc-127">-TrustedPublisher: 直接信頼された発行元の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="150fc-127">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="150fc-128">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="150fc-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="150fc-129">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="150fc-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="150fc-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="150fc-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="150fc-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="150fc-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="150fc-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="150fc-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="150fc-133">-Findbysubjectdistinguishedname です</span><span class="sxs-lookup"><span data-stu-id="150fc-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="150fc-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="150fc-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="150fc-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="150fc-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="150fc-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="150fc-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="150fc-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="150fc-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="150fc-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="150fc-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="150fc-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="150fc-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="150fc-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="150fc-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="150fc-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="150fc-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="150fc-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="150fc-142">-   FindByExtension</span></span><br /><span data-ttu-id="150fc-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="150fc-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="150fc-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="150fc-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="150fc-145">`findValue` 属性に含まれている型は、指定された X509FindType の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="150fc-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified X509FindType.</span></span><br /><br /> <span data-ttu-id="150fc-146">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="150fc-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="150fc-147">子要素</span><span class="sxs-lookup"><span data-stu-id="150fc-147">Child Elements</span></span>  
 <span data-ttu-id="150fc-148">なし。</span><span class="sxs-lookup"><span data-stu-id="150fc-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="150fc-149">親要素</span><span class="sxs-lookup"><span data-stu-id="150fc-149">Parent Elements</span></span>  
  
|<span data-ttu-id="150fc-150">要素</span><span class="sxs-lookup"><span data-stu-id="150fc-150">Element</span></span>|<span data-ttu-id="150fc-151">説明</span><span class="sxs-lookup"><span data-stu-id="150fc-151">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCertificate>](clientcertificate-of-servicecredentials.md)||  
  
## <a name="remarks"></a><span data-ttu-id="150fc-152">解説</span><span class="sxs-lookup"><span data-stu-id="150fc-152">Remarks</span></span>  
 <span data-ttu-id="150fc-153">`<certificate>` 要素は、サービスがクライアントと安全に通信するために、サービスが前もってクライアントの証明書を持っている必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="150fc-153">The `<certificate>` element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="150fc-154">このような状況は、双方向通信パターンを使用する場合に生じます。</span><span class="sxs-lookup"><span data-stu-id="150fc-154">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="150fc-155">より一般的な要求/応答パターンでは、クライアントは自身の証明書を要求に含め、サービスはそれを使用してクライアントへの応答を暗号化し、署名します。</span><span class="sxs-lookup"><span data-stu-id="150fc-155">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="150fc-156">一方、双方向通信パターンでは、サービスにはクライアントからの要求が来ないので、クライアントの証明書をあらかじめ取得することで、クライアント宛のメッセージのセキュリティを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="150fc-156">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="150fc-157">このため、クライアントの証明書を帯域外のネゴシエーションで取得し、この要素を使用して証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="150fc-157">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="150fc-158">双方向サービスの詳細については、「[方法: 双方向コントラクトを作成](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="150fc-158">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="150fc-159">例</span><span class="sxs-lookup"><span data-stu-id="150fc-159">Example</span></span>  
 <span data-ttu-id="150fc-160">次のコードは、`<authentication>` 要素の適切な X.509 証明書とカスタム検証タイプの検索方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="150fc-160">The following code specifies how to find an appropriate X.509 certificate and a custom validation type in the `<authentication>` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="150fc-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="150fc-161">See also</span></span>

- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>
- [<span data-ttu-id="150fc-162">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="150fc-162">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="150fc-163">方法: カスタム証明書検証を使用するサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="150fc-163">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)
- [<span data-ttu-id="150fc-164">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="150fc-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
