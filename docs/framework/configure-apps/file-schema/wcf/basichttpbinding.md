---
title: <basicHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- basicHttpBinding Element
ms.assetid: 85cf1a4f-26c2-48c7-bda6-6c960d5d3fb3
ms.openlocfilehash: f1be0997fc7b2b884c7ec90ea6a02ea0af96ab4c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431026"
---
# <a name="basichttpbinding"></a><span data-ttu-id="29e31-101">basicHttpBinding > \<</span><span class="sxs-lookup"><span data-stu-id="29e31-101">\<basicHttpBinding></span></span>
<span data-ttu-id="29e31-102">ASMX ベースの Web サービスやクライアント、および WS-I Basic Profile 1.1 に準拠するその他のサービスとの通信が可能なエンドポイントを構成および公開するために、Windows Communication Foundation (WCF) サービスが使用できるバインドを表します。</span><span class="sxs-lookup"><span data-stu-id="29e31-102">Represents a binding that a Windows Communication Foundation (WCF) service can use to configure and expose endpoints that are able to communicate with ASMX-based Web services and clients and other services that conform to the WS-I Basic Profile 1.1.</span></span>  
  
<span data-ttu-id="29e31-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="29e31-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="29e31-104">&nbsp;&nbsp;[ **\<system.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="29e31-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="29e31-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)></span><span class="sxs-lookup"><span data-stu-id="29e31-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="29e31-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**basicHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="29e31-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<basicHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e31-107">構文</span><span class="sxs-lookup"><span data-stu-id="29e31-107">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
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
                 realm="String" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29e31-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="29e31-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29e31-109">次のセクションでは、属性、子要素、親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="29e31-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29e31-110">属性</span><span class="sxs-lookup"><span data-stu-id="29e31-110">Attributes</span></span>  
  
|<span data-ttu-id="29e31-111">属性</span><span class="sxs-lookup"><span data-stu-id="29e31-111">Attribute</span></span>|<span data-ttu-id="29e31-112">説明</span><span class="sxs-lookup"><span data-stu-id="29e31-112">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="29e31-113">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="29e31-113">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="29e31-114">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="29e31-114">The default is `false`.</span></span><br /><br /> <span data-ttu-id="29e31-115">クッキーを使用する ASMX Web サービスと対話する場合にこのプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29e31-115">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="29e31-116">この方法で、サーバーから返されるクッキーを、それ以降のサービスに対するすべてのクライアント要求に自動的にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="29e31-116">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="29e31-117">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="29e31-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="29e31-118">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="29e31-118">The default is `false`.</span></span><br /><br /> <span data-ttu-id="29e31-119">インターネット リソースは、ローカル アドレスを持つ場合ローカルです。</span><span class="sxs-lookup"><span data-stu-id="29e31-119">An Internet resource is local if it has a local address.</span></span> <span data-ttu-id="29e31-120">ローカルアドレスは、同じコンピューター、ローカル LAN、またはイントラネット上にあり、構文的には、Uri "http://webserver/" と "http://localhost/" のようにピリオド (.) がないことで識別されます。</span><span class="sxs-lookup"><span data-stu-id="29e31-120">A local address is one that is on same computer, the local LAN or intranet and is identified, syntactically, by the lack of a period (.) as in the URIs "http://webserver/" and "http://localhost/".</span></span><br /><br /> <span data-ttu-id="29e31-121">この属性の設定は、BasicHttpBinding で構成されたエンドポイントがローカル リソースへのアクセス時にプロキシ サーバーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="29e31-121">Setting this attribute determines whether endpoints configured with the BasicHttpBinding use the proxy server when accessing local resources.</span></span> <span data-ttu-id="29e31-122">この属性が `true` の場合、ローカル インターネット リソースへの要求はプロキシ サーバーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="29e31-122">If this attribute is `true`, requests to local Internet resources do not use the proxy server.</span></span> <span data-ttu-id="29e31-123">この属性を `true` に設定した場合で、同じコンピューター上のサービスと対話するクライアントがプロキシを経由するときは、(localhost ではなく) ホスト名を使用します。</span><span class="sxs-lookup"><span data-stu-id="29e31-123">Use the host name (rather than localhost) if you want clients to go through a proxy when talking to services on the same machine when this attribute is set to `true`.</span></span><br /><br /> <span data-ttu-id="29e31-124">この属性が `false` の場合、すべてのインターネット要求はプロキシ サーバー経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="29e31-124">When this attribute is `false`, all Internet requests are made through the proxy server.</span></span>|  
|`closeTimeout`|<span data-ttu-id="29e31-125">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="29e31-125">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="29e31-126">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-126">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29e31-127">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="29e31-127">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="29e31-128">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="29e31-128">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="29e31-129">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="29e31-129">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="29e31-130">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="29e31-130">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="29e31-131">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="29e31-131">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="29e31-132">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="29e31-132">The default value is 524288 (0x80000) bytes.</span></span><br /><br /> <span data-ttu-id="29e31-133">バッファー マネージャーは、バッファー プールを使用することで、バッファーの使用コストを最小化します。</span><span class="sxs-lookup"><span data-stu-id="29e31-133">The Buffer Manager minimizes the cost of using buffers by using a buffer pool.</span></span> <span data-ttu-id="29e31-134">バッファーは、チャネルから出てくるメッセージをサービスが処理するときに必要です。</span><span class="sxs-lookup"><span data-stu-id="29e31-134">Buffers are required to process messages by the service when they come out of the channel.</span></span> <span data-ttu-id="29e31-135">メッセージの読み込み処理に十分なメモリがバッファー プールにない場合、バッファー マネージャーは、CLR ヒープから追加のメモリを割り当てる必要があります。これにより、ガベージ コレクションのオーバーヘッドが増加します。</span><span class="sxs-lookup"><span data-stu-id="29e31-135">If there is not sufficient memory in the buffer pool to process the message load, the Buffer Manager must allocate additional memory from the CLR heap, which increases the garbage collection overhead.</span></span> <span data-ttu-id="29e31-136">CLR ガベージ ヒープから多大な割り当てが行われることは、バッファー プール サイズが小さすぎること、およびこの属性で指定される制限を緩めて割り当てを増やすとパフォーマンスが向上する可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="29e31-136">Extensive allocation from the CLR garbage heap is an indication that the buffer pool size is too small and that performance can be improved with a larger allocation by increasing the limit specified by this attribute.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="29e31-137">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="29e31-137">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="29e31-138">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="29e31-138">The default value is 65,536 bytes.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="29e31-139">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="29e31-139">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="29e31-140">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="29e31-140">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="29e31-141">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="29e31-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="29e31-142">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="29e31-142">The default is 65,536 bytes.</span></span>|  
|`messageEncoding`|<span data-ttu-id="29e31-143">SOAP メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="29e31-143">Defines the encoder used to encode the SOAP message.</span></span> <span data-ttu-id="29e31-144">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29e31-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29e31-145">-Text: テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="29e31-145">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="29e31-146">-Mtom: メッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="29e31-146">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="29e31-147">既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="29e31-147">The default is Text.</span></span> <span data-ttu-id="29e31-148">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="29e31-148">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="29e31-149">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="29e31-149">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="29e31-150">この値は、同じ型のバインド間で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-150">This value should be unique among bindings of the same type.</span></span> <span data-ttu-id="29e31-151">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29e31-151">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="29e31-152">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e31-152">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="29e31-153">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="29e31-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="29e31-154">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29e31-155">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="29e31-155">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="29e31-156">HTTP プロキシのアドレスを格納する URI。</span><span class="sxs-lookup"><span data-stu-id="29e31-156">A URI that contains the address of the HTTP proxy.</span></span> <span data-ttu-id="29e31-157">`useSystemWebProxy` が `true` に設定されている場合、この設定は `null` である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-157">If `useSystemWebProxy` is set to `true`, this setting must be `null`.</span></span> <span data-ttu-id="29e31-158">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="29e31-158">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="29e31-159">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="29e31-159">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="29e31-160">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-160">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29e31-161">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="29e31-161">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="29e31-162">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="29e31-162">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="29e31-163">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-163">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="29e31-164">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="29e31-164">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="29e31-165">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="29e31-165">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="29e31-166">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29e31-166">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="29e31-167">-BigEndianUnicode: Unicode BigEndian エンコード。</span><span class="sxs-lookup"><span data-stu-id="29e31-167">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="29e31-168">-Unicode:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="29e31-168">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="29e31-169">-UTF8: 8 ビットエンコーディング</span><span class="sxs-lookup"><span data-stu-id="29e31-169">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="29e31-170">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="29e31-170">The default is UTF8.</span></span> <span data-ttu-id="29e31-171">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="29e31-171">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transferMode`|<span data-ttu-id="29e31-172">要求または応答に対してメッセージがバッファーされるか、ストリーム配信されるかを指定する有効な <xref:System.ServiceModel.TransferMode> 値。</span><span class="sxs-lookup"><span data-stu-id="29e31-172">A valid <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed on a request or response.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="29e31-173">使用できる場合にシステムの自動設定 HTTP プロキシを使用するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="29e31-173">A Boolean value that specifies whether the auto-configured HTTP proxy of the system should be used, if available.</span></span> <span data-ttu-id="29e31-174">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="29e31-174">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29e31-175">子要素</span><span class="sxs-lookup"><span data-stu-id="29e31-175">Child Elements</span></span>  
  
|<span data-ttu-id="29e31-176">要素</span><span class="sxs-lookup"><span data-stu-id="29e31-176">Element</span></span>|<span data-ttu-id="29e31-177">説明</span><span class="sxs-lookup"><span data-stu-id="29e31-177">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29e31-178">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="29e31-178">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="29e31-179">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="29e31-179">Defines the security settings for the binding.</span></span> <span data-ttu-id="29e31-180">この要素は <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="29e31-180">This element is of type <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="29e31-181">[readerQuotas > の \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="29e31-181">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="29e31-182">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="29e31-182">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="29e31-183">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="29e31-183">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29e31-184">親要素</span><span class="sxs-lookup"><span data-stu-id="29e31-184">Parent Elements</span></span>  
  
|<span data-ttu-id="29e31-185">要素</span><span class="sxs-lookup"><span data-stu-id="29e31-185">Element</span></span>|<span data-ttu-id="29e31-186">説明</span><span class="sxs-lookup"><span data-stu-id="29e31-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29e31-187">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="29e31-187">\<bindings></span></span>](bindings.md)|<span data-ttu-id="29e31-188">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="29e31-188">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29e31-189">コメント</span><span class="sxs-lookup"><span data-stu-id="29e31-189">Remarks</span></span>  
 <span data-ttu-id="29e31-190">BasicHttpBinding では、SOAP 1.1 メッセージを送信するために、HTTP をトランスポートとして使用します。</span><span class="sxs-lookup"><span data-stu-id="29e31-190">The BasicHttpBinding uses HTTP as the transport for sending SOAP 1.1 messages.</span></span> <span data-ttu-id="29e31-191">サービスは、ASMX クライアントが消費するエンドポイントなど、WS-I BP 1.1 に準拠するエンドポイントを開示するためにこのバインディングを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29e31-191">A service can use this binding to expose endpoints that conform to WS-I BP 1.1, such as those that ASMX clients consume.</span></span> <span data-ttu-id="29e31-192">同様に、クライアントは BasicHttpBinding を使用して、ASMX Web サービスや BasicHttpBinding で構成されるサービスなどの WS-I BP 1.1 に準じるエンドポイントを公開するサービスと通信できます。</span><span class="sxs-lookup"><span data-stu-id="29e31-192">Similarly, a client can use the BasicHttpBinding to communicate with services exposing endpoints that conform to WS-I BP 1.1, such as ASMX Web services or services configured with the BasicHttpBinding.</span></span>  
  
 <span data-ttu-id="29e31-193">既定ではセキュリティはオフになっていますが、 [\<セキュリティ >](security-of-basichttpbinding.md)の子要素の mode 属性を `None`以外の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="29e31-193">Security is turned off by default, but can be added setting the mode attribute of the [\<security>](security-of-basichttpbinding.md) child element to a value other than `None`.</span></span> <span data-ttu-id="29e31-194">サービスは、"Text" メッセージ エンコードおよび UTF-8 テキスト エンコードを既定で使用します。</span><span class="sxs-lookup"><span data-stu-id="29e31-194">It uses a "Text" message encoding and UTF-8 text encoding by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29e31-195">例</span><span class="sxs-lookup"><span data-stu-id="29e31-195">Example</span></span>  
 <span data-ttu-id="29e31-196">第 1 世代と第 2 世代の Web サービスで HTTP 通信と最大限の相互運用性を実現する、<xref:System.ServiceModel.BasicHttpBinding> の使用例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="29e31-196">The following example demonstrates the use of <xref:System.ServiceModel.BasicHttpBinding> that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span> <span data-ttu-id="29e31-197">バインディングは、クライアントとサービスの構成ファイルに指定されます。</span><span class="sxs-lookup"><span data-stu-id="29e31-197">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="29e31-198">バインディングの種類は、`binding` 要素の `<endpoint>` 属性を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="29e31-198">The binding type is specified using the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="29e31-199">基本的なバインディングを構成してその設定の一部を変更する場合は、バインド構成を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29e31-199">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="29e31-200">エンドポイントは、`bindingConfiguration` 要素の `<endpoint>` 属性を使用して、名前でバインディング構成を参照する必要があります。次のサービスの構成コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e31-200">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the `<endpoint>` element, as shown in the following configuration code for the service.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
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
               messageEncoding="Text"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="example"></a><span data-ttu-id="29e31-201">例</span><span class="sxs-lookup"><span data-stu-id="29e31-201">Example</span></span>  
 <span data-ttu-id="29e31-202">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="29e31-202">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="29e31-203">前の例の機能は、エンドポイントアドレスから bindingConfiguration を削除し、バインドから名前を削除することで実現できます。</span><span class="sxs-lookup"><span data-stu-id="29e31-203">The functionality from the previous example can be accomplished by removing the bindingConfiguration from the endpoint address and the name from the binding.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <binding hostNameComparisonMode="StrongWildcard"
               receiveTimeout="00:10:00"
               sendTimeout="00:10:00"
               openTimeout="00:10:00"
               closeTimeout="00:10:00"
               maxReceivedMessageSize="65536"
               maxBufferSize="65536"
               maxBufferPoolSize="524288"
               transferMode="Buffered"
               messageEncoding="Text"
               textEncoding="utf-8"
               bypassProxyOnLocal="false"
               useDefaultWebProxy="true">
        <security mode="None" />
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
 <span data-ttu-id="29e31-204">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29e31-204">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29e31-205">参照</span><span class="sxs-lookup"><span data-stu-id="29e31-205">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="29e31-206">バインディング</span><span class="sxs-lookup"><span data-stu-id="29e31-206">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="29e31-207">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="29e31-207">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="29e31-208">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="29e31-208">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="29e31-209">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="29e31-209">\<binding></span></span>](bindings.md)
