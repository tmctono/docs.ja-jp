---
title: <message> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 306bc56820cdbcba17cce9fc50d426260eb0e0d4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360668"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="2fa35-102">\<メッセージ > の\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="2fa35-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="2fa35-103">この `netMsmqBinding` バインディングでの SOAP メッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="2fa35-104">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="2fa35-104">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="2fa35-105">\<bindings>\\</span><span class="sxs-lookup"><span data-stu-id="2fa35-105">\<bindings>\\</span></span>
<span data-ttu-id="2fa35-106">\<netMsmqBinding>\\</span><span class="sxs-lookup"><span data-stu-id="2fa35-106">\<netMsmqBinding>\\</span></span>
<span data-ttu-id="2fa35-107">\<バインド > \\</span><span class="sxs-lookup"><span data-stu-id="2fa35-107">\<binding>\\</span></span>
<span data-ttu-id="2fa35-108">\<security>\\</span><span class="sxs-lookup"><span data-stu-id="2fa35-108">\<security>\\</span></span>
<span data-ttu-id="2fa35-109">\<message></span><span class="sxs-lookup"><span data-stu-id="2fa35-109">\<message></span></span>

## <a name="syntax"></a><span data-ttu-id="2fa35-110">構文</span><span class="sxs-lookup"><span data-stu-id="2fa35-110">Syntax</span></span>

```xml
<netMsmqBinding>
  <binding>
    <security>
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
    </security>
  </binding>
</netMsmqBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2fa35-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="2fa35-111">Attributes and Elements</span></span>

<span data-ttu-id="2fa35-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-112">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2fa35-113">属性</span><span class="sxs-lookup"><span data-stu-id="2fa35-113">Attributes</span></span>

|<span data-ttu-id="2fa35-114">属性</span><span class="sxs-lookup"><span data-stu-id="2fa35-114">Attribute</span></span>|<span data-ttu-id="2fa35-115">説明</span><span class="sxs-lookup"><span data-stu-id="2fa35-115">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2fa35-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="2fa35-116">algorithmSuite</span></span>|<span data-ttu-id="2fa35-117">MSMQ トランスポートを介して送信されるメッセージにメッセージ ベースのセキュリティを実現するために使用されるメッセージの暗号化およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-117">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="2fa35-118">既定値は `Aes256` です。</span><span class="sxs-lookup"><span data-stu-id="2fa35-118">The default value is `Aes256`.</span></span> <span data-ttu-id="2fa35-119">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="2fa35-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="2fa35-120">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2fa35-120">clientCredentialType</span></span>|<span data-ttu-id="2fa35-121">MSMQ トランスポートで送信されるメッセージに対してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-121">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="2fa35-122">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="2fa35-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="2fa35-123">-None。サービスが匿名クライアントと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2fa35-123">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="2fa35-124">サービスとクライアントはいずれも資格情報を要求しません。</span><span class="sxs-lookup"><span data-stu-id="2fa35-124">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="2fa35-125">-Windows:これにより、SOAP 交換を Windows 資格情報の認証済みコンテキストの下にあることができます。</span><span class="sxs-lookup"><span data-stu-id="2fa35-125">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="2fa35-126">これは、常に Kerberos ベースの認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-126">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="2fa35-127">-ユーザー名:これにより、サービスを必要とする UserName 資格情報を使用してクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-127">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="2fa35-128">この場合、資格情報を使用して指定する必要があります、`clientCredentials`動作**注意が必要です。** Windows Communication Foundation (WCF) は、パスワード ダイジェストの送信、またはパスワードを使用して、このようなキーを使用して、メッセージ セキュリティのためのキーの派生をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2fa35-128">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="2fa35-129">そのため、WCF は、UserName 資格情報を使用する場合、exchange がセキュリティで保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-129">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="2fa35-130">このモードは、サービス証明書が、`clientCredential` 動作および `serviceCertificate` を使用してクライアント側で指定されることを要求します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-130">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="2fa35-131">-証明書:これにより、必要とするサービス証明書を使用してクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-131">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="2fa35-132">この場合のクライアント資格情報は、`clientCredentials` 動作を使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fa35-132">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="2fa35-133">この場合のサービス資格情報は、`clientCredentials` を指定して `serviceCertificate` 動作を使用することで、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fa35-133">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="2fa35-134">-CardSpace:これにより、サービスが要求、CardSpace を使用してクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-134">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="2fa35-135">`serviceCertificate` は、`clientCredential` 動作で提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2fa35-135">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="2fa35-136">既定値は `Windows` です。</span><span class="sxs-lookup"><span data-stu-id="2fa35-136">The default value is `Windows`.</span></span> <span data-ttu-id="2fa35-137">この属性は <xref:System.ServiceModel.MessageCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="2fa35-137">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2fa35-138">子要素</span><span class="sxs-lookup"><span data-stu-id="2fa35-138">Child Elements</span></span>

<span data-ttu-id="2fa35-139">なし</span><span class="sxs-lookup"><span data-stu-id="2fa35-139">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2fa35-140">親要素</span><span class="sxs-lookup"><span data-stu-id="2fa35-140">Parent Elements</span></span>

|<span data-ttu-id="2fa35-141">要素</span><span class="sxs-lookup"><span data-stu-id="2fa35-141">Element</span></span>|<span data-ttu-id="2fa35-142">説明</span><span class="sxs-lookup"><span data-stu-id="2fa35-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="2fa35-143">\<security></span><span class="sxs-lookup"><span data-stu-id="2fa35-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="2fa35-144">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="2fa35-144">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2fa35-145">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fa35-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="2fa35-146">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="2fa35-146">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="2fa35-147">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="2fa35-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2fa35-148">バインディング</span><span class="sxs-lookup"><span data-stu-id="2fa35-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2fa35-149">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="2fa35-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2fa35-150">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="2fa35-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2fa35-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="2fa35-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
