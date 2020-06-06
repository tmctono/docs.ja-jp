---
title: <transport> の <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
ms.openlocfilehash: cc47c01cccc931e81ba57ab37ad9e3accfaa693b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152932"
---
# <a name="transport-of-netmsmqbinding"></a><span data-ttu-id="758d7-102">\<transport> の \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="758d7-102">\<transport> of \<netMsmqBinding></span></span>
<span data-ttu-id="758d7-103">トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="758d7-103">Defines the transport security settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="758d7-104">構文</span><span class="sxs-lookup"><span data-stu-id="758d7-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="758d7-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="758d7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="758d7-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="758d7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="758d7-107">属性</span><span class="sxs-lookup"><span data-stu-id="758d7-107">Attributes</span></span>  
  
|<span data-ttu-id="758d7-108">属性</span><span class="sxs-lookup"><span data-stu-id="758d7-108">Attribute</span></span>|<span data-ttu-id="758d7-109">説明</span><span class="sxs-lookup"><span data-stu-id="758d7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="758d7-110">msmqAuthenticationMode</span><span class="sxs-lookup"><span data-stu-id="758d7-110">msmqAuthenticationMode</span></span>|<span data-ttu-id="758d7-111">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="758d7-111">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="758d7-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="758d7-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="758d7-113">-None: 認証なし。</span><span class="sxs-lookup"><span data-stu-id="758d7-113">-   None: No authentication.</span></span><br /><span data-ttu-id="758d7-114">-WindowsDomain: 認証メカニズムは Active Directory を使用して、メッセージに関連付けられているセキュリティ識別子の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="758d7-114">-   WindowsDomain: The authentication mechanism uses Active Directory to retrieve the X.509 certificate for the security identifier associated with the message.</span></span> <span data-ttu-id="758d7-115">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューへの書き込み権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="758d7-115">This is then used to check the ACL of the queue to ensure the user has write permission for the queue.</span></span><br /><span data-ttu-id="758d7-116">-Certificate: チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="758d7-116">-   Certificate: The channel retrieves the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="758d7-117">既定値は、`WindowsDomain` です。</span><span class="sxs-lookup"><span data-stu-id="758d7-117">The default is `WindowsDomain`.</span></span><br /><br /> <span data-ttu-id="758d7-118">この属性が `None` に設定されている場合、`msmqProtectionLevel` 属性も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="758d7-118">If this attribute is set to `None`, the `msmqProtectionLevel` attribute must also be set to `None`.</span></span> <span data-ttu-id="758d7-119">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="758d7-119">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode></span></span>|  
|<span data-ttu-id="758d7-120">msmqEncryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="758d7-120">msmqEncryptionAlgorithm</span></span>|<span data-ttu-id="758d7-121">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="758d7-121">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="758d7-122">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="758d7-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="758d7-123">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="758d7-123">-   RC4Stream</span></span><br /><span data-ttu-id="758d7-124">-AES</span><span class="sxs-lookup"><span data-stu-id="758d7-124">-   AES</span></span><br /><span data-ttu-id="758d7-125">-既定値は `RC4Stream` です。</span><span class="sxs-lookup"><span data-stu-id="758d7-125">-   The default value is `RC4Stream`.</span></span> <span data-ttu-id="758d7-126">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="758d7-126">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|<span data-ttu-id="758d7-127">msmqProtectionLevel</span><span class="sxs-lookup"><span data-stu-id="758d7-127">msmqProtectionLevel</span></span>|<span data-ttu-id="758d7-128">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="758d7-128">Specifies the way messages are secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="758d7-129">暗号化を行うとメッセージの整合性が確保されますが、署名および暗号化を使用するとメッセージの整合性と否認防止の両方が確保されます。</span><span class="sxs-lookup"><span data-stu-id="758d7-129">Encryption ensures message integrity, while sign and encrypt ensures both message integrity and non-repudiation.</span></span> <span data-ttu-id="758d7-130">つまり、実際には送信者から送信されたメッセージであり、送信者はその人物であると言います。</span><span class="sxs-lookup"><span data-stu-id="758d7-130">That is, the message indeed came from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="758d7-131">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="758d7-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="758d7-132">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="758d7-132">-   None: No protection.</span></span><br /><span data-ttu-id="758d7-133">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="758d7-133">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="758d7-134">-EncryptAndSign: メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="758d7-134">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><span data-ttu-id="758d7-135">-既定値は `Sign` です。</span><span class="sxs-lookup"><span data-stu-id="758d7-135">-   The default is `Sign`.</span></span>|  
|<span data-ttu-id="758d7-136">msmqSecureHashAlgorithm</span><span class="sxs-lookup"><span data-stu-id="758d7-136">msmqSecureHashAlgorithm</span></span>|<span data-ttu-id="758d7-137">メッセージ ダイジェストの計算に使用されるハッシュ アルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="758d7-137">Specifies the hash algorithm to be used for computing the message digest.</span></span> <span data-ttu-id="758d7-138">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="758d7-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="758d7-139">-MD5</span><span class="sxs-lookup"><span data-stu-id="758d7-139">-   MD5</span></span><br /><span data-ttu-id="758d7-140">-SHA1</span><span class="sxs-lookup"><span data-stu-id="758d7-140">-   SHA1</span></span><br /><span data-ttu-id="758d7-141">-SHA256</span><span class="sxs-lookup"><span data-stu-id="758d7-141">-   SHA256</span></span><br /><span data-ttu-id="758d7-142">-SHA512</span><span class="sxs-lookup"><span data-stu-id="758d7-142">-   SHA512</span></span><br /><br /> <span data-ttu-id="758d7-143">既定値は、`SHA1` です。</span><span class="sxs-lookup"><span data-stu-id="758d7-143">The default is `SHA1`.</span></span> <span data-ttu-id="758d7-144">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="758d7-144">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="758d7-145">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="758d7-145">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="758d7-146">子要素</span><span class="sxs-lookup"><span data-stu-id="758d7-146">Child Elements</span></span>  
 <span data-ttu-id="758d7-147">なし</span><span class="sxs-lookup"><span data-stu-id="758d7-147">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="758d7-148">親要素</span><span class="sxs-lookup"><span data-stu-id="758d7-148">Parent Elements</span></span>  
  
|<span data-ttu-id="758d7-149">要素</span><span class="sxs-lookup"><span data-stu-id="758d7-149">Element</span></span>|<span data-ttu-id="758d7-150">Description</span><span class="sxs-lookup"><span data-stu-id="758d7-150">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netmsmqbinding.md)|<span data-ttu-id="758d7-151">キューに置かれているトランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="758d7-151">Defines the transport security settings for queued transports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="758d7-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="758d7-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="758d7-153">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="758d7-153">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="758d7-154">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="758d7-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="758d7-155">バインド</span><span class="sxs-lookup"><span data-stu-id="758d7-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="758d7-156">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="758d7-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="758d7-157">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="758d7-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
