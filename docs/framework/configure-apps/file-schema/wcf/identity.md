---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 15c9e38a141fc294c47863b1a932711444ac079a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855156"
---
# \<identity>
<span data-ttu-id="76315-101">ID 要素を使用すると、クライアント開発者は予想されるサービスの ID をデザイン時に指定できます。</span><span class="sxs-lookup"><span data-stu-id="76315-101">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="76315-102">クライアントとサービスの間のハンドシェイクプロセスでは、Windows Communication Foundation (WCF) インフラストラクチャによって、予期されるサービスの id がこの要素の値と一致することが保証されるため、認証することができます。</span><span class="sxs-lookup"><span data-stu-id="76315-102">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="76315-103">詳細については、「[サービス id と認証](../../../wcf/feature-details/service-identity-and-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76315-103">For more information, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<identity>**  
  
## <a name="syntax"></a><span data-ttu-id="76315-104">構文</span><span class="sxs-lookup"><span data-stu-id="76315-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76315-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="76315-105">Attributes and Elements</span></span>  
 <span data-ttu-id="76315-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="76315-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="76315-107">属性</span><span class="sxs-lookup"><span data-stu-id="76315-107">Attributes</span></span>  
 <span data-ttu-id="76315-108">なし。</span><span class="sxs-lookup"><span data-stu-id="76315-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="76315-109">子要素</span><span class="sxs-lookup"><span data-stu-id="76315-109">Child Elements</span></span>  
  
|<span data-ttu-id="76315-110">要素</span><span class="sxs-lookup"><span data-stu-id="76315-110">Element</span></span>|<span data-ttu-id="76315-111">説明</span><span class="sxs-lookup"><span data-stu-id="76315-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76315-112">証明書 (certificate)</span><span class="sxs-lookup"><span data-stu-id="76315-112">certificate</span></span>|<span data-ttu-id="76315-113">X.509 証明書の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-113">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="76315-114">この要素は <xref:System.ServiceModel.Configuration.CertificateElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="76315-114">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="76315-115">この要素には、この証明書でエンコードされる値を指定する文字列の `encodedValue` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76315-115">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="76315-116">certificateReference</span><span class="sxs-lookup"><span data-stu-id="76315-116">certificateReference</span></span>|<span data-ttu-id="76315-117">X.509 証明書検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-117">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="76315-118">この要素は <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="76315-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="76315-119">dns</span><span class="sxs-lookup"><span data-stu-id="76315-119">dns</span></span>|<span data-ttu-id="76315-120">サービスの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-120">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="76315-121">この要素には、実際の ID を含む文字列の `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76315-121">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="76315-122">rsa</span><span class="sxs-lookup"><span data-stu-id="76315-122">rsa</span></span>|<span data-ttu-id="76315-123">クライアントに対するサービスの認証に使用される X.509 証明書の RSA フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-123">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="76315-124">この要素には、実際の ID を含む文字列の `value` 属性が含まれています</span><span class="sxs-lookup"><span data-stu-id="76315-124">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="76315-125">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="76315-125">servicePrincipalName</span></span>|<span data-ttu-id="76315-126">サーバー プリンシパル名 (SPN) ID を指定します。これは、サービスのインスタンスを一意に識別するために、クライアントにより使用されるプリンシパル名です。</span><span class="sxs-lookup"><span data-stu-id="76315-126">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="76315-127">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76315-127">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="76315-128">この要素は <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="76315-128">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="76315-129">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="76315-129">userPrincipalName</span></span>|<span data-ttu-id="76315-130">ユーザー プリンシパル名 (UPN) ID を指定します。これは、ネットワーク上のユーザーのログオン名の種類です。</span><span class="sxs-lookup"><span data-stu-id="76315-130">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="76315-131">ユーザープリンシパル名は、Active Directory で使用されるユーザーオブジェクト名の後にアットマーク () が続き、 \@ 通常はドメイン名システムの親ドメインで構成されます。</span><span class="sxs-lookup"><span data-stu-id="76315-131">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="76315-132">たとえば、Fabrikam.com ドメインツリーの Jeff には、ユーザープリンシパル名が含まれている場合があり [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com) ます。</span><span class="sxs-lookup"><span data-stu-id="76315-132">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="76315-133">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76315-133">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="76315-134">この要素は <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="76315-134">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="76315-135">親要素</span><span class="sxs-lookup"><span data-stu-id="76315-135">Parent Elements</span></span>  
  
|<span data-ttu-id="76315-136">要素</span><span class="sxs-lookup"><span data-stu-id="76315-136">Element</span></span>|<span data-ttu-id="76315-137">説明</span><span class="sxs-lookup"><span data-stu-id="76315-137">Description</span></span>|  
|-------------|-----------------|  
|[\<custom>](custom.md)|<span data-ttu-id="76315-138">netPeerTcpBinding のカスタム ピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-138">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[\<endpoint>](endpoint-element.md)|<span data-ttu-id="76315-139">サービスエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="76315-139">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="76315-140">\<endpoint>の\<client></span><span class="sxs-lookup"><span data-stu-id="76315-140">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="76315-141">チャネルエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="76315-141">Configures channel endpoints.</span></span>|  
|[\<issuer>](issuer.md)|<span data-ttu-id="76315-142">フェデレーション サービスのセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-142">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[\<issuerMetadata>](issuermetadata.md)|<span data-ttu-id="76315-143">フェデレーション サービスのセキュリティ トークン サービス (STS) のメタデータ エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-143">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|<span data-ttu-id="76315-144">カスタム バインドで発行済みトークンのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="76315-144">Defines parameters for an issued token in a custom binding.</span></span>|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="76315-145">ローカル セキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="76315-145">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="76315-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="76315-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="76315-147">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="76315-147">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="76315-148">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="76315-148">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
