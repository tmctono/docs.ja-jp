---
title: <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: b0d81ca0-87c5-4090-8baa-e390fd3656d2
ms.openlocfilehash: ff589c502333851de4dcf23101bb14fac767d25d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933082"
---
# <a name="nethttpbinding"></a><span data-ttu-id="b83b5-101">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b83b5-101">\<netHttpBinding></span></span>
<span data-ttu-id="b83b5-102">HTTP 経由で通信できるエンドポイントを構成および公開するために Windows Communication Foundation (WCF) サービスが使用できるバインディングを表します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate over HTTP.</span></span> <span data-ttu-id="b83b5-103">双方向コントラクトで使用すると、Web ソケットが使用されます。それ以外の場合は、HTTP が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-103">When used with a duplex contract, Web Sockets will be used, otherwise HTTP will be used.</span></span>  
  
 <span data-ttu-id="b83b5-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b83b5-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b83b5-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b83b5-105">\<bindings></span></span>  
<span data-ttu-id="b83b5-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="b83b5-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b83b5-107">構文</span><span class="sxs-lookup"><span data-stu-id="b83b5-107">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Binary/Text/Mtom"
           name="String"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="b83b5-108">型</span><span class="sxs-lookup"><span data-stu-id="b83b5-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b83b5-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="b83b5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b83b5-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b83b5-111">属性</span><span class="sxs-lookup"><span data-stu-id="b83b5-111">Attributes</span></span>  
  
|<span data-ttu-id="b83b5-112">属性</span><span class="sxs-lookup"><span data-stu-id="b83b5-112">Attribute</span></span>|<span data-ttu-id="b83b5-113">説明</span><span class="sxs-lookup"><span data-stu-id="b83b5-113">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="b83b5-114">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-114">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="b83b5-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-115">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b83b5-116">クッキーを使用する ASMX Web サービスと対話する場合にこのプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-116">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="b83b5-117">この方法で、サーバーから返されるクッキーを、それ以降のサービスに対するすべてのクライアント要求に自動的にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-117">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="b83b5-118">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="b83b5-118">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="b83b5-119">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-119">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b83b5-120">インターネット リソースは、ローカル アドレスを持つ場合ローカルです。</span><span class="sxs-lookup"><span data-stu-id="b83b5-120">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="b83b5-121">によって識別される、構文的に、Uri と同様にピリオド (.) の欠如が同じコンピューター、ローカル LAN またはイントラネット上にあり、ローカル アドレスは "http://webserver/" と "http://localhost/" です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-121">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="b83b5-122">この属性の設定は、BasicHttpBinding で構成されたエンドポイントがローカル リソースへのアクセス時にプロキシ サーバーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-122">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="b83b5-123">この属性が `true` の場合、ローカル インターネット リソースへの要求はプロキシ サーバーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="b83b5-123">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="b83b5-124">この属性を `true` に設定した場合で、同じコンピューター上のサービスと対話するクライアントがプロキシを経由するときは、(localhost ではなく) ホスト名を使用します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-124">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="b83b5-125">この属性が `false` の場合、すべてのインターネット要求はプロキシ サーバー経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-125">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="b83b5-126">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="b83b5-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="b83b5-127">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b83b5-128">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-128">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="b83b5-129">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-129">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="b83b5-130">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-130">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="b83b5-131">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-131">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="b83b5-132">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="b83b5-132">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="b83b5-133">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="b83b5-133">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="b83b5-134">バッファー マネージャーは、バッファー プールを使用することで、バッファーの使用コストを最小化します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-134">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="b83b5-135">バッファーは、チャネルから出てくるメッセージをサービスが処理するときに必要です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-135">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="b83b5-136">メッセージの読み込み処理に十分なメモリがバッファー プールにない場合、バッファー マネージャーは、CLR ヒープから追加のメモリを割り当てる必要があります。これにより、ガベージ コレクションのオーバーヘッドが増加します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-136">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="b83b5-137">CLR ガベージ ヒープから多大な割り当てが行われることは、バッファー プール サイズが小さすぎること、およびこの属性で指定される制限を緩めて割り当てを増やすとパフォーマンスが向上する可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-137">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="b83b5-138">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="b83b5-138">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="b83b5-139">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="b83b5-139">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="b83b5-140">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="b83b5-140">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="b83b5-141">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-141">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="b83b5-142">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-142">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="b83b5-143">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="b83b5-143">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="b83b5-144">SOAP メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-144">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="b83b5-145">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b83b5-145">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b83b5-146">本文テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-146">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="b83b5-147">Mtomメッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-147">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="b83b5-148">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-148">The default is Text.</span></span> <span data-ttu-id="b83b5-149">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-149">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="b83b5-150">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-150">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="b83b5-151">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-151">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="b83b5-152">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b83b5-152">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="b83b5-153">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-153">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="b83b5-154">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b83b5-154">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b83b5-155">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b83b5-155">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`namespace`|<span data-ttu-id="b83b5-156">バインディングの XML 名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-156">Specifies the XML namespace of the binding.</span></span> <span data-ttu-id="b83b5-157">既定値は "http://tempuri.org/Bindings" です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-157">The default value is "http://tempuri.org/Bindings".</span></span> <span data-ttu-id="b83b5-158">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b83b5-158">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span>|  
|`openTimeout`|<span data-ttu-id="b83b5-159">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="b83b5-160">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b83b5-161">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-161">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="b83b5-162">HTTP プロキシのアドレスを格納する URI。</span><span class="sxs-lookup"><span data-stu-id="b83b5-162">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="b83b5-163">`useSystemWebProxy` が `true` に設定されている場合、この設定は `null` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-163">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="b83b5-164">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-164">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="b83b5-165">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-165">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="b83b5-166">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-166">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b83b5-167">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-167">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="b83b5-168">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-168">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="b83b5-169">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-169">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="b83b5-170">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-170">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="b83b5-171">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-171">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b83b5-172">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-172">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="b83b5-173">BigEndianUnicodeUnicode BigEndian エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="b83b5-173">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="b83b5-174">対応16ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="b83b5-174">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="b83b5-175">UTF88ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="b83b5-175">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="b83b5-176">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-176">The default is UTF8.</span></span> <span data-ttu-id="b83b5-177">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-177">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="b83b5-178">要求または応答に対してメッセージがバッファーされるか、ストリーム配信されるかを指定する有効な <xref:System.ServiceModel.TransferMode> 値。</span><span class="sxs-lookup"><span data-stu-id="b83b5-178">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="b83b5-179">使用できる場合にシステムの自動設定 HTTP プロキシを使用するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="b83b5-179">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="b83b5-180">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-180">The default is `true`.</span></span>|  
|||  
  
### <a name="child-elements"></a><span data-ttu-id="b83b5-181">子要素</span><span class="sxs-lookup"><span data-stu-id="b83b5-181">Child Elements</span></span>  
  
|<span data-ttu-id="b83b5-182">要素</span><span class="sxs-lookup"><span data-stu-id="b83b5-182">Element</span></span>|<span data-ttu-id="b83b5-183">説明</span><span class="sxs-lookup"><span data-stu-id="b83b5-183">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b83b5-184">\<security></span><span class="sxs-lookup"><span data-stu-id="b83b5-184">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="b83b5-185">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-185">Defines the security settings for the binding.</span></span> <span data-ttu-id="b83b5-186">この要素は <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-186">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="b83b5-187">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b83b5-187">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="b83b5-188">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-188">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b83b5-189">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="b83b5-189">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b83b5-190">親要素</span><span class="sxs-lookup"><span data-stu-id="b83b5-190">Parent Elements</span></span>  
  
|<span data-ttu-id="b83b5-191">要素</span><span class="sxs-lookup"><span data-stu-id="b83b5-191">Element</span></span>|<span data-ttu-id="b83b5-192">説明</span><span class="sxs-lookup"><span data-stu-id="b83b5-192">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b83b5-193">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b83b5-193">\<bindings></span></span>](bindings.md)|<span data-ttu-id="b83b5-194">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-194">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b83b5-195">Remarks</span><span class="sxs-lookup"><span data-stu-id="b83b5-195">Remarks</span></span>  
 <span data-ttu-id="b83b5-196">NetHttpBinding では、メッセージを送信するために、HTTP をトランスポートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-196">The NetHttpBinding uses HTTP as the transport for sending messages.</span></span> <span data-ttu-id="b83b5-197">双方向コントラクトで使用すると、Web ソケットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-197">When used with a duplex contract, Web Sockets will be used.</span></span>  <span data-ttu-id="b83b5-198">要求/応答コントラクト NetHttpBinding と使用する場合、バイナリ エンコーダーとの BasicHttpBinding のように動作します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-198">When used with a request-reply contract NetHttpBinding will behave like a BasicHttpBinding with a binary encoder.</span></span>  
  
 <span data-ttu-id="b83b5-199">既定ではセキュリティはオフになっていますが、 [ \<セキュリティ >](security-of-basichttpbinding.md)の子要素の mode 属性を以外`None`の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-199">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="b83b5-200">サービスは、"Text" メッセージ エンコードおよび UTF-8 テキスト エンコードを既定で使用します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-200">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b83b5-201">例</span><span class="sxs-lookup"><span data-stu-id="b83b5-201">Example</span></span>  
 <span data-ttu-id="b83b5-202">第 1 世代と第 2 世代の Web サービスで HTTP 通信と最大限の相互運用性を実現する、<xref:System.ServiceModel.NetHttpBinding> の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-202">The following example demonstrates the use of <xref:System.ServiceModel.NetHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="b83b5-203">バインディングは、クライアントとサービスの構成ファイルに指定されます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-203">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="b83b5-204">バインディングの種類は、`binding` 要素の `<endpoint>` 属性を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="b83b5-204">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="b83b5-205">基本的なバインディングを構成してその設定の一部を変更する場合は、バインド構成を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b83b5-205">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="b83b5-206">エンドポイントは、`bindingConfiguration` 要素の `<endpoint>` 属性を使用して、名前でバインディング構成を参照する必要があります。次のサービスの構成コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b83b5-206">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <binding name="Binding1"
               hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="b83b5-207">例</span><span class="sxs-lookup"><span data-stu-id="b83b5-207">Example</span></span>  
 <span data-ttu-id="b83b5-208">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b83b5-208">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="b83b5-209">前の例の機能は、エンドポイントアドレスから bindingConfiguration を削除し、バインドから名前を削除することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="b83b5-209">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <binding hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Binary"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="b83b5-210">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b83b5-210">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b83b5-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="b83b5-211">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="b83b5-212">バインディング</span><span class="sxs-lookup"><span data-stu-id="b83b5-212">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b83b5-213">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="b83b5-213">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b83b5-214">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="b83b5-214">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b83b5-215">\<binding></span><span class="sxs-lookup"><span data-stu-id="b83b5-215">\<binding></span></span>](../../../misc/binding.md)
