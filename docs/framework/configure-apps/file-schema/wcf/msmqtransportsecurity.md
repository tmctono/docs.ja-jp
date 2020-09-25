---
title: <msmqTransportSecurity>
ms.date: 03/30/2017
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
ms.openlocfilehash: 9d28f3f08e9c3984c055567df03f2839709a1522
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204646"
---
# \<msmqTransportSecurity>

<span data-ttu-id="06065-101">カスタム バインディングの MSMQ トランスポート セキュリティ設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-101">Specifies MSMQ transport security settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegration>**](msmqintegration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransportSecurity>**  
  
## <a name="syntax"></a><span data-ttu-id="06065-102">構文</span><span class="sxs-lookup"><span data-stu-id="06065-102">Syntax</span></span>  
  
```xml  
<msmqTransportSecurity msmqAuthenticationMode="None/Windows/Certificate"
                       msmqEncryptionAlgorithm="RC4Stream/AES"
                       msmqProtectionLevel="None/Sign/EncryptAndSign"
                       msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</msmqTransportSecurity>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06065-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="06065-103">Attributes and Elements</span></span>  

 <span data-ttu-id="06065-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="06065-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06065-105">属性</span><span class="sxs-lookup"><span data-stu-id="06065-105">Attributes</span></span>  
  
|<span data-ttu-id="06065-106">属性</span><span class="sxs-lookup"><span data-stu-id="06065-106">Attribute</span></span>|<span data-ttu-id="06065-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="06065-107">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="06065-108">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-108">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="06065-109">これが `None` に設定されている場合、`msmqProtectionLevel` 属性の値も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06065-109">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="06065-110">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06065-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06065-111">-None: 認証なし。</span><span class="sxs-lookup"><span data-stu-id="06065-111">-   None: No authentication.</span></span><br /><span data-ttu-id="06065-112">-Windows: 認証メカニズムは Active Directory を使用して、メッセージに関連付けられている SID の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="06065-112">-   Windows: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="06065-113">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューに書き込む権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="06065-113">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="06065-114">-Certificate: チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="06065-114">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="06065-115">既定値は Windows です。</span><span class="sxs-lookup"><span data-stu-id="06065-115">The default value is Windows.</span></span> <span data-ttu-id="06065-116">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="06065-116">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="06065-117">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-117">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="06065-118">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06065-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06065-119">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="06065-119">-   RC4Stream</span></span><br /><span data-ttu-id="06065-120">-AES</span><span class="sxs-lookup"><span data-stu-id="06065-120">-   AES</span></span><br /><br /> <span data-ttu-id="06065-121">既定値は RC4Stream です。</span><span class="sxs-lookup"><span data-stu-id="06065-121">The default value is RC4Stream.</span></span> <span data-ttu-id="06065-122">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="06065-122">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="06065-123">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-123">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="06065-124">暗号化によってメッセージの整合性が確保されますが、EncryptAndSign ではメッセージの整合性と否認不可が保証されます。つまり、メッセージは実際には送信者から送信され、送信者はそのことを伝えるものです。</span><span class="sxs-lookup"><span data-stu-id="06065-124">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span> <span data-ttu-id="06065-125">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06065-125">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06065-126">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="06065-126">-   None: No protection.</span></span><br /><span data-ttu-id="06065-127">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="06065-127">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="06065-128">-EncryptAndSign: メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="06065-128">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="06065-129">既定値は Sign です。</span><span class="sxs-lookup"><span data-stu-id="06065-129">The default value is Sign.</span></span> <span data-ttu-id="06065-130">この属性は <xref:System.Net.Security.ProtectionLevel> 型です。</span><span class="sxs-lookup"><span data-stu-id="06065-130">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="06065-131">署名の一部としてダイジェストの計算に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-131">Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="06065-132">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="06065-132">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="06065-133">-MD5</span><span class="sxs-lookup"><span data-stu-id="06065-133">-   MD5</span></span><br /><span data-ttu-id="06065-134">-SHA1</span><span class="sxs-lookup"><span data-stu-id="06065-134">-   SHA1</span></span><br /><span data-ttu-id="06065-135">-SHA256</span><span class="sxs-lookup"><span data-stu-id="06065-135">-   SHA256</span></span><br /><span data-ttu-id="06065-136">-SHA512</span><span class="sxs-lookup"><span data-stu-id="06065-136">-   SHA512</span></span><br /><br /> <span data-ttu-id="06065-137">既定値は SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="06065-137">The default value is SHA1.</span></span> <span data-ttu-id="06065-138">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="06065-138">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="06065-139">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="06065-139">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="06065-140">子要素</span><span class="sxs-lookup"><span data-stu-id="06065-140">Child Elements</span></span>  

 <span data-ttu-id="06065-141">なし。</span><span class="sxs-lookup"><span data-stu-id="06065-141">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="06065-142">親要素</span><span class="sxs-lookup"><span data-stu-id="06065-142">Parent Elements</span></span>  
  
|<span data-ttu-id="06065-143">要素</span><span class="sxs-lookup"><span data-stu-id="06065-143">Element</span></span>|<span data-ttu-id="06065-144">説明</span><span class="sxs-lookup"><span data-stu-id="06065-144">Description</span></span>|  
|-------------|-----------------|  
|[\<msmqIntegration>](msmqintegration.md)|<span data-ttu-id="06065-145">Message Queuing (MSMQ) の送信側または受信側とのやり取りに必要な設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-145">Specifies settings required for interaction with a Message Queuing (MSMQ) sender or receiver.</span></span>|  
|[\<msmqTransport>](msmqtransport.md)|<span data-ttu-id="06065-146">ネイティブ MSMQ プロトコルを使用する Windows Communication Foundation (WCF) サービスのキュー通信プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="06065-146">Specifies the queuing communication properties for a Windows Communication Foundation (WCF) service that uses the native MSMQ protocol.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06065-147">解説</span><span class="sxs-lookup"><span data-stu-id="06065-147">Remarks</span></span>  

 <span data-ttu-id="06065-148">トランスポートセキュリティの詳細については、「 [トランスポートセキュリティ](../../../wcf/feature-details/transport-security.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06065-148">For more information on transport security, see [Transport Security](../../../wcf/feature-details/transport-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06065-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="06065-149">See also</span></span>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="06065-150">WCF のキュー</span><span class="sxs-lookup"><span data-stu-id="06065-150">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="06065-151">トランスポート</span><span class="sxs-lookup"><span data-stu-id="06065-151">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="06065-152">トランスポートの選択</span><span class="sxs-lookup"><span data-stu-id="06065-152">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="06065-153">バインド</span><span class="sxs-lookup"><span data-stu-id="06065-153">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="06065-154">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="06065-154">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="06065-155">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="06065-155">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [<span data-ttu-id="06065-156">トランスポートセキュリティ</span><span class="sxs-lookup"><span data-stu-id="06065-156">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
