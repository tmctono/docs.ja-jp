---
title: <wsDualHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: ca841499f5a1584d5fd5c1bb763da4f3460c4f13
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399042"
---
# <a name="wsdualhttpbinding"></a><span data-ttu-id="4f02d-101">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4f02d-101">\<wsDualHttpBinding></span></span>
<span data-ttu-id="4f02d-102">双方向サービス コントラクト、または SOAP 中継局を介しての通信に適した、セキュリティで保護されて信頼できる相互操作可能なバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-102">Defines a secure, reliable and interoperable binding that is suitable for duplex service contracts or communication through SOAP intermediaries.</span></span>  
  
<span data-ttu-id="4f02d-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f02d-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f02d-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4f02d-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4f02d-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4f02d-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4f02d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<wsDualHttpBinding >**</span><span class="sxs-lookup"><span data-stu-id="4f02d-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsDualHttpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f02d-107">構文</span><span class="sxs-lookup"><span data-stu-id="4f02d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f02d-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="4f02d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4f02d-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f02d-110">属性</span><span class="sxs-lookup"><span data-stu-id="4f02d-110">Attributes</span></span>  
  
|<span data-ttu-id="4f02d-111">属性</span><span class="sxs-lookup"><span data-stu-id="4f02d-111">Attribute</span></span>|<span data-ttu-id="4f02d-112">説明</span><span class="sxs-lookup"><span data-stu-id="4f02d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f02d-113">bypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="4f02d-113">bypassProxyOnLocal</span></span>|<span data-ttu-id="4f02d-114">ローカル アドレスでプロキシ サーバーをバイパスするかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="4f02d-114">A Boolean value that indicates whether to bypass the proxy server for local addresses.</span></span> <span data-ttu-id="4f02d-115">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-115">The default is `false`.</span></span>|  
|<span data-ttu-id="4f02d-116">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="4f02d-116">clientBaseAddress</span></span>|<span data-ttu-id="4f02d-117">サービスからの応答メッセージをクライアントがリッスンするベース アドレスを設定する URI。</span><span class="sxs-lookup"><span data-stu-id="4f02d-117">A URI that sets the base address that the client listens to for response messages from the service.</span></span> <span data-ttu-id="4f02d-118">指定されている場合は、このアドレス (およびチャネルごとの GUID) がリッスンに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-118">If specified, this address (plus a per-channelGUID) is used for listening.</span></span> <span data-ttu-id="4f02d-119">値が指定されていない場合は、クライアント ベース アドレスは、トランスポートに固有の方法で生成されます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-119">If the value is not specified, the client base address is generated in a transport-specific manner.</span></span> <span data-ttu-id="4f02d-120">既定値は `null` です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-120">The default is `null`.</span></span>|  
|<span data-ttu-id="4f02d-121">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="4f02d-121">closeTimeout</span></span>|<span data-ttu-id="4f02d-122">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="4f02d-122">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="4f02d-123">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-123">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4f02d-124">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-124">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4f02d-125">hostnameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="4f02d-125">hostnameComparisonMode</span></span>|<span data-ttu-id="4f02d-126">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-126">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="4f02d-127">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-127">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="4f02d-128">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-128">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|<span data-ttu-id="4f02d-129">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="4f02d-129">maxBufferPoolSize</span></span>|<span data-ttu-id="4f02d-130">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="4f02d-130">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="4f02d-131">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-131">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="4f02d-132">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-132">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="4f02d-133">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-133">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="4f02d-134">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-134">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="4f02d-135">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-135">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="4f02d-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="4f02d-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="4f02d-137">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="4f02d-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="4f02d-138">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="4f02d-139">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="4f02d-140">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-140">The default is 65536.</span></span>|  
|<span data-ttu-id="4f02d-141">messageEncoding</span><span class="sxs-lookup"><span data-stu-id="4f02d-141">messageEncoding</span></span>|<span data-ttu-id="4f02d-142">メッセージのエンコードに使用されるエンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-142">Defines the encoder used to encode the message.</span></span> <span data-ttu-id="4f02d-143">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4f02d-144">本文テキストメッセージエンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-144">-   Text: Use a text message encoder.</span></span><br /><span data-ttu-id="4f02d-145">Mtomメッセージ伝送組織機構 1.0 (MTOM) エンコーダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-145">-   Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder.</span></span><br /><span data-ttu-id="4f02d-146">-既定値は Text です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-146">-   The default is Text.</span></span><br /><br /> <span data-ttu-id="4f02d-147">この属性は <xref:System.ServiceModel.WSMessageEncoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-147">This attribute is of type <xref:System.ServiceModel.WSMessageEncoding>.</span></span>|  
|<span data-ttu-id="4f02d-148">name</span><span class="sxs-lookup"><span data-stu-id="4f02d-148">name</span></span>|<span data-ttu-id="4f02d-149">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-149">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="4f02d-150">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-150">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="4f02d-151">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4f02d-151">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="4f02d-152">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f02d-152">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="4f02d-153">openTimeout</span><span class="sxs-lookup"><span data-stu-id="4f02d-153">openTimeout</span></span>|<span data-ttu-id="4f02d-154">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="4f02d-155">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4f02d-156">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-156">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4f02d-157">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="4f02d-157">proxyAddress</span></span>|<span data-ttu-id="4f02d-158">HTTP プロキシのアドレスを指定する URI。</span><span class="sxs-lookup"><span data-stu-id="4f02d-158">A URI that specifies the address of the HTTP proxy.</span></span> <span data-ttu-id="4f02d-159">`useDefaultWebProxy` が `true` の場合、この設定を `null` にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-159">If `useDefaultWebProxy` is `true`, this setting must be `null`.</span></span> <span data-ttu-id="4f02d-160">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-160">The default is `null`.</span></span>|  
|<span data-ttu-id="4f02d-161">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="4f02d-161">receiveTimeout</span></span>|<span data-ttu-id="4f02d-162">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-162">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="4f02d-163">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-163">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4f02d-164">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-164">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4f02d-165">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="4f02d-165">sendTimeout</span></span>|<span data-ttu-id="4f02d-166">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-166">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="4f02d-167">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-167">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="4f02d-168">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-168">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="4f02d-169">textEncoding</span><span class="sxs-lookup"><span data-stu-id="4f02d-169">textEncoding</span></span>|<span data-ttu-id="4f02d-170">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-170">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4f02d-171">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-171">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="4f02d-172">BigEndianUnicodeUnicode BigEndian エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="4f02d-172">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="4f02d-173">対応16ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="4f02d-173">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="4f02d-174">UTF88ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="4f02d-174">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4f02d-175">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-175">The default is UTF8.</span></span> <span data-ttu-id="4f02d-176">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-176">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|<span data-ttu-id="4f02d-177">transactionFlow</span><span class="sxs-lookup"><span data-stu-id="4f02d-177">transactionFlow</span></span>|<span data-ttu-id="4f02d-178">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-178">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="4f02d-179">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-179">The default is `false`.</span></span>|  
|<span data-ttu-id="4f02d-180">useDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="4f02d-180">useDefaultWebProxy</span></span>|<span data-ttu-id="4f02d-181">システムの自動設定 HTTP プロキシを使用するかどうかを示すブール値。</span><span class="sxs-lookup"><span data-stu-id="4f02d-181">A Boolean value that indicates whether the system’s auto-configured HTTP proxy is used.</span></span> <span data-ttu-id="4f02d-182">この属性が `null` の場合、プロキシ アドレスを `true` (つまり、設定しない) にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-182">The proxy address must be `null` (that is, not set) if this attribute is `true`.</span></span> <span data-ttu-id="4f02d-183">既定値は `true` です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-183">The default is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f02d-184">子要素</span><span class="sxs-lookup"><span data-stu-id="4f02d-184">Child Elements</span></span>  
  
|<span data-ttu-id="4f02d-185">要素</span><span class="sxs-lookup"><span data-stu-id="4f02d-185">Element</span></span>|<span data-ttu-id="4f02d-186">説明</span><span class="sxs-lookup"><span data-stu-id="4f02d-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f02d-187">\<security></span><span class="sxs-lookup"><span data-stu-id="4f02d-187">\<security></span></span>](security-of-wsdualhttpbinding.md)|<span data-ttu-id="4f02d-188">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-188">Defines the security settings for the binding.</span></span> <span data-ttu-id="4f02d-189">この要素は <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-189">This element is of type <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.</span></span>|  
|<span data-ttu-id="4f02d-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4f02d-190">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="4f02d-191">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-191">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4f02d-192">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-192">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="4f02d-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="4f02d-193">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="4f02d-194">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-194">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f02d-195">親要素</span><span class="sxs-lookup"><span data-stu-id="4f02d-195">Parent Elements</span></span>  
  
|<span data-ttu-id="4f02d-196">要素</span><span class="sxs-lookup"><span data-stu-id="4f02d-196">Element</span></span>|<span data-ttu-id="4f02d-197">説明</span><span class="sxs-lookup"><span data-stu-id="4f02d-197">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f02d-198">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4f02d-198">\<bindings></span></span>](bindings.md)|<span data-ttu-id="4f02d-199">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-199">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f02d-200">Remarks</span><span class="sxs-lookup"><span data-stu-id="4f02d-200">Remarks</span></span>  
 <span data-ttu-id="4f02d-201">`WSDualHttpBinding` は、`WSHttpBinding` と同じ Web サービス プロトコルをサポートしますが、双方向コントラクトでの使用を想定しています。</span><span class="sxs-lookup"><span data-stu-id="4f02d-201">The `WSDualHttpBinding` provides the same support for Web Service protocols as the `WSHttpBinding`, but for use with duplex contracts.</span></span> <span data-ttu-id="4f02d-202">`WSDualHttpBinding` は SOAP セキュリティのみをサポートし、信頼できるメッセージングを要求します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-202">`WSDualHttpBinding` only supports SOAP security and requires reliable messaging.</span></span> <span data-ttu-id="4f02d-203">このバインディングでは、クライアントが、サービスのコールバック エンドポイントを提供するパブリック URI を保持していることが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f02d-203">This binding requires that the client has a public URI that provides a callback endpoint for the service.</span></span> <span data-ttu-id="4f02d-204">これは `clientBaseAddress` 属性によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-204">This is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="4f02d-205">二重バインディングでは、クライアントの IP アドレスをサービスに公開します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-205">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="4f02d-206">クライアントは、セキュリティを使用して信頼するサービスに対して接続のみを可能にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f02d-206">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
 <span data-ttu-id="4f02d-207">このバインディングは、1 つ以上の SOAP 中継局を通じて信頼できる方法で通信するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f02d-207">This binding can be used to communicate reliably through one or more SOAP intermediaries.</span></span>  
  
 <span data-ttu-id="4f02d-208">既定では、このバインディングは、信頼のための WS-ReliableMessaging、メッセージ セキュリティと認証用 WS-Security、メッセージ配信用 HTTP、および Text/XML メッセージ エンコーディングを持つランタイム スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="4f02d-208">By default, this binding generates a runtime stack with WS-ReliableMessaging for reliability, WS-Security for message security and authentication, HTTP for message delivery, and a Text/XML message encoding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f02d-209">例</span><span class="sxs-lookup"><span data-stu-id="4f02d-209">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f02d-210">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f02d-210">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>
- <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>
- [<span data-ttu-id="4f02d-211">バインディング</span><span class="sxs-lookup"><span data-stu-id="4f02d-211">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4f02d-212">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="4f02d-212">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4f02d-213">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="4f02d-213">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4f02d-214">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f02d-214">\<binding></span></span>](../../../misc/binding.md)
