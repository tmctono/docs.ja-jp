---
title: <clientCertificate><clientCredentials>要素の
ms.date: 03/30/2017
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
ms.openlocfilehash: 74209c43dcafb1e27bb1d7943ee7832eaea0ef57
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204945"
---
# <a name="clientcertificate-of-clientcredentials-element"></a><span data-ttu-id="301bc-102">\<clientCertificate>\<clientCredentials>要素の</span><span class="sxs-lookup"><span data-stu-id="301bc-102">\<clientCertificate> of \<clientCredentials> Element</span></span>

<span data-ttu-id="301bc-103">サービスに対するクライアントの認証に使用する X.509 証明書を定義します。</span><span class="sxs-lookup"><span data-stu-id="301bc-103">Defines an X.509 certificate used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="301bc-104">構文</span><span class="sxs-lookup"><span data-stu-id="301bc-104">Syntax</span></span>  
  
```xml  
<clientCertificate findValue="String"
                   storeLocation="LocalMachine/CurrentUser"
                   storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                   X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="301bc-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="301bc-105">Attributes and Elements</span></span>  

 <span data-ttu-id="301bc-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="301bc-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="301bc-107">属性</span><span class="sxs-lookup"><span data-stu-id="301bc-107">Attributes</span></span>  
  
|<span data-ttu-id="301bc-108">属性</span><span class="sxs-lookup"><span data-stu-id="301bc-108">Attribute</span></span>|<span data-ttu-id="301bc-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="301bc-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="301bc-110">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="301bc-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="301bc-111">属性に格納されている型は、`X509FindType` 属性値の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bc-111">The type contained in the attribute must satisfy the requirements of the `X509FindType` attribute value.</span></span> <span data-ttu-id="301bc-112">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="301bc-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="301bc-113">クライアントがサービスに対して自身を認証するために使用する X.509 証明書の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="301bc-113">Specifies the location of the X.509 certificate that the client uses to authenticate itself to the service.</span></span> <span data-ttu-id="301bc-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="301bc-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="301bc-115">-LocalMachine: ローカルコンピューターに割り当てられた証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="301bc-116">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="301bc-117">既定値は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="301bc-117">The default is LocalMachine.</span></span> <span data-ttu-id="301bc-118">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 型です。</span><span class="sxs-lookup"><span data-stu-id="301bc-118">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreLocation>.</span></span>|  
|`storeName`|<span data-ttu-id="301bc-119">検索する X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="301bc-119">Specifies the name of the X.509 certificate store to search.</span></span> <span data-ttu-id="301bc-120">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="301bc-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="301bc-121">-アドレス帳: 他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-121">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="301bc-122">-AuthRoot: サードパーティの証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-122">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="301bc-123">-CertificateAuthority: 中間証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-123">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="301bc-124">-許可されていません: 失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-124">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="301bc-125">-My: 個人証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-125">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="301bc-126">-Root: 信頼されたルート証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-126">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="301bc-127">-TrustedPeople: 直接信頼されている人間とリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-127">-   TrustedPeople: Certificate store for directly trusted people and resources.</span></span><br /><span data-ttu-id="301bc-128">-TrustedPublisher: 直接信頼された発行元の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="301bc-128">-   TrustedPublisher: Certificate store for directly trusted publishers.</span></span><br /><br /> <span data-ttu-id="301bc-129">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="301bc-129">The default is My.</span></span> <span data-ttu-id="301bc-130">この属性は <xref:System.Security.Cryptography.X509Certificates.StoreName> 型です。</span><span class="sxs-lookup"><span data-stu-id="301bc-130">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.StoreName>.</span></span>|  
|<span data-ttu-id="301bc-131">X509FindType</span><span class="sxs-lookup"><span data-stu-id="301bc-131">X509FindType</span></span>|<span data-ttu-id="301bc-132">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="301bc-132">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="301bc-133">`findValue` 属性に格納されている型は、この属性の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="301bc-133">The type contained in the `findValue` attribute must satisfy the requirements of this attribute.</span></span> <span data-ttu-id="301bc-134">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="301bc-134">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="301bc-135">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="301bc-135">-   FindByThumbPrint</span></span><br /><span data-ttu-id="301bc-136">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="301bc-136">-   FindBySubjectName</span></span><br /><span data-ttu-id="301bc-137">-Findbysubjectdistinguishedname です</span><span class="sxs-lookup"><span data-stu-id="301bc-137">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="301bc-138">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="301bc-138">-   FindByIssuerName</span></span><br /><span data-ttu-id="301bc-139">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="301bc-139">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="301bc-140">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="301bc-140">-   FindBySerialNumber</span></span><br /><span data-ttu-id="301bc-141">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="301bc-141">-   FindByTimeValid</span></span><br /><span data-ttu-id="301bc-142">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="301bc-142">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="301bc-143">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="301bc-143">-   FindByTemplateName</span></span><br /><span data-ttu-id="301bc-144">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="301bc-144">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="301bc-145">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="301bc-145">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="301bc-146">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="301bc-146">-   FindByExtension</span></span><br /><span data-ttu-id="301bc-147">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="301bc-147">-   FindByKeyUsage</span></span><br /><span data-ttu-id="301bc-148">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="301bc-148">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="301bc-149">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="301bc-149">The default value is FindBySubjectDistinguishedName.</span></span> <span data-ttu-id="301bc-150">この属性は <xref:System.Security.Cryptography.X509Certificates.X509FindType> 型です。</span><span class="sxs-lookup"><span data-stu-id="301bc-150">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="301bc-151">子要素</span><span class="sxs-lookup"><span data-stu-id="301bc-151">Child Elements</span></span>  

 <span data-ttu-id="301bc-152">なし。</span><span class="sxs-lookup"><span data-stu-id="301bc-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="301bc-153">親要素</span><span class="sxs-lookup"><span data-stu-id="301bc-153">Parent Elements</span></span>  
  
|<span data-ttu-id="301bc-154">要素</span><span class="sxs-lookup"><span data-stu-id="301bc-154">Element</span></span>|<span data-ttu-id="301bc-155">説明</span><span class="sxs-lookup"><span data-stu-id="301bc-155">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="301bc-156">サービスに対するクライアントの認証に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="301bc-156">Specifies the credentials used to authenticate the client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="301bc-157">解説</span><span class="sxs-lookup"><span data-stu-id="301bc-157">Remarks</span></span>  

 <span data-ttu-id="301bc-158">この構成要素は、この要素によるクライアントの認証に使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="301bc-158">This configuration element specifies the certificate used to authenticate the client with this element.</span></span> <span data-ttu-id="301bc-159">詳細については、「 [方法: クライアント資格情報の値を指定する](../../../wcf/how-to-specify-client-credential-values.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="301bc-159">For more information, see [How to: Specify Client Credential Values](../../../wcf/how-to-specify-client-credential-values.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301bc-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="301bc-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="301bc-161">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="301bc-161">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="301bc-162">方法: クライアントの資格情報の値を指定する</span><span class="sxs-lookup"><span data-stu-id="301bc-162">How to: Specify Client Credential Values</span></span>](../../../wcf/how-to-specify-client-credential-values.md)
- [<span data-ttu-id="301bc-163">クライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="301bc-163">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="301bc-164">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="301bc-164">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="301bc-165">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="301bc-165">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
