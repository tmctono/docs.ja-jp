---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 1494cee0e412bebc6637ad73354f7c91dc636e15
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399429"
---
# <a name="textmessageencoding"></a><span data-ttu-id="cffe5-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cffe5-101">\<textMessageEncoding></span></span>
<span data-ttu-id="cffe5-102">テキストベースの XML メッセージに使用される文字エンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
<span data-ttu-id="cffe5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cffe5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cffe5-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="cffe5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="cffe5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cffe5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="cffe5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="cffe5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="cffe5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="cffe5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="cffe5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<textMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="cffe5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffe5-109">構文</span><span class="sxs-lookup"><span data-stu-id="cffe5-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cffe5-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cffe5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cffe5-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cffe5-112">属性</span><span class="sxs-lookup"><span data-stu-id="cffe5-112">Attributes</span></span>  
  
|<span data-ttu-id="cffe5-113">属性</span><span class="sxs-lookup"><span data-stu-id="cffe5-113">Attribute</span></span>|<span data-ttu-id="cffe5-114">説明</span><span class="sxs-lookup"><span data-stu-id="cffe5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cffe5-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="cffe5-115">maxReadPoolSize</span></span>|<span data-ttu-id="cffe5-116">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="cffe5-117">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="cffe5-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cffe5-118">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-118">The default is 64.</span></span>|  
|<span data-ttu-id="cffe5-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="cffe5-119">maxWritePoolSize</span></span>|<span data-ttu-id="cffe5-120">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="cffe5-121">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="cffe5-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cffe5-122">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-122">The default is 16.</span></span>|  
|<span data-ttu-id="cffe5-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="cffe5-123">messageVersion</span></span>|<span data-ttu-id="cffe5-124">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="cffe5-125">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cffe5-125">Valid values are</span></span><br /><br /> <span data-ttu-id="cffe5-126">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="cffe5-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="cffe5-127">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="cffe5-127">-   Soap12Addressing10</span></span><br /><span data-ttu-id="cffe5-128">- Soap11</span><span class="sxs-lookup"><span data-stu-id="cffe5-128">-   Soap11</span></span><br /><span data-ttu-id="cffe5-129">- Soap12</span><span class="sxs-lookup"><span data-stu-id="cffe5-129">-  Soap12</span></span><br /><br /><span data-ttu-id="cffe5-130">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="cffe5-131">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="cffe5-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="cffe5-132">writeEncoding</span></span>|<span data-ttu-id="cffe5-133">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="cffe5-134">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cffe5-134">Valid values are</span></span><br /><br /> <span data-ttu-id="cffe5-135">UnicodeFffeTextEncodingUnicode BigEndian エンコーディング</span><span class="sxs-lookup"><span data-stu-id="cffe5-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="cffe5-136">Utf16TextEncodingUnicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="cffe5-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="cffe5-137">Utf8TextEncoding8ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="cffe5-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="cffe5-138">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="cffe5-139">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cffe5-140">子要素</span><span class="sxs-lookup"><span data-stu-id="cffe5-140">Child Elements</span></span>  
  
|<span data-ttu-id="cffe5-141">要素</span><span class="sxs-lookup"><span data-stu-id="cffe5-141">Element</span></span>|<span data-ttu-id="cffe5-142">説明</span><span class="sxs-lookup"><span data-stu-id="cffe5-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cffe5-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cffe5-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="cffe5-144">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cffe5-145">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cffe5-146">親要素</span><span class="sxs-lookup"><span data-stu-id="cffe5-146">Parent Elements</span></span>  
  
|<span data-ttu-id="cffe5-147">要素</span><span class="sxs-lookup"><span data-stu-id="cffe5-147">Element</span></span>|<span data-ttu-id="cffe5-148">説明</span><span class="sxs-lookup"><span data-stu-id="cffe5-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cffe5-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="cffe5-149">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="cffe5-150">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cffe5-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="cffe5-151">Remarks</span></span>  
 <span data-ttu-id="cffe5-152">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="cffe5-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="cffe5-153">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="cffe5-153">Decoding is the reverse process.</span></span> <span data-ttu-id="cffe5-154">Windows Communication Foundation (WCF) には、SOAP メッセージの3種類のエンコードが含まれています。テキスト、バイナリ、およびメッセージ転送の最適化メカニズム (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="cffe5-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="cffe5-155">`textMessageEncoding` 要素で表されるテキスト エンコーディングでは相互運用性が最も高くなりますが、XML メッセージのエンコーダーとしての効率は最も低くなります。</span><span class="sxs-lookup"><span data-stu-id="cffe5-155">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="cffe5-156">テキスト エンコーダーは、ネットワーク上でテキストベースのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="cffe5-156">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="cffe5-157">このエンコーダーにより生成されるメッセージは、WS-\* ベースの相互運用に適しています。</span><span class="sxs-lookup"><span data-stu-id="cffe5-157">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="cffe5-158">Web サービスまたは Web サービス クライアントは、一般に、テキスト形式の XML を認識できます。</span><span class="sxs-lookup"><span data-stu-id="cffe5-158">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="cffe5-159">しかし、大きいブロックのバイナリ データをテキストとして転送するのは、XML メッセージをエンコードする上では、最も非効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="cffe5-159">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cffe5-160">例</span><span class="sxs-lookup"><span data-stu-id="cffe5-160">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="cffe5-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="cffe5-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="cffe5-162">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="cffe5-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="cffe5-163">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="cffe5-163">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="cffe5-164">バインディング</span><span class="sxs-lookup"><span data-stu-id="cffe5-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cffe5-165">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="cffe5-165">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cffe5-166">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="cffe5-166">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cffe5-167">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cffe5-167">\<customBinding></span></span>](custombinding.md)
