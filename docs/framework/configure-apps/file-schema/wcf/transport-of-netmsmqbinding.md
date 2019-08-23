---
title: <transport> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ede4103f9c8f2f73ac34036fe7a58242e32350e0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934692"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="615d1-102">\<netmsmqbinding \<> のトランスポート ></span><span class="sxs-lookup"><span data-stu-id="615d1-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="615d1-103">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="615d1-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="615d1-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="615d1-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="615d1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="615d1-105">\<bindings></span></span>  
<span data-ttu-id="615d1-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="615d1-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="615d1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="615d1-107">\<binding></span></span>  
<span data-ttu-id="615d1-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="615d1-108">\<security></span></span>  
<span data-ttu-id="615d1-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="615d1-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="615d1-110">構文</span><span class="sxs-lookup"><span data-stu-id="615d1-110">Syntax</span></span>  
  
```xml  
<netMsmqBinding>
  <binding>
    <security>
      <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    </security>
  </binding>
</netMsmqBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="615d1-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="615d1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="615d1-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="615d1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="615d1-113">属性</span><span class="sxs-lookup"><span data-stu-id="615d1-113">Attributes</span></span>  
  
|<span data-ttu-id="615d1-114">属性</span><span class="sxs-lookup"><span data-stu-id="615d1-114">Attribute</span></span>|<span data-ttu-id="615d1-115">説明</span><span class="sxs-lookup"><span data-stu-id="615d1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="615d1-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="615d1-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="615d1-117">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="615d1-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="615d1-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="615d1-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="615d1-119">存在認証なし。</span><span class="sxs-lookup"><span data-stu-id="615d1-119">-   None: No authentication.</span></span><br /><span data-ttu-id="615d1-120">WindowsDomain認証メカニズムでは、Active Directory を使用して、メッセージに関連付けられているセキュリティ識別子の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="615d1-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="615d1-121">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューへの書き込み権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="615d1-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="615d1-122">証明チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="615d1-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="615d1-123">既定値は `WindowsDomain` です。</span><span class="sxs-lookup"><span data-stu-id="615d1-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="615d1-124">この属性が `None` に設定されている場合、`msmqProtectionLevel` 属性も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="615d1-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="615d1-125">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="615d1-125">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="615d1-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="615d1-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="615d1-127">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="615d1-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="615d1-128">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="615d1-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="615d1-129">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="615d1-129">-   RC4Stream</span></span><br /><span data-ttu-id="615d1-130">-AES</span><span class="sxs-lookup"><span data-stu-id="615d1-130">-   AES</span></span><br /><span data-ttu-id="615d1-131">-既定値は`RC4Stream`です。</span><span class="sxs-lookup"><span data-stu-id="615d1-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="615d1-132">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="615d1-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="615d1-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="615d1-133">msmqProtectionLevel</span></span>|<span data-ttu-id="615d1-134">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="615d1-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="615d1-135">暗号化を行うとメッセージの整合性が確保されますが、署名および暗号化を使用するとメッセージの整合性と否認防止の両方が確保されます。</span><span class="sxs-lookup"><span data-stu-id="615d1-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="615d1-136">つまり、メッセージは本当にその送信者から送信されていることになり、記載されている送信者が実際の送信者になります。</span><span class="sxs-lookup"><span data-stu-id="615d1-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="615d1-137">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="615d1-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="615d1-138">存在保護されません。</span><span class="sxs-lookup"><span data-stu-id="615d1-138">-   None: No protection.</span></span><br /><span data-ttu-id="615d1-139">シャープメッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="615d1-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="615d1-140">EncryptAndSignメッセージは暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="615d1-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="615d1-141">-既定値は`Sign`です。</span><span class="sxs-lookup"><span data-stu-id="615d1-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="615d1-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="615d1-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="615d1-143">メッセージ ダイジェストの計算に使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="615d1-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="615d1-144">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="615d1-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="615d1-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="615d1-145">-   MD5</span></span><br /><span data-ttu-id="615d1-146">-SHA1</span><span class="sxs-lookup"><span data-stu-id="615d1-146">-   SHA1</span></span><br /><span data-ttu-id="615d1-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="615d1-147">-   SHA256</span></span><br /><span data-ttu-id="615d1-148">-SHA512</span><span class="sxs-lookup"><span data-stu-id="615d1-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="615d1-149">既定値は `SHA1` です。</span><span class="sxs-lookup"><span data-stu-id="615d1-149">The default is `SHA1`.</span></span> <span data-ttu-id="615d1-150">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="615d1-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="615d1-151">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="615d1-151">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="615d1-152">子要素</span><span class="sxs-lookup"><span data-stu-id="615d1-152">Child Elements</span></span>  
 <span data-ttu-id="615d1-153">なし</span><span class="sxs-lookup"><span data-stu-id="615d1-153">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="615d1-154">親要素</span><span class="sxs-lookup"><span data-stu-id="615d1-154">Parent Elements</span></span>  
  
|<span data-ttu-id="615d1-155">要素</span><span class="sxs-lookup"><span data-stu-id="615d1-155">Element</span></span>|<span data-ttu-id="615d1-156">説明</span><span class="sxs-lookup"><span data-stu-id="615d1-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="615d1-157">\<security></span><span class="sxs-lookup"><span data-stu-id="615d1-157">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="615d1-158">キューに置かれているトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="615d1-158">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="615d1-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="615d1-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="615d1-160">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="615d1-160">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="615d1-161">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="615d1-161">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="615d1-162">バインディング</span><span class="sxs-lookup"><span data-stu-id="615d1-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="615d1-163">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="615d1-163">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="615d1-164">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="615d1-164">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="615d1-165">\<binding></span><span class="sxs-lookup"><span data-stu-id="615d1-165">\<binding></span></span>](../../../misc/binding.md)
