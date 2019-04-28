---
title: <message> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
ms.openlocfilehash: c623b7daf1e91c9c1800b9653525cd51b1087506
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768954"
---
# <a name="message-of-netmsmqbinding"></a><span data-ttu-id="a1369-102">\<メッセージ > の\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="a1369-102">\<message> of \<netMsmqBinding></span></span>

<span data-ttu-id="a1369-103">この `netMsmqBinding` バインディングでの SOAP メッセージ セキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a1369-103">Defines the SOAP message security settings on this `netMsmqBinding` binding.</span></span>

```xml
<system.ServiceModel>
  <bindings>
    <netMsmqBinding>
      <binding>
        <security>
          <message>
```

## <a name="syntax"></a><span data-ttu-id="a1369-104">構文</span><span class="sxs-lookup"><span data-stu-id="a1369-104">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="a1369-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a1369-105">Attributes and Elements</span></span>

<span data-ttu-id="a1369-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a1369-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a1369-107">属性</span><span class="sxs-lookup"><span data-stu-id="a1369-107">Attributes</span></span>

|<span data-ttu-id="a1369-108">属性</span><span class="sxs-lookup"><span data-stu-id="a1369-108">Attribute</span></span>|<span data-ttu-id="a1369-109">説明</span><span class="sxs-lookup"><span data-stu-id="a1369-109">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="a1369-110">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a1369-110">algorithmSuite</span></span>|<span data-ttu-id="a1369-111">MSMQ トランスポートを介して送信されるメッセージにメッセージ ベースのセキュリティを実現するために使用されるメッセージの暗号化およびキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="a1369-111">Sets the message encryption and key-wrap algorithms that are used to achieve message-based security for messages sent over MSMQ transport.</span></span><br /><br /> <span data-ttu-id="a1369-112">既定値は `Aes256` です。</span><span class="sxs-lookup"><span data-stu-id="a1369-112">The default value is `Aes256`.</span></span> <span data-ttu-id="a1369-113">この属性は <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 型です。</span><span class="sxs-lookup"><span data-stu-id="a1369-113">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span>|
|<span data-ttu-id="a1369-114">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="a1369-114">clientCredentialType</span></span>|<span data-ttu-id="a1369-115">MSMQ トランスポートで送信されるメッセージに対してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="a1369-115">Specifies the type of credential to be used when performing client authentication for messages sent over the MSMQ transport.</span></span> <span data-ttu-id="a1369-116">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="a1369-116">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a1369-117">-None。サービスが匿名クライアントと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a1369-117">-   None: This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="a1369-118">サービスとクライアントはいずれも資格情報を要求しません。</span><span class="sxs-lookup"><span data-stu-id="a1369-118">Neither the service nor the client requires a credential.</span></span><br /><span data-ttu-id="a1369-119">-Windows:これにより、SOAP 交換を Windows 資格情報の認証済みコンテキストの下にあることができます。</span><span class="sxs-lookup"><span data-stu-id="a1369-119">-   Windows: This enables the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span> <span data-ttu-id="a1369-120">これは、常に Kerberos ベースの認証を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1369-120">This always performs Kerberos-based authentication.</span></span><br /><span data-ttu-id="a1369-121">-ユーザー名:これにより、サービスを必要とする UserName 資格情報を使用してクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="a1369-121">-   UserName: This enables the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="a1369-122">この場合、資格情報を使用して指定する必要があります、`clientCredentials`動作**注意が必要です。** Windows Communication Foundation (WCF) は、パスワード ダイジェストの送信、またはパスワードを使用して、このようなキーを使用して、メッセージ セキュリティのためのキーの派生をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="a1369-122">The credential in this case needs to be specified using the `clientCredentials` behavior **Caution:**  Windows Communication Foundation (WCF) does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="a1369-123">そのため、WCF は、UserName 資格情報を使用する場合、exchange がセキュリティで保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="a1369-123">Therefore, WCF enforces that the exchange is secured when using UserName credentials.</span></span> <span data-ttu-id="a1369-124">このモードは、サービス証明書が、`clientCredential` 動作および `serviceCertificate` を使用してクライアント側で指定されることを要求します。</span><span class="sxs-lookup"><span data-stu-id="a1369-124">This mode requires that the service certificate be specified on the client side using `clientCredential` behavior and `serviceCertificate`.</span></span> <br /><br /> <span data-ttu-id="a1369-125">-証明書:これにより、必要とするサービス証明書を使用してクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="a1369-125">-   Certificate: This enables the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="a1369-126">この場合のクライアント資格情報は、`clientCredentials` 動作を使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1369-126">The client credential in this case needs to be specified using the `clientCredentials` behavior.</span></span> <span data-ttu-id="a1369-127">この場合のサービス資格情報は、`clientCredentials` を指定して `serviceCertificate` 動作を使用することで、指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1369-127">The service credential in this case needs to be specified using the `clientCredentials` behavior by specifying the `serviceCertificate`.</span></span><br /><span data-ttu-id="a1369-128">-CardSpace:これにより、サービスが要求、CardSpace を使用してクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="a1369-128">-   CardSpace: This allows the service to require that the client be authenticated using a CardSpace.</span></span> <span data-ttu-id="a1369-129">`serviceCertificate` は、`clientCredential` 動作で提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1369-129">The `serviceCertificate` must be provisioned in the `clientCredential` behavior.</span></span><br /><br /> <span data-ttu-id="a1369-130">既定値は `Windows` です。</span><span class="sxs-lookup"><span data-stu-id="a1369-130">The default value is `Windows`.</span></span> <span data-ttu-id="a1369-131">この属性は <xref:System.ServiceModel.MessageCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="a1369-131">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="a1369-132">子要素</span><span class="sxs-lookup"><span data-stu-id="a1369-132">Child Elements</span></span>

<span data-ttu-id="a1369-133">なし</span><span class="sxs-lookup"><span data-stu-id="a1369-133">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a1369-134">親要素</span><span class="sxs-lookup"><span data-stu-id="a1369-134">Parent Elements</span></span>

|<span data-ttu-id="a1369-135">要素</span><span class="sxs-lookup"><span data-stu-id="a1369-135">Element</span></span>|<span data-ttu-id="a1369-136">説明</span><span class="sxs-lookup"><span data-stu-id="a1369-136">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a1369-137">\<security></span><span class="sxs-lookup"><span data-stu-id="a1369-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="a1369-138">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="a1369-138">Defines the security settings for a binding.</span></span>|

## <a name="see-also"></a><span data-ttu-id="a1369-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1369-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>
- <xref:System.ServiceModel.MessageSecurityOverMsmq>
- [<span data-ttu-id="a1369-140">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="a1369-140">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="a1369-141">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="a1369-141">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a1369-142">バインディング</span><span class="sxs-lookup"><span data-stu-id="a1369-142">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a1369-143">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="a1369-143">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a1369-144">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="a1369-144">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a1369-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="a1369-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
