---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 5fe221c5ec6c51afb199b2c66eab9d72cdfd750b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556142"
---
# \<netPeerTcpBinding>
<span data-ttu-id="54a07-101">ピア チャネル固有の TCP メッセージングのバインディングを定義します。</span><span class="sxs-lookup"><span data-stu-id="54a07-101">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="54a07-102">構文</span><span class="sxs-lookup"><span data-stu-id="54a07-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54a07-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="54a07-103">Attributes and Elements</span></span>  
 <span data-ttu-id="54a07-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="54a07-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54a07-105">属性</span><span class="sxs-lookup"><span data-stu-id="54a07-105">Attributes</span></span>  
  
|<span data-ttu-id="54a07-106">属性</span><span class="sxs-lookup"><span data-stu-id="54a07-106">Attribute</span></span>|<span data-ttu-id="54a07-107">説明</span><span class="sxs-lookup"><span data-stu-id="54a07-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54a07-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="54a07-108">closeTimeout</span></span>|<span data-ttu-id="54a07-109">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="54a07-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="54a07-110">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a07-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54a07-111">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="54a07-111">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="54a07-112">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="54a07-112">listenIPAddress</span></span>|<span data-ttu-id="54a07-113">ピア ノードが TCP メッセージをリッスンする IP アドレスを指定する文字列です。</span><span class="sxs-lookup"><span data-stu-id="54a07-113">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="54a07-114">既定値は、`null` です。</span><span class="sxs-lookup"><span data-stu-id="54a07-114">The default is `null`.</span></span>|  
|<span data-ttu-id="54a07-115">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="54a07-115">maxBufferPoolSize</span></span>|<span data-ttu-id="54a07-116">このバインディングに使用するバッファー プール サイズの上限を指定する整数。</span><span class="sxs-lookup"><span data-stu-id="54a07-116">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="54a07-117">既定は 524,288 バイト (512 \* 1024) です。</span><span class="sxs-lookup"><span data-stu-id="54a07-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="54a07-118">Windows Communication Foundation (WCF) では、多くの部分でバッファーを使用します。</span><span class="sxs-lookup"><span data-stu-id="54a07-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="54a07-119">使用するたびに毎回バッファーを作成および破壊すると負荷が高くなります。バッファーのガベージ コレクションも同様です。</span><span class="sxs-lookup"><span data-stu-id="54a07-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="54a07-120">バッファー プールを使用すると、バッファーをプールから取得して使用し、作業が終わったらプールに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="54a07-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="54a07-121">これで、バッファーの作成と破棄のオーバーヘッドを回避できます。</span><span class="sxs-lookup"><span data-stu-id="54a07-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="54a07-122">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="54a07-122">maxReceivedMessageSize</span></span>|<span data-ttu-id="54a07-123">このバインディングで構成されるチャネルで受信可能な最大メッセージ サイズ (ヘッダーを含む) をバイト単位で指定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="54a07-123">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="54a07-124">この制限を超えるメッセージの送信者が、SOAP エラーを受信します。</span><span class="sxs-lookup"><span data-stu-id="54a07-124">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="54a07-125">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="54a07-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="54a07-126">既定値は 65536 です。</span><span class="sxs-lookup"><span data-stu-id="54a07-126">The default is 65536.</span></span>|  
|<span data-ttu-id="54a07-127">name</span><span class="sxs-lookup"><span data-stu-id="54a07-127">name</span></span>|<span data-ttu-id="54a07-128">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="54a07-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="54a07-129">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a07-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="54a07-130">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="54a07-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="54a07-131">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54a07-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="54a07-132">openTimeout</span><span class="sxs-lookup"><span data-stu-id="54a07-132">openTimeout</span></span>|<span data-ttu-id="54a07-133">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="54a07-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="54a07-134">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a07-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54a07-135">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="54a07-135">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="54a07-136">port</span><span class="sxs-lookup"><span data-stu-id="54a07-136">port</span></span>|<span data-ttu-id="54a07-137">このバインディングがピア チャネルの TCP メッセージを処理するネットワーク インターフェイス ポートを指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="54a07-137">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="54a07-138">この値の有効値の範囲は <xref:System.Net.IPEndPoint.MinPort> ～ <xref:System.Net.IPEndPoint.MaxPort> です。</span><span class="sxs-lookup"><span data-stu-id="54a07-138">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="54a07-139">既定値は 0 です。</span><span class="sxs-lookup"><span data-stu-id="54a07-139">The default is 0.</span></span>|  
|<span data-ttu-id="54a07-140">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="54a07-140">receiveTimeout</span></span>|<span data-ttu-id="54a07-141">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="54a07-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="54a07-142">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a07-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54a07-143">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="54a07-143">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="54a07-144">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="54a07-144">sendTimeout</span></span>|<span data-ttu-id="54a07-145">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="54a07-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="54a07-146">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="54a07-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="54a07-147">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="54a07-147">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54a07-148">子要素</span><span class="sxs-lookup"><span data-stu-id="54a07-148">Child Elements</span></span>  
  
|<span data-ttu-id="54a07-149">要素</span><span class="sxs-lookup"><span data-stu-id="54a07-149">Element</span></span>|<span data-ttu-id="54a07-150">説明</span><span class="sxs-lookup"><span data-stu-id="54a07-150">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="54a07-151">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="54a07-151">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="54a07-152">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="54a07-152">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="54a07-153">ピア メッシュ ID を解決してピア メッシュ内のノードのエンドポイント ID アドレスを取得するために、このバインディングによって使用されるピア リゾルバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="54a07-153">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="54a07-154">メッセージのセキュリティ設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="54a07-154">Defines the security settings for the message.</span></span> <span data-ttu-id="54a07-155">この要素は <xref:System.ServiceModel.Configuration.PeerSecurityElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="54a07-155">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="54a07-156">親要素</span><span class="sxs-lookup"><span data-stu-id="54a07-156">Parent Elements</span></span>  
  
|<span data-ttu-id="54a07-157">要素</span><span class="sxs-lookup"><span data-stu-id="54a07-157">Element</span></span>|<span data-ttu-id="54a07-158">説明</span><span class="sxs-lookup"><span data-stu-id="54a07-158">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="54a07-159">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="54a07-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54a07-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="54a07-160">Remarks</span></span>  
 <span data-ttu-id="54a07-161">このバインディングは、TCP を介したピア トランスポートを使用するピア ツー ピア アプリケーションまたはマルチパーティ アプリケーションの作成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="54a07-161">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="54a07-162">各ピア ノードは、この種類のバイディングを使用して定義された複数のピア チャネルをホストできます。</span><span class="sxs-lookup"><span data-stu-id="54a07-162">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54a07-163">例</span><span class="sxs-lookup"><span data-stu-id="54a07-163">Example</span></span>  
 <span data-ttu-id="54a07-164">次の例では、ピア チャネルを使用してマルチパーティ通信を実現する、NetPeerTcpBinding バインディングを使用する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="54a07-164">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="54a07-165">このバインディングを使用する詳細なシナリオについては、「 [Net ピア TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54a07-165">For a detailed scenario of using this binding, see [Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54a07-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="54a07-166">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="54a07-167">バインド</span><span class="sxs-lookup"><span data-stu-id="54a07-167">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="54a07-168">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="54a07-168">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="54a07-169">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="54a07-169">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="54a07-170">[ネット ピア TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="54a07-170">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="54a07-171">ピアツーピアネットワーク</span><span class="sxs-lookup"><span data-stu-id="54a07-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
