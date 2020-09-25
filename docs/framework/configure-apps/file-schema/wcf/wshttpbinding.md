---
title: <wsHttpBinding>
description: WS-TRUST メッセージングと WS-SECURITY を実装する、双方向ではないサービスコントラクトに適した、セキュリティで保護された、信頼性の高い、相互運用可能な HTTP バインディングを定義します。
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: 33d7c40faa0bf8b78ebc6f79c7db341bb44887ec
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202436"
---
# \<wsHttpBinding>

<span data-ttu-id="f1d7e-102">双方向サービス コントラクト以外に適した、安全で信頼のおける相互操作可能なバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-102">Defines a secure, reliable, interoperable binding suitable for non-duplex service contracts.</span></span> <span data-ttu-id="f1d7e-103">バインディングは、信頼のための WS-ReliableMessaging、およびメッセージのセキュリティと認証のための WS-Security を実装します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-103">The binding implements the following specifications: WS-Reliable Messaging for reliability, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="f1d7e-104">トランスポートは HTTP、メッセージ エンコーディングは Text/XML エンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-104">The transport is HTTP, and message encoding is Text/XML encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="f1d7e-105">構文</span><span class="sxs-lookup"><span data-stu-id="f1d7e-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1d7e-106">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f1d7e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f1d7e-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1d7e-108">属性</span><span class="sxs-lookup"><span data-stu-id="f1d7e-108">Attributes</span></span>  
  
|<span data-ttu-id="f1d7e-109">属性</span><span class="sxs-lookup"><span data-stu-id="f1d7e-109">Attribute</span></span>|<span data-ttu-id="f1d7e-110">[説明]</span><span class="sxs-lookup"><span data-stu-id="f1d7e-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1d7e-111">allowCookies</span><span class="sxs-lookup"><span data-stu-id="f1d7e-111">allowCookies</span></span>|<span data-ttu-id="f1d7e-112">クライアントがクッキーを受け入れて、それらを今後の要求に反映させるかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-112">A Boolean value that indicates whether the client accepts cookies and propagates them on future requests.</span></span> <span data-ttu-id="f1d7e-113">既定値は false です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-113">The default is false.</span></span><br /><br /> <span data-ttu-id="f1d7e-114">クッキーを使用する ASMX Web サービスと対話する場合にこのプロパティを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-114">You can use this property when you interact with ASMX Web services that use cookies.</span></span> <span data-ttu-id="f1d7e-115">この方法で、サーバーから返されるクッキーを、それ以降のサービスに対するすべてのクライアント要求に自動的にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-115">In this way, you can be sure that the cookies returned from the server are automatically copied to all future client requests for that service.</span></span>|  
|<span data-ttu-id="f1d7e-116">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="f1d7e-116">bypassProxyOnLocal</span></span>|<span data-ttu-id="f1d7e-117">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-117">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="f1d7e-118">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-118">The default is `false`.</span></span>|  
|<span data-ttu-id="f1d7e-119">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="f1d7e-119">closeTimeout</span></span>|<span data-ttu-id="f1d7e-120">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f1d7e-121">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f1d7e-122">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-122">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f1d7e-123">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="f1d7e-123">hostnameComparisonMode</span></span>|<span data-ttu-id="f1d7e-124">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-124">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="f1d7e-125">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-125">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="f1d7e-126">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-126">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="f1d7e-127">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f1d7e-127">maxBufferPoolSize</span></span>|<span data-ttu-id="f1d7e-128">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-128">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="f1d7e-129">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-129">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="f1d7e-130">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-130">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="f1d7e-131">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-131">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="f1d7e-132">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-132">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="f1d7e-133">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-133">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="f1d7e-134">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f1d7e-134">maxReceivedMessageSize</span></span>|<span data-ttu-id="f1d7e-135">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-135">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="f1d7e-136">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-136">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="f1d7e-137">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-137">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="f1d7e-138">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-138">The default is 65536.</span></span>|  
|<span data-ttu-id="f1d7e-139">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="f1d7e-139">messageEncoding</span></span>|<span data-ttu-id="f1d7e-140">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-140">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="f1d7e-141">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-141">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f1d7e-142">-Text: テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-142">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="f1d7e-143">-Mtom: メッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-143">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="f1d7e-144">-既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-144">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="f1d7e-145">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-145">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="f1d7e-146">name</span><span class="sxs-lookup"><span data-stu-id="f1d7e-146">name</span></span>|<span data-ttu-id="f1d7e-147">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-147">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f1d7e-148">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-148">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f1d7e-149">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-149">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f1d7e-150">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-150">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="f1d7e-151">openTimeout</span><span class="sxs-lookup"><span data-stu-id="f1d7e-151">openTimeout</span></span>|<span data-ttu-id="f1d7e-152">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-152">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f1d7e-153">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-153">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f1d7e-154">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-154">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f1d7e-155">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="f1d7e-155">proxyAddress</span></span>|<span data-ttu-id="f1d7e-156">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-156">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="f1d7e-157">`useSystemWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-157">If `useSystemWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="f1d7e-158">既定では、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-158">The default is `null`.</span></span>|  
|<span data-ttu-id="f1d7e-159">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="f1d7e-159">receiveTimeout</span></span>|<span data-ttu-id="f1d7e-160">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-160">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f1d7e-161">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-161">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f1d7e-162">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-162">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f1d7e-163">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="f1d7e-163">sendTimeout</span></span>|<span data-ttu-id="f1d7e-164">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-164">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f1d7e-165">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-165">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f1d7e-166">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-166">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="f1d7e-167">textEncoding</span><span class="sxs-lookup"><span data-stu-id="f1d7e-167">textEncoding</span></span>|<span data-ttu-id="f1d7e-168">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-168">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="f1d7e-169">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-169">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f1d7e-170">-UnicodeFffeTextEncoding: Unicode BigEndian エンコード。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-170">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="f1d7e-171">-Utf16TextEncoding:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-171">-   Utf16TextEncoding: 16-bit encoding.</span></span><br /><span data-ttu-id="f1d7e-172">-Utf8TextEncoding: 8 ビットエンコーディング。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-172">-   Utf8TextEncoding: 8-bit encoding.</span></span><br /><br /> <span data-ttu-id="f1d7e-173">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-173">The default is Utf8TextEncoding.</span></span><br /><br /> <span data-ttu-id="f1d7e-174">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-174">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="f1d7e-175">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="f1d7e-175">transactionFlow</span></span>|<span data-ttu-id="f1d7e-176">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-176">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="f1d7e-177">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-177">The default is `false`.</span></span>|  
|<span data-ttu-id="f1d7e-178">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="f1d7e-178">useDefaultWebProxy</span></span>|<span data-ttu-id="f1d7e-179">システムの自動設定 HTTP プロキシを使用するかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-179">A Boolean value that specifies whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="f1d7e-180">既定では、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-180">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1d7e-181">子要素</span><span class="sxs-lookup"><span data-stu-id="f1d7e-181">Child Elements</span></span>  
  
|<span data-ttu-id="f1d7e-182">要素</span><span class="sxs-lookup"><span data-stu-id="f1d7e-182">Element</span></span>|<span data-ttu-id="f1d7e-183">説明</span><span class="sxs-lookup"><span data-stu-id="f1d7e-183">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="f1d7e-184">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-184">Defines the security settings for the binding.</span></span> <span data-ttu-id="f1d7e-185">この要素は <xref:System.ServiceModel.Configuration.WSHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-185">This element is of type <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="f1d7e-186">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-186">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f1d7e-187">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-187">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="f1d7e-188">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-188">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1d7e-189">親要素</span><span class="sxs-lookup"><span data-stu-id="f1d7e-189">Parent Elements</span></span>  
  
|<span data-ttu-id="f1d7e-190">要素</span><span class="sxs-lookup"><span data-stu-id="f1d7e-190">Element</span></span>|<span data-ttu-id="f1d7e-191">説明</span><span class="sxs-lookup"><span data-stu-id="f1d7e-191">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="f1d7e-192">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-192">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1d7e-193">解説</span><span class="sxs-lookup"><span data-stu-id="f1d7e-193">Remarks</span></span>  

 <span data-ttu-id="f1d7e-194">`WSHttpBinding` は `BasicHttpBinding` に似ていますが、より多くの Web サービス機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-194">The `WSHttpBinding` is similar to the `BasicHttpBinding` but provides more Web service features.</span></span> <span data-ttu-id="f1d7e-195">BasicHttpBinding と同じように HTTP トランスポートを使用し、メッセージ セキュリティを提供します。さらに、トランザクション、信頼できるメッセージング、および WS-Addressing も提供します。これらは、既定で有効化になっているか、または単一の制御設定で使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f1d7e-195">It uses the HTTP transport and provides message security, as does BasicHttpBinding, but it also provides transactions, reliable messaging, and WS-Addressing, either enabled by default or available through a single control setting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1d7e-196">例</span><span class="sxs-lookup"><span data-stu-id="f1d7e-196">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1d7e-197">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1d7e-197">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [<span data-ttu-id="f1d7e-198">バインド</span><span class="sxs-lookup"><span data-stu-id="f1d7e-198">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f1d7e-199">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="f1d7e-199">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f1d7e-200">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="f1d7e-200">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
