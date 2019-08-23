---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 5a7dcac4edce75029bb2e0293461557f56e3c3be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933220"
---
# <a name="msmqtransportsecurity"></a><span data-ttu-id="92bb2-101">\<msmqTransportSecurity ></span><span class="sxs-lookup"><span data-stu-id="92bb2-101">\<msmqTransportSecurity></span></span>
<span data-ttu-id="92bb2-102">カスタム バインディングの MSMQ トランスポート セキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-102">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
 <span data-ttu-id="92bb2-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="92bb2-103">\<system.serviceModel></span></span>  
<span data-ttu-id="92bb2-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="92bb2-104">\<bindings></span></span>  
<span data-ttu-id="92bb2-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="92bb2-105">\<customBinding></span></span>  
<span data-ttu-id="92bb2-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="92bb2-106">\<binding></span></span>  
<span data-ttu-id="92bb2-107">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="92bb2-107">\<msmqIntegration></span></span>  
<span data-ttu-id="92bb2-108">\<msmqTransportSecurity ></span><span class="sxs-lookup"><span data-stu-id="92bb2-108">\<msmqTransportSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92bb2-109">構文</span><span class="sxs-lookup"><span data-stu-id="92bb2-109">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92bb2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="92bb2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="92bb2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92bb2-112">属性</span><span class="sxs-lookup"><span data-stu-id="92bb2-112">Attributes</span></span>  
  
|<span data-ttu-id="92bb2-113">属性</span><span class="sxs-lookup"><span data-stu-id="92bb2-113">Attribute</span></span>|<span data-ttu-id="92bb2-114">説明</span><span class="sxs-lookup"><span data-stu-id="92bb2-114">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="92bb2-115">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-115">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="92bb2-116">これが `None` に設定されている場合、`msmqProtectionLevel` 属性の値も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92bb2-116">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="92bb2-117">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92bb2-118">存在認証なし。</span><span class="sxs-lookup"><span data-stu-id="92bb2-118">-   None: No authentication.</span></span><br /><span data-ttu-id="92bb2-119">ウィンドウ認証メカニズムでは、Active Directory を使用して、メッセージに関連付けられている SID の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-119">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="92bb2-120">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューに書き込む権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="92bb2-120">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="92bb2-121">証明チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-121">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="92bb2-122">既定値は Windows です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-122">The default value is Windows.</span></span> <span data-ttu-id="92bb2-123">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-123">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="92bb2-124">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-124">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="92bb2-125">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92bb2-126">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="92bb2-126">-   RC4Stream</span></span><br /><span data-ttu-id="92bb2-127">-AES</span><span class="sxs-lookup"><span data-stu-id="92bb2-127">-   AES</span></span><br /><br /> <span data-ttu-id="92bb2-128">既定値は RC4Stream です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-128">The default value is RC4Stream.</span></span> <span data-ttu-id="92bb2-129">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-129">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="92bb2-130">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-130">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="92bb2-131">暗号化を行うとメッセージの整合性が確保されますが、EncryptAndSign を使用するとメッセージの整合性と否認防止の両方が確保されます。つまり、メッセージは本当にその送信者から送信されていることになり、記載されている送信者が実際の送信者になります。</span><span class="sxs-lookup"><span data-stu-id="92bb2-131">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who he says he is.</span></span> <span data-ttu-id="92bb2-132">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92bb2-133">存在保護されません。</span><span class="sxs-lookup"><span data-stu-id="92bb2-133">-   None: No protection.</span></span><br /><span data-ttu-id="92bb2-134">シャープメッセージは署名されます。</span><span class="sxs-lookup"><span data-stu-id="92bb2-134">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="92bb2-135">EncryptAndSignメッセージは暗号化および署名されます。</span><span class="sxs-lookup"><span data-stu-id="92bb2-135">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="92bb2-136">既定値は Sign です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-136">The default value is Sign.</span></span> <span data-ttu-id="92bb2-137">この属性は <xref:System.Net.Security.ProtectionLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-137">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="92bb2-138">署名の一部としてダイジェストの計算に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-138">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="92bb2-139">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-139">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="92bb2-140">-   MD5</span><span class="sxs-lookup"><span data-stu-id="92bb2-140">-   MD5</span></span><br /><span data-ttu-id="92bb2-141">-SHA1</span><span class="sxs-lookup"><span data-stu-id="92bb2-141">-   SHA1</span></span><br /><span data-ttu-id="92bb2-142">-   SHA256</span><span class="sxs-lookup"><span data-stu-id="92bb2-142">-   SHA256</span></span><br /><span data-ttu-id="92bb2-143">-SHA512</span><span class="sxs-lookup"><span data-stu-id="92bb2-143">-   SHA512</span></span><br /><br /> <span data-ttu-id="92bb2-144">既定値は SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-144">The default value is SHA1.</span></span> <span data-ttu-id="92bb2-145">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="92bb2-145">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="92bb2-146">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="92bb2-146">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="92bb2-147">子要素</span><span class="sxs-lookup"><span data-stu-id="92bb2-147">Child Elements</span></span>  
 <span data-ttu-id="92bb2-148">なし。</span><span class="sxs-lookup"><span data-stu-id="92bb2-148">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="92bb2-149">親要素</span><span class="sxs-lookup"><span data-stu-id="92bb2-149">Parent Elements</span></span>  
  
|<span data-ttu-id="92bb2-150">要素</span><span class="sxs-lookup"><span data-stu-id="92bb2-150">Element</span></span>|<span data-ttu-id="92bb2-151">説明</span><span class="sxs-lookup"><span data-stu-id="92bb2-151">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92bb2-152">\<msmqIntegration></span><span class="sxs-lookup"><span data-stu-id="92bb2-152">\<msmqIntegration></span></span>](msmqintegration.md)|<span data-ttu-id="92bb2-153">Message Queuing (MSMQ) の送信側または受信側とのやり取りに必要な設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-153">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[<span data-ttu-id="92bb2-154">\<msmqTransport></span><span class="sxs-lookup"><span data-stu-id="92bb2-154">\<msmqTransport></span></span>](msmqtransport.md)|<span data-ttu-id="92bb2-155">ネイティブ MSMQ プロトコルを使用する Windows Communication Foundation (WCF) サービスのキュー通信プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="92bb2-155">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92bb2-156">Remarks</span><span class="sxs-lookup"><span data-stu-id="92bb2-156">Remarks</span></span>  
 <span data-ttu-id="92bb2-157">トランスポートセキュリティの詳細については、「[トランスポートセキュリティ](../../../wcf/feature-details/transport-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92bb2-157">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92bb2-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="92bb2-158">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="92bb2-159">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="92bb2-159">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="92bb2-160">トランスポート</span><span class="sxs-lookup"><span data-stu-id="92bb2-160">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="92bb2-161">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="92bb2-161">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="92bb2-162">バインディング</span><span class="sxs-lookup"><span data-stu-id="92bb2-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="92bb2-163">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="92bb2-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="92bb2-164">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="92bb2-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="92bb2-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="92bb2-165">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="92bb2-166">トランスポート セキュリティ</span><span class="sxs-lookup"><span data-stu-id="92bb2-166">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
