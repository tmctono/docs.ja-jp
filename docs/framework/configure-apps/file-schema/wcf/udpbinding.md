---
title: <udpBinding>
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 7fa72d233d6489ab6a2c534f69c66a55a22d0f59
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429834"
---
# <a name="udpbinding"></a><span data-ttu-id="51955-101">\<udpBinding></span><span class="sxs-lookup"><span data-stu-id="51955-101">\<udpBinding></span></span>
<span data-ttu-id="51955-102"><xref:System.ServiceModel.UdpBinding> バインディングの構成に使用する構成要素です。</span><span class="sxs-lookup"><span data-stu-id="51955-102">A configuration element used to configure the <xref:System.ServiceModel.UdpBinding> binding.</span></span>  
  
<span data-ttu-id="51955-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="51955-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="51955-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="51955-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="51955-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="51955-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="51955-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<udpBinding>**</span><span class="sxs-lookup"><span data-stu-id="51955-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<udpBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51955-107">構文</span><span class="sxs-lookup"><span data-stu-id="51955-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51955-108">属性および要素</span><span class="sxs-lookup"><span data-stu-id="51955-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51955-109">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="51955-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51955-110">属性</span><span class="sxs-lookup"><span data-stu-id="51955-110">Attributes</span></span>  
  
|<span data-ttu-id="51955-111">属性</span><span class="sxs-lookup"><span data-stu-id="51955-111">Attribute</span></span>|<span data-ttu-id="51955-112">説明</span><span class="sxs-lookup"><span data-stu-id="51955-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="51955-113">クローズ操作が完了するまでの期間を指定する <xref:System.TimeSpan> 値。</span><span class="sxs-lookup"><span data-stu-id="51955-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="51955-114">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51955-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51955-115">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="51955-115">The default is 00:01:00.</span></span>|  
|`duplicateMessageHistoryLength`|<span data-ttu-id="51955-116">重複するメッセージの履歴の長さを指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="51955-116">An integer value that specifies the duplicate message history length.</span></span>|  
|`maxBufferPoolSize`|<span data-ttu-id="51955-117">チャネルからメッセージを受け取るメッセージ バッファーのマネージャーが使用するために割り当てられる、最大メモリ量を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="51955-117">An integer value that specifies the maximum amount of memory that is allocated for use by the manager of the message buffers that receive messages from the channel.</span></span> <span data-ttu-id="51955-118">既定値は 524288 (0x80000) バイトです。</span><span class="sxs-lookup"><span data-stu-id="51955-118">The default value is 524288 (0x80000) bytes.</span></span>|  
|`maxBufferSize`|<span data-ttu-id="51955-119">このバインディングで構成されるエンドポイントのメッセージが処理されるときのメッセージを格納するバッファーの最大サイズを指定する整数値 (バイト単位)。</span><span class="sxs-lookup"><span data-stu-id="51955-119">An integer value that specifies the maximum size, in bytes, of a buffer that stores messages while they are processed for an endpoint configured with this binding.</span></span> <span data-ttu-id="51955-120">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="51955-120">The default value is 65,536 bytes.</span></span>|  
|`maxPendingMessagesTotalSize`|<span data-ttu-id="51955-121">受信して、各チャネル インスタンスの入力キューからまだ削除していないメッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="51955-121">An integer value that specifies the maximum number of messages that are received but not yet removed from the input queue for an individual channel instance.</span></span>|  
|`maxReceivedMessageSize`|<span data-ttu-id="51955-122">このバインディングで構成されるチャネルが受信可能なメッセージの最大メッセージ サイズ (ヘッダーを含む) をバイト単位で定義する正の整数。</span><span class="sxs-lookup"><span data-stu-id="51955-122">A positive integer that defines the maximum message size, in bytes, including headers, for a message that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="51955-123">受信側のメッセージが大きすぎると、送信側は SOAP エラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="51955-123">The sender receives a SOAP fault if the message is too large for the receiver.</span></span> <span data-ttu-id="51955-124">メッセージは受信者によってドロップされ、トレース ログにこのイベントのエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="51955-124">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="51955-125">既定値は 65,536 バイトです。</span><span class="sxs-lookup"><span data-stu-id="51955-125">The default is 65,536 bytes.</span></span>|  
|`maxRetransmitCount`|<span data-ttu-id="51955-126">再送信メッセージの最大数を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="51955-126">An integer value that specifies the maximum number of retransmit messages.</span></span>|  
|`multicastInterfaceId`|<span data-ttu-id="51955-127">マルチキャストのインターフェイス ID を指定する整数値。</span><span class="sxs-lookup"><span data-stu-id="51955-127">An integer value that specifies the multicast interface ID.</span></span>|  
|`name`|<span data-ttu-id="51955-128">バインディングの構成名を格納する文字列です。</span><span class="sxs-lookup"><span data-stu-id="51955-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="51955-129">この値は、バインディングの ID として使用されるため、一意にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51955-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="51955-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="51955-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="51955-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="51955-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="51955-132">実行中の操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="51955-132">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="51955-133">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51955-133">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51955-134">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="51955-134">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="51955-135">受信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="51955-135">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="51955-136">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51955-136">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51955-137">既定値は 00:10:00 です。</span><span class="sxs-lookup"><span data-stu-id="51955-137">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="51955-138">送信操作が完了するまでの時間間隔を指定する <xref:System.TimeSpan> 値です。</span><span class="sxs-lookup"><span data-stu-id="51955-138">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="51955-139">この値は必ず <xref:System.TimeSpan.Zero> 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="51955-139">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="51955-140">既定値は 00:01:00 です。</span><span class="sxs-lookup"><span data-stu-id="51955-140">The default is 00:01:00.</span></span>|  
|`textEncoding`|<span data-ttu-id="51955-141">バインディングでメッセージの発行に使用される文字セット エンコーディングを設定します。</span><span class="sxs-lookup"><span data-stu-id="51955-141">Sets the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="51955-142">以下の値が有効です。</span><span class="sxs-lookup"><span data-stu-id="51955-142">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="51955-143">-   BigEndianUnicode: Unicode BigEndian encoding.</span><span class="sxs-lookup"><span data-stu-id="51955-143">-   BigEndianUnicode: Unicode BigEndian encoding.</span></span><br /><span data-ttu-id="51955-144">-   Unicode: 16-bit encoding.</span><span class="sxs-lookup"><span data-stu-id="51955-144">-   Unicode: 16-bit encoding.</span></span><br /><span data-ttu-id="51955-145">-   UTF8: 8-bit encoding</span><span class="sxs-lookup"><span data-stu-id="51955-145">-   UTF8: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="51955-146">既定値は UTF8 です。</span><span class="sxs-lookup"><span data-stu-id="51955-146">The default is UTF8.</span></span> <span data-ttu-id="51955-147">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="51955-147">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
|`timeToLive`|<span data-ttu-id="51955-148">バインディングに対する有効期間を指定する期間値。</span><span class="sxs-lookup"><span data-stu-id="51955-148">A timespan value that specifies the time to live for the binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51955-149">子要素</span><span class="sxs-lookup"><span data-stu-id="51955-149">Child Elements</span></span>  
  
|<span data-ttu-id="51955-150">要素</span><span class="sxs-lookup"><span data-stu-id="51955-150">Element</span></span>|<span data-ttu-id="51955-151">説明</span><span class="sxs-lookup"><span data-stu-id="51955-151">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51955-152">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="51955-152">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="51955-153">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="51955-153">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="51955-154">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="51955-154">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="51955-155">親要素</span><span class="sxs-lookup"><span data-stu-id="51955-155">Parent Elements</span></span>  
  
|<span data-ttu-id="51955-156">要素</span><span class="sxs-lookup"><span data-stu-id="51955-156">Element</span></span>|<span data-ttu-id="51955-157">説明</span><span class="sxs-lookup"><span data-stu-id="51955-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51955-158">\<bindings></span><span class="sxs-lookup"><span data-stu-id="51955-158">\<bindings></span></span>](bindings.md)|<span data-ttu-id="51955-159">この要素には、標準バインディングおよびカスタム バインドのコレクションが保持されます。</span><span class="sxs-lookup"><span data-stu-id="51955-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51955-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="51955-160">Remarks</span></span>  
 <span data-ttu-id="51955-161">UdpBinding により、WCF サービスが UDP トランスポートを介して通信することができます。</span><span class="sxs-lookup"><span data-stu-id="51955-161">The UdpBinding allows WCF services to communicate over the UDP transport.</span></span> <span data-ttu-id="51955-162">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span><span class="sxs-lookup"><span data-stu-id="51955-162">It allows for "fire and forget" message exchanges where a client sends a message to a service and expects no response back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51955-163">例</span><span class="sxs-lookup"><span data-stu-id="51955-163">Example</span></span>  
 <span data-ttu-id="51955-164">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span><span class="sxs-lookup"><span data-stu-id="51955-164">The following example shows how to configure the <xref:System.ServiceModel.UdpBinding> using the <`udpBinding`> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51955-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="51955-165">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="51955-166">バインディング</span><span class="sxs-lookup"><span data-stu-id="51955-166">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="51955-167">システムが提供するバインディングの構成</span><span class="sxs-lookup"><span data-stu-id="51955-167">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="51955-168">サービスとクライアントを構成するためのバインディングの使用</span><span class="sxs-lookup"><span data-stu-id="51955-168">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="51955-169">\<binding></span><span class="sxs-lookup"><span data-stu-id="51955-169">\<binding></span></span>](bindings.md)
