---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: d719b5c65eda8299170705cede81907a51b12e79
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780934"
---
# <a name="nettcpbinding"></a><span data-ttu-id="68272-101">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="68272-101">\<netTcpBinding></span></span>

<span data-ttu-id="68272-102">複数コンピューターの通信に適し、セキュリティで保護されて信頼できる最適化されたバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="68272-102">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="68272-103">既定では、メッセージ セキュリティと認証用 Windows セキュリティ、メッセージ配信用 TCP、およびバイナリ メッセージ エンコーディングを持つランタイム通信スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="68272-103">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

<span data-ttu-id="68272-104">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68272-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68272-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="68272-105">\<bindings></span></span>  
<span data-ttu-id="68272-106">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="68272-106">\<netTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68272-107">構文</span><span class="sxs-lookup"><span data-stu-id="68272-107">Syntax</span></span>  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68272-108">属性と要素</span><span class="sxs-lookup"><span data-stu-id="68272-108">Attributes and elements</span></span>

<span data-ttu-id="68272-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="68272-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68272-110">属性</span><span class="sxs-lookup"><span data-stu-id="68272-110">Attributes</span></span>  
  
|<span data-ttu-id="68272-111">属性</span><span class="sxs-lookup"><span data-stu-id="68272-111">Attribute</span></span>|<span data-ttu-id="68272-112">説明</span><span class="sxs-lookup"><span data-stu-id="68272-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="68272-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="68272-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="68272-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="68272-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="68272-115">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="68272-116">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="68272-116">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="68272-117">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="68272-117">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="68272-118">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="68272-118">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="68272-119">リスナーで受け入れを待機するチャネルの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="68272-119">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="68272-120">この制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="68272-120">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="68272-121">`connectionTimeout` 属性は、クライアントが接続を待つ時間を制限します。この時間が経過すると接続の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="68272-121">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="68272-122">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="68272-122">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="68272-123">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="68272-123">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="68272-124">既定は 512 \* 1024 バイトです。</span><span class="sxs-lookup"><span data-stu-id="68272-124">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="68272-125">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="68272-125">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="68272-126">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="68272-126">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="68272-127">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="68272-127">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="68272-128">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="68272-128">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="68272-129">メッセージをメモリに保存するのに使用するバッファーの最大サイズをバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="68272-129">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="68272-130">`transferMode` 属性が `Buffered` に等しい場合は、この属性が `maxReceivedMessageSize` 属性の値と等しくなっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-130">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="68272-131">`transferMode` 属性が `Streamed` に等しい場合は、この属性が `maxReceivedMessageSize` 属性の値以下であり、またヘッダーのサイズ以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-131">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="68272-132">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="68272-132">The default is 65536.</span></span> <span data-ttu-id="68272-133">詳細については、「 <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68272-133">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="68272-134">サービスが作成し受け付ける発信/着信接続数の上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="68272-134">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="68272-135">この属性により指定された別個の制限に対して、着信接続および発信接続がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="68272-135">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="68272-136">制限を超える着信接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="68272-136">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="68272-137">制限を超える発信接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="68272-137">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="68272-138">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="68272-138">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="68272-139">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="68272-139">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="68272-140">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="68272-140">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="68272-141">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="68272-141">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="68272-142">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="68272-142">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="68272-143">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="68272-143">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="68272-144">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-144">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="68272-145">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="68272-145">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="68272-146">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="68272-146">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="68272-147">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="68272-147">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="68272-148">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-148">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="68272-149">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="68272-149">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="68272-150">TCP ポート共有をこの接続で有効にするかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="68272-150">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="68272-151">これが `false` の場合、各バインドは独自の排他ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="68272-151">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="68272-152">クライアントには影響しないため、この設定はサービスのみに関連します。</span><span class="sxs-lookup"><span data-stu-id="68272-152">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="68272-153">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="68272-153">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="68272-154">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-154">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="68272-155">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="68272-155">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="68272-156">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="68272-156">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="68272-157">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-157">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="68272-158">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="68272-158">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="68272-159">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="68272-159">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="68272-160">既定値は `false` です。</span><span class="sxs-lookup"><span data-stu-id="68272-160">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="68272-161">このバインディングで使用されるトランザクション プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="68272-161">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="68272-162">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="68272-162">Valid values are</span></span><br /><br /> <span data-ttu-id="68272-163">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="68272-163">-   OleTransactions</span></span><br /><span data-ttu-id="68272-164">-   WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="68272-164">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="68272-165">既定値は OleTransactions です。</span><span class="sxs-lookup"><span data-stu-id="68272-165">The default is OleTransactions.</span></span> <span data-ttu-id="68272-166">この属性は <xref:System.ServiceModel.TransactionProtocol> 型です。</span><span class="sxs-lookup"><span data-stu-id="68272-166">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="68272-167">メッセージが要求や応答をバッファーするか、ストリーミングするかを指定する <xref:System.ServiceModel.TransferMode> 値です。</span><span class="sxs-lookup"><span data-stu-id="68272-167">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68272-168">子要素</span><span class="sxs-lookup"><span data-stu-id="68272-168">Child elements</span></span>  
  
|<span data-ttu-id="68272-169">要素</span><span class="sxs-lookup"><span data-stu-id="68272-169">Element</span></span>|<span data-ttu-id="68272-170">説明</span><span class="sxs-lookup"><span data-stu-id="68272-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68272-171">\<security></span><span class="sxs-lookup"><span data-stu-id="68272-171">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|<span data-ttu-id="68272-172">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="68272-172">Defines the security settings for the binding.</span></span> <span data-ttu-id="68272-173">この要素は <xref:System.ServiceModel.Configuration.NetTcpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="68272-173">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|<span data-ttu-id="68272-174">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="68272-174">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="68272-175">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="68272-175">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="68272-176">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="68272-176">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|<span data-ttu-id="68272-177">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="68272-177">[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))</span></span>|<span data-ttu-id="68272-178">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="68272-178">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68272-179">親要素</span><span class="sxs-lookup"><span data-stu-id="68272-179">Parent elements</span></span>  
  
|<span data-ttu-id="68272-180">要素</span><span class="sxs-lookup"><span data-stu-id="68272-180">Element</span></span>|<span data-ttu-id="68272-181">説明</span><span class="sxs-lookup"><span data-stu-id="68272-181">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68272-182">\<bindings></span><span class="sxs-lookup"><span data-stu-id="68272-182">\<bindings></span></span>](bindings.md)|<span data-ttu-id="68272-183">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="68272-183">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68272-184">Remarks</span><span class="sxs-lookup"><span data-stu-id="68272-184">Remarks</span></span>

<span data-ttu-id="68272-185">このバインディングは、既定ではランタイム通信スタックを生成し、トランスポート セキュリティ、メッセージ配信用 TCP、およびバイナリ メッセージ エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="68272-185">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="68272-186">このバインディングは、イントラネット経由で通信するため適切な Windows Communication Foundation (WCF) システムで指定された方法です。</span><span class="sxs-lookup"><span data-stu-id="68272-186">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="68272-187">既定の構成、`netTcpBinding`によって提供される構成よりも高速、 `wsHttpBinding`WCF の通信のみを対象としていますが、します。</span><span class="sxs-lookup"><span data-stu-id="68272-187">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="68272-188">このセキュリティ動作は、省略可能な `securityMode` 属性を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="68272-188">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="68272-189">WS-ReliableMessaging を使用するかどうかは、省略可能な `reliableSessionEnabled` 属性を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="68272-189">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="68272-190">ただし、信頼できるメッセージングは、既定ではオフです。</span><span class="sxs-lookup"><span data-stu-id="68272-190">But reliable messaging is off by default.</span></span> <span data-ttu-id="68272-191">`wsHttpBinding` や `basicHttpBinding` などの HTTP システム指定のバインディングは、既定では設定をオンにするように構成され、`netTcpBinding` バインディングは、既定では設定をオフにするように構成されているのが一般的であるため、たとえば、いずれかの WS-\* 仕様のサポートを得るには、サポートを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-191">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="68272-192">これは、TCP の既定の構成の方が、HTTP バインディング用の既定の構成より、エンドポイント間でのメッセージ交換が高速になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="68272-192">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68272-193">例</span><span class="sxs-lookup"><span data-stu-id="68272-193">Example</span></span>

<span data-ttu-id="68272-194">バインディングは、クライアントとサービスの構成ファイルに指定されます。</span><span class="sxs-lookup"><span data-stu-id="68272-194">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="68272-195">バインディングの種類は、`binding` 要素の `<endpoint>` 属性に指定します。</span><span class="sxs-lookup"><span data-stu-id="68272-195">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="68272-196">netTcpBinding バインディングを構成してその設定の一部を変更する場合は、バインド構成を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-196">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="68272-197">エンドポイントは、`bindingConfiguration` 属性を使用してバインディング構成を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68272-197">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="68272-198">次の例では、バインド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="68272-198">In the following example, a binding configuration is defined.</span></span>  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="68272-199">関連項目</span><span class="sxs-lookup"><span data-stu-id="68272-199">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="68272-200">バインディング</span><span class="sxs-lookup"><span data-stu-id="68272-200">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="68272-201">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="68272-201">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="68272-202">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="68272-202">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="68272-203">\<binding></span><span class="sxs-lookup"><span data-stu-id="68272-203">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
