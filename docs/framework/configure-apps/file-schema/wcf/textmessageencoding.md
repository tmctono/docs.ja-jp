---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e2fec2c2e5979b08ed0d832f636b3d0847b9a5dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915655"
---
# <a name="textmessageencoding"></a><span data-ttu-id="5013e-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="5013e-101">\<textMessageEncoding></span></span>
<span data-ttu-id="5013e-102">テキストベースの XML メッセージに使用される文字エンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="5013e-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="5013e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5013e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5013e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5013e-104">\<bindings></span></span>  
<span data-ttu-id="5013e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5013e-105">\<customBinding></span></span>  
<span data-ttu-id="5013e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5013e-106">\<binding></span></span>  
<span data-ttu-id="5013e-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="5013e-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5013e-108">構文</span><span class="sxs-lookup"><span data-stu-id="5013e-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5013e-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="5013e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5013e-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="5013e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5013e-111">属性</span><span class="sxs-lookup"><span data-stu-id="5013e-111">Attributes</span></span>  
  
|<span data-ttu-id="5013e-112">属性</span><span class="sxs-lookup"><span data-stu-id="5013e-112">Attribute</span></span>|<span data-ttu-id="5013e-113">説明</span><span class="sxs-lookup"><span data-stu-id="5013e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5013e-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="5013e-114">maxReadPoolSize</span></span>|<span data-ttu-id="5013e-115">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="5013e-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="5013e-116">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="5013e-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5013e-117">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="5013e-117">The default is 64.</span></span>|  
|<span data-ttu-id="5013e-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="5013e-118">maxWritePoolSize</span></span>|<span data-ttu-id="5013e-119">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="5013e-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="5013e-120">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="5013e-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5013e-121">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="5013e-121">The default is 16.</span></span>|  
|<span data-ttu-id="5013e-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="5013e-122">messageVersion</span></span>|<span data-ttu-id="5013e-123">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="5013e-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="5013e-124">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5013e-124">Valid values are</span></span><br /><br /> <span data-ttu-id="5013e-125">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="5013e-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="5013e-126">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="5013e-126">-   Soap12Addressing10</span></span><br /><span data-ttu-id="5013e-127">- Soap11</span><span class="sxs-lookup"><span data-stu-id="5013e-127">-   Soap11</span></span><br /><span data-ttu-id="5013e-128">- Soap12</span><span class="sxs-lookup"><span data-stu-id="5013e-128">-  Soap12</span></span><br /><br /><span data-ttu-id="5013e-129">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="5013e-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="5013e-130">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="5013e-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="5013e-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="5013e-131">writeEncoding</span></span>|<span data-ttu-id="5013e-132">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="5013e-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5013e-133">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5013e-133">Valid values are</span></span><br /><br /> <span data-ttu-id="5013e-134">UnicodeFffeTextEncodingUnicode BigEndian エンコーディング</span><span class="sxs-lookup"><span data-stu-id="5013e-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="5013e-135">Utf16TextEncodingUnicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="5013e-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="5013e-136">Utf8TextEncoding8ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="5013e-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="5013e-137">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="5013e-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="5013e-138">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="5013e-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5013e-139">子要素</span><span class="sxs-lookup"><span data-stu-id="5013e-139">Child Elements</span></span>  
  
|<span data-ttu-id="5013e-140">要素</span><span class="sxs-lookup"><span data-stu-id="5013e-140">Element</span></span>|<span data-ttu-id="5013e-141">説明</span><span class="sxs-lookup"><span data-stu-id="5013e-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5013e-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5013e-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="5013e-143">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="5013e-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5013e-144">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="5013e-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5013e-145">親要素</span><span class="sxs-lookup"><span data-stu-id="5013e-145">Parent Elements</span></span>  
  
|<span data-ttu-id="5013e-146">要素</span><span class="sxs-lookup"><span data-stu-id="5013e-146">Element</span></span>|<span data-ttu-id="5013e-147">説明</span><span class="sxs-lookup"><span data-stu-id="5013e-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5013e-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="5013e-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="5013e-149">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="5013e-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5013e-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="5013e-150">Remarks</span></span>  
 <span data-ttu-id="5013e-151">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="5013e-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="5013e-152">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="5013e-152">Decoding is the reverse process.</span></span> <span data-ttu-id="5013e-153">Windows Communication Foundation (WCF) には、SOAP メッセージの3種類のエンコードが含まれています。テキスト、バイナリ、およびメッセージ転送の最適化メカニズム (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="5013e-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="5013e-154">`textMessageEncoding` 要素で表されるテキスト エンコーディングでは相互運用性が最も高くなりますが、XML メッセージのエンコーダーとしての効率は最も低くなります。</span><span class="sxs-lookup"><span data-stu-id="5013e-154">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="5013e-155">テキスト エンコーダーは、ネットワーク上でテキストベースのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="5013e-155">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="5013e-156">このエンコーダーにより生成されるメッセージは、WS-\* ベースの相互運用に適しています。</span><span class="sxs-lookup"><span data-stu-id="5013e-156">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="5013e-157">Web サービスまたは Web サービス クライアントは、一般に、テキスト形式の XML を認識できます。</span><span class="sxs-lookup"><span data-stu-id="5013e-157">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="5013e-158">しかし、大きいブロックのバイナリ データをテキストとして転送するのは、XML メッセージをエンコードする上では、最も非効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="5013e-158">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5013e-159">例</span><span class="sxs-lookup"><span data-stu-id="5013e-159">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5013e-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="5013e-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="5013e-161">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="5013e-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="5013e-162">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="5013e-162">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="5013e-163">バインディング</span><span class="sxs-lookup"><span data-stu-id="5013e-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5013e-164">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="5013e-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5013e-165">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="5013e-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5013e-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5013e-166">\<customBinding></span></span>](custombinding.md)
