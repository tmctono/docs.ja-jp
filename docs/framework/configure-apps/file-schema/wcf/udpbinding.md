---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 7fa72d233d6489ab6a2c534f69c66a55a22d0f59
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "74429834"
---
# \<udpBinding>
<span data-ttu-id="66d66-101"><xref:System.ServiceModel.UdpBinding> バインディングの構成に使用する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="66d66-101">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="66d66-102">構文</span><span class="sxs-lookup"><span data-stu-id="66d66-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66d66-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="66d66-103">Attributes and Elements</span></span>  
 <span data-ttu-id="66d66-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="66d66-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66d66-105">属性</span><span class="sxs-lookup"><span data-stu-id="66d66-105">Attributes</span></span>  
  
|<span data-ttu-id="66d66-106">属性</span><span class="sxs-lookup"><span data-stu-id="66d66-106">Attribute</span></span>|<span data-ttu-id="66d66-107">説明</span><span class="sxs-lookup"><span data-stu-id="66d66-107">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="66d66-108">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="66d66-108">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="66d66-109">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="66d66-109">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d66-110">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="66d66-110">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="66d66-111">重複するメッセージの履歴の長さを指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="66d66-111">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="66d66-112">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="66d66-112">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="66d66-113">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="66d66-113">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="66d66-114">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="66d66-114">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="66d66-115">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="66d66-115">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="66d66-116">受信して、各チャネル インスタンスの入力キューからまだ削除していないメッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="66d66-116">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="66d66-117">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="66d66-117">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="66d66-118">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="66d66-118">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="66d66-119">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="66d66-119">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="66d66-120">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="66d66-120">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="66d66-121">再送信メッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="66d66-121">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="66d66-122">マルチキャストのインターフェイス ID を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="66d66-122">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="66d66-123">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="66d66-123">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="66d66-124">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66d66-124">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="66d66-125">.NET Framework 4 以降では、バインドと動作に名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="66d66-125">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="66d66-126">既定の構成と無名のバインドおよび動作の詳細については、「 [WCF サービスの](../../../wcf/samples/simplified-configuration-for-wcf-services.md)構成と簡略化された構成の[簡略化](../../../wcf/simplified-configuration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66d66-126">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="66d66-127">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="66d66-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="66d66-128">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="66d66-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d66-129">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="66d66-129">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="66d66-130">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="66d66-130">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="66d66-131">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="66d66-131">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d66-132">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="66d66-132">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="66d66-133">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="66d66-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="66d66-134">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="66d66-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="66d66-135">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="66d66-135">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="66d66-136">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="66d66-136">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="66d66-137">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="66d66-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="66d66-138">-BigEndianUnicode: Unicode BigEndian エンコード。</span><span class="sxs-lookup"><span data-stu-id="66d66-138">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="66d66-139">-Unicode:16 ビットエンコード。</span><span class="sxs-lookup"><span data-stu-id="66d66-139">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="66d66-140">-UTF8: 8 ビットエンコーディング</span><span class="sxs-lookup"><span data-stu-id="66d66-140">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="66d66-141">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="66d66-141">The default is UTF8.</span></span> <span data-ttu-id="66d66-142">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="66d66-142">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="66d66-143">バインディングに対する有効期間を指定する期間値。</span><span class="sxs-lookup"><span data-stu-id="66d66-143">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66d66-144">子要素</span><span class="sxs-lookup"><span data-stu-id="66d66-144">Child Elements</span></span>  
  
|<span data-ttu-id="66d66-145">要素</span><span class="sxs-lookup"><span data-stu-id="66d66-145">Element</span></span>|<span data-ttu-id="66d66-146">Description</span><span class="sxs-lookup"><span data-stu-id="66d66-146">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="66d66-147">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="66d66-147">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="66d66-148">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="66d66-148">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66d66-149">親要素</span><span class="sxs-lookup"><span data-stu-id="66d66-149">Parent Elements</span></span>  
  
|<span data-ttu-id="66d66-150">要素</span><span class="sxs-lookup"><span data-stu-id="66d66-150">Element</span></span>|<span data-ttu-id="66d66-151">Description</span><span class="sxs-lookup"><span data-stu-id="66d66-151">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="66d66-152">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="66d66-152">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66d66-153">解説</span><span class="sxs-lookup"><span data-stu-id="66d66-153">Remarks</span></span>  
 <span data-ttu-id="66d66-154">UdpBinding により、WCF サービスが UDP トランスポートを介して通信することができます。</span><span class="sxs-lookup"><span data-stu-id="66d66-154">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="66d66-155">これにより、クライアントがメッセージをサービスに送信し、応答が返されないというメッセージ交換が可能になります。</span><span class="sxs-lookup"><span data-stu-id="66d66-155">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66d66-156">例</span><span class="sxs-lookup"><span data-stu-id="66d66-156">Example</span></span>  
 <span data-ttu-id="66d66-157">次の例は、<> 要素を使用してを構成する方法を示して <xref:System.ServiceModel.UdpBinding> `udpBinding` います。</span><span class="sxs-lookup"><span data-stu-id="66d66-157">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66d66-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="66d66-158">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="66d66-159">バインド</span><span class="sxs-lookup"><span data-stu-id="66d66-159">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="66d66-160">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="66d66-160">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="66d66-161">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="66d66-161">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
