---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: d5d06953c67b90e8367f2c0d01a670a46f487526
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925424"
---
# <a name="identity"></a><span data-ttu-id="3628f-101">\<identity></span><span class="sxs-lookup"><span data-stu-id="3628f-101">\<identity></span></span>
<span data-ttu-id="3628f-102">ID 要素を使用すると、クライアント開発者は予想されるサービスの ID をデザイン時に指定できます。</span><span class="sxs-lookup"><span data-stu-id="3628f-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="3628f-103">クライアントとサービスの間のハンドシェイクプロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、予期されるサービスの id がこの要素の値と一致することが保証されるため、認証することができます。</span><span class="sxs-lookup"><span data-stu-id="3628f-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="3628f-104">詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3628f-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="3628f-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3628f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="3628f-106">\<client></span><span class="sxs-lookup"><span data-stu-id="3628f-106">\<client></span></span>  
<span data-ttu-id="3628f-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="3628f-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3628f-108">構文</span><span class="sxs-lookup"><span data-stu-id="3628f-108">Syntax</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="String" />
  <certificateReference findValue="String"
                        isChainIncluded="Boolean"
                        storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                        storeLocation="LocalMachine/CurrentUser"
                        X509FindType="Enumeration" />
  <dns value="String" />
  <rsa value="String" />
  <servicePrincipalName value="String" />
  <usePrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3628f-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3628f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3628f-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3628f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3628f-111">属性</span><span class="sxs-lookup"><span data-stu-id="3628f-111">Attributes</span></span>  
 <span data-ttu-id="3628f-112">なし。</span><span class="sxs-lookup"><span data-stu-id="3628f-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3628f-113">子要素</span><span class="sxs-lookup"><span data-stu-id="3628f-113">Child Elements</span></span>  
  
|<span data-ttu-id="3628f-114">要素</span><span class="sxs-lookup"><span data-stu-id="3628f-114">Element</span></span>|<span data-ttu-id="3628f-115">説明</span><span class="sxs-lookup"><span data-stu-id="3628f-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3628f-116">certificate</span><span class="sxs-lookup"><span data-stu-id="3628f-116">certificate</span></span>|<span data-ttu-id="3628f-117">X.509 証明書の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="3628f-118">この要素は <xref:System.ServiceModel.Configuration.CertificateElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3628f-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="3628f-119">この要素には、この証明書でエンコードされる値を指定する文字列の `encodedValue` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3628f-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="3628f-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="3628f-120">certificateReference</span></span>|<span data-ttu-id="3628f-121">X.509 証明書検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="3628f-122">この要素は <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3628f-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="3628f-123">dns</span><span class="sxs-lookup"><span data-stu-id="3628f-123">dns</span></span>|<span data-ttu-id="3628f-124">サービスの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="3628f-125">この要素には、実際の ID を含む文字列の `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3628f-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="3628f-126">rsa</span><span class="sxs-lookup"><span data-stu-id="3628f-126">rsa</span></span>|<span data-ttu-id="3628f-127">クライアントに対するサービスの認証に使用される X.509 証明書の RSA フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="3628f-128">この要素には、実際の ID を含む文字列の `value` 属性が含まれています</span><span class="sxs-lookup"><span data-stu-id="3628f-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="3628f-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="3628f-129">servicePrincipalName</span></span>|<span data-ttu-id="3628f-130">サーバー プリンシパル名 (SPN) ID を指定します。これは、サービスのインスタンスを一意に識別するために、クライアントにより使用されるプリンシパル名です。</span><span class="sxs-lookup"><span data-stu-id="3628f-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="3628f-131">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3628f-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="3628f-132">この要素は <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3628f-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="3628f-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="3628f-133">userPrincipalName</span></span>|<span data-ttu-id="3628f-134">ユーザー プリンシパル名 (UPN) ID を指定します。これは、ネットワーク上のユーザーのログオン名の種類です。</span><span class="sxs-lookup"><span data-stu-id="3628f-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="3628f-135">ユーザープリンシパル名は、Active Directory で使用されるユーザーオブジェクト名の後にアットマーク (\@) が続き、通常はドメイン名システムの親ドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="3628f-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="3628f-136">たとえば、Fabrikam.com ドメインツリーの Jeff には、ユーザープリンシパル名[jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="3628f-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="3628f-137">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3628f-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="3628f-138">この要素は <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="3628f-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3628f-139">親要素</span><span class="sxs-lookup"><span data-stu-id="3628f-139">Parent Elements</span></span>  
  
|<span data-ttu-id="3628f-140">要素</span><span class="sxs-lookup"><span data-stu-id="3628f-140">Element</span></span>|<span data-ttu-id="3628f-141">説明</span><span class="sxs-lookup"><span data-stu-id="3628f-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3628f-142">\<custom></span><span class="sxs-lookup"><span data-stu-id="3628f-142">\<custom></span></span>](custom.md)|<span data-ttu-id="3628f-143">netPeerTcpBinding のカスタム ピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="3628f-144">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="3628f-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="3628f-145">サービスエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3628f-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="3628f-146">\<クライアント > の\<エンドポイント ></span><span class="sxs-lookup"><span data-stu-id="3628f-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="3628f-147">チャネルエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="3628f-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="3628f-148">\<issuer></span><span class="sxs-lookup"><span data-stu-id="3628f-148">\<issuer></span></span>](issuer.md)|<span data-ttu-id="3628f-149">フェデレーション サービスのセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="3628f-150">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="3628f-150">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="3628f-151">フェデレーション サービスのセキュリティ トークン サービス (STS) のメタデータ エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="3628f-152">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="3628f-152">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="3628f-153">カスタム バインドで発行済みトークンのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="3628f-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="3628f-154">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="3628f-154">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="3628f-155">ローカル セキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="3628f-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3628f-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="3628f-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="3628f-157">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="3628f-157">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3628f-158">アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="3628f-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
