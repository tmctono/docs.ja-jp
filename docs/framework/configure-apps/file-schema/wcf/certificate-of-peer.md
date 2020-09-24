---
title: <certificate> の <peer>
ms.date: 03/30/2017
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
ms.openlocfilehash: 8ec839df02af4a01d31192eebc96e4c5e58313e9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151117"
---
# <a name="certificate-of-peer"></a><span data-ttu-id="72e8f-102">\<certificate> の \<peer></span><span class="sxs-lookup"><span data-stu-id="72e8f-102">\<certificate> of \<peer></span></span>

<span data-ttu-id="72e8f-103">ピアで使用される証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="72e8f-103">Specifies a certificate used by a peer.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="72e8f-104">構文</span><span class="sxs-lookup"><span data-stu-id="72e8f-104">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"
             storeLocation = "CurrentUser/LocalMachine"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72e8f-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="72e8f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="72e8f-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="72e8f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72e8f-107">属性</span><span class="sxs-lookup"><span data-stu-id="72e8f-107">Attributes</span></span>  
  
|<span data-ttu-id="72e8f-108">属性</span><span class="sxs-lookup"><span data-stu-id="72e8f-108">Attribute</span></span>|<span data-ttu-id="72e8f-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="72e8f-109">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="72e8f-110">X.509 証明書ストアで検索する値を含む文字列。</span><span class="sxs-lookup"><span data-stu-id="72e8f-110">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="72e8f-111">属性に格納されている型は、指定された `x509FindType` の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="72e8f-111">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="72e8f-112">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="72e8f-112">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="72e8f-113">クライアントがピアの証明書の検証に使用する X.509 証明書ストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="72e8f-113">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="72e8f-114">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72e8f-114">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="72e8f-115">-LocalMachine: ローカルコンピューターに割り当てられた証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-115">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="72e8f-116">-CurrentUser: 現在のユーザーに割り当てられている証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-116">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="72e8f-117">既定値は LocalMachine です。</span><span class="sxs-lookup"><span data-stu-id="72e8f-117">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="72e8f-118">開く X.509 証明書ストアの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="72e8f-118">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="72e8f-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72e8f-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="72e8f-120">-アドレス帳: 他のユーザーの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-120">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="72e8f-121">-AuthRoot: サードパーティの証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-121">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="72e8f-122">-CertificateAuthority: 中間証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-122">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="72e8f-123">-許可されていません: 失効した証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-123">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="72e8f-124">-My: 個人証明書の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-124">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="72e8f-125">-Root: 信頼されたルート証明機関 (Ca) の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-125">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="72e8f-126">-TrustedPeople: 直接信頼されている人間とリソースの証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-126">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="72e8f-127">-TrustedPublisher: 直接信頼された発行元の証明書ストア。</span><span class="sxs-lookup"><span data-stu-id="72e8f-127">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="72e8f-128">既定値は My です。</span><span class="sxs-lookup"><span data-stu-id="72e8f-128">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="72e8f-129">実行する X.509 検索の種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="72e8f-129">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="72e8f-130">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72e8f-130">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="72e8f-131">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="72e8f-131">-   FindByThumbPrint</span></span><br /><span data-ttu-id="72e8f-132">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="72e8f-132">-   FindBySubjectName</span></span><br /><span data-ttu-id="72e8f-133">-Findbysubjectdistinguishedname です</span><span class="sxs-lookup"><span data-stu-id="72e8f-133">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="72e8f-134">- FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="72e8f-134">-   FindByIssuerName</span></span><br /><span data-ttu-id="72e8f-135">- FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="72e8f-135">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="72e8f-136">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="72e8f-136">-   FindBySerialNumber</span></span><br /><span data-ttu-id="72e8f-137">- FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="72e8f-137">-   FindByTimeValid</span></span><br /><span data-ttu-id="72e8f-138">- FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="72e8f-138">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="72e8f-139">- FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="72e8f-139">-   FindByTemplateName</span></span><br /><span data-ttu-id="72e8f-140">- FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="72e8f-140">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="72e8f-141">- FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="72e8f-141">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="72e8f-142">- FindByExtension</span><span class="sxs-lookup"><span data-stu-id="72e8f-142">-   FindByExtension</span></span><br /><span data-ttu-id="72e8f-143">- FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="72e8f-143">-   FindByKeyUsage</span></span><br /><span data-ttu-id="72e8f-144">- FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="72e8f-144">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="72e8f-145">`findValue` 属性に格納されている型は、指定された `X509FindType` の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="72e8f-145">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="72e8f-146">既定値は FindBySubjectDistinguishedName です。</span><span class="sxs-lookup"><span data-stu-id="72e8f-146">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72e8f-147">子要素</span><span class="sxs-lookup"><span data-stu-id="72e8f-147">Child Elements</span></span>  

 <span data-ttu-id="72e8f-148">なし。</span><span class="sxs-lookup"><span data-stu-id="72e8f-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72e8f-149">親要素</span><span class="sxs-lookup"><span data-stu-id="72e8f-149">Parent Elements</span></span>  
  
|<span data-ttu-id="72e8f-150">要素</span><span class="sxs-lookup"><span data-stu-id="72e8f-150">Element</span></span>|<span data-ttu-id="72e8f-151">説明</span><span class="sxs-lookup"><span data-stu-id="72e8f-151">Description</span></span>|  
|-------------|-----------------|  
|[\<peer>](peer-of-servicecredentials.md)|<span data-ttu-id="72e8f-152">ピア ノードの現在の資格情報を指定します。</span><span class="sxs-lookup"><span data-stu-id="72e8f-152">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72e8f-153">解説</span><span class="sxs-lookup"><span data-stu-id="72e8f-153">Remarks</span></span>  

 <span data-ttu-id="72e8f-154">この構成要素には、ピア メッシュ内の近隣ノードを認証するときに使用される `X509Certificate2` インスタンスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="72e8f-154">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="72e8f-155">ピアツーピアプログラミングの詳細については、「 [ピアツーピアネットワーク](../../../wcf/feature-details/peer-to-peer-networking.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72e8f-155">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e8f-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="72e8f-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- <xref:System.ServiceModel.Security.PeerCredential>
- [<span data-ttu-id="72e8f-157">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="72e8f-157">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="72e8f-158">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="72e8f-158">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="72e8f-159">[ピア チャネル メッセージの認証](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="72e8f-159">[Peer Channel Message Authentication](/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="72e8f-160">[ピア チャネル カスタム認証](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="72e8f-160">[Peer Channel Custom Authentication](/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="72e8f-161">セキュリティによるピア チャネル アプリケーションの保護</span><span class="sxs-lookup"><span data-stu-id="72e8f-161">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
- [<span data-ttu-id="72e8f-162">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="72e8f-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
