---
title: <transport> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 859bc00557f66e27d7bd82a16704fc59c6044613
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934728"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="c8072-102">\<msmqIntegrationBinding の\<トランスポート > ></span><span class="sxs-lookup"><span data-stu-id="c8072-102">\<transport> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="c8072-103">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8072-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
 <span data-ttu-id="c8072-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c8072-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c8072-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c8072-105">\<bindings></span></span>  
<span data-ttu-id="c8072-106">msmqIntegrationBinding</span><span class="sxs-lookup"><span data-stu-id="c8072-106">msmqIntegrationBinding</span></span>  
<span data-ttu-id="c8072-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c8072-107">\<binding></span></span>  
<span data-ttu-id="c8072-108">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="c8072-108">\<security></span></span>  
<span data-ttu-id="c8072-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="c8072-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8072-110">構文</span><span class="sxs-lookup"><span data-stu-id="c8072-110">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8072-111">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c8072-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c8072-112">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c8072-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c8072-113">属性</span><span class="sxs-lookup"><span data-stu-id="c8072-113">Attributes</span></span>  
  
|<span data-ttu-id="c8072-114">属性</span><span class="sxs-lookup"><span data-stu-id="c8072-114">Attribute</span></span>|<span data-ttu-id="c8072-115">説明</span><span class="sxs-lookup"><span data-stu-id="c8072-115">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="c8072-116">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8072-116">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="c8072-117">これが `None` に設定されている場合、`msmqProtectionLevel` 属性の値も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c8072-117">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="c8072-118">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="c8072-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c8072-119">存在認証なし。</span><span class="sxs-lookup"><span data-stu-id="c8072-119">-   None: No authentication.</span></span><br /><span data-ttu-id="c8072-120">WindowsDomain認証メカニズムでは、Active Directory を使用して、メッセージに関連付けられている SID の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8072-120">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="c8072-121">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューに書き込む権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="c8072-121">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="c8072-122">証明チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="c8072-122">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="c8072-123">既定値は WindowsDomain です。</span><span class="sxs-lookup"><span data-stu-id="c8072-123">The default value is WindowsDomain.</span></span> <span data-ttu-id="c8072-124">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8072-124">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="c8072-125">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8072-125">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="c8072-126">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="c8072-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c8072-127">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="c8072-127">-   RC4Stream</span></span><br /><span data-ttu-id="c8072-128">-AES</span><span class="sxs-lookup"><span data-stu-id="c8072-128">-   AES</span></span><br /><br /> <span data-ttu-id="c8072-129">既定値は RC4Stream です。</span><span class="sxs-lookup"><span data-stu-id="c8072-129">The default value is RC4Stream.</span></span> <span data-ttu-id="c8072-130">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8072-130">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="c8072-131">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="c8072-131">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="c8072-132">暗号化を行うとメッセージの整合性が確保されますが、EncryptAndSign を使用するとメッセージの整合性と否認防止の両方が確保されます。つまり、メッセージは本当にその送信者から送信されていることになり、記載されている送信者が実際の送信者になります。</span><span class="sxs-lookup"><span data-stu-id="c8072-132">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span><br /><br /> <span data-ttu-id="c8072-133">-有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8072-133">-   Valid values include the following:</span></span><br /><span data-ttu-id="c8072-134">存在保護されません。</span><span class="sxs-lookup"><span data-stu-id="c8072-134">-   None: No protection.</span></span><br /><span data-ttu-id="c8072-135">シャープメッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="c8072-135">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="c8072-136">EncryptAndSignメッセージは暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="c8072-136">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="c8072-137">既定値は Sign です。</span><span class="sxs-lookup"><span data-stu-id="c8072-137">The default value is Sign.</span></span> <span data-ttu-id="c8072-138">この属性は、ProtectionLevel 型です。</span><span class="sxs-lookup"><span data-stu-id="c8072-138">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="c8072-139">-署名の一部としてダイジェストを計算するために使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="c8072-139">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="c8072-140">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c8072-140">Valid values include the following:</span></span><br /><span data-ttu-id="c8072-141">-   MD5</span><span class="sxs-lookup"><span data-stu-id="c8072-141">-   MD5</span></span><br /><span data-ttu-id="c8072-142">-SHA1</span><span class="sxs-lookup"><span data-stu-id="c8072-142">-   SHA1</span></span><br /><span data-ttu-id="c8072-143">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="c8072-143">-   SHA256</span></span><br /><span data-ttu-id="c8072-144">-SHA512</span><span class="sxs-lookup"><span data-stu-id="c8072-144">-   SHA512</span></span><br /><br /> <span data-ttu-id="c8072-145">既定値は SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="c8072-145">The default value is SHA1.</span></span> <span data-ttu-id="c8072-146">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="c8072-146">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="c8072-147">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c8072-147">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c8072-148">子要素</span><span class="sxs-lookup"><span data-stu-id="c8072-148">Child Elements</span></span>  
 <span data-ttu-id="c8072-149">なし</span><span class="sxs-lookup"><span data-stu-id="c8072-149">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c8072-150">親要素</span><span class="sxs-lookup"><span data-stu-id="c8072-150">Parent Elements</span></span>  
  
|<span data-ttu-id="c8072-151">要素</span><span class="sxs-lookup"><span data-stu-id="c8072-151">Element</span></span>|<span data-ttu-id="c8072-152">説明</span><span class="sxs-lookup"><span data-stu-id="c8072-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c8072-153">\<security></span><span class="sxs-lookup"><span data-stu-id="c8072-153">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="c8072-154">MSMQ バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="c8072-154">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c8072-155">Remarks</span><span class="sxs-lookup"><span data-stu-id="c8072-155">Remarks</span></span>  
 <span data-ttu-id="c8072-156">この要素は、メッセージ キュー統合トランスポートのセキュリティ設定をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="c8072-156">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="c8072-157">設定は、メッセージ キュー統合トランスポートとキューに置かれているトランスポートの両方で同じです。</span><span class="sxs-lookup"><span data-stu-id="c8072-157">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="c8072-158">この設定を使用すると、認証モード、暗号化アルゴリズム、セキュア ハッシュ アルゴリズム、および保護レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c8072-158">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8072-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="c8072-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="c8072-160">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="c8072-160">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c8072-161">バインディング</span><span class="sxs-lookup"><span data-stu-id="c8072-161">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c8072-162">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="c8072-162">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c8072-163">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="c8072-163">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c8072-164">\<binding></span><span class="sxs-lookup"><span data-stu-id="c8072-164">\<binding></span></span>](../../../misc/binding.md)
