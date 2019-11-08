---
title: <transport> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: 0df17832818e6e4e7c8e551fabaf4f5241807a74
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736002"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="6c7e0-102">\<netMsmqBinding の \<transport > ></span><span class="sxs-lookup"><span data-stu-id="6c7e0-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="6c7e0-103">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-103">Defines the transport security settings.</span></span>  
  
<span data-ttu-id="6c7e0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c7e0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6c7e0-105">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="6c7e0-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6c7e0-106">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6c7e0-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6c7e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**netMsmqBinding >** ](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6c7e0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="6c7e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="6c7e0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6c7e0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**セキュリティ >** ](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6c7e0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="6c7e0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**トランスポート >**</span><span class="sxs-lookup"><span data-stu-id="6c7e0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c7e0-111">構文</span><span class="sxs-lookup"><span data-stu-id="6c7e0-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c7e0-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6c7e0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c7e0-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c7e0-114">属性</span><span class="sxs-lookup"><span data-stu-id="6c7e0-114">Attributes</span></span>  
  
|<span data-ttu-id="6c7e0-115">属性</span><span class="sxs-lookup"><span data-stu-id="6c7e0-115">Attribute</span></span>|<span data-ttu-id="6c7e0-116">説明</span><span class="sxs-lookup"><span data-stu-id="6c7e0-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c7e0-117">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="6c7e0-117">msmqAuthenticationMode</span></span>|<span data-ttu-id="6c7e0-118">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-118">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="6c7e0-119">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c7e0-120">-None: 認証なし。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-120">-   None: No authentication.</span></span><br /><span data-ttu-id="6c7e0-121">-WindowsDomain: 認証メカニズムは Active Directory を使用して、メッセージに関連付けられているセキュリティ識別子の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-121">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="6c7e0-122">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューへの書き込み権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-122">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="6c7e0-123">-Certificate: チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-123">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="6c7e0-124">既定値は、 `WindowsDomain`です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-124">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="6c7e0-125">この属性が `None` に設定されている場合、`msmqProtectionLevel` 属性も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-125">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="6c7e0-126">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-126">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="6c7e0-127">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="6c7e0-127">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="6c7e0-128">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-128">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="6c7e0-129">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-129">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c7e0-130">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="6c7e0-130">-   RC4Stream</span></span><br /><span data-ttu-id="6c7e0-131">-AES</span><span class="sxs-lookup"><span data-stu-id="6c7e0-131">-   AES</span></span><br /><span data-ttu-id="6c7e0-132">-既定値は `RC4Stream`です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-132">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="6c7e0-133">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-133">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="6c7e0-134">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="6c7e0-134">msmqProtectionLevel</span></span>|<span data-ttu-id="6c7e0-135">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-135">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="6c7e0-136">暗号化を行うとメッセージの整合性が確保されますが、署名および暗号化を使用するとメッセージの整合性と否認防止の両方が確保されます。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-136">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="6c7e0-137">つまり、メッセージは本当にその送信者から送信されていることになり、記載されている送信者が実際の送信者になります。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-137">That is, the message indeed came from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="6c7e0-138">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c7e0-139">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-139">-   None: No protection.</span></span><br /><span data-ttu-id="6c7e0-140">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-140">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="6c7e0-141">-EncryptAndSign: メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-141">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="6c7e0-142">-既定値は `Sign`です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-142">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="6c7e0-143">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="6c7e0-143">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="6c7e0-144">メッセージ ダイジェストの計算に使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-144">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="6c7e0-145">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6c7e0-146">-MD5</span><span class="sxs-lookup"><span data-stu-id="6c7e0-146">-   MD5</span></span><br /><span data-ttu-id="6c7e0-147">-SHA1</span><span class="sxs-lookup"><span data-stu-id="6c7e0-147">-   SHA1</span></span><br /><span data-ttu-id="6c7e0-148">-SHA256</span><span class="sxs-lookup"><span data-stu-id="6c7e0-148">-   SHA256</span></span><br /><span data-ttu-id="6c7e0-149">-SHA512</span><span class="sxs-lookup"><span data-stu-id="6c7e0-149">-   SHA512</span></span><br /><br /> <span data-ttu-id="6c7e0-150">既定値は、 `SHA1`です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-150">The default is `SHA1`.</span></span> <span data-ttu-id="6c7e0-151">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-151">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="6c7e0-152">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-152">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c7e0-153">子要素</span><span class="sxs-lookup"><span data-stu-id="6c7e0-153">Child Elements</span></span>  
 <span data-ttu-id="6c7e0-154">None</span><span class="sxs-lookup"><span data-stu-id="6c7e0-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c7e0-155">親要素</span><span class="sxs-lookup"><span data-stu-id="6c7e0-155">Parent Elements</span></span>  
  
|<span data-ttu-id="6c7e0-156">要素</span><span class="sxs-lookup"><span data-stu-id="6c7e0-156">Element</span></span>|<span data-ttu-id="6c7e0-157">説明</span><span class="sxs-lookup"><span data-stu-id="6c7e0-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c7e0-158">\< セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="6c7e0-158">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="6c7e0-159">キューに置かれているトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6c7e0-159">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c7e0-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="6c7e0-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="6c7e0-161">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="6c7e0-161">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="6c7e0-162">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="6c7e0-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6c7e0-163">バインディング</span><span class="sxs-lookup"><span data-stu-id="6c7e0-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6c7e0-164">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="6c7e0-164">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6c7e0-165">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="6c7e0-165">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="6c7e0-166">\<binding ></span><span class="sxs-lookup"><span data-stu-id="6c7e0-166">\<binding></span></span>](bindings.md)
