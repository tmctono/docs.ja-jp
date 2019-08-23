---
title: <clientCertificate> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 277e5e33bcc7f9d417da7ce24caa4c6200c23e23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919549"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="36216-102">\<serviceCredentials の\<clientCertificate > ></span><span class="sxs-lookup"><span data-stu-id="36216-102">\<clientCertificate> of \<serviceCredentials></span></span>
<span data-ttu-id="36216-103">双方向通信パターンでサービスからクライアントへのメッセージの署名および暗号化に使用される X.509 証明書を定義します。</span><span class="sxs-lookup"><span data-stu-id="36216-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
 <span data-ttu-id="36216-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="36216-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36216-105">\<<behaviors></span><span class="sxs-lookup"><span data-stu-id="36216-105">\<behaviors></span></span>  
<span data-ttu-id="36216-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="36216-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="36216-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="36216-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="36216-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="36216-108">\<behavior></span></span>  
<span data-ttu-id="36216-109">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="36216-109">\<serviceCredentials></span></span>  
<span data-ttu-id="36216-110">\<clientCertificate></span><span class="sxs-lookup"><span data-stu-id="36216-110">\<clientCertificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36216-111">構文</span><span class="sxs-lookup"><span data-stu-id="36216-111">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36216-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="36216-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36216-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="36216-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36216-114">属性</span><span class="sxs-lookup"><span data-stu-id="36216-114">Attributes</span></span>  
 <span data-ttu-id="36216-115">なし。</span><span class="sxs-lookup"><span data-stu-id="36216-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36216-116">子要素</span><span class="sxs-lookup"><span data-stu-id="36216-116">Child Elements</span></span>  
  
|<span data-ttu-id="36216-117">要素</span><span class="sxs-lookup"><span data-stu-id="36216-117">Element</span></span>|<span data-ttu-id="36216-118">説明</span><span class="sxs-lookup"><span data-stu-id="36216-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36216-119">\<authentication></span><span class="sxs-lookup"><span data-stu-id="36216-119">\<authentication></span></span>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="36216-120">クライアント証明書の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="36216-120">Specifies authentication options for the client certificate.</span></span>|  
|[<span data-ttu-id="36216-121">\<certificate></span><span class="sxs-lookup"><span data-stu-id="36216-121">\<certificate></span></span>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="36216-122">使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="36216-122">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36216-123">親要素</span><span class="sxs-lookup"><span data-stu-id="36216-123">Parent Elements</span></span>  
  
|<span data-ttu-id="36216-124">要素</span><span class="sxs-lookup"><span data-stu-id="36216-124">Element</span></span>|<span data-ttu-id="36216-125">説明</span><span class="sxs-lookup"><span data-stu-id="36216-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36216-126">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="36216-126">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="36216-127">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="36216-127">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36216-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="36216-128">Remarks</span></span>  
 <span data-ttu-id="36216-129">この要素は、サービスがクライアントと安全に通信するために、サービスが前もってクライアントの証明書を持っている必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="36216-129">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="36216-130">このような状況は、双方向通信パターンを使用する場合に生じます。</span><span class="sxs-lookup"><span data-stu-id="36216-130">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="36216-131">より一般的な要求/応答パターンでは、クライアントは自身の証明書を要求に含め、サービスはそれを使用してクライアントへの応答を暗号化し、署名します。</span><span class="sxs-lookup"><span data-stu-id="36216-131">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="36216-132">一方、双方向通信パターンでは、サービスにはクライアントからの要求が来ないので、クライアントの証明書をあらかじめ取得することで、クライアント宛のメッセージのセキュリティを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36216-132">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="36216-133">このため、クライアントの証明書を帯域外のネゴシエーションで取得し、この要素を使用して証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="36216-133">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="36216-134">双方向サービスの詳細については、次を参照してください。[方法。双方向コントラクトを作成する](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)します。</span><span class="sxs-lookup"><span data-stu-id="36216-134">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="36216-135">この要素で設定される証明書は、`MutualCertificateDuplex` メッセージ セキュリティ認証モードで構成されているバインディングのみを対象に、クライアントへのメッセージを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="36216-135">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36216-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="36216-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="36216-137">方法: 双方向コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="36216-137">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="36216-138">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="36216-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="36216-139">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="36216-139">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
