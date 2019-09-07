---
title: <certificate> 要素
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400552"
---
# <a name="certificate-element"></a><span data-ttu-id="149fb-102">\<certificate > 要素</span><span class="sxs-lookup"><span data-stu-id="149fb-102">\<certificate> Element</span></span>
<span data-ttu-id="149fb-103">ピアツーピア クライアントのメッセージの署名と暗号化に使用する X.509 証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="149fb-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="149fb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="149fb-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="149fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="149fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="149fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<動作 >** ](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="149fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clientCredentials >** ](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="149fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<ピア >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="149fb-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="149fb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<証明書の >**</span><span class="sxs-lookup"><span data-stu-id="149fb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="149fb-112">構文</span><span class="sxs-lookup"><span data-stu-id="149fb-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="149fb-113">属性および要素</span><span class="sxs-lookup"><span data-stu-id="149fb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="149fb-114">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="149fb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="149fb-115">属性</span><span class="sxs-lookup"><span data-stu-id="149fb-115">Attributes</span></span>  
  
|<span data-ttu-id="149fb-116">属性</span><span class="sxs-lookup"><span data-stu-id="149fb-116">Attribute</span></span>|<span data-ttu-id="149fb-117">説明</span><span class="sxs-lookup"><span data-stu-id="149fb-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="149fb-118">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="149fb-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="149fb-119">属性に格納されている型は、指定された `x509FindType` の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="149fb-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="149fb-120">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="149fb-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="149fb-121">クライアントがピアの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="149fb-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="149fb-122">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="149fb-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="149fb-123">-LocalMachine: ローカル マシンに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="149fb-124">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="149fb-125">既定は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="149fb-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="149fb-126">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="149fb-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="149fb-127">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="149fb-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="149fb-128">-AddressBook:他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="149fb-129">-   AuthRoot:サード パーティ証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="149fb-130">CertificateAuthority中間証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="149fb-131">-許可されていません。失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="149fb-132">-My:個人用証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="149fb-133">ルート:信頼されたルート証明機関 (Ca) 証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="149fb-134">-TrustedPeople:直接信頼されている人材とリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="149fb-135">-TrustedPublisher:直接信頼された発行元の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="149fb-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="149fb-136">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="149fb-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="149fb-137">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="149fb-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="149fb-138">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="149fb-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="149fb-139">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="149fb-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="149fb-140">-   FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="149fb-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="149fb-141">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="149fb-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="149fb-142">-   FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="149fb-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="149fb-143">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="149fb-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="149fb-144">-   FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="149fb-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="149fb-145">-   FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="149fb-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="149fb-146">-   FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="149fb-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="149fb-147">-   FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="149fb-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="149fb-148">-   FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="149fb-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="149fb-149">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="149fb-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="149fb-150">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="149fb-150">-   FindByExtension</span></span><br /><span data-ttu-id="149fb-151">-   FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="149fb-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="149fb-152">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="149fb-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="149fb-153">`findValue` 属性に格納されている型は、指定された `X509FindType` の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="149fb-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="149fb-154">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="149fb-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="149fb-155">子要素</span><span class="sxs-lookup"><span data-stu-id="149fb-155">Child Elements</span></span>  
 <span data-ttu-id="149fb-156">なし。</span><span class="sxs-lookup"><span data-stu-id="149fb-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="149fb-157">親要素</span><span class="sxs-lookup"><span data-stu-id="149fb-157">Parent Elements</span></span>  
  
|<span data-ttu-id="149fb-158">要素</span><span class="sxs-lookup"><span data-stu-id="149fb-158">Element</span></span>|<span data-ttu-id="149fb-159">説明</span><span class="sxs-lookup"><span data-stu-id="149fb-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="149fb-160">\<peer></span><span class="sxs-lookup"><span data-stu-id="149fb-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="149fb-161">ピアツーピア クライアントの認証時に使用される資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="149fb-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="149fb-162">Remarks</span><span class="sxs-lookup"><span data-stu-id="149fb-162">Remarks</span></span>  
 <span data-ttu-id="149fb-163">この構成要素には、ピア メッシュ内の近隣ノードを認証するときに使用される X509Certificate2 インスタンスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="149fb-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="149fb-164">ピアツーピアプログラミングの詳細については、「[ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="149fb-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="149fb-165">例</span><span class="sxs-lookup"><span data-stu-id="149fb-165">Example</span></span>  
 <span data-ttu-id="149fb-166">次のコードは、ピアツーピア シナリオで使用される証明書の検索方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="149fb-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="149fb-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="149fb-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="149fb-168">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="149fb-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="149fb-169">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="149fb-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="149fb-170">[ピアチャネルメッセージの認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="149fb-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="149fb-171">[ピアチャネルのカスタム認証](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="149fb-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="149fb-172">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="149fb-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
