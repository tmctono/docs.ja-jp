---
title: <identity>
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 0f5eace346fd0ed2c0532fb602585c4593d97291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756690"
---
# <a name="identity"></a><span data-ttu-id="9d125-101">\<identity></span><span class="sxs-lookup"><span data-stu-id="9d125-101">\<identity></span></span>
<span data-ttu-id="9d125-102">ID 要素を使用すると、クライアント開発者は予想されるサービスの ID をデザイン時に指定できます。</span><span class="sxs-lookup"><span data-stu-id="9d125-102">The identity element allows a client developer to specify at design time the expected identity of the service.</span></span> <span data-ttu-id="9d125-103">クライアントとサービス間のハンドシェイク プロセスで Windows Communication Foundation (WCF) インフラストラクチャが予期されるサービスと一致する、この要素の値の id を保証して、そのため、認証されたことができます。</span><span class="sxs-lookup"><span data-stu-id="9d125-103">In the handshake process between the client and service, the Windows Communication Foundation (WCF) infrastructure will ensure that the identity of the expected service matches the values of this element, and thus can be authenticated.</span></span> <span data-ttu-id="9d125-104">詳細については、次を参照してください。[サービス Id と認証](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)します。</span><span class="sxs-lookup"><span data-stu-id="9d125-104">For more information, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="9d125-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9d125-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9d125-106">\<client></span><span class="sxs-lookup"><span data-stu-id="9d125-106">\<client></span></span>  
<span data-ttu-id="9d125-107">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="9d125-107">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d125-108">構文</span><span class="sxs-lookup"><span data-stu-id="9d125-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d125-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9d125-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9d125-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d125-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d125-111">属性</span><span class="sxs-lookup"><span data-stu-id="9d125-111">Attributes</span></span>  
 <span data-ttu-id="9d125-112">なし。</span><span class="sxs-lookup"><span data-stu-id="9d125-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9d125-113">子要素</span><span class="sxs-lookup"><span data-stu-id="9d125-113">Child Elements</span></span>  
  
|<span data-ttu-id="9d125-114">要素</span><span class="sxs-lookup"><span data-stu-id="9d125-114">Element</span></span>|<span data-ttu-id="9d125-115">説明</span><span class="sxs-lookup"><span data-stu-id="9d125-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d125-116">certificate</span><span class="sxs-lookup"><span data-stu-id="9d125-116">certificate</span></span>|<span data-ttu-id="9d125-117">X.509 証明書の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-117">Specifies settings of an X.509 certificate.</span></span> <span data-ttu-id="9d125-118">この要素は <xref:System.ServiceModel.Configuration.CertificateElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9d125-118">This element is of type <xref:System.ServiceModel.Configuration.CertificateElement>.</span></span> <span data-ttu-id="9d125-119">この要素には、この証明書でエンコードされる値を指定する文字列の `encodedValue` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d125-119">It contains an attribute `encodedValue` that is a string, which specifies the value encoded by this certificate.</span></span>|  
|<span data-ttu-id="9d125-120">certificateReference</span><span class="sxs-lookup"><span data-stu-id="9d125-120">certificateReference</span></span>|<span data-ttu-id="9d125-121">X.509 証明書検証の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-121">Specifies settings for X.509 certificate validation.</span></span> <span data-ttu-id="9d125-122">この要素は <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9d125-122">This element is of type <xref:System.ServiceModel.Configuration.CertificateReferenceElement>.</span></span>|  
|<span data-ttu-id="9d125-123">dns</span><span class="sxs-lookup"><span data-stu-id="9d125-123">dns</span></span>|<span data-ttu-id="9d125-124">サービスの認証に使用される X.509 証明書の DNS を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-124">Specifies the DNS of an X.509 certificate used to authenticate a service.</span></span> <span data-ttu-id="9d125-125">この要素には、実際の ID を含む文字列の `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d125-125">This element contains an attribute `value` that is a string, and contains the actual identity.</span></span>|  
|<span data-ttu-id="9d125-126">rsa</span><span class="sxs-lookup"><span data-stu-id="9d125-126">rsa</span></span>|<span data-ttu-id="9d125-127">クライアントに対するサービスの認証に使用される X.509 証明書の RSA フィールドの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-127">Specifies the value of the RSA field of an X.509 certificate used to authenticate a service to a client.</span></span> <span data-ttu-id="9d125-128">この要素には、実際の ID を含む文字列の `value` 属性が含まれています</span><span class="sxs-lookup"><span data-stu-id="9d125-128">This element contains an attribute `value` that is a string, and contains the actual identity</span></span>|  
|<span data-ttu-id="9d125-129">servicePrincipalName</span><span class="sxs-lookup"><span data-stu-id="9d125-129">servicePrincipalName</span></span>|<span data-ttu-id="9d125-130">サーバー プリンシパル名 (SPN) ID を指定します。これは、サービスのインスタンスを一意に識別するために、クライアントにより使用されるプリンシパル名です。</span><span class="sxs-lookup"><span data-stu-id="9d125-130">Specifies a server principal name (SPN) identity, which is the principal name used by a client to uniquely identify an instance of a service.</span></span> <span data-ttu-id="9d125-131">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d125-131">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="9d125-132">この要素は <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9d125-132">This element is of type <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>.</span></span>|  
|<span data-ttu-id="9d125-133">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="9d125-133">userPrincipalName</span></span>|<span data-ttu-id="9d125-134">ユーザー プリンシパル名 (UPN) ID を指定します。これは、ネットワーク上のユーザーのログオン名の種類です。</span><span class="sxs-lookup"><span data-stu-id="9d125-134">Specifies a user principal name (UPN) identity, which is the logon name type of a user on a network.</span></span> <span data-ttu-id="9d125-135">ユーザー プリンシパル名から成る後に、Active Directory で使用されるユーザー オブジェクト名、アット マーク (\@) およびドメインを親通常は、次に、ドメイン ネーム システム。</span><span class="sxs-lookup"><span data-stu-id="9d125-135">The user principal name consists of the user object name used in Active Directory, followed by the at symbol (\@) and then, typically, the Domain Name System parent domain.</span></span> <span data-ttu-id="9d125-136">たとえば、Fabrikam.com ドメイン ツリーの Jeff のユーザー プリンシパル名がある[ jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com)します。</span><span class="sxs-lookup"><span data-stu-id="9d125-136">For example, Jeff in the Fabrikam.com domain tree might have the user principal name [jeff@fabrikam.com](mailto:jeffsmith@fabrikam.com).</span></span>  <span data-ttu-id="9d125-137">この要素には、実際のプリンシパル名が文字列で含まれている `value` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9d125-137">This element contains an attribute `value` that is a string, and contains the actual principal name.</span></span> <span data-ttu-id="9d125-138">この要素は <xref:System.ServiceModel.Configuration.UserPrincipalNameElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9d125-138">This element is of type <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9d125-139">親要素</span><span class="sxs-lookup"><span data-stu-id="9d125-139">Parent Elements</span></span>  
  
|<span data-ttu-id="9d125-140">要素</span><span class="sxs-lookup"><span data-stu-id="9d125-140">Element</span></span>|<span data-ttu-id="9d125-141">説明</span><span class="sxs-lookup"><span data-stu-id="9d125-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d125-142">\<custom></span><span class="sxs-lookup"><span data-stu-id="9d125-142">\<custom></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|<span data-ttu-id="9d125-143">netPeerTcpBinding のカスタム ピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-143">Specifies a custom peer resolver for a netPeerTcpBinding.</span></span>|  
|[<span data-ttu-id="9d125-144">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="9d125-144">\<endpoint></span></span>](endpoint-element.md)|<span data-ttu-id="9d125-145">サービス エンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d125-145">Configures service endpoints.</span></span>|  
|[<span data-ttu-id="9d125-146">\<エンドポイント > の\<クライアント ></span><span class="sxs-lookup"><span data-stu-id="9d125-146">\<endpoint> of \<client></span></span>](endpoint-of-client.md)|<span data-ttu-id="9d125-147">チャネルのエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="9d125-147">Configures channel endpoints.</span></span>|  
|[<span data-ttu-id="9d125-148">\<issuer></span><span class="sxs-lookup"><span data-stu-id="9d125-148">\<issuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|<span data-ttu-id="9d125-149">フェデレーション サービスのセキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-149">Specifies the Security Token Service (STS) for the federated service.</span></span>|  
|[<span data-ttu-id="9d125-150">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="9d125-150">\<issuerMetadata></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|<span data-ttu-id="9d125-151">フェデレーション サービスのセキュリティ トークン サービス (STS) のメタデータ エンドポイントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-151">Specifies the metadata endpoint for the Security Token Service (STS) of a federated service.</span></span>|  
|[<span data-ttu-id="9d125-152">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="9d125-152">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="9d125-153">カスタム バインドで発行済みトークンのパラメーターを定義します。</span><span class="sxs-lookup"><span data-stu-id="9d125-153">Defines parameters for an issued token in a custom binding.</span></span>|  
|[<span data-ttu-id="9d125-154">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="9d125-154">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="9d125-155">ローカル セキュリティ トークン サービス (STS) を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d125-155">Specifies a local Security Token Service (STS).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d125-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d125-156">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- [<span data-ttu-id="9d125-157">サービス ID と認証</span><span class="sxs-lookup"><span data-stu-id="9d125-157">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9d125-158">エンドポイント:アドレス、バインディング、およびコントラクト</span><span class="sxs-lookup"><span data-stu-id="9d125-158">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
