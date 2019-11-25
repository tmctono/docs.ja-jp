---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 921da4d0b010672585a045d58d03182e480a255a
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140732"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="9f8d0-101">\<netPeerTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="9f8d0-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="9f8d0-102">ピア チャネル固有の TCP メッセージングのバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
<span data-ttu-id="9f8d0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9f8d0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9f8d0-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9f8d0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9f8d0-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9f8d0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9f8d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**netPeerTcpBinding\<**</span><span class="sxs-lookup"><span data-stu-id="9f8d0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8d0-107">構文</span><span class="sxs-lookup"><span data-stu-id="9f8d0-107">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding name="string"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           listenIPAddress="String"
           maxBufferPoolSize="integer"
           maxReceiveMessageSize="Integer"
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f8d0-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9f8d0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9f8d0-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f8d0-110">属性</span><span class="sxs-lookup"><span data-stu-id="9f8d0-110">Attributes</span></span>  
  
|<span data-ttu-id="9f8d0-111">属性</span><span class="sxs-lookup"><span data-stu-id="9f8d0-111">Attribute</span></span>|<span data-ttu-id="9f8d0-112">説明</span><span class="sxs-lookup"><span data-stu-id="9f8d0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f8d0-113">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="9f8d0-113">closeTimeout</span></span>|<span data-ttu-id="9f8d0-114">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-114">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="9f8d0-115">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-115">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f8d0-116">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-116">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="9f8d0-117">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="9f8d0-117">listenIPAddress</span></span>|<span data-ttu-id="9f8d0-118">ピア ノードが TCP メッセージをリッスンする IP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-118">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="9f8d0-119">既定値は、 `null`です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-119">The default is `null`.</span></span>|  
|<span data-ttu-id="9f8d0-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="9f8d0-120">maxBufferPoolSize</span></span>|<span data-ttu-id="9f8d0-121">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-121">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="9f8d0-122">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-122">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="9f8d0-123">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-123">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="9f8d0-124">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-124">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="9f8d0-125">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-125">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="9f8d0-126">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-126">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="9f8d0-127">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="9f8d0-127">maxReceivedMessageSize</span></span>|<span data-ttu-id="9f8d0-128">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-128">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="9f8d0-129">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-129">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="9f8d0-130">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-130">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="9f8d0-131">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-131">The default is 65536.</span></span>|  
|<span data-ttu-id="9f8d0-132">name</span><span class="sxs-lookup"><span data-stu-id="9f8d0-132">name</span></span>|<span data-ttu-id="9f8d0-133">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-133">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="9f8d0-134">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-134">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="9f8d0-135">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-135">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="9f8d0-136">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-136">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="9f8d0-137">openTimeout</span><span class="sxs-lookup"><span data-stu-id="9f8d0-137">openTimeout</span></span>|<span data-ttu-id="9f8d0-138">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="9f8d0-139">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f8d0-140">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-140">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="9f8d0-141">ポート</span><span class="sxs-lookup"><span data-stu-id="9f8d0-141">port</span></span>|<span data-ttu-id="9f8d0-142">このバインディングがピア チャネルの TCP メッセージを処理するネットワーク インターフェイス ポートを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-142">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="9f8d0-143">この値の有効値の範囲は <xref:System.Net.IPEndPoint.MinPort> ～ <xref:System.Net.IPEndPoint.MaxPort> です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-143">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="9f8d0-144">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-144">The default is 0.</span></span>|  
|<span data-ttu-id="9f8d0-145">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="9f8d0-145">receiveTimeout</span></span>|<span data-ttu-id="9f8d0-146">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="9f8d0-147">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f8d0-148">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-148">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="9f8d0-149">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="9f8d0-149">sendTimeout</span></span>|<span data-ttu-id="9f8d0-150">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-150">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="9f8d0-151">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-151">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="9f8d0-152">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-152">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f8d0-153">子要素</span><span class="sxs-lookup"><span data-stu-id="9f8d0-153">Child Elements</span></span>  
  
|<span data-ttu-id="9f8d0-154">要素</span><span class="sxs-lookup"><span data-stu-id="9f8d0-154">Element</span></span>|<span data-ttu-id="9f8d0-155">説明</span><span class="sxs-lookup"><span data-stu-id="9f8d0-155">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9f8d0-156">[readerQuotas > の \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9f8d0-156">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="9f8d0-157">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-157">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9f8d0-158">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-158">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="9f8d0-159">\<リゾルバー ></span><span class="sxs-lookup"><span data-stu-id="9f8d0-159">\<resolver></span></span>](resolver.md)|<span data-ttu-id="9f8d0-160">ピア メッシュ ID を解決してピア メッシュ内のノードのエンドポイント ID アドレスを取得するために、このバインディングによって使用されるピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-160">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="9f8d0-161">\<セキュリティ ></span><span class="sxs-lookup"><span data-stu-id="9f8d0-161">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="9f8d0-162">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-162">Defines the security settings for the message.</span></span> <span data-ttu-id="9f8d0-163">この要素は <xref:System.ServiceModel.Configuration.PeerSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-163">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f8d0-164">親要素</span><span class="sxs-lookup"><span data-stu-id="9f8d0-164">Parent Elements</span></span>  
  
|<span data-ttu-id="9f8d0-165">要素</span><span class="sxs-lookup"><span data-stu-id="9f8d0-165">Element</span></span>|<span data-ttu-id="9f8d0-166">説明</span><span class="sxs-lookup"><span data-stu-id="9f8d0-166">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f8d0-167">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="9f8d0-167">\<bindings></span></span>](bindings.md)|<span data-ttu-id="9f8d0-168">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-168">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f8d0-169">Remarks</span><span class="sxs-lookup"><span data-stu-id="9f8d0-169">Remarks</span></span>  
 <span data-ttu-id="9f8d0-170">このバインディングは、TCP を介したピア トランスポートを使用するピア ツー ピア アプリケーションまたはマルチパーティ アプリケーションの作成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-170">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="9f8d0-171">各ピア ノードは、この種類のバイディングを使用して定義された複数のピア チャネルをホストできます。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-171">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f8d0-172">例</span><span class="sxs-lookup"><span data-stu-id="9f8d0-172">Example</span></span>  
 <span data-ttu-id="9f8d0-173">次の例では、ピア チャネルを使用してマルチパーティ通信を実現する、NetPeerTcpBinding バインディングを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-173">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="9f8d0-174">このバインディングを使用する詳細なシナリオについては、「 [Net ピア TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8d0-174">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 maxBufferSize="1001"
                 maxConnections="123"
                 maxReceiveMessageSize="1000">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="TransportWithMessageCredential">
            <message clientCredentialType="CardSpace" />
          </security>
        </binding>
      </netPeerBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="9f8d0-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="9f8d0-175">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="9f8d0-176">バインディング</span><span class="sxs-lookup"><span data-stu-id="9f8d0-176">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9f8d0-177">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="9f8d0-177">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9f8d0-178">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="9f8d0-178">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9f8d0-179">\<バインド ></span><span class="sxs-lookup"><span data-stu-id="9f8d0-179">\<binding></span></span>](bindings.md)
- <span data-ttu-id="9f8d0-180">[Net ピア TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9f8d0-180">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="9f8d0-181">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="9f8d0-181">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
