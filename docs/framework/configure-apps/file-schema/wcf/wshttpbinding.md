---
title: <wsHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 6059bc91588492afdd1f205398e6cdfdba0be7ef
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670184"
---
# <a name="wshttpbinding"></a><span data-ttu-id="1e63b-101">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1e63b-101">\<wsHttpBinding></span></span>
<span data-ttu-id="1e63b-102">双方向サービス コントラクト以外に適した、安全で信頼のおける相互操作可能なバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="1e63b-103">バインディングは、次の仕様を実装します。Ws-reliable メッセージングの信頼性、およびメッセージ セキュリティと認証用 Ws-security。</span><span class="sxs-lookup"><span data-stu-id="1e63b-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="1e63b-104">トランスポートは HTTP、メッセージ エンコーディングは Text/XML エンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="1e63b-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
 <span data-ttu-id="1e63b-105">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1e63b-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="1e63b-106">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1e63b-106">\<bindings></span></span>  
<span data-ttu-id="1e63b-107">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="1e63b-107">\<wsHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e63b-108">構文</span><span class="sxs-lookup"><span data-stu-id="1e63b-108">Syntax</span></span>  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e63b-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1e63b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1e63b-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e63b-111">属性</span><span class="sxs-lookup"><span data-stu-id="1e63b-111">Attributes</span></span>  
  
|<span data-ttu-id="1e63b-112">属性</span><span class="sxs-lookup"><span data-stu-id="1e63b-112">Attribute</span></span>|<span data-ttu-id="1e63b-113">説明</span><span class="sxs-lookup"><span data-stu-id="1e63b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1e63b-114">allowCookies</span><span class="sxs-lookup"><span data-stu-id="1e63b-114">allowCookies</span></span>|<span data-ttu-id="1e63b-115">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-115">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="1e63b-116">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-116">The default is false.</span></span><br /><br /> <span data-ttu-id="1e63b-117">クッキーを使用する ASMX Web サービスと対話する場合にこのプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="1e63b-117">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="1e63b-118">この方法で、サーバーから返されるクッキーを、それ以降のサービスに対するすべてのクライアント要求に自動的にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="1e63b-118">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="1e63b-119">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="1e63b-119">bypassProxyOnLocal</span></span>|<span data-ttu-id="1e63b-120">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="1e63b-120">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="1e63b-121">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-121">The default is `false`.</span></span>|  
|<span data-ttu-id="1e63b-122">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="1e63b-122">closeTimeout</span></span>|<span data-ttu-id="1e63b-123">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="1e63b-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="1e63b-124">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1e63b-125">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-125">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1e63b-126">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="1e63b-126">hostnameComparisonMode</span></span>|<span data-ttu-id="1e63b-127">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-127">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="1e63b-128">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-128">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="1e63b-129">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-129">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="1e63b-130">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="1e63b-130">maxBufferPoolSize</span></span>|<span data-ttu-id="1e63b-131">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="1e63b-131">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="1e63b-132">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-132">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="1e63b-133">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-133">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="1e63b-134">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-134">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="1e63b-135">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="1e63b-135">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="1e63b-136">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="1e63b-136">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="1e63b-137">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="1e63b-137">maxReceivedMessageSize</span></span>|<span data-ttu-id="1e63b-138">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="1e63b-138">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="1e63b-139">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-139">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="1e63b-140">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1e63b-140">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="1e63b-141">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-141">The default is 65536.</span></span>|  
|<span data-ttu-id="1e63b-142">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="1e63b-142">messageEncoding</span></span>|<span data-ttu-id="1e63b-143">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-143">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="1e63b-144">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1e63b-145">テキスト:テキスト メッセージ エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="1e63b-146">Mtom:Message Transmission 組織 Mechanism 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="1e63b-147">-既定値はテキストです。</span><span class="sxs-lookup"><span data-stu-id="1e63b-147">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="1e63b-148">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="1e63b-149">name</span><span class="sxs-lookup"><span data-stu-id="1e63b-149">name</span></span>|<span data-ttu-id="1e63b-150">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="1e63b-151">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="1e63b-152">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1e63b-152">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="1e63b-153">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e63b-153">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="1e63b-154">openTimeout</span><span class="sxs-lookup"><span data-stu-id="1e63b-154">openTimeout</span></span>|<span data-ttu-id="1e63b-155">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-155">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="1e63b-156">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-156">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1e63b-157">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-157">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1e63b-158">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="1e63b-158">proxyAddress</span></span>|<span data-ttu-id="1e63b-159">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="1e63b-159">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="1e63b-160">`useSystemWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-160">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="1e63b-161">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-161">The default is `null`.</span></span>|  
|<span data-ttu-id="1e63b-162">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="1e63b-162">receiveTimeout</span></span>|<span data-ttu-id="1e63b-163">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-163">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="1e63b-164">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-164">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1e63b-165">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-165">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1e63b-166">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="1e63b-166">sendTimeout</span></span>|<span data-ttu-id="1e63b-167">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-167">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="1e63b-168">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-168">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="1e63b-169">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-169">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="1e63b-170">textEncoding</span><span class="sxs-lookup"><span data-stu-id="1e63b-170">textEncoding</span></span>|<span data-ttu-id="1e63b-171">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-171">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="1e63b-172">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1e63b-173">-   UnicodeFffeTextEncoding:Unicode BigEndian エンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="1e63b-173">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="1e63b-174">-   Utf16TextEncoding:16 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="1e63b-174">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="1e63b-175">-   Utf8TextEncoding:8 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="1e63b-175">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="1e63b-176">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-176">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="1e63b-177">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="1e63b-178">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="1e63b-178">transactionFlow</span></span>|<span data-ttu-id="1e63b-179">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-179">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="1e63b-180">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-180">The default is `false`.</span></span>|  
|<span data-ttu-id="1e63b-181">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="1e63b-181">useDefaultWebProxy</span></span>|<span data-ttu-id="1e63b-182">システムの自動設定 HTTP プロキシを使用するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="1e63b-182">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="1e63b-183">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e63b-184">子要素</span><span class="sxs-lookup"><span data-stu-id="1e63b-184">Child Elements</span></span>  
  
|<span data-ttu-id="1e63b-185">要素</span><span class="sxs-lookup"><span data-stu-id="1e63b-185">Element</span></span>|<span data-ttu-id="1e63b-186">説明</span><span class="sxs-lookup"><span data-stu-id="1e63b-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e63b-187">\<security></span><span class="sxs-lookup"><span data-stu-id="1e63b-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="1e63b-188">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="1e63b-189">この要素は <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-189">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="1e63b-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1e63b-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="1e63b-191">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1e63b-192">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="1e63b-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="1e63b-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1e63b-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="1e63b-194">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e63b-195">親要素</span><span class="sxs-lookup"><span data-stu-id="1e63b-195">Parent Elements</span></span>  
  
|<span data-ttu-id="1e63b-196">要素</span><span class="sxs-lookup"><span data-stu-id="1e63b-196">Element</span></span>|<span data-ttu-id="1e63b-197">説明</span><span class="sxs-lookup"><span data-stu-id="1e63b-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e63b-198">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1e63b-198">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="1e63b-199">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="1e63b-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e63b-200">Remarks</span><span class="sxs-lookup"><span data-stu-id="1e63b-200">Remarks</span></span>  
 <span data-ttu-id="1e63b-201">`WSHttpBinding` は `BasicHttpBinding` に似ていますが、より多くの Web サービス機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="1e63b-201">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="1e63b-202">BasicHttpBinding と同じように HTTP トランスポートを使用し、メッセージ セキュリティを提供します。さらに、トランザクション、信頼できるメッセージング、および WS-Addressing も提供します。これらは、既定で有効化になっているか、または単一の制御設定で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1e63b-202">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e63b-203">例</span><span class="sxs-lookup"><span data-stu-id="1e63b-203">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="1e63b-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="1e63b-204">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="1e63b-205">バインディング</span><span class="sxs-lookup"><span data-stu-id="1e63b-205">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1e63b-206">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="1e63b-206">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1e63b-207">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="1e63b-207">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1e63b-208">\<binding></span><span class="sxs-lookup"><span data-stu-id="1e63b-208">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
