---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855156"
---
# <a name="identity"></a><span data-ttu-id="7b15d-101">\<identity></span><span class="sxs-lookup"><span data-stu-id="7b15d-101">\<identity></span></span>
<span data-ttu-id="7b15d-102">ID 要素を使用すると、クライアント開発者は予想されるサービスの ID をデザイン時に指定できます。</span><span class="sxs-lookup"><span data-stu-id="7b15d-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="7b15d-103">クライアントとサービスの間のハンドシェイクプロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、予期されるサービスの id がこの要素の値と一致することが保証されるため、認証することができます。</span><span class="sxs-lookup"><span data-stu-id="7b15d-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="7b15d-104">詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b15d-104">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="7b15d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b15d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7b15d-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7b15d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7b15d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<クライアント >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="7b15d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="7b15d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<エンドポイント >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="7b15d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="7b15d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<id >**</span><span class="sxs-lookup"><span data-stu-id="7b15d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b15d-110">構文</span><span class="sxs-lookup"><span data-stu-id="7b15d-110">Syntax</span></span>  
  
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
  <userPrincipalName value="String" />
</identity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b15d-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7b15d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7b15d-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b15d-113">属性</span><span class="sxs-lookup"><span data-stu-id="7b15d-113">Attributes</span></span>  
 <span data-ttu-id="7b15d-114">なし。</span><span class="sxs-lookup"><span data-stu-id="7b15d-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7b15d-115">子要素</span><span class="sxs-lookup"><span data-stu-id="7b15d-115">Child Elements</span></span>  
  
|<span data-ttu-id="7b15d-116">要素</span><span class="sxs-lookup"><span data-stu-id="7b15d-116">Element</span></span>|<span data-ttu-id="7b15d-117">説明</span><span class="sxs-lookup"><span data-stu-id="7b15d-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b15d-118">certificate</span><span class="sxs-lookup"><span data-stu-id="7b15d-118">certificate</span></span>|<span data-ttu-id="7b15d-119">X.509 証明書の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-119">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="7b15d-120">この要素は <xref:System.ServiceModel.Configuration.CertificateElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b15d-120">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="7b15d-121">この要素には、この証明書でエンコードされる値を指定する文字列の `encodedValue` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b15d-121">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="7b15d-122">certificateReference</span><span class="sxs-lookup"><span data-stu-id="7b15d-122">certificateReference</span></span>|<span data-ttu-id="7b15d-123">X.509 証明書検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-123">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="7b15d-124">この要素は <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b15d-124">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="7b15d-125">dns</span><span class="sxs-lookup"><span data-stu-id="7b15d-125">dns</span></span>|<span data-ttu-id="7b15d-126">サービスの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-126">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="7b15d-127">この要素には、実際の ID を含む文字列の `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b15d-127">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="7b15d-128">rsa</span><span class="sxs-lookup"><span data-stu-id="7b15d-128">rsa</span></span>|<span data-ttu-id="7b15d-129">クライアントに対するサービスの認証に使用される X.509 証明書の RSA フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-129">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="7b15d-130">この要素には、実際の ID を含む文字列の `value` 属性が含まれています</span><span class="sxs-lookup"><span data-stu-id="7b15d-130">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="7b15d-131">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="7b15d-131">servicePrincipalName</span></span>|<span data-ttu-id="7b15d-132">サーバー プリンシパル名 (SPN) ID を指定します。これは、サービスのインスタンスを一意に識別するために、クライアントにより使用されるプリンシパル名です。</span><span class="sxs-lookup"><span data-stu-id="7b15d-132">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="7b15d-133">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b15d-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="7b15d-134">この要素は <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b15d-134">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="7b15d-135">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7b15d-135">userPrincipalName</span></span>|<span data-ttu-id="7b15d-136">ユーザー プリンシパル名 (UPN) ID を指定します。これは、ネットワーク上のユーザーのログオン名の種類です。</span><span class="sxs-lookup"><span data-stu-id="7b15d-136">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="7b15d-137">ユーザープリンシパル名は、Active Directory で使用されるユーザーオブジェクト名の後にアットマーク (\@) が続き、通常はドメイン名システムの親ドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="7b15d-137">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="7b15d-138">たとえば、Fabrikam.com ドメインツリーの Jeff には、ユーザープリンシパル名[jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)が含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b15d-138">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="7b15d-139">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7b15d-139">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="7b15d-140">この要素は <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7b15d-140">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7b15d-141">親要素</span><span class="sxs-lookup"><span data-stu-id="7b15d-141">Parent Elements</span></span>  
  
|<span data-ttu-id="7b15d-142">要素</span><span class="sxs-lookup"><span data-stu-id="7b15d-142">Element</span></span>|<span data-ttu-id="7b15d-143">説明</span><span class="sxs-lookup"><span data-stu-id="7b15d-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7b15d-144">\<custom></span><span class="sxs-lookup"><span data-stu-id="7b15d-144">\<custom></span></span>](custom.md)|<span data-ttu-id="7b15d-145">netPeerTcpBinding のカスタム ピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-145">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="7b15d-146">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="7b15d-146">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="7b15d-147">サービスエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-147">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="7b15d-148">\<クライアント > の\<エンドポイント ></span><span class="sxs-lookup"><span data-stu-id="7b15d-148">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="7b15d-149">チャネルエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-149">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="7b15d-150">\<issuer></span><span class="sxs-lookup"><span data-stu-id="7b15d-150">\<issuer></span></span>](issuer.md)|<span data-ttu-id="7b15d-151">フェデレーション サービスのセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-151">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="7b15d-152">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="7b15d-152">\<issuerMetadata></span></span>](issuermetadata.md)|<span data-ttu-id="7b15d-153">フェデレーション サービスのセキュリティ トークン サービス (STS) のメタデータ エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-153">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="7b15d-154">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="7b15d-154">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="7b15d-155">カスタム バインドで発行済みトークンのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-155">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="7b15d-156">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="7b15d-156">\<localIssuer></span></span>](localissuer.md)|<span data-ttu-id="7b15d-157">ローカル セキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="7b15d-157">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b15d-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="7b15d-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="7b15d-159">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="7b15d-159">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7b15d-160">アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="7b15d-160">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
