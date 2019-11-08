---
title: <message> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: 5a4a4e8b645ee2c607988ac3031af537c93ca8c0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736751"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="9d62e-102">\<netMsmqBinding の \<メッセージ > ></span><span class="sxs-lookup"><span data-stu-id="9d62e-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="9d62e-103">この `netMsmqBinding` バインディングでの SOAP メッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

<span data-ttu-id="9d62e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d62e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9d62e-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9d62e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9d62e-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9d62e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9d62e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9d62e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="9d62e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="9d62e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9d62e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9d62e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="9d62e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**メッセージ >**</span><span class="sxs-lookup"><span data-stu-id="9d62e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="9d62e-111">構文</span><span class="sxs-lookup"><span data-stu-id="9d62e-111">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9d62e-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9d62e-112">Attributes and Elements</span></span>

<span data-ttu-id="9d62e-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-113">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d62e-114">属性</span><span class="sxs-lookup"><span data-stu-id="9d62e-114">Attributes</span></span>

|<span data-ttu-id="9d62e-115">属性</span><span class="sxs-lookup"><span data-stu-id="9d62e-115">Attribute</span></span>|<span data-ttu-id="9d62e-116">説明</span><span class="sxs-lookup"><span data-stu-id="9d62e-116">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="9d62e-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="9d62e-117">algorithmSuite</span></span>|<span data-ttu-id="9d62e-118">MSMQ トランスポートを介して送信されるメッセージにメッセージ ベースのセキュリティを実現するために使用されるメッセージの暗号化およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-118">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="9d62e-119">既定値は `Aes256`です。</span><span class="sxs-lookup"><span data-stu-id="9d62e-119">The default value is `Aes256`.</span></span> <span data-ttu-id="9d62e-120">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="9d62e-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="9d62e-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="9d62e-121">clientCredentialType</span></span>|<span data-ttu-id="9d62e-122">MSMQ トランスポートで送信されるメッセージに対してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-122">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="9d62e-123">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="9d62e-123">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9d62e-124">-None: サービスが匿名クライアントと対話できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9d62e-124">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="9d62e-125">サービスとクライアントはいずれも資格情報を要求しません。</span><span class="sxs-lookup"><span data-stu-id="9d62e-125">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="9d62e-126">-Windows: これにより、Windows 資格情報の認証済みコンテキストで SOAP 交換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9d62e-126">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="9d62e-127">これは、常に Kerberos ベースの認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-127">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="9d62e-128">-UserName: これにより、サービスは、ユーザー名資格情報を使用してクライアントの認証を要求できます。</span><span class="sxs-lookup"><span data-stu-id="9d62e-128">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="9d62e-129">この場合の資格情報は、`clientCredentials` の動作を使用して指定する必要があり**ます。注意:** WINDOWS COMMUNICATION FOUNDATION (WCF) では、パスワードダイジェストの送信や、パスワードを使用したキーの派生、およびメッセージセキュリティのためのこのようなキーの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d62e-129">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="9d62e-130">そのため、ユーザー名の資格情報を使用する場合、WCF は exchange がセキュリティで保護されるように強制します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-130">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="9d62e-131">このモードは、サービス証明書が、`clientCredential` 動作および `serviceCertificate` を使用してクライアント側で指定されることを要求します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-131">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="9d62e-132">-Certificate: これにより、サービスは、証明書を使用してクライアントを認証するよう要求できます。</span><span class="sxs-lookup"><span data-stu-id="9d62e-132">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="9d62e-133">この場合のクライアント資格情報は、`clientCredentials` 動作を使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d62e-133">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="9d62e-134">この場合のサービス資格情報は、`clientCredentials` を指定して `serviceCertificate` 動作を使用することで、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d62e-134">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="9d62e-135">-CardSpace: サービスでは、クライアントが CardSpace を使用して認証されるように要求できます。</span><span class="sxs-lookup"><span data-stu-id="9d62e-135">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="9d62e-136">`serviceCertificate` は、`clientCredential` 動作で提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d62e-136">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="9d62e-137">既定値は `Windows`です。</span><span class="sxs-lookup"><span data-stu-id="9d62e-137">The default value is `Windows`.</span></span> <span data-ttu-id="9d62e-138">この属性は <xref:System.ServiceModel.MessageCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="9d62e-138">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9d62e-139">子要素</span><span class="sxs-lookup"><span data-stu-id="9d62e-139">Child Elements</span></span>

<span data-ttu-id="9d62e-140">None</span><span class="sxs-lookup"><span data-stu-id="9d62e-140">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d62e-141">親要素</span><span class="sxs-lookup"><span data-stu-id="9d62e-141">Parent Elements</span></span>

|<span data-ttu-id="9d62e-142">要素</span><span class="sxs-lookup"><span data-stu-id="9d62e-142">Element</span></span>|<span data-ttu-id="9d62e-143">説明</span><span class="sxs-lookup"><span data-stu-id="9d62e-143">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d62e-144">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="9d62e-144">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="9d62e-145">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9d62e-145">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9d62e-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d62e-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="9d62e-147">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="9d62e-147">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="9d62e-148">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="9d62e-148">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9d62e-149">バインディング</span><span class="sxs-lookup"><span data-stu-id="9d62e-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9d62e-150">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="9d62e-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9d62e-151">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="9d62e-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9d62e-152">\<binding ></span><span class="sxs-lookup"><span data-stu-id="9d62e-152">\<binding></span></span>](bindings.md)
