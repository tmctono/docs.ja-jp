---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 114543e43306e4195f92ca625e894a532084be6b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177775"
---
# \<wsDualHttpBinding>

<span data-ttu-id="6e9e3-101">双方向サービス コントラクト、または SOAP 中継局を介しての通信に適した、セキュリティで保護されて信頼できる相互操作可能なバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-101">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsDualHttpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="6e9e3-102">構文</span><span class="sxs-lookup"><span data-stu-id="6e9e3-102">Syntax</span></span>  
  
```xml  
<wsDualHttpBinding>
  <binding name="String"
          closeTimeout="TimeSpan"
          openTimeout="TimeSpan"
          receiveTimeout="TimeSpan"
          sendTimeout="TimeSpan"
          bypassProxyOnLocal="Boolean"
          clientBaseAddress="URI"
          transactionFlow="Boolean"
          hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
          maxBufferPoolSize="integer"
          maxReceivedMessageSize="Integer"
          messageEncoding="Text/Mtom"
          proxyAddress="URI"
          textEncoding="Unicode/BigEndianUnicode/UTF8"
          useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan" />
    <security mode="None/Message">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsDualHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e9e3-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="6e9e3-103">Attributes and Elements</span></span>  

 <span data-ttu-id="6e9e3-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e9e3-105">属性</span><span class="sxs-lookup"><span data-stu-id="6e9e3-105">Attributes</span></span>  
  
|<span data-ttu-id="6e9e3-106">属性</span><span class="sxs-lookup"><span data-stu-id="6e9e3-106">Attribute</span></span>|<span data-ttu-id="6e9e3-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="6e9e3-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e9e3-108">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="6e9e3-108">bypassProxyOnLocal</span></span>|<span data-ttu-id="6e9e3-109">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-109">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="6e9e3-110">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-110">The default is `false`.</span></span>|  
|<span data-ttu-id="6e9e3-111">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="6e9e3-111">clientBaseAddress</span></span>|<span data-ttu-id="6e9e3-112">サービスからの応答メッセージをクライアントがリッスンするベース アドレスを設定する URI。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-112">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="6e9e3-113">指定されている場合は、このアドレス (およびチャネルごとの GUID) がリッスンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-113">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="6e9e3-114">値が指定されていない場合は、クライアント ベース アドレスは、トランスポートに固有の方法で生成されます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-114">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="6e9e3-115">既定では、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-115">The default is `null`.</span></span>|  
|<span data-ttu-id="6e9e3-116">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="6e9e3-116">closeTimeout</span></span>|<span data-ttu-id="6e9e3-117">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-117">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="6e9e3-118">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-118">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6e9e3-119">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-119">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="6e9e3-120">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="6e9e3-120">hostnameComparisonMode</span></span>|<span data-ttu-id="6e9e3-121">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-121">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="6e9e3-122">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-122">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="6e9e3-123">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-123">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="6e9e3-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="6e9e3-124">maxBufferPoolSize</span></span>|<span data-ttu-id="6e9e3-125">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-125">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="6e9e3-126">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-126">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="6e9e3-127">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-127">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="6e9e3-128">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-128">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="6e9e3-129">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-129">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="6e9e3-130">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-130">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="6e9e3-131">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="6e9e3-131">maxReceivedMessageSize</span></span>|<span data-ttu-id="6e9e3-132">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-132">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="6e9e3-133">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-133">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="6e9e3-134">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-134">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="6e9e3-135">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-135">The default is 65536.</span></span>|  
|<span data-ttu-id="6e9e3-136">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="6e9e3-136">messageEncoding</span></span>|<span data-ttu-id="6e9e3-137">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-137">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="6e9e3-138">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e9e3-139">-Text: テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-139">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="6e9e3-140">-Mtom: メッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-140">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="6e9e3-141">-既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-141">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="6e9e3-142">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-142">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="6e9e3-143">name</span><span class="sxs-lookup"><span data-stu-id="6e9e3-143">name</span></span>|<span data-ttu-id="6e9e3-144">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-144">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="6e9e3-145">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-145">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="6e9e3-146">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-146">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="6e9e3-147">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-147">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="6e9e3-148">openTimeout</span><span class="sxs-lookup"><span data-stu-id="6e9e3-148">openTimeout</span></span>|<span data-ttu-id="6e9e3-149">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="6e9e3-150">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6e9e3-151">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-151">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="6e9e3-152">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="6e9e3-152">proxyAddress</span></span>|<span data-ttu-id="6e9e3-153">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-153">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="6e9e3-154">`useDefaultWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-154">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="6e9e3-155">既定では、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-155">The default is `null`.</span></span>|  
|<span data-ttu-id="6e9e3-156">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="6e9e3-156">receiveTimeout</span></span>|<span data-ttu-id="6e9e3-157">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-157">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="6e9e3-158">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-158">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6e9e3-159">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-159">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="6e9e3-160">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="6e9e3-160">sendTimeout</span></span>|<span data-ttu-id="6e9e3-161">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-161">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="6e9e3-162">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-162">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="6e9e3-163">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-163">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="6e9e3-164">textEncoding</span><span class="sxs-lookup"><span data-stu-id="6e9e3-164">textEncoding</span></span>|<span data-ttu-id="6e9e3-165">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-165">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="6e9e3-166">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-166">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6e9e3-167">-BigEndianUnicode: Unicode BigEndian エンコード。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-167">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="6e9e3-168">-Unicode:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-168">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="6e9e3-169">-UTF8: 8 ビットエンコーディング</span><span class="sxs-lookup"><span data-stu-id="6e9e3-169">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="6e9e3-170">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-170">The default is UTF8.</span></span> <span data-ttu-id="6e9e3-171">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-171">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="6e9e3-172">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="6e9e3-172">transactionFlow</span></span>|<span data-ttu-id="6e9e3-173">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-173">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="6e9e3-174">既定では、 `false`です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-174">The default is `false`.</span></span>|  
|<span data-ttu-id="6e9e3-175">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="6e9e3-175">useDefaultWebProxy</span></span>|<span data-ttu-id="6e9e3-176">システムの自動設定 HTTP プロキシを使用するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-176">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="6e9e3-177">この属性が `null` の場合、プロキシ アドレスを `true` (つまり、設定しない) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-177">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="6e9e3-178">既定では、 `true`です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-178">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e9e3-179">子要素</span><span class="sxs-lookup"><span data-stu-id="6e9e3-179">Child Elements</span></span>  
  
|<span data-ttu-id="6e9e3-180">要素</span><span class="sxs-lookup"><span data-stu-id="6e9e3-180">Element</span></span>|<span data-ttu-id="6e9e3-181">説明</span><span class="sxs-lookup"><span data-stu-id="6e9e3-181">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-wsdualhttpbinding.md)|<span data-ttu-id="6e9e3-182">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-182">Defines the security settings for the binding.</span></span> <span data-ttu-id="6e9e3-183">この要素は <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-183">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="6e9e3-184">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-184">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="6e9e3-185">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-185">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="6e9e3-186">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-186">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6e9e3-187">親要素</span><span class="sxs-lookup"><span data-stu-id="6e9e3-187">Parent Elements</span></span>  
  
|<span data-ttu-id="6e9e3-188">要素</span><span class="sxs-lookup"><span data-stu-id="6e9e3-188">Element</span></span>|<span data-ttu-id="6e9e3-189">説明</span><span class="sxs-lookup"><span data-stu-id="6e9e3-189">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="6e9e3-190">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-190">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e9e3-191">解説</span><span class="sxs-lookup"><span data-stu-id="6e9e3-191">Remarks</span></span>  

 <span data-ttu-id="6e9e3-192">`WSDualHttpBinding` は、`WSHttpBinding` と同じ Web サービス プロトコルをサポートしますが、双方向コントラクトでの使用を想定しています。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-192">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="6e9e3-193">`WSDualHttpBinding` は SOAP セキュリティのみをサポートし、信頼できるメッセージングを要求します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-193">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="6e9e3-194">このバインディングでは、クライアントが、サービスのコールバック エンドポイントを提供するパブリック URI を保持していることが必要です。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-194">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="6e9e3-195">これは `clientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-195">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="6e9e3-196">二重バインディングでは、クライアントの IP アドレスをサービスに公開します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-196">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="6e9e3-197">クライアントは、セキュリティを使用して信頼するサービスに対して接続のみを可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-197">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="6e9e3-198">このバインディングは、1 つ以上の SOAP 中継局を通じて信頼できる方法で通信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-198">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="6e9e3-199">既定では、このバインディングは、信頼のための WS-ReliableMessaging、メッセージ セキュリティと認証用 WS-Security、メッセージ配信用 HTTP、および Text/XML メッセージ エンコーディングを持つランタイム スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-199">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e9e3-200">例</span><span class="sxs-lookup"><span data-stu-id="6e9e3-200">Example</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsDualHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 clientBaseAddress="http://localhost:8001/client/"
                 transactionFlow="true"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00" />
          <security mode="None">
            <message clientCredentialType="None"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128" />
          </security>
        </binding>
      </wsDualHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="6e9e3-201">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e9e3-201">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [<span data-ttu-id="6e9e3-202">バインド</span><span class="sxs-lookup"><span data-stu-id="6e9e3-202">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6e9e3-203">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="6e9e3-203">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6e9e3-204">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="6e9e3-204">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
