---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 84a5bc763f898b3d323a6cee468c6e22d27d85a0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788207"
---
# <a name="udpbinding"></a><span data-ttu-id="c4e05-101">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="c4e05-101">\<udpBinding></span></span>
<span data-ttu-id="c4e05-102"><xref:System.ServiceModel.UdpBinding> バインディングの構成に使用する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
 <span data-ttu-id="c4e05-103">\<system.ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c4e05-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c4e05-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c4e05-104">\<bindings></span></span>  
<span data-ttu-id="c4e05-105">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="c4e05-105">\<udpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e05-106">構文</span><span class="sxs-lookup"><span data-stu-id="c4e05-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4e05-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c4e05-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c4e05-108">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4e05-109">属性</span><span class="sxs-lookup"><span data-stu-id="c4e05-109">Attributes</span></span>  
  
|<span data-ttu-id="c4e05-110">属性</span><span class="sxs-lookup"><span data-stu-id="c4e05-110">Attribute</span></span>|<span data-ttu-id="c4e05-111">説明</span><span class="sxs-lookup"><span data-stu-id="c4e05-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="c4e05-112">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="c4e05-113">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c4e05-114">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-114">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="c4e05-115">重複するメッセージの履歴の長さを指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-115">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="c4e05-116">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-116">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="c4e05-117">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="c4e05-117">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="c4e05-118">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="c4e05-118">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="c4e05-119">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="c4e05-119">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="c4e05-120">受信して、各チャネル インスタンスの入力キューからまだ削除していないメッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-120">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="c4e05-121">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="c4e05-121">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="c4e05-122">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-122">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="c4e05-123">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-123">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c4e05-124">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="c4e05-124">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="c4e05-125">再送信メッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-125">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="c4e05-126">マルチキャストのインターフェイス ID を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-126">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="c4e05-127">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-127">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="c4e05-128">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-128">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="c4e05-129">各バインドには、サービスのメタデータでこれをまとめて一意に識別する `name` および `namespace` 属性が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c4e05-129">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="c4e05-130">また、この名前は、同じ種類のバインディング間で一意です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-130">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="c4e05-131">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 以降では、バインディングおよび動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c4e05-131">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="c4e05-132">既定の構成と無名のバインディングおよび動作の詳細については、「[簡略化された構成](../../../../../docs/framework/wcf/simplified-configuration.md)」と「[WCF サービスの構成を簡略化](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c4e05-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="c4e05-133">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="c4e05-134">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c4e05-135">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-135">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="c4e05-136">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-136">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="c4e05-137">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-137">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c4e05-138">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-138">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="c4e05-139">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-139">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="c4e05-140">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c4e05-140">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="c4e05-141">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-141">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="c4e05-142">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-142">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="c4e05-143">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-143">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c4e05-144">-BigEndianUnicode:Unicode BigEndian エンコーディングします。</span><span class="sxs-lookup"><span data-stu-id="c4e05-144">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="c4e05-145">Unicode:16 ビット エンコーディング。</span><span class="sxs-lookup"><span data-stu-id="c4e05-145">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="c4e05-146">UTF8:8 ビット エンコード</span><span class="sxs-lookup"><span data-stu-id="c4e05-146">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="c4e05-147">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-147">The default is UTF8.</span></span> <span data-ttu-id="c4e05-148">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-148">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="c4e05-149">バインディングに対する有効期間を指定する期間値。</span><span class="sxs-lookup"><span data-stu-id="c4e05-149">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4e05-150">子要素</span><span class="sxs-lookup"><span data-stu-id="c4e05-150">Child Elements</span></span>  
  
|<span data-ttu-id="c4e05-151">要素</span><span class="sxs-lookup"><span data-stu-id="c4e05-151">Element</span></span>|<span data-ttu-id="c4e05-152">説明</span><span class="sxs-lookup"><span data-stu-id="c4e05-152">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c4e05-153">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c4e05-153">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="c4e05-154">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="c4e05-154">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c4e05-155">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="c4e05-155">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4e05-156">親要素</span><span class="sxs-lookup"><span data-stu-id="c4e05-156">Parent Elements</span></span>  
  
|<span data-ttu-id="c4e05-157">要素</span><span class="sxs-lookup"><span data-stu-id="c4e05-157">Element</span></span>|<span data-ttu-id="c4e05-158">説明</span><span class="sxs-lookup"><span data-stu-id="c4e05-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4e05-159">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c4e05-159">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="c4e05-160">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4e05-161">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4e05-161">Remarks</span></span>  
 <span data-ttu-id="c4e05-162">UdpBinding により、WCF サービスが UDP トランスポートを介して通信することができます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-162">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="c4e05-163">クライアントがサービスにメッセージを送信し、応答を返信しても、メッセージ交換の「ファイア アンド フォーゲット」できます。</span><span class="sxs-lookup"><span data-stu-id="c4e05-163">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4e05-164">例</span><span class="sxs-lookup"><span data-stu-id="c4e05-164">Example</span></span>  
 <span data-ttu-id="c4e05-165">次の例は、構成する方法を示します、<xref:System.ServiceModel.UdpBinding>を使用して、<`udpBinding`> 要素。</span><span class="sxs-lookup"><span data-stu-id="c4e05-165">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c4e05-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="c4e05-166">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="c4e05-167">バインディング</span><span class="sxs-lookup"><span data-stu-id="c4e05-167">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c4e05-168">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="c4e05-168">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c4e05-169">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="c4e05-169">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="c4e05-170">\<binding></span><span class="sxs-lookup"><span data-stu-id="c4e05-170">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
