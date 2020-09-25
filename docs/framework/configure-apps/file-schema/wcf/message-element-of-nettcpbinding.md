---
title: <message> の要素 <netTcpBinding>
ms.date: 03/30/2017
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
ms.openlocfilehash: ab767a5a1179de81bf9a8adc61799ede2d915ac1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204906"
---
# <a name="message-element-of-nettcpbinding"></a><span data-ttu-id="3f8ad-102">\<message> の要素 \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="3f8ad-102">\<message> element of \<netTcpBinding></span></span>

<span data-ttu-id="3f8ad-103">で構成されるエンドポイントのメッセージレベルのセキュリティ要件の種類を定義し [\<netTcpBinding>](nettcpbinding.md) ます。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-103">Defines the type of message-level security requirements for an endpoint configured with the [\<netTcpBinding>](nettcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netTcpBinding>**](nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nettcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a><span data-ttu-id="3f8ad-104">構文</span><span class="sxs-lookup"><span data-stu-id="3f8ad-104">Syntax</span></span>  
  
```xml  
<message algorithmSuite="System.Servicemodel.Security.SecurityAlgorithmsuite"
         clientCredentialType="None/Windows/UserName/Certificate/IssuedToken" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f8ad-105">属性および要素</span><span class="sxs-lookup"><span data-stu-id="3f8ad-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3f8ad-106">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f8ad-107">属性</span><span class="sxs-lookup"><span data-stu-id="3f8ad-107">Attributes</span></span>  
  
|<span data-ttu-id="3f8ad-108">属性</span><span class="sxs-lookup"><span data-stu-id="3f8ad-108">Attribute</span></span>|<span data-ttu-id="3f8ad-109">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f8ad-109">Description</span></span>|  
|---------------|-----------------|  
|`algorithmSuite`|<span data-ttu-id="3f8ad-110">メッセージの暗号化とキー ラップ アルゴリズムを設定します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-110">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="3f8ad-111">アルゴリズムとキー サイズは、<xref:System.ServiceModel.Security.SecurityAlgorithmSuite> クラスにより決まります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-111">The algorithms and the key sizes are determined by the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> class.</span></span> <span data-ttu-id="3f8ad-112">これらのアルゴリズムは、セキュリティ ポリシー言語 (WS-SecurityPolicy) 仕様で指定されたアルゴリズムにマップされます。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-112">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="3f8ad-113">次の表に、使用可能な値を示します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-113">Possible values are shown in the following table.</span></span> <span data-ttu-id="3f8ad-114">既定値は `Basic256` です。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-114">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="3f8ad-115">サービス バインディングで指定されている `algorithmSuite` 値が既定値と異なると、Svcutil.exe を使用して構成ファイルを生成したときにファイルが正しく生成されません。この場合は、構成ファイルを手動で編集して、この属性を適切な値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-115">If the service binding specifies an `algorithmSuite` value that is not equal to the default, and you generate the configuration file using Svcutil.exe, then it is not generated correctly, and you must manually edit the configuration file to set this attribute to the desired value.</span></span>|  
|`clientCredentialType`|<span data-ttu-id="3f8ad-116">メッセージ ベースのセキュリティを使用してクライアント認証を実行するときに使用される資格情報の種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-116">Specifies the type of credential to be used when performing client authentication using Message-based security.</span></span> <span data-ttu-id="3f8ad-117">次の表に、使用可能な値を示します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-117">Possible values are shown in the following table.</span></span> <span data-ttu-id="3f8ad-118">既定値は `UserName` です。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-118">The default value is `UserName`.</span></span> <span data-ttu-id="3f8ad-119">この属性は <xref:System.ServiceModel.MessageCredentialType> 型です。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-119">This attribute is of type <xref:System.ServiceModel.MessageCredentialType>.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="3f8ad-120">algorithmSuite 属性</span><span class="sxs-lookup"><span data-stu-id="3f8ad-120">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="3f8ad-121">値</span><span class="sxs-lookup"><span data-stu-id="3f8ad-121">Value</span></span>|<span data-ttu-id="3f8ad-122">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f8ad-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f8ad-123">Basic128</span><span class="sxs-lookup"><span data-stu-id="3f8ad-123">Basic128</span></span>|<span data-ttu-id="3f8ad-124">Aes128 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-124">Use Aes128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-125">Basic192</span><span class="sxs-lookup"><span data-stu-id="3f8ad-125">Basic192</span></span>|<span data-ttu-id="3f8ad-126">Aes192 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-126">Use Aes192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-127">Basic256</span><span class="sxs-lookup"><span data-stu-id="3f8ad-127">Basic256</span></span>|<span data-ttu-id="3f8ad-128">Aes256 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-128">Use Aes256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-129">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-129">Basic256Rsa15</span></span>|<span data-ttu-id="3f8ad-130">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-130">Use Aes256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-131">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-131">Basic192Rsa15</span></span>|<span data-ttu-id="3f8ad-132">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-132">Use Aes192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-133">TripleDes</span><span class="sxs-lookup"><span data-stu-id="3f8ad-133">TripleDes</span></span>|<span data-ttu-id="3f8ad-134">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-134">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-135">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-135">Basic128Rsa15</span></span>|<span data-ttu-id="3f8ad-136">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-136">Use Aes128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-137">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-137">TripleDesRsa15</span></span>|<span data-ttu-id="3f8ad-138">TripleDes 暗号化を使用し、メッセージ ダイジェストには Sha1 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-138">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-139">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="3f8ad-139">Basic128Sha256</span></span>|<span data-ttu-id="3f8ad-140">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-140">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-141">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="3f8ad-141">Basic192Sha256</span></span>|<span data-ttu-id="3f8ad-142">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-142">Use Aes192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-143">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="3f8ad-143">Basic256Sha256</span></span>|<span data-ttu-id="3f8ad-144">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-144">Use Aes256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-145">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="3f8ad-145">TripleDesSha256</span></span>|<span data-ttu-id="3f8ad-146">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa-oaep-mgf1p を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-146">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-147">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-147">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="3f8ad-148">メッセージの暗号化には Aes128 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-148">Use Aes128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-149">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-149">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="3f8ad-150">メッセージの暗号化には Aes192 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-150">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-151">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-151">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="3f8ad-152">メッセージの暗号化には Aes256 を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-152">Use Aes256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="3f8ad-153">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="3f8ad-153">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="3f8ad-154">メッセージの暗号化には TripleDes を使用し、メッセージ ダイジェストには Sha256 を、キー ラップには Rsa15 を使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-154">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="3f8ad-155">clientCredentialType 属性</span><span class="sxs-lookup"><span data-stu-id="3f8ad-155">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="3f8ad-156">値</span><span class="sxs-lookup"><span data-stu-id="3f8ad-156">Value</span></span>|<span data-ttu-id="3f8ad-157">説明</span><span class="sxs-lookup"><span data-stu-id="3f8ad-157">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3f8ad-158">None</span><span class="sxs-lookup"><span data-stu-id="3f8ad-158">None</span></span>|<span data-ttu-id="3f8ad-159">サービスが匿名クライアントと対話できるようになります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-159">This allows the service to interact with anonymous clients.</span></span> <span data-ttu-id="3f8ad-160">サービス側では、サービスがクライアントの資格情報を必要としないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-160">On the service, this indicates that the service does not require any client credential.</span></span> <span data-ttu-id="3f8ad-161">クライアント側では、クライアントがクライアントの資格情報を提示しないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-161">On the client, this indicates that the client does not provide any client credential.</span></span>|  
|<span data-ttu-id="3f8ad-162">Windows</span><span class="sxs-lookup"><span data-stu-id="3f8ad-162">Windows</span></span>|<span data-ttu-id="3f8ad-163">SOAP 交換を、Windows 資格情報の認証されたコンテキストで行うことが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-163">Allows the SOAP exchanges to be under the authenticated context of a Windows credential.</span></span>|  
|<span data-ttu-id="3f8ad-164">UserName</span><span class="sxs-lookup"><span data-stu-id="3f8ad-164">UserName</span></span>|<span data-ttu-id="3f8ad-165">サービスが、UserName 資格情報を使用したクライアントの認証を要求できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-165">Allows the service to require that the client be authenticated using a UserName credential.</span></span> <span data-ttu-id="3f8ad-166">WCF では、パスワード ダイジェストの送信や、パスワードを使用したキーの派生およびこうしたキーの使用がサポートされません。これはメッセージのセキュリティを確保するためです。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-166">WCF does not support sending a password digest or deriving keys using password and using such keys for message security.</span></span> <span data-ttu-id="3f8ad-167">そのため、ユーザー名の資格情報を使用する場合、WCF はトランスポートがセキュリティで保護されることを強制します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-167">As such, WCF enforces that the transport is secured when using UserName credentials.</span></span> <span data-ttu-id="3f8ad-168">この資格情報モードは、`negotiateServiceCredential` 属性に基づいて、同時実行可能な交換か、同時実行できないネゴシエーションのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-168">This credential mode results in either an interoperable exchange or a non-interoperable negotiation based on the `negotiateServiceCredential` attribute.</span></span>|  
|<span data-ttu-id="3f8ad-169">Certificate</span><span class="sxs-lookup"><span data-stu-id="3f8ad-169">Certificate</span></span>|<span data-ttu-id="3f8ad-170">証明書を使用したクライアントの認証を、サービスで要求することが可能になります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-170">Allows the service to require that the client be authenticated using a certificate.</span></span> <span data-ttu-id="3f8ad-171">メッセージ セキュリティ モードが使用され、`negotiateServiceCredential` 属性が `false` に設定されている場合、クライアントにサービス証明書を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-171">If message security mode is used and the `negotiateServiceCredential` attribute is set to `false`, the client must be provisioned with the service certificate.</span></span>|  
|<span data-ttu-id="3f8ad-172">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="3f8ad-172">IssuedToken</span></span>|<span data-ttu-id="3f8ad-173">通常はセキュリティ トークン サービス (STS) により発行されるカスタム トークンを指定します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-173">Specifies a custom token, usually issued by a Security Token Service (STS).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f8ad-174">子要素</span><span class="sxs-lookup"><span data-stu-id="3f8ad-174">Child Elements</span></span>  

 <span data-ttu-id="3f8ad-175">None</span><span class="sxs-lookup"><span data-stu-id="3f8ad-175">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f8ad-176">親要素</span><span class="sxs-lookup"><span data-stu-id="3f8ad-176">Parent Elements</span></span>  
  
|<span data-ttu-id="3f8ad-177">要素</span><span class="sxs-lookup"><span data-stu-id="3f8ad-177">Element</span></span>|<span data-ttu-id="3f8ad-178">説明</span><span class="sxs-lookup"><span data-stu-id="3f8ad-178">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="3f8ad-179"><xref:System.ServiceModel.Configuration.NetTcpBindingElement>のセキュリティ機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-179">Defines the security capabilities for the <xref:System.ServiceModel.Configuration.NetTcpBindingElement>.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f8ad-180">解説</span><span class="sxs-lookup"><span data-stu-id="3f8ad-180">Remarks</span></span>  

 <span data-ttu-id="3f8ad-181">メッセージは、SOAP メッセージの整合性と機密性を確保し、通信ピアの相互認証を行うために、メッセージ レベルのセキュリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-181">Message uses message-level security for the integrity and confidentiality of the SOAP message, and for mutual authentication of the communication peers.</span></span> <span data-ttu-id="3f8ad-182">バインディング上でこのセキュリティ モードが選択された場合、チャネル スタックは、メッセージ セキュリティ バインド要素を使用して構成され、SOAP メッセージは WS-Security\* 標準に従って保護されます。</span><span class="sxs-lookup"><span data-stu-id="3f8ad-182">If this security mode is selected on a binding, the channel stack is configured with message security binding elements and the SOAP messages are secured in compliance with WS-Security\* standards.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f8ad-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="3f8ad-183">See also</span></span>

- <xref:System.ServiceModel.MessageSecurityOverTcp>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>
- <xref:System.ServiceModel.NetTcpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>
- [<span data-ttu-id="3f8ad-184">サービスおよびクライアントのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="3f8ad-184">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3f8ad-185">バインド</span><span class="sxs-lookup"><span data-stu-id="3f8ad-185">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3f8ad-186">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="3f8ad-186">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3f8ad-187">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="3f8ad-187">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
