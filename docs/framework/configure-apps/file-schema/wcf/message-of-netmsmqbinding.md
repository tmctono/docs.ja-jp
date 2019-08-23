---
title: <message> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: b163dcb08e9656e3bde9c7fbb71fa1c92c9957ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931517"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="39aaf-102">\<netmsmqbinding \<> のメッセージ ></span><span class="sxs-lookup"><span data-stu-id="39aaf-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="39aaf-103">この `netMsmqBinding` バインディングでの SOAP メッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="39aaf-104">構文</span><span class="sxs-lookup"><span data-stu-id="39aaf-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="39aaf-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="39aaf-105">Attributes and Elements</span></span>

<span data-ttu-id="39aaf-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="39aaf-107">属性</span><span class="sxs-lookup"><span data-stu-id="39aaf-107">Attributes</span></span>

|<span data-ttu-id="39aaf-108">属性</span><span class="sxs-lookup"><span data-stu-id="39aaf-108">Attribute</span></span>|<span data-ttu-id="39aaf-109">説明</span><span class="sxs-lookup"><span data-stu-id="39aaf-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="39aaf-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="39aaf-110">algorithmSuite</span></span>|<span data-ttu-id="39aaf-111">MSMQ トランスポートを介して送信されるメッセージにメッセージ ベースのセキュリティを実現するために使用されるメッセージの暗号化およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="39aaf-112">既定値は `Aes256` です。</span><span class="sxs-lookup"><span data-stu-id="39aaf-112">The default value is `Aes256`.</span></span> <span data-ttu-id="39aaf-113">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="39aaf-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="39aaf-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="39aaf-114">clientCredentialType</span></span>|<span data-ttu-id="39aaf-115">MSMQ トランスポートで送信されるメッセージに対してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="39aaf-116">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39aaf-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="39aaf-117">存在サービスが匿名クライアントと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="39aaf-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="39aaf-118">サービスとクライアントはいずれも資格情報を要求しません。</span><span class="sxs-lookup"><span data-stu-id="39aaf-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="39aaf-119">ウィンドウこれにより、Windows 資格情報の認証済みコンテキストで SOAP 交換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="39aaf-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="39aaf-120">これは、常に Kerberos ベースの認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="39aaf-121">ユーザー名これにより、サービスは、ユーザー名資格情報を使用したクライアントの認証を要求できます。</span><span class="sxs-lookup"><span data-stu-id="39aaf-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="39aaf-122">この場合の資格情報は、 `clientCredentials`動作に注意して指定する必要があり**ます。** Windows Communication Foundation (WCF) では、パスワードダイジェストの送信や、パスワードを使用したキーの派生、およびメッセージセキュリティのためのこのようなキーの使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="39aaf-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="39aaf-123">そのため、ユーザー名の資格情報を使用する場合、WCF は exchange がセキュリティで保護されるように強制します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="39aaf-124">このモードは、サービス証明書が、`clientCredential` 動作および `serviceCertificate` を使用してクライアント側で指定されることを要求します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="39aaf-125">証明これにより、サービスは、クライアントが証明書を使用して認証されるように要求できます。</span><span class="sxs-lookup"><span data-stu-id="39aaf-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="39aaf-126">この場合のクライアント資格情報は、`clientCredentials` 動作を使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39aaf-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="39aaf-127">この場合のサービス資格情報は、`clientCredentials` を指定して `serviceCertificate` 動作を使用することで、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39aaf-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="39aaf-128">CardSpaceこれにより、サービスは、クライアントが CardSpace を使用して認証されるように要求できます。</span><span class="sxs-lookup"><span data-stu-id="39aaf-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="39aaf-129">`serviceCertificate` は、`clientCredential` 動作で提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="39aaf-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="39aaf-130">既定値は `Windows` です。</span><span class="sxs-lookup"><span data-stu-id="39aaf-130">The default value is `Windows`.</span></span> <span data-ttu-id="39aaf-131">この属性は <xref:System.ServiceModel.MessageCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="39aaf-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="39aaf-132">子要素</span><span class="sxs-lookup"><span data-stu-id="39aaf-132">Child Elements</span></span>

<span data-ttu-id="39aaf-133">なし</span><span class="sxs-lookup"><span data-stu-id="39aaf-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="39aaf-134">親要素</span><span class="sxs-lookup"><span data-stu-id="39aaf-134">Parent Elements</span></span>

|<span data-ttu-id="39aaf-135">要素</span><span class="sxs-lookup"><span data-stu-id="39aaf-135">Element</span></span>|<span data-ttu-id="39aaf-136">説明</span><span class="sxs-lookup"><span data-stu-id="39aaf-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="39aaf-137">\<security></span><span class="sxs-lookup"><span data-stu-id="39aaf-137">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="39aaf-138">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="39aaf-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="39aaf-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="39aaf-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="39aaf-140">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="39aaf-140">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="39aaf-141">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="39aaf-141">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="39aaf-142">バインディング</span><span class="sxs-lookup"><span data-stu-id="39aaf-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="39aaf-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="39aaf-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="39aaf-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="39aaf-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="39aaf-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="39aaf-145">\<binding></span></span>](../../../misc/binding.md)
