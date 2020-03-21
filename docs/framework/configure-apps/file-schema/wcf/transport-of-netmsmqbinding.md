---
title: <transport> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152932"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="4597e-102">\<\<転送>の></span><span class="sxs-lookup"><span data-stu-id="4597e-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="4597e-103">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4597e-103">Defines the transport security settings.</span></span>  
  
<span data-ttu-id="4597e-104">[**\<構成>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4597e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4597e-105">&nbsp;&nbsp;[**\<システム.サービスモデル>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4597e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4597e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<バインディング>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4597e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4597e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>をバインドします。**](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4597e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)</span></span>\
<span data-ttu-id="4597e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<バインド>**</span><span class="sxs-lookup"><span data-stu-id="4597e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4597e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<セキュリティ>**](security-of-netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4597e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)</span></span>\
<span data-ttu-id="4597e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<輸送>**</span><span class="sxs-lookup"><span data-stu-id="4597e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4597e-111">構文</span><span class="sxs-lookup"><span data-stu-id="4597e-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4597e-112">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4597e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4597e-113">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4597e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4597e-114">属性</span><span class="sxs-lookup"><span data-stu-id="4597e-114">Attributes</span></span>  
  
|<span data-ttu-id="4597e-115">属性</span><span class="sxs-lookup"><span data-stu-id="4597e-115">Attribute</span></span>|<span data-ttu-id="4597e-116">説明</span><span class="sxs-lookup"><span data-stu-id="4597e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4597e-117">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="4597e-117">msmqAuthenticationMode</span></span>|<span data-ttu-id="4597e-118">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4597e-118">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="4597e-119">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4597e-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4597e-120">- なし: 認証なし。</span><span class="sxs-lookup"><span data-stu-id="4597e-120">-   None: No authentication.</span></span><br /><span data-ttu-id="4597e-121">- Windows ドメイン: 認証メカニズムは、Active Directory を使用して、メッセージに関連付けられたセキュリティ識別子の X.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="4597e-121">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="4597e-122">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューへの書き込み権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="4597e-122">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="4597e-123">- 証明書: チャネルは証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="4597e-123">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="4597e-124">既定では、 `WindowsDomain`です。</span><span class="sxs-lookup"><span data-stu-id="4597e-124">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="4597e-125">この属性が `None` に設定されている場合、`msmqProtectionLevel` 属性も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4597e-125">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="4597e-126">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="4597e-126">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="4597e-127">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="4597e-127">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="4597e-128">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="4597e-128">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="4597e-129">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4597e-129">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4597e-130">- RC4ストリーム</span><span class="sxs-lookup"><span data-stu-id="4597e-130">-   RC4Stream</span></span><br /><span data-ttu-id="4597e-131">- AES</span><span class="sxs-lookup"><span data-stu-id="4597e-131">-   AES</span></span><br /><span data-ttu-id="4597e-132">- デフォルト値は`RC4Stream`です。</span><span class="sxs-lookup"><span data-stu-id="4597e-132">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="4597e-133">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="4597e-133">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="4597e-134">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="4597e-134">msmqProtectionLevel</span></span>|<span data-ttu-id="4597e-135">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="4597e-135">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="4597e-136">暗号化を行うとメッセージの整合性が確保されますが、署名および暗号化を使用するとメッセージの整合性と否認防止の両方が確保されます。</span><span class="sxs-lookup"><span data-stu-id="4597e-136">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="4597e-137">つまり、メッセージは実際に送信者から来て、送信者は彼らが誰であるかを言う。</span><span class="sxs-lookup"><span data-stu-id="4597e-137">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="4597e-138">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4597e-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4597e-139">- なし:保護なし。</span><span class="sxs-lookup"><span data-stu-id="4597e-139">-   None: No protection.</span></span><br /><span data-ttu-id="4597e-140">- 署名: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="4597e-140">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="4597e-141">- 暗号化と署名: メッセージは暗号化され、署名されています。</span><span class="sxs-lookup"><span data-stu-id="4597e-141">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="4597e-142">- デフォルトは`Sign`です。</span><span class="sxs-lookup"><span data-stu-id="4597e-142">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="4597e-143">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="4597e-143">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="4597e-144">メッセージ ダイジェストの計算に使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="4597e-144">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="4597e-145">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4597e-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4597e-146">- MD5</span><span class="sxs-lookup"><span data-stu-id="4597e-146">-   MD5</span></span><br /><span data-ttu-id="4597e-147">- SHA1</span><span class="sxs-lookup"><span data-stu-id="4597e-147">-   SHA1</span></span><br /><span data-ttu-id="4597e-148">- SHA256</span><span class="sxs-lookup"><span data-stu-id="4597e-148">-   SHA256</span></span><br /><span data-ttu-id="4597e-149">- SHA512</span><span class="sxs-lookup"><span data-stu-id="4597e-149">-   SHA512</span></span><br /><br /> <span data-ttu-id="4597e-150">既定では、 `SHA1`です。</span><span class="sxs-lookup"><span data-stu-id="4597e-150">The default is `SHA1`.</span></span> <span data-ttu-id="4597e-151">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="4597e-151">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="4597e-152">MD5 と SHA1 の衝突の問題のため、マイクロソフトは SHA256 以上を推奨します。</span><span class="sxs-lookup"><span data-stu-id="4597e-152">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4597e-153">子要素</span><span class="sxs-lookup"><span data-stu-id="4597e-153">Child Elements</span></span>  
 <span data-ttu-id="4597e-154">なし</span><span class="sxs-lookup"><span data-stu-id="4597e-154">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4597e-155">親要素</span><span class="sxs-lookup"><span data-stu-id="4597e-155">Parent Elements</span></span>  
  
|<span data-ttu-id="4597e-156">要素</span><span class="sxs-lookup"><span data-stu-id="4597e-156">Element</span></span>|<span data-ttu-id="4597e-157">説明</span><span class="sxs-lookup"><span data-stu-id="4597e-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4597e-158">\<セキュリティ></span><span class="sxs-lookup"><span data-stu-id="4597e-158">\<security></span></span>](security-of-netmsmqbinding.md)|<span data-ttu-id="4597e-159">キューに置かれているトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4597e-159">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4597e-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="4597e-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="4597e-161">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="4597e-161">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="4597e-162">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="4597e-162">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4597e-163">バインド</span><span class="sxs-lookup"><span data-stu-id="4597e-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4597e-164">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="4597e-164">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4597e-165">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="4597e-165">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4597e-166">\<バインド></span><span class="sxs-lookup"><span data-stu-id="4597e-166">\<binding></span></span>](bindings.md)
