---
title: <certificate> 要素
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 8cc0404a5896dd23cffce6f1f77b91a2f01f23d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151091"
---
# <a name="certificate-element"></a><span data-ttu-id="53be4-102">\<certificate> 要素</span><span class="sxs-lookup"><span data-stu-id="53be4-102">\<certificate> Element</span></span>

<span data-ttu-id="53be4-103">ピアツーピア クライアントのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="53be4-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="53be4-104">構文</span><span class="sxs-lookup"><span data-stu-id="53be4-104">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53be4-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="53be4-105">Attributes and Elements</span></span>  

 <span data-ttu-id="53be4-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="53be4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53be4-107">属性</span><span class="sxs-lookup"><span data-stu-id="53be4-107">Attributes</span></span>  
  
|<span data-ttu-id="53be4-108">属性</span><span class="sxs-lookup"><span data-stu-id="53be4-108">Attribute</span></span>|<span data-ttu-id="53be4-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="53be4-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="53be4-110">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="53be4-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="53be4-111">属性に格納されている型は、指定された `x509FindType` の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="53be4-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="53be4-112">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="53be4-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="53be4-113">クライアントがピアの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="53be4-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="53be4-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53be4-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53be4-115">-LocalMachine: ローカルコンピューターに割り当てられた証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="53be4-116">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="53be4-117">既定値は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="53be4-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="53be4-118">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="53be4-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="53be4-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53be4-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53be4-120">-アドレス帳: 他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="53be4-121">-AuthRoot: サードパーティ証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-121">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="53be4-122">-CertificateAuthority: 中間証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-122">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="53be4-123">-許可されていません: 失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="53be4-124">-My: 個人証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="53be4-125">-Root: 信頼されたルート証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-125">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="53be4-126">-TrustedPeople: 直接信頼されている人間とリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="53be4-127">-TrustedPublisher: 直接信頼された発行元の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="53be4-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="53be4-128">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="53be4-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="53be4-129">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="53be4-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="53be4-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53be4-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="53be4-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="53be4-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="53be4-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="53be4-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="53be4-133">-Findbysubjectdistinguishedname です</span><span class="sxs-lookup"><span data-stu-id="53be4-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="53be4-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="53be4-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="53be4-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="53be4-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="53be4-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="53be4-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="53be4-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="53be4-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="53be4-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="53be4-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="53be4-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="53be4-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="53be4-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="53be4-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="53be4-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="53be4-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="53be4-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="53be4-142">-   FindByExtension</span></span><br /><span data-ttu-id="53be4-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="53be4-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="53be4-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="53be4-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="53be4-145">`findValue` 属性に格納されている型は、指定された `X509FindType` の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="53be4-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="53be4-146">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="53be4-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53be4-147">子要素</span><span class="sxs-lookup"><span data-stu-id="53be4-147">Child Elements</span></span>  

 <span data-ttu-id="53be4-148">なし。</span><span class="sxs-lookup"><span data-stu-id="53be4-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53be4-149">親要素</span><span class="sxs-lookup"><span data-stu-id="53be4-149">Parent Elements</span></span>  
  
|<span data-ttu-id="53be4-150">要素</span><span class="sxs-lookup"><span data-stu-id="53be4-150">Element</span></span>|<span data-ttu-id="53be4-151">説明</span><span class="sxs-lookup"><span data-stu-id="53be4-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|<span data-ttu-id="53be4-152">ピアツーピア クライアントの認証時に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="53be4-152">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53be4-153">解説</span><span class="sxs-lookup"><span data-stu-id="53be4-153">Remarks</span></span>  

 <span data-ttu-id="53be4-154">この構成要素には、ピア メッシュ内の近隣ノードを認証するときに使用される X509Certificate2 インスタンスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="53be4-154">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="53be4-155">ピアツーピアプログラミングの詳細については、「 [ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53be4-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53be4-156">例</span><span class="sxs-lookup"><span data-stu-id="53be4-156">Example</span></span>  

 <span data-ttu-id="53be4-157">次のコードは、ピアツーピア シナリオで使用される証明書の検索方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="53be4-157">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="53be4-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="53be4-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="53be4-159">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="53be4-159">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="53be4-160">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="53be4-160">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="53be4-161">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="53be4-161">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="53be4-162">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="53be4-162">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="53be4-163">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="53be4-163">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
