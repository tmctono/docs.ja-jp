---
title: <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 8586ecc9-bdaa-44d6-8d4d-7038e4ea1741
ms.openlocfilehash: 379552f461a79415e3140a8084901e0c1d6b2c32
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140480"
---
# \<ws2007HttpBinding>
<span data-ttu-id="ac394-101"><xref:System.ServiceModel.WSHttpBinding.Security%2A>、<xref:System.ServiceModel.ReliableSession>、および <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> の各バインド要素の適切なバージョンをサポートする相互運用可能なバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac394-101">Defines an interoperable binding that provides support for the correct versions of the <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession>, and <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A> binding elements.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<ws2007HttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="ac394-102">構文</span><span class="sxs-lookup"><span data-stu-id="ac394-102">Syntax</span></span>  
  
```xml  
<ws2007HttpBinding>
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
        <message clientCredentialType ="Certificate/IssuedToken/None/UserName/Windows"
                 negotiateServiceCredential="Boolean"
                 algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
                 establishSecurityContext="Boolean"
                 negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac394-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="ac394-103">Attributes and Elements</span></span>  
 <span data-ttu-id="ac394-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac394-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac394-105">属性</span><span class="sxs-lookup"><span data-stu-id="ac394-105">Attributes</span></span>  
  
|<span data-ttu-id="ac394-106">属性</span><span class="sxs-lookup"><span data-stu-id="ac394-106">Attribute</span></span>|<span data-ttu-id="ac394-107">説明</span><span class="sxs-lookup"><span data-stu-id="ac394-107">Description</span></span>|  
|---------------|-----------------|  
|`allowCookies`|<span data-ttu-id="ac394-108">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定する値です。</span><span class="sxs-lookup"><span data-stu-id="ac394-108">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="ac394-109">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-109">The default is `false`.</span></span><br /><br /> <span data-ttu-id="ac394-110">クッキーを使用する ASMX (ASP.NET Web サービス) と対話する場合に、このプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac394-110">You can use this property when you interact with ASP.NET Web services (ASMX) that use cookies.</span></span> <span data-ttu-id="ac394-111">これにより、サーバーから返されるクッキーが、このサービスに対するそれ以降のすべてのクライアント要求に自動的にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="ac394-111">This ensures that cookies that the server returns are automatically copied to all future client requests for that service.</span></span>|  
|`bypassProxyOnLocal`|<span data-ttu-id="ac394-112">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示す値。</span><span class="sxs-lookup"><span data-stu-id="ac394-112">A value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="ac394-113">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-113">The default is `false`.</span></span>|  
|`closeTimeout`|<span data-ttu-id="ac394-114">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="ac394-114">A <xref:System.TimeSpan> value that specifies the time interval for a close operation to complete.</span></span> <span data-ttu-id="ac394-115">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac394-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ac394-116">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="ac394-116">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="ac394-117">URI (Uniform Resource Identifier) の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac394-117">Specifies the HTTP hostname comparison mode used to parse Uniform Resource Identifiers (URIs).</span></span> <span data-ttu-id="ac394-118">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac394-118">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="ac394-119">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="ac394-119">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="ac394-120">このバインドに使用するバッファー プールの最大サイズ。</span><span class="sxs-lookup"><span data-stu-id="ac394-120">The maximum buffer pool size for this binding.</span></span> <span data-ttu-id="ac394-121">既定値は 524,288 バイト (512 × 1,024) です。</span><span class="sxs-lookup"><span data-stu-id="ac394-121">The default is 524,288 bytes (512 × 1,024).</span></span> <span data-ttu-id="ac394-122">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac394-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="ac394-123">使用するたびに毎回バッファーを作成および破棄すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="ac394-123">Creating and destroying buffers each time they are used is expensive, as is garbage collection for buffers.</span></span> <span data-ttu-id="ac394-124">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac394-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool when you are done.</span></span> <span data-ttu-id="ac394-125">これで、バッファーの作成と破棄によるオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="ac394-125">This avoids the overhead in creating and destroying buffers.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="ac394-126">このバインディングで構成されたチャネルで受信可能な、ヘッダーを含む最大メッセージ サイズ (バイト単位) です。</span><span class="sxs-lookup"><span data-stu-id="ac394-126">The maximum message size, in bytes, including headers, which a channel configured with this binding, can receive.</span></span> <span data-ttu-id="ac394-127">この制限を超える場合、メッセージの送信者は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="ac394-127">The sender of a message exceeding this limit receives a SOAP fault.</span></span> <span data-ttu-id="ac394-128">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ac394-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="ac394-129">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="ac394-129">The default is 65536.</span></span>|  
|`messageEncoding`|<span data-ttu-id="ac394-130">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="ac394-130">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="ac394-131">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac394-131">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ac394-132">-   `Text`: テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac394-132">-   `Text`: Use a text message encoder.</span></span><br /><span data-ttu-id="ac394-133">-   `Mtom`: メッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac394-133">-   `Mtom`: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><br /> <span data-ttu-id="ac394-134">既定値は、`Text` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-134">The default is `Text`.</span></span><br /><br /> <span data-ttu-id="ac394-135">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="ac394-135">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|`name`|<span data-ttu-id="ac394-136">バインドの構成名。</span><span class="sxs-lookup"><span data-stu-id="ac394-136">The configuration name of the binding.</span></span> <span data-ttu-id="ac394-137">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac394-137">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="ac394-138">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac394-138">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="ac394-139">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac394-139">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="ac394-140">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="ac394-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="ac394-141">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac394-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ac394-142">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="ac394-142">The default is 00:01:00.</span></span>|  
|`proxyAddress`|<span data-ttu-id="ac394-143">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="ac394-143">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="ac394-144">`useSystemWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac394-144">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="ac394-145">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-145">The default is `null`.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="ac394-146">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="ac394-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="ac394-147">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac394-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ac394-148">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="ac394-148">The default is 00:01:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="ac394-149">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="ac394-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="ac394-150">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac394-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="ac394-151">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="ac394-151">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="ac394-152">バインディングでメッセージの発行に使用する文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac394-152">Specifies the character set encoding to use for emitting messages on the binding.</span></span> <span data-ttu-id="ac394-153">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ac394-153">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="ac394-154">-   `UnicodeFffeTextEncoding`: Unicode ビッグエンディアンエンコーディング。</span><span class="sxs-lookup"><span data-stu-id="ac394-154">-   `UnicodeFffeTextEncoding`: Unicode Big Endian encoding.</span></span><br /><span data-ttu-id="ac394-155">-   `Utf16TextEncoding`:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="ac394-155">-   `Utf16TextEncoding`: 16-bit encoding.</span></span><br /><span data-ttu-id="ac394-156">-   `Utf8TextEncoding`: 8 ビットエンコーディング。</span><span class="sxs-lookup"><span data-stu-id="ac394-156">-   `Utf8TextEncoding`: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="ac394-157">既定値は、`Utf8TextEncoding` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-157">The default is `Utf8TextEncoding`.</span></span><br /><br /> <span data-ttu-id="ac394-158">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="ac394-158">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`transactionFlow`|<span data-ttu-id="ac394-159">バインドが WS-Transactions のフローをサポートするかどうかを指定する値。</span><span class="sxs-lookup"><span data-stu-id="ac394-159">A value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="ac394-160">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-160">The default is `false`.</span></span>|  
|`useDefaultWebProxy`|<span data-ttu-id="ac394-161">システムの自動設定 HTTP プロキシを使用するかどうかを示す値です。</span><span class="sxs-lookup"><span data-stu-id="ac394-161">A value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="ac394-162">既定値は、`true` です。</span><span class="sxs-lookup"><span data-stu-id="ac394-162">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac394-163">子要素</span><span class="sxs-lookup"><span data-stu-id="ac394-163">Child Elements</span></span>  
  
|<span data-ttu-id="ac394-164">要素</span><span class="sxs-lookup"><span data-stu-id="ac394-164">Element</span></span>|<span data-ttu-id="ac394-165">Description</span><span class="sxs-lookup"><span data-stu-id="ac394-165">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="ac394-166">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac394-166">Defines the security settings for the binding.</span></span> <span data-ttu-id="ac394-167">この要素は <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ac394-167">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="ac394-168">このバインディングを使用して設定されるエンドポイントで処理できる、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="ac394-168">Defines the constraints on the complexity of SOAP messages that endpoints configured with this binding can process.</span></span> <span data-ttu-id="ac394-169">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="ac394-169">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="ac394-170">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac394-170">Specifies whether reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ac394-171">親要素</span><span class="sxs-lookup"><span data-stu-id="ac394-171">Parent Elements</span></span>  
  
|<span data-ttu-id="ac394-172">要素</span><span class="sxs-lookup"><span data-stu-id="ac394-172">Element</span></span>|<span data-ttu-id="ac394-173">Description</span><span class="sxs-lookup"><span data-stu-id="ac394-173">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="ac394-174">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="ac394-174">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac394-175">解説</span><span class="sxs-lookup"><span data-stu-id="ac394-175">Remarks</span></span>  
 <span data-ttu-id="ac394-176">`WS2007HttpBinding` は、`WSHttpBinding` と同様のシステム標準のバインディングを追加しますが、ReliableSession、Security、および TransactionFlow の各プロトコルの OASIS (Organization for the Advancement of Structured Information Standards) 標準バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac394-176">The `WS2007HttpBinding` adds a system-provided binding similar to `WSHttpBinding` but uses the Organization for the Advancement of Structured Information Standards (OASIS) standard versions of the ReliableSession, Security, and TransactionFlow protocols.</span></span> <span data-ttu-id="ac394-177">このバインドを使用する場合、オブジェクト モデルも既定の設定も変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac394-177">No changes to the object model or default settings are required when using this binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac394-178">例</span><span class="sxs-lookup"><span data-stu-id="ac394-178">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <ws2007HttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://www.contoso.com"
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
      </ws2007HttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="ac394-179">関連項目</span><span class="sxs-lookup"><span data-stu-id="ac394-179">See also</span></span>

- <xref:System.ServiceModel.WS2007HttpBinding>
- <xref:System.ServiceModel.Configuration.WS2007HttpBindingElement>
- [<span data-ttu-id="ac394-180">バインド</span><span class="sxs-lookup"><span data-stu-id="ac394-180">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ac394-181">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="ac394-181">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ac394-182">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="ac394-182">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
