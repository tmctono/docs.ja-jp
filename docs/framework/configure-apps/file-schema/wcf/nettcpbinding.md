---
title: <netTcpBinding>
description: TCP を使用する WCF コンピューター間の通信のみを目的とした、セキュリティで保護された、信頼性の高い、最適化されたバインディングを表します。 既定では、信頼できるメッセージはオフになっています。
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: a366b26d87c8796822e4fbbb2001823c116f2629
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556129"
---
# \<netTcpBinding>

<span data-ttu-id="f23ef-103">複数コンピューターの通信に適し、セキュリティで保護されて信頼できる最適化されたバインディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-103">Specifies a secure, reliable, optimized binding suitable for cross-machine communication.</span></span> <span data-ttu-id="f23ef-104">既定では、メッセージ セキュリティと認証用 Windows セキュリティ、メッセージ配信用 TCP、およびバイナリ メッセージ エンコーディングを持つランタイム通信スタックを生成します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-104">By default, it generates a runtime communication stack with Windows Security for message security and authentication, TCP for message delivery, and binary message encoding.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="f23ef-105">構文</span><span class="sxs-lookup"><span data-stu-id="f23ef-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f23ef-106">属性と要素</span><span class="sxs-lookup"><span data-stu-id="f23ef-106">Attributes and elements</span></span>

<span data-ttu-id="f23ef-107">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f23ef-108">属性</span><span class="sxs-lookup"><span data-stu-id="f23ef-108">Attributes</span></span>  
  
|<span data-ttu-id="f23ef-109">属性</span><span class="sxs-lookup"><span data-stu-id="f23ef-109">Attribute</span></span>|<span data-ttu-id="f23ef-110">説明</span><span class="sxs-lookup"><span data-stu-id="f23ef-110">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="f23ef-111">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="f23ef-111">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="f23ef-112">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-112">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f23ef-113">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-113">The default is 00:01:00.</span></span>|  
|`hostNameComparisonMode`|<span data-ttu-id="f23ef-114">URI の解析に使用する HTTP ホスト名比較モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-114">Specifies the HTTP hostname comparison mode used to parse URIs.</span></span> <span data-ttu-id="f23ef-115">この属性は <xref:System.ServiceModel.HostNameComparisonMode> 型で、URI が一致したときにサービスへのアクセスにホスト名を使用するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-115">This attribute is of type <xref:System.ServiceModel.HostNameComparisonMode>, which indicates whether the hostname is used to reach the service when matching on the URI.</span></span> <span data-ttu-id="f23ef-116">既定値は <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard> で、一致しているホスト名を無視します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-116">The default value is <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, which ignores the hostname in the match.</span></span>|  
|`listenBacklog`|<span data-ttu-id="f23ef-117">リスナーで受け入れを待機するチャネルの最大数を指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="f23ef-117">A positive integer that specifies the maximum number of channels waiting to be accepted on the listener.</span></span> <span data-ttu-id="f23ef-118">この制限を超えた接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-118">Connections in excess of this limit are queued until space below the limit becomes available.</span></span> <span data-ttu-id="f23ef-119">`connectionTimeout` 属性は、クライアントが接続を待つ時間を制限します。この時間が経過すると接続の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="f23ef-119">The `connectionTimeout` attribute limits the time a client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="f23ef-120">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-120">The default is 10.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="f23ef-121">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="f23ef-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="f23ef-122">既定は 512 \* 1024 バイトです。</span><span class="sxs-lookup"><span data-stu-id="f23ef-122">The default is 512 \* 1024 bytes.</span></span> <span data-ttu-id="f23ef-123">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="f23ef-124">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="f23ef-125">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="f23ef-126">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="f23ef-127">メッセージをメモリに保存するのに使用するバッファーの最大サイズをバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="f23ef-127">A positive integer that specifies the maximum size, in bytes, of the buffer used to store messages in memory.</span></span><br /><br /> <span data-ttu-id="f23ef-128">`transferMode` 属性が `Buffered` に等しい場合は、この属性が `maxReceivedMessageSize` 属性の値と等しくなっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-128">If the `transferMode` attribute equals to `Buffered`, this attribute should be equal to the `maxReceivedMessageSize` attribute value.</span></span><br /><br /> <span data-ttu-id="f23ef-129">`transferMode` 属性が `Streamed` に等しい場合は、この属性が `maxReceivedMessageSize` 属性の値以下であり、またヘッダーのサイズ以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-129">If the `transferMode` attribute equals to `Streamed`, this attribute cannot be more than the `maxReceivedMessageSize` attribute value, and should be at least the size of the headers.</span></span><br /><br /> <span data-ttu-id="f23ef-130">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-130">The default is 65536.</span></span> <span data-ttu-id="f23ef-131">詳細については、「<xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23ef-131">For more information, see <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.</span></span>|  
|`maxConnections`|<span data-ttu-id="f23ef-132">サービスが作成し受け付ける発信/着信接続数の上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="f23ef-132">An integer that specifies the maximum number of outbound and inbound connections the service will create/accept.</span></span> <span data-ttu-id="f23ef-133">この属性により指定された別個の制限に対して、着信接続および発信接続がカウントされます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-133">Incoming and outgoing connections are counted against a separate limit specified by this attribute.</span></span><br /><br /> <span data-ttu-id="f23ef-134">制限を超える着信接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-134">Inbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="f23ef-135">制限を超える発信接続は、制限内に空きができるまでキューに置かれます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-135">Outbound connections in excess of the limit are queued until a space below the limit becomes available.</span></span><br /><br /> <span data-ttu-id="f23ef-136">既定値は 10 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-136">The default is 10.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="f23ef-137">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="f23ef-137">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="f23ef-138">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-138">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="f23ef-139">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-139">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="f23ef-140">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-140">The default is 65536.</span></span>|  
|`name`|<span data-ttu-id="f23ef-141">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-141">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="f23ef-142">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-142">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="f23ef-143">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f23ef-143">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="f23ef-144">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f23ef-144">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="f23ef-145">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="f23ef-146">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f23ef-147">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-147">The default is 00:01:00.</span></span>|  
|`portSharingEnabled`|<span data-ttu-id="f23ef-148">TCP ポート共有をこの接続で有効にするかどうかを指定するブール値。</span><span class="sxs-lookup"><span data-stu-id="f23ef-148">A Boolean value that specifies whether TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="f23ef-149">これが `false` の場合、各バインドは独自の排他ポートを使用します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-149">If this is `false`, each binding uses its own exclusive port.</span></span> <span data-ttu-id="f23ef-150">クライアントには影響しないため、この設定はサービスのみに関連します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-150">This setting is relevant only to services, because clients are not affected.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="f23ef-151">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-151">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="f23ef-152">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-152">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f23ef-153">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-153">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="f23ef-154">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-154">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="f23ef-155">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-155">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="f23ef-156">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-156">The default is 00:01:00.</span></span>|  
|`transactionFlow`|<span data-ttu-id="f23ef-157">バインディングが WS-Transactions のフローをサポートするかどうかを指定するブール値です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-157">A Boolean value that specifies whether the binding supports flowing WS-Transactions.</span></span> <span data-ttu-id="f23ef-158">既定値は、`false` です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-158">The default is `false`.</span></span>|  
|`transactionProtocol`|<span data-ttu-id="f23ef-159">このバインディングで使用されるトランザクション プロトコルを指定します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-159">Specifies the transaction protocol to be used with this binding.</span></span> <span data-ttu-id="f23ef-160">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f23ef-160">Valid values are</span></span><br /><br /> <span data-ttu-id="f23ef-161">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="f23ef-161">-   OleTransactions</span></span><br /><span data-ttu-id="f23ef-162">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="f23ef-162">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="f23ef-163">既定値は OleTransactions です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-163">The default is OleTransactions.</span></span> <span data-ttu-id="f23ef-164">この属性は <xref:System.ServiceModel.TransactionProtocol> 型です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-164">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
|`transferMode`|<span data-ttu-id="f23ef-165">メッセージが要求や応答をバッファーするか、ストリーミングするかを指定する <xref:System.ServiceModel.TransferMode> 値です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-165">A <xref:System.ServiceModel.TransferMode> value that specifies whether messages are buffered or streamed or a request or response.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f23ef-166">子要素</span><span class="sxs-lookup"><span data-stu-id="f23ef-166">Child elements</span></span>  
  
|<span data-ttu-id="f23ef-167">要素</span><span class="sxs-lookup"><span data-stu-id="f23ef-167">Element</span></span>|<span data-ttu-id="f23ef-168">説明</span><span class="sxs-lookup"><span data-stu-id="f23ef-168">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|<span data-ttu-id="f23ef-169">バインディングのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-169">Defines the security settings for the binding.</span></span> <span data-ttu-id="f23ef-170">この要素は <xref:System.ServiceModel.Configuration.NetTcpSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-170">This element is of type <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.</span></span>|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="f23ef-171">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-171">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f23ef-172">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-172">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<reliableSession>](/previous-versions/ms731375(v=vs.90))|<span data-ttu-id="f23ef-173">チャネルのエンドポイント間に信頼できるセッションを確立するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-173">Specifies if reliable sessions are established between channel endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f23ef-174">親要素</span><span class="sxs-lookup"><span data-stu-id="f23ef-174">Parent elements</span></span>  
  
|<span data-ttu-id="f23ef-175">要素</span><span class="sxs-lookup"><span data-stu-id="f23ef-175">Element</span></span>|<span data-ttu-id="f23ef-176">説明</span><span class="sxs-lookup"><span data-stu-id="f23ef-176">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="f23ef-177">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-177">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f23ef-178">Remarks</span><span class="sxs-lookup"><span data-stu-id="f23ef-178">Remarks</span></span>

<span data-ttu-id="f23ef-179">このバインディングは、既定ではランタイム通信スタックを生成し、トランスポート セキュリティ、メッセージ配信用 TCP、およびバイナリ メッセージ エンコーディングを使用します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-179">This binding generates a run-time communication stack by default, which uses transport security, TCP for message delivery, and a binary message encoding.</span></span> <span data-ttu-id="f23ef-180">このバインディングは、イントラネット経由で通信するための適切な Windows Communication Foundation (WCF) システム提供の選択肢です。</span><span class="sxs-lookup"><span data-stu-id="f23ef-180">This binding is an appropriate Windows Communication Foundation (WCF) system-provided choice for communicating over an Intranet.</span></span>  
  
 <span data-ttu-id="f23ef-181">の既定の構成は `netTcpBinding` 、によって提供される構成よりも高速です `wsHttpBinding` が、WCF 通信のみを目的としています。</span><span class="sxs-lookup"><span data-stu-id="f23ef-181">The default configuration for the `netTcpBinding` is faster than the configuration provided by the `wsHttpBinding`, but it is intended only for WCF communication.</span></span> <span data-ttu-id="f23ef-182">このセキュリティ動作は、省略可能な `securityMode` 属性を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-182">The security behavior is configurable using the optional `securityMode` attribute.</span></span> <span data-ttu-id="f23ef-183">WS-ReliableMessaging を使用するかどうかは、省略可能な `reliableSessionEnabled` 属性を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-183">The use of WS-ReliableMessaging is configurable using the optional `reliableSessionEnabled` attribute.</span></span> <span data-ttu-id="f23ef-184">ただし、信頼できるメッセージングは、既定ではオフです。</span><span class="sxs-lookup"><span data-stu-id="f23ef-184">But reliable messaging is off by default.</span></span> <span data-ttu-id="f23ef-185">`wsHttpBinding` や `basicHttpBinding` などの HTTP システム指定のバインディングは、既定では設定をオンにするように構成され、`netTcpBinding` バインディングは、既定では設定をオフにするように構成されているのが一般的であるため、たとえば、いずれかの WS-\* 仕様のサポートを得るには、サポートを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-185">More generally, the HTTP system-provided bindings such as `wsHttpBinding` and `basicHttpBinding` are configured to turn things on by default, whereas the `netTcpBinding` binding turns things off by default so that you have to opt-in to get support, for example, for one of the WS-\* specifications.</span></span> <span data-ttu-id="f23ef-186">これは、TCP の既定の構成の方が、HTTP バインディング用の既定の構成より、エンドポイント間でのメッセージ交換が高速になることを意味します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-186">This means that the default configuration for TCP is faster at exchanging messages between endpoints than those configured for the HTTP bindings by default.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f23ef-187">例</span><span class="sxs-lookup"><span data-stu-id="f23ef-187">Example</span></span>

<span data-ttu-id="f23ef-188">バインディングは、クライアントとサービスの構成ファイルに指定されます。</span><span class="sxs-lookup"><span data-stu-id="f23ef-188">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="f23ef-189">バインディングの種類は、`binding` 要素の `<endpoint>` 属性に指定します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-189">The binding type is specified in the `binding` attribute of the `<endpoint>` element.</span></span> <span data-ttu-id="f23ef-190">netTcpBinding バインディングを構成してその設定の一部を変更する場合は、バインド構成を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-190">If you want to configure the netTcpBinding binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="f23ef-191">エンドポイントは、`bindingConfiguration` 属性を使用してバインディング構成を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f23ef-191">The endpoint must reference the binding configuration with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="f23ef-192">次の例では、バインド構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="f23ef-192">In the following example, a binding configuration is defined.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f23ef-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="f23ef-193">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [<span data-ttu-id="f23ef-194">バインド</span><span class="sxs-lookup"><span data-stu-id="f23ef-194">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f23ef-195">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="f23ef-195">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f23ef-196">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="f23ef-196">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
