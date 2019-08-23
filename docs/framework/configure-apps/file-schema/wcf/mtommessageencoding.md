---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 70a124fda5bc0e52e1271716f7e2166b7717b49a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933198"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="a406c-101">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="a406c-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="a406c-102">SOAP Message Transmission Optimization Mechanism (MTOM) ベースのメッセージに使用されるエンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="a406c-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="a406c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a406c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a406c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a406c-104">\<bindings></span></span>  
<span data-ttu-id="a406c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a406c-105">\<customBinding></span></span>  
<span data-ttu-id="a406c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a406c-106">\<binding></span></span>  
<span data-ttu-id="a406c-107">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="a406c-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a406c-108">構文</span><span class="sxs-lookup"><span data-stu-id="a406c-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a406c-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="a406c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a406c-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="a406c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a406c-111">属性</span><span class="sxs-lookup"><span data-stu-id="a406c-111">Attributes</span></span>  
  
|<span data-ttu-id="a406c-112">属性</span><span class="sxs-lookup"><span data-stu-id="a406c-112">Attribute</span></span>|<span data-ttu-id="a406c-113">説明</span><span class="sxs-lookup"><span data-stu-id="a406c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a406c-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="a406c-114">maxBufferSize</span></span>|<span data-ttu-id="a406c-115">使用できるバッファーの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="a406c-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="a406c-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="a406c-116">maxReadPoolSize</span></span>|<span data-ttu-id="a406c-117">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="a406c-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="a406c-118">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="a406c-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="a406c-119">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="a406c-119">The default is 64.</span></span>|  
|<span data-ttu-id="a406c-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="a406c-120">maxWritePoolSize</span></span>|<span data-ttu-id="a406c-121">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="a406c-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="a406c-122">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="a406c-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="a406c-123">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="a406c-123">The default is 16.</span></span>|  
|<span data-ttu-id="a406c-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="a406c-124">messageVersion</span></span>|<span data-ttu-id="a406c-125">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="a406c-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="a406c-126">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a406c-126">Valid values are</span></span><br /><br /> <span data-ttu-id="a406c-127">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="a406c-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="a406c-128">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="a406c-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="a406c-129">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="a406c-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="a406c-130">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="a406c-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="a406c-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="a406c-131">writeEncoding</span></span>|<span data-ttu-id="a406c-132">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="a406c-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="a406c-133">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a406c-133">Valid values are</span></span><br /><br /> <span data-ttu-id="a406c-134">UnicodeFffeTextEncodingUnicode BigEndian エンコーディング</span><span class="sxs-lookup"><span data-stu-id="a406c-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="a406c-135">Utf16TextEncodingUnicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="a406c-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="a406c-136">Utf8TextEncoding8ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="a406c-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="a406c-137">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="a406c-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="a406c-138">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="a406c-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a406c-139">子要素</span><span class="sxs-lookup"><span data-stu-id="a406c-139">Child Elements</span></span>  
  
|<span data-ttu-id="a406c-140">要素</span><span class="sxs-lookup"><span data-stu-id="a406c-140">Element</span></span>|<span data-ttu-id="a406c-141">説明</span><span class="sxs-lookup"><span data-stu-id="a406c-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a406c-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a406c-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="a406c-143">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="a406c-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="a406c-144">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="a406c-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a406c-145">親要素</span><span class="sxs-lookup"><span data-stu-id="a406c-145">Parent Elements</span></span>  
  
|<span data-ttu-id="a406c-146">要素</span><span class="sxs-lookup"><span data-stu-id="a406c-146">Element</span></span>|<span data-ttu-id="a406c-147">説明</span><span class="sxs-lookup"><span data-stu-id="a406c-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a406c-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="a406c-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="a406c-149">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="a406c-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a406c-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="a406c-150">Remarks</span></span>  
 <span data-ttu-id="a406c-151">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a406c-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="a406c-152">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="a406c-152">Decoding is the reverse process.</span></span> <span data-ttu-id="a406c-153">Windows Communication Foundation (WCF) には、SOAP メッセージの3種類のエンコードが含まれています。テキスト、バイナリ、およびメッセージ転送の最適化メカニズム (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="a406c-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="a406c-154">`MtomMessageEncoding` 要素は、MTOM (Message Transmission Optimization Mechanism) エンコーディングを使用するメッセージの文字エンコーディング、メッセージのバージョン管理、およびその他の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="a406c-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="a406c-155">MTOM は、WCF メッセージでバイナリ データを転送するための効率的なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="a406c-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="a406c-156">MTOM エンコーダーは、効率と相互運用性のバランスをとろうとします。</span><span class="sxs-lookup"><span data-stu-id="a406c-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="a406c-157">MTOM エンコーディングは、ほとんどの XML をテキスト形式で転送しますが、大きいサイズのバイナリ データ ブロックは、base64 でエンコードされた形式に変換せずに、そのまま転送することによって最適化します。</span><span class="sxs-lookup"><span data-stu-id="a406c-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a406c-158">例</span><span class="sxs-lookup"><span data-stu-id="a406c-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="a406c-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="a406c-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="a406c-160">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="a406c-160">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="a406c-161">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="a406c-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="a406c-162">バインディング</span><span class="sxs-lookup"><span data-stu-id="a406c-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a406c-163">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="a406c-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a406c-164">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="a406c-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a406c-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a406c-165">\<customBinding></span></span>](custombinding.md)
