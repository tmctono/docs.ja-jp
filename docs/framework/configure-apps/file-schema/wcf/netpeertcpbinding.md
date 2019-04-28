---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: b35e2f365e82291d3f8b827850fdebfe8fa2237d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780368"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="42761-101">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="42761-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="42761-102">ピア チャネル固有の TCP メッセージングのバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="42761-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="42761-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="42761-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="42761-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="42761-104">\<bindings></span></span>  
<span data-ttu-id="42761-105">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="42761-105">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42761-106">構文</span><span class="sxs-lookup"><span data-stu-id="42761-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42761-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="42761-107">Attributes and Elements</span></span>  
 <span data-ttu-id="42761-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="42761-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42761-109">属性</span><span class="sxs-lookup"><span data-stu-id="42761-109">Attributes</span></span>  
  
|<span data-ttu-id="42761-110">属性</span><span class="sxs-lookup"><span data-stu-id="42761-110">Attribute</span></span>|<span data-ttu-id="42761-111">説明</span><span class="sxs-lookup"><span data-stu-id="42761-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42761-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="42761-112">closeTimeout</span></span>|<span data-ttu-id="42761-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="42761-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="42761-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42761-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="42761-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="42761-115">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="42761-116">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="42761-116">listenIPAddress</span></span>|<span data-ttu-id="42761-117">ピア ノードが TCP メッセージをリッスンする IP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="42761-117">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="42761-118">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="42761-118">The default is `null`.</span></span>|  
|<span data-ttu-id="42761-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="42761-119">maxBufferPoolSize</span></span>|<span data-ttu-id="42761-120">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="42761-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="42761-121">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="42761-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="42761-122">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="42761-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="42761-123">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="42761-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="42761-124">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="42761-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="42761-125">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="42761-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="42761-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="42761-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="42761-127">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="42761-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="42761-128">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="42761-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="42761-129">メッセージは受信者によって破棄され、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="42761-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="42761-130">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="42761-130">The default is 65536.</span></span>|  
|<span data-ttu-id="42761-131">name</span><span class="sxs-lookup"><span data-stu-id="42761-131">name</span></span>|<span data-ttu-id="42761-132">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="42761-132">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="42761-133">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42761-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="42761-134">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="42761-134">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="42761-135">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42761-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="42761-136">openTimeout</span><span class="sxs-lookup"><span data-stu-id="42761-136">openTimeout</span></span>|<span data-ttu-id="42761-137">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="42761-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="42761-138">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42761-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="42761-139">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="42761-139">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="42761-140">ポート</span><span class="sxs-lookup"><span data-stu-id="42761-140">port</span></span>|<span data-ttu-id="42761-141">このバインディングがピア チャネルの TCP メッセージを処理するネットワーク インターフェイス ポートを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="42761-141">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="42761-142">この値の有効値の範囲は <xref:System.Net.IPEndPoint.MinPort> ～ <xref:System.Net.IPEndPoint.MaxPort> です。</span><span class="sxs-lookup"><span data-stu-id="42761-142">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="42761-143">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="42761-143">The default is 0.</span></span>|  
|<span data-ttu-id="42761-144">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="42761-144">receiveTimeout</span></span>|<span data-ttu-id="42761-145">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="42761-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="42761-146">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42761-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="42761-147">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="42761-147">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="42761-148">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="42761-148">sendTimeout</span></span>|<span data-ttu-id="42761-149">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="42761-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="42761-150">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42761-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="42761-151">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="42761-151">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42761-152">子要素</span><span class="sxs-lookup"><span data-stu-id="42761-152">Child Elements</span></span>  
  
|<span data-ttu-id="42761-153">要素</span><span class="sxs-lookup"><span data-stu-id="42761-153">Element</span></span>|<span data-ttu-id="42761-154">説明</span><span class="sxs-lookup"><span data-stu-id="42761-154">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42761-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="42761-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="42761-156">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="42761-156">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="42761-157">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="42761-157">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="42761-158">\<resolver></span><span class="sxs-lookup"><span data-stu-id="42761-158">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="42761-159">ピア メッシュ ID を解決してピア メッシュ内のノードのエンドポイント ID アドレスを取得するために、このバインディングによって使用されるピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="42761-159">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="42761-160">\<security></span><span class="sxs-lookup"><span data-stu-id="42761-160">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netpeerbinding.md)|<span data-ttu-id="42761-161">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="42761-161">Defines the security settings for the message.</span></span> <span data-ttu-id="42761-162">この要素は <xref:System.ServiceModel.Configuration.PeerSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="42761-162">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42761-163">親要素</span><span class="sxs-lookup"><span data-stu-id="42761-163">Parent Elements</span></span>  
  
|<span data-ttu-id="42761-164">要素</span><span class="sxs-lookup"><span data-stu-id="42761-164">Element</span></span>|<span data-ttu-id="42761-165">説明</span><span class="sxs-lookup"><span data-stu-id="42761-165">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42761-166">\<bindings></span><span class="sxs-lookup"><span data-stu-id="42761-166">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="42761-167">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="42761-167">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42761-168">Remarks</span><span class="sxs-lookup"><span data-stu-id="42761-168">Remarks</span></span>  
 <span data-ttu-id="42761-169">このバインディングは、TCP を介したピア トランスポートを使用するピア ツー ピア アプリケーションまたはマルチパーティ アプリケーションの作成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="42761-169">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="42761-170">各ピア ノードは、この種類のバイディングを使用して定義された複数のピア チャネルをホストできます。</span><span class="sxs-lookup"><span data-stu-id="42761-170">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42761-171">例</span><span class="sxs-lookup"><span data-stu-id="42761-171">Example</span></span>  
 <span data-ttu-id="42761-172">次の例では、ピア チャネルを使用してマルチパーティ通信を実現する、NetPeerTcpBinding バインディングを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="42761-172">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="42761-173">このバインディングの使い方の詳細なシナリオでは、次を参照してください。[ネット ピア TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))します。</span><span class="sxs-lookup"><span data-stu-id="42761-173">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42761-174">関連項目</span><span class="sxs-lookup"><span data-stu-id="42761-174">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="42761-175">バインディング</span><span class="sxs-lookup"><span data-stu-id="42761-175">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="42761-176">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="42761-176">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="42761-177">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="42761-177">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="42761-178">\<binding></span><span class="sxs-lookup"><span data-stu-id="42761-178">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- <span data-ttu-id="42761-179">[ネット ピア TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="42761-179">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="42761-180">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="42761-180">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)
