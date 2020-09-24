---
title: <transport> の <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
ms.openlocfilehash: 03e6236d1e89f16a460860f5dffff19b7bed8a0a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169831"
---
# <a name="transport-of-msmqintegrationbinding"></a><span data-ttu-id="3f209-102">\<transport> の \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="3f209-102">\<transport> of \<msmqIntegrationBinding></span></span>

<span data-ttu-id="3f209-103">メッセージ キュー統合トランスポートのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f209-103">Defines the security settings for the Message Queuing integration transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="3f209-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f209-104">Syntax</span></span>  
  
```xml  
<security>
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f209-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3f209-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3f209-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f209-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f209-107">属性</span><span class="sxs-lookup"><span data-stu-id="3f209-107">Attributes</span></span>  
  
|<span data-ttu-id="3f209-108">属性</span><span class="sxs-lookup"><span data-stu-id="3f209-108">Attribute</span></span>|<span data-ttu-id="3f209-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f209-109">Description</span></span>|  
|---------------|-----------------|  
|`msmqAuthenticationMode`|<span data-ttu-id="3f209-110">MSMQ トランスポートによるメッセージの認証方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f209-110">Specifies how the message must be authenticated by the MSMQ transport.</span></span> <span data-ttu-id="3f209-111">これが `None` に設定されている場合、`msmqProtectionLevel` 属性の値も `None` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f209-111">If this is set to `None`, the value of the `msmqProtectionLevel` attribute must also be set to `None`.</span></span><br /><br /> <span data-ttu-id="3f209-112">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f209-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3f209-113">-None: 認証なし。</span><span class="sxs-lookup"><span data-stu-id="3f209-113">-   None: No authentication.</span></span><br /><span data-ttu-id="3f209-114">-WindowsDomain: 認証メカニズムは Active Directory を使用して、メッセージに関連付けられている SID の x.509 証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f209-114">-   WindowsDomain: The authentication mechanism uses Active Directory to get the X.509 certificate for the SID associated with the message.</span></span> <span data-ttu-id="3f209-115">次に、これを使用してキューの ACL がチェックされ、ユーザーがキューに書き込む権限を持っていることが確認されます。</span><span class="sxs-lookup"><span data-stu-id="3f209-115">This is then used to check the ACL of the queue to ensure the user has permission to write to the queue.</span></span><br /><span data-ttu-id="3f209-116">-Certificate: チャネルは、証明書ストアから証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f209-116">-   Certificate: The channel gets the certificate from the certificate store.</span></span><br /><br /> <span data-ttu-id="3f209-117">既定値は WindowsDomain です。</span><span class="sxs-lookup"><span data-stu-id="3f209-117">The default value is WindowsDomain.</span></span> <span data-ttu-id="3f209-118">この属性は <xref:System.ServiceModel.MsmqAuthenticationMode> 型です。</span><span class="sxs-lookup"><span data-stu-id="3f209-118">This attribute is of type <xref:System.ServiceModel.MsmqAuthenticationMode>.</span></span>|  
|`msmqEncryptionAlgorithm`|<span data-ttu-id="3f209-119">メッセージ キュー マネージャー間でメッセージを転送するときに、ネットワーク上でメッセージの暗号化に使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f209-119">Specifies the algorithm to be used for message encryption on the wire when transferring messages between message queue managers.</span></span> <span data-ttu-id="3f209-120">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f209-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="3f209-121">- RC4Stream</span><span class="sxs-lookup"><span data-stu-id="3f209-121">-   RC4Stream</span></span><br /><span data-ttu-id="3f209-122">-AES</span><span class="sxs-lookup"><span data-stu-id="3f209-122">-   AES</span></span><br /><br /> <span data-ttu-id="3f209-123">既定値は RC4Stream です。</span><span class="sxs-lookup"><span data-stu-id="3f209-123">The default value is RC4Stream.</span></span> <span data-ttu-id="3f209-124">この属性は <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="3f209-124">This attribute is of type <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.</span></span>|  
|`msmqProtectionLevel`|<span data-ttu-id="3f209-125">MSMQ トランスポートのレベルでメッセージをセキュリティで保護する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f209-125">Specifies how the message is secured at the level of the MSMQ transport.</span></span> <span data-ttu-id="3f209-126">暗号化によってメッセージの整合性が確保されますが、EncryptAndSign ではメッセージの整合性と否認不可が保証されます。つまり、メッセージは実際には送信者から送信され、送信者はそのことを伝えるものです。</span><span class="sxs-lookup"><span data-stu-id="3f209-126">Encryption ensures message integrity while EncryptAndSign ensures both message integrity and non-repudiation; that is, the message indeed comes from the sender and the sender is who they say they are.</span></span><br /><br /> <span data-ttu-id="3f209-127">-有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f209-127">-   Valid values include the following:</span></span><br /><span data-ttu-id="3f209-128">-None: 保護がありません。</span><span class="sxs-lookup"><span data-stu-id="3f209-128">-   None: No protection.</span></span><br /><span data-ttu-id="3f209-129">-Sign: メッセージは署名されています。</span><span class="sxs-lookup"><span data-stu-id="3f209-129">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="3f209-130">-EncryptAndSign: メッセージは暗号化され、署名されます。</span><span class="sxs-lookup"><span data-stu-id="3f209-130">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="3f209-131">既定値は Sign です。</span><span class="sxs-lookup"><span data-stu-id="3f209-131">The default value is Sign.</span></span> <span data-ttu-id="3f209-132">この属性は、ProtectionLevel 型です。</span><span class="sxs-lookup"><span data-stu-id="3f209-132">This attribute is of type ProtectionLevel.</span></span>|  
|`msmqSecureHashAlgorithm`|<span data-ttu-id="3f209-133">-署名の一部としてダイジェストを計算するために使用されるアルゴリズムを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f209-133">-   Specifies the algorithm to be used in computing the digest as part of signatures.</span></span> <span data-ttu-id="3f209-134">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f209-134">Valid values include the following:</span></span><br /><span data-ttu-id="3f209-135">-MD5</span><span class="sxs-lookup"><span data-stu-id="3f209-135">-   MD5</span></span><br /><span data-ttu-id="3f209-136">-SHA1</span><span class="sxs-lookup"><span data-stu-id="3f209-136">-   SHA1</span></span><br /><span data-ttu-id="3f209-137">-SHA256</span><span class="sxs-lookup"><span data-stu-id="3f209-137">-   SHA256</span></span><br /><span data-ttu-id="3f209-138">-SHA512</span><span class="sxs-lookup"><span data-stu-id="3f209-138">-   SHA512</span></span><br /><br /> <span data-ttu-id="3f209-139">既定値は SHA1 です。</span><span class="sxs-lookup"><span data-stu-id="3f209-139">The default value is SHA1.</span></span> <span data-ttu-id="3f209-140">この属性は <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 型です。</span><span class="sxs-lookup"><span data-stu-id="3f209-140">This attribute is of type <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.</span></span><br><span data-ttu-id="3f209-141">MD5 と SHA1 の衝突の問題のため、SHA256 以上をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3f209-141">Due to collision problems with MD5 and SHA1, Microsoft recommends SHA256 or better.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f209-142">子要素</span><span class="sxs-lookup"><span data-stu-id="3f209-142">Child Elements</span></span>  

 <span data-ttu-id="3f209-143">None</span><span class="sxs-lookup"><span data-stu-id="3f209-143">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f209-144">親要素</span><span class="sxs-lookup"><span data-stu-id="3f209-144">Parent Elements</span></span>  
  
|<span data-ttu-id="3f209-145">要素</span><span class="sxs-lookup"><span data-stu-id="3f209-145">Element</span></span>|<span data-ttu-id="3f209-146">説明</span><span class="sxs-lookup"><span data-stu-id="3f209-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="3f209-147">MSMQ バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f209-147">Defines the security settings for a MSMQ binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f209-148">解説</span><span class="sxs-lookup"><span data-stu-id="3f209-148">Remarks</span></span>  

 <span data-ttu-id="3f209-149">この要素は、メッセージ キュー統合トランスポートのセキュリティ設定をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="3f209-149">This element encapsulates the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="3f209-150">設定は、メッセージ キュー統合トランスポートとキューに置かれているトランスポートの両方で同じです。</span><span class="sxs-lookup"><span data-stu-id="3f209-150">The settings are the same for both the Message Queuing integration and queued transports.</span></span> <span data-ttu-id="3f209-151">この設定を使用すると、認証モード、暗号化アルゴリズム、セキュア ハッシュ アルゴリズム、および保護レベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="3f209-151">It enables you to set the Authentication Mode, Encryption Algorithm, Secure Hash Algorithm, and Protection Level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f209-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f209-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>
- <xref:System.ServiceModel.MsmqTransportSecurity>
- [<span data-ttu-id="3f209-153">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3f209-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3f209-154">バインド</span><span class="sxs-lookup"><span data-stu-id="3f209-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3f209-155">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="3f209-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3f209-156">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="3f209-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
