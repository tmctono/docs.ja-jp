---
title: <clientCertificate> の <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 9df49777efc80f425cad3b353f95db523a027214
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148918"
---
# <a name="clientcertificate-of-servicecredentials"></a><span data-ttu-id="ca6eb-102">\<clientCertificate> の \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="ca6eb-102">\<clientCertificate> of \<serviceCredentials></span></span>

<span data-ttu-id="ca6eb-103">双方向通信パターンでサービスからクライアントへのメッセージの署名および暗号化に使用される X.509 証明書を定義します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-103">Defines an X.509 certificate used to sign and encrypt messages to a client form a service in a duplex communication pattern.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clientCertificate>**  
  
## <a name="syntax"></a><span data-ttu-id="ca6eb-104">構文</span><span class="sxs-lookup"><span data-stu-id="ca6eb-104">Syntax</span></span>  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca6eb-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ca6eb-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ca6eb-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca6eb-107">属性</span><span class="sxs-lookup"><span data-stu-id="ca6eb-107">Attributes</span></span>  

 <span data-ttu-id="ca6eb-108">なし。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ca6eb-109">子要素</span><span class="sxs-lookup"><span data-stu-id="ca6eb-109">Child Elements</span></span>  
  
|<span data-ttu-id="ca6eb-110">要素</span><span class="sxs-lookup"><span data-stu-id="ca6eb-110">Element</span></span>|<span data-ttu-id="ca6eb-111">説明</span><span class="sxs-lookup"><span data-stu-id="ca6eb-111">Description</span></span>|  
|-------------|-----------------|  
|[\<authentication>](authentication-of-clientcertificate-element.md)|<span data-ttu-id="ca6eb-112">クライアント証明書の認証オプションを指定します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-112">Specifies authentication options for the client certificate.</span></span>|  
|[\<certificate>](certificate-of-clientcertificate-element.md)|<span data-ttu-id="ca6eb-113">使用する証明書を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-113">Specifies the certificate to use.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ca6eb-114">親要素</span><span class="sxs-lookup"><span data-stu-id="ca6eb-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ca6eb-115">要素</span><span class="sxs-lookup"><span data-stu-id="ca6eb-115">Element</span></span>|<span data-ttu-id="ca6eb-116">説明</span><span class="sxs-lookup"><span data-stu-id="ca6eb-116">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceCredentials>](servicecredentials.md)|<span data-ttu-id="ca6eb-117">サービスの認証に使用される資格情報と、クライアントの資格情報検証関連の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-117">Specifies the credentials to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca6eb-118">解説</span><span class="sxs-lookup"><span data-stu-id="ca6eb-118">Remarks</span></span>  

 <span data-ttu-id="ca6eb-119">この要素は、サービスがクライアントと安全に通信するために、サービスが前もってクライアントの証明書を持っている必要がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-119">This element is used when the service must have the client's certificate in advance to communicate securely with the client.</span></span> <span data-ttu-id="ca6eb-120">このような状況は、双方向通信パターンを使用する場合に生じます。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-120">This occurs when using the duplex communication pattern.</span></span> <span data-ttu-id="ca6eb-121">より一般的な要求/応答パターンでは、クライアントは自身の証明書を要求に含め、サービスはそれを使用してクライアントへの応答を暗号化し、署名します。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-121">In the more typical request/response pattern, the client includes its certificate in the request, which the service uses to encrypt and sign its response back to the client.</span></span> <span data-ttu-id="ca6eb-122">一方、双方向通信パターンでは、サービスにはクライアントからの要求が来ないので、クライアントの証明書をあらかじめ取得することで、クライアント宛のメッセージのセキュリティを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-122">In the duplex communication pattern, however, the service does not have a request from the client and therefore it needs the client's certificate in advance to secure the message to the client.</span></span> <span data-ttu-id="ca6eb-123">このため、クライアントの証明書を帯域外のネゴシエーションで取得し、この要素を使用して証明書を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-123">Therefore you must obtain the client's certificate in an out-of-band negotiation, and specify the certificate using this element.</span></span> <span data-ttu-id="ca6eb-124">双方向サービスの詳細については、「 [方法: 双方向コントラクトを作成](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-124">For more information about duplex services, see [How to: Create a Duplex Contract](../../../wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
 <span data-ttu-id="ca6eb-125">この要素で設定される証明書は、`MutualCertificateDuplex` メッセージ セキュリティ認証モードで構成されているバインディングのみを対象に、クライアントへのメッセージを暗号化するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ca6eb-125">The certificate set in this element is used to encrypt messages to the client only for bindings that are configured with `MutualCertificateDuplex` message security authentication mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6eb-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca6eb-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>
- [<span data-ttu-id="ca6eb-127">方法: 双方向コントラクトを作成する</span><span class="sxs-lookup"><span data-stu-id="ca6eb-127">How to: Create a Duplex Contract</span></span>](../../../wcf/feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="ca6eb-128">セキュリティ動作</span><span class="sxs-lookup"><span data-stu-id="ca6eb-128">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="ca6eb-129">証明書の使用</span><span class="sxs-lookup"><span data-stu-id="ca6eb-129">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
