---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 95ce89aabb400c01002799fd8251383a2e5dd4c2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732696"
---
# <a name="udpbinding"></a><span data-ttu-id="7d084-101">\<udpBinding ></span><span class="sxs-lookup"><span data-stu-id="7d084-101">\<udpBinding></span></span>
<span data-ttu-id="7d084-102"><xref:System.ServiceModel.UdpBinding> バインディングの構成に使用する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="7d084-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
<span data-ttu-id="7d084-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7d084-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7d084-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="7d084-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7d084-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="7d084-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="7d084-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**udpBinding >**</span><span class="sxs-lookup"><span data-stu-id="7d084-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d084-107">構文</span><span class="sxs-lookup"><span data-stu-id="7d084-107">Syntax</span></span>  
  
```xml  
<udpBinding>
  <binding closeTimeout="TimeSpan"
           duplicateMessageHistoryLength="Integer"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxPendingMessagesTotalSize="Integer"
           maxReceivedMessageSize="Integer"
           maxRetransmitCount="Integer"
           multicastInterfaceId="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           timeToLive="TimeSpan">
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d084-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="7d084-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7d084-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d084-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d084-110">属性</span><span class="sxs-lookup"><span data-stu-id="7d084-110">Attributes</span></span>  
  
|<span data-ttu-id="7d084-111">属性</span><span class="sxs-lookup"><span data-stu-id="7d084-111">Attribute</span></span>|<span data-ttu-id="7d084-112">説明</span><span class="sxs-lookup"><span data-stu-id="7d084-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="7d084-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="7d084-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="7d084-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d084-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d084-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d084-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="7d084-116">重複するメッセージの履歴の長さを指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="7d084-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="7d084-117">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="7d084-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="7d084-118">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="7d084-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="7d084-119">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="7d084-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="7d084-120">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="7d084-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="7d084-121">受信して、各チャネル インスタンスの入力キューからまだ削除していないメッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="7d084-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="7d084-122">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="7d084-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="7d084-123">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="7d084-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="7d084-124">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="7d084-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="7d084-125">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="7d084-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="7d084-126">再送信メッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="7d084-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="7d084-127">マルチキャストのインターフェイス ID を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="7d084-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="7d084-128">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="7d084-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="7d084-129">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d084-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="7d084-130">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7d084-130">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="7d084-131">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="7d084-131">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="7d084-132">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="7d084-132">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7d084-133">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7d084-133">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="7d084-134">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="7d084-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="7d084-135">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d084-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d084-136">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d084-136">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="7d084-137">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="7d084-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="7d084-138">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d084-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d084-139">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d084-139">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="7d084-140">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="7d084-140">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="7d084-141">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7d084-141">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="7d084-142">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="7d084-142">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="7d084-143">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="7d084-143">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="7d084-144">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="7d084-144">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="7d084-145">-BigEndianUnicode: Unicode BigEndian エンコード。</span><span class="sxs-lookup"><span data-stu-id="7d084-145">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="7d084-146">-Unicode:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="7d084-146">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="7d084-147">-UTF8: 8 ビットエンコーディング</span><span class="sxs-lookup"><span data-stu-id="7d084-147">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="7d084-148">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="7d084-148">The default is UTF8.</span></span> <span data-ttu-id="7d084-149">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d084-149">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="7d084-150">バインディングに対する有効期間を指定する期間値。</span><span class="sxs-lookup"><span data-stu-id="7d084-150">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d084-151">子要素</span><span class="sxs-lookup"><span data-stu-id="7d084-151">Child Elements</span></span>  
  
|<span data-ttu-id="7d084-152">要素</span><span class="sxs-lookup"><span data-stu-id="7d084-152">Element</span></span>|<span data-ttu-id="7d084-153">説明</span><span class="sxs-lookup"><span data-stu-id="7d084-153">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7d084-154">[readerQuotas > の \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="7d084-154">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="7d084-155">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="7d084-155">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="7d084-156">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="7d084-156">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d084-157">親要素</span><span class="sxs-lookup"><span data-stu-id="7d084-157">Parent Elements</span></span>  
  
|<span data-ttu-id="7d084-158">要素</span><span class="sxs-lookup"><span data-stu-id="7d084-158">Element</span></span>|<span data-ttu-id="7d084-159">説明</span><span class="sxs-lookup"><span data-stu-id="7d084-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d084-160">\< バインド ></span><span class="sxs-lookup"><span data-stu-id="7d084-160">\<bindings></span></span>](bindings.md)|<span data-ttu-id="7d084-161">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="7d084-161">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d084-162">Remarks</span><span class="sxs-lookup"><span data-stu-id="7d084-162">Remarks</span></span>  
 <span data-ttu-id="7d084-163">UdpBinding により、WCF サービスが UDP トランスポートを介して通信することができます。</span><span class="sxs-lookup"><span data-stu-id="7d084-163">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="7d084-164">これにより、クライアントがメッセージをサービスに送信し、応答が返されないというメッセージ交換が可能になります。</span><span class="sxs-lookup"><span data-stu-id="7d084-164">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d084-165">例</span><span class="sxs-lookup"><span data-stu-id="7d084-165">Example</span></span>  
 <span data-ttu-id="7d084-166">次の例は、<`udpBinding`> 要素を使用して <xref:System.ServiceModel.UdpBinding> を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="7d084-166">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
```xml  
<udpBinding>
  <binding  closeTimeout="00:10:00"
            duplicateMessageHistoryLength="100"
            maxBufferPoolSize="100"
            maxPendingMessagesTotalSize="100000"
            maxReceivedMessageSize="65536"
            maxRetransmitCount="10"
            multicastInterfaceId="00000"
            name="myUdpBinding"
            openTimeout="00:10:00"
            receiveTimeout="00:10:00"
            sendTimeout="00:10:00"
            textEncoding="utf-8"
            timeToLive="00:10:00">
    <readerQuotas />
  </binding>
</udpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="7d084-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="7d084-167">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="7d084-168">バインディング</span><span class="sxs-lookup"><span data-stu-id="7d084-168">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7d084-169">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="7d084-169">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7d084-170">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="7d084-170">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7d084-171">\<binding ></span><span class="sxs-lookup"><span data-stu-id="7d084-171">\<binding></span></span>](bindings.md)
