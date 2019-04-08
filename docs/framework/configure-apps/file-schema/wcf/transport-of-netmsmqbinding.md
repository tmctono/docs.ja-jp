---
title: <transport> (行中)  <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: ec726c4b39fedbf63a7ecc9e685a86367609fa43
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085013"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="6e571-102">\<トランスポート > の\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="6e571-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="6e571-103">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e571-103">Defines the transport security settings.</span></span>  
  
 <span data-ttu-id="6e571-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6e571-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6e571-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6e571-105">\<bindings></span></span>  
<span data-ttu-id="6e571-106">\<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="6e571-106">\<netMsmqBinding></span></span>  
<span data-ttu-id="6e571-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6e571-107">\<binding></span></span>  
<span data-ttu-id="6e571-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="6e571-108">\<security></span></span>  
<span data-ttu-id="6e571-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="6e571-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e571-110">構文</span><span class="sxs-lookup"><span data-stu-id="6e571-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e571-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6e571-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6e571-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e571-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e571-113">属性</span><span class="sxs-lookup"><span data-stu-id="6e571-113">Attributes</span></span>  
  
|<span data-ttu-id="6e571-114">属性</span><span class="sxs-lookup"><span data-stu-id="6e571-114">Attribute</span></span>|<span data-ttu-id="6e571-115">説明</span><span class="sxs-lookup"><span data-stu-id="6e571-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e571-116">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="6e571-116">msmqAuthenticationMode</span></span>|<span data-ttu-id="6e571-117">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e571-117">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="6e571-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6e571-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e571-119">-None。認証はありません。</span><span class="sxs-lookup"><span data-stu-id="6e571-119">-   None: No authentication.</span></span><br /><span data-ttu-id="6e571-120">-   WindowsDomain:認証メカニズムは、メッセージに関連付けられたセキュリティ識別子の X.509 証明書を取得するのに Active Directory を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e571-120">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="6e571-121">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューへの書き込み権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="6e571-121">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="6e571-122">-証明書:チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="6e571-122">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="6e571-123">既定値は `WindowsDomain` です。</span><span class="sxs-lookup"><span data-stu-id="6e571-123">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="6e571-124">この属性が `None` に設定されている場合、`msmqProtectionLevel` 属性も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e571-124">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="6e571-125">この属性の型です。</span><span class="sxs-lookup"><span data-stu-id="6e571-125">This attribute is of type</span></span> <xref:System.ServiceModel.MsmqAuthenticationMode>|  
|<span data-ttu-id="6e571-126">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="6e571-126">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="6e571-127">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e571-127">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="6e571-128">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6e571-128">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e571-129">-[Rc4stream]</span><span class="sxs-lookup"><span data-stu-id="6e571-129">-   RC4Stream</span></span><br /><span data-ttu-id="6e571-130">-AES</span><span class="sxs-lookup"><span data-stu-id="6e571-130">-   AES</span></span><br /><span data-ttu-id="6e571-131">-既定値は`RC4Stream`します。</span><span class="sxs-lookup"><span data-stu-id="6e571-131">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="6e571-132">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="6e571-132">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="6e571-133">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="6e571-133">msmqProtectionLevel</span></span>|<span data-ttu-id="6e571-134">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6e571-134">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="6e571-135">暗号化を行うとメッセージの整合性が確保されますが、署名および暗号化を使用するとメッセージの整合性と否認防止の両方が確保されます。</span><span class="sxs-lookup"><span data-stu-id="6e571-135">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="6e571-136">つまり、メッセージは本当にその送信者から送信されていることになり、記載されている送信者が実際の送信者になります。</span><span class="sxs-lookup"><span data-stu-id="6e571-136">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="6e571-137">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6e571-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e571-138">-None。保護されません。</span><span class="sxs-lookup"><span data-stu-id="6e571-138">-   None: No protection.</span></span><br /><span data-ttu-id="6e571-139">署名:メッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="6e571-139">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="6e571-140">-EncryptAndSign:メッセージは暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="6e571-140">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="6e571-141">-既定値は`Sign`します。</span><span class="sxs-lookup"><span data-stu-id="6e571-141">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="6e571-142">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="6e571-142">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="6e571-143">メッセージ ダイジェストの計算に使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e571-143">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="6e571-144">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6e571-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e571-145">-   MD5</span><span class="sxs-lookup"><span data-stu-id="6e571-145">-   MD5</span></span><br /><span data-ttu-id="6e571-146">-SHA1</span><span class="sxs-lookup"><span data-stu-id="6e571-146">-   SHA1</span></span><br /><span data-ttu-id="6e571-147">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="6e571-147">-   SHA256</span></span><br /><span data-ttu-id="6e571-148">-SHA512</span><span class="sxs-lookup"><span data-stu-id="6e571-148">-   SHA512</span></span><br /><br /> <span data-ttu-id="6e571-149">既定値は `SHA1` です。</span><span class="sxs-lookup"><span data-stu-id="6e571-149">The default is `SHA1`.</span></span> <span data-ttu-id="6e571-150">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="6e571-150">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="6e571-151">MD5 と SHA1 に衝突の問題、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e571-151">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e571-152">子要素</span><span class="sxs-lookup"><span data-stu-id="6e571-152">Child Elements</span></span>  
 <span data-ttu-id="6e571-153">なし</span><span class="sxs-lookup"><span data-stu-id="6e571-153">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e571-154">親要素</span><span class="sxs-lookup"><span data-stu-id="6e571-154">Parent Elements</span></span>  
  
|<span data-ttu-id="6e571-155">要素</span><span class="sxs-lookup"><span data-stu-id="6e571-155">Element</span></span>|<span data-ttu-id="6e571-156">説明</span><span class="sxs-lookup"><span data-stu-id="6e571-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e571-157">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="6e571-157">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|<span data-ttu-id="6e571-158">キューに置かれているトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e571-158">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e571-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e571-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="6e571-160">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="6e571-160">Queues in WCF</span></span>](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="6e571-161">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6e571-161">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6e571-162">バインディング</span><span class="sxs-lookup"><span data-stu-id="6e571-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6e571-163">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="6e571-163">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6e571-164">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="6e571-164">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6e571-165">\<binding></span><span class="sxs-lookup"><span data-stu-id="6e571-165">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
