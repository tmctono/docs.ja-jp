---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 61b23957c56bad81598dd65b0dd68f7b44d329e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59146797"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="35e6a-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="35e6a-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="35e6a-102">SOAP Message Transmission Optimization Mechanism (MTOM) ベースのメッセージに使用されるエンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="35e6a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="35e6a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="35e6a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="35e6a-104">\<bindings></span></span>  
<span data-ttu-id="35e6a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="35e6a-105">\<customBinding></span></span>  
<span data-ttu-id="35e6a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="35e6a-106">\<binding></span></span>  
<span data-ttu-id="35e6a-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="35e6a-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35e6a-108">構文</span><span class="sxs-lookup"><span data-stu-id="35e6a-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35e6a-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="35e6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="35e6a-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35e6a-111">属性</span><span class="sxs-lookup"><span data-stu-id="35e6a-111">Attributes</span></span>  
  
|<span data-ttu-id="35e6a-112">属性</span><span class="sxs-lookup"><span data-stu-id="35e6a-112">Attribute</span></span>|<span data-ttu-id="35e6a-113">説明</span><span class="sxs-lookup"><span data-stu-id="35e6a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="35e6a-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="35e6a-114">maxBufferSize</span></span>|<span data-ttu-id="35e6a-115">使用できるバッファーの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="35e6a-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="35e6a-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="35e6a-116">maxReadPoolSize</span></span>|<span data-ttu-id="35e6a-117">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="35e6a-118">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="35e6a-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="35e6a-119">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-119">The default is 64.</span></span>|  
|<span data-ttu-id="35e6a-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="35e6a-120">maxWritePoolSize</span></span>|<span data-ttu-id="35e6a-121">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="35e6a-122">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="35e6a-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="35e6a-123">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-123">The default is 16.</span></span>|  
|<span data-ttu-id="35e6a-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="35e6a-124">messageVersion</span></span>|<span data-ttu-id="35e6a-125">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="35e6a-126">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35e6a-126">Valid values are</span></span><br /><br /> <span data-ttu-id="35e6a-127">-Soap11addressing1 です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="35e6a-128">-Soap12addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="35e6a-129">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="35e6a-130">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="35e6a-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="35e6a-131">writeEncoding</span></span>|<span data-ttu-id="35e6a-132">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="35e6a-133">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="35e6a-133">Valid values are</span></span><br /><br /> <span data-ttu-id="35e6a-134">-   UnicodeFffeTextEncoding:Unicode BigEndian エンコーディング</span><span class="sxs-lookup"><span data-stu-id="35e6a-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="35e6a-135">-   Utf16TextEncoding:Unicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="35e6a-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="35e6a-136">-   Utf8TextEncoding:8 ビット エンコード</span><span class="sxs-lookup"><span data-stu-id="35e6a-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="35e6a-137">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="35e6a-138">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35e6a-139">子要素</span><span class="sxs-lookup"><span data-stu-id="35e6a-139">Child Elements</span></span>  
  
|<span data-ttu-id="35e6a-140">要素</span><span class="sxs-lookup"><span data-stu-id="35e6a-140">Element</span></span>|<span data-ttu-id="35e6a-141">説明</span><span class="sxs-lookup"><span data-stu-id="35e6a-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="35e6a-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="35e6a-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="35e6a-143">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="35e6a-144">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="35e6a-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35e6a-145">親要素</span><span class="sxs-lookup"><span data-stu-id="35e6a-145">Parent Elements</span></span>  
  
|<span data-ttu-id="35e6a-146">要素</span><span class="sxs-lookup"><span data-stu-id="35e6a-146">Element</span></span>|<span data-ttu-id="35e6a-147">説明</span><span class="sxs-lookup"><span data-stu-id="35e6a-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35e6a-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="35e6a-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="35e6a-149">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35e6a-150">Remarks</span><span class="sxs-lookup"><span data-stu-id="35e6a-150">Remarks</span></span>  
 <span data-ttu-id="35e6a-151">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="35e6a-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="35e6a-152">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="35e6a-152">Decoding is the reverse process.</span></span> <span data-ttu-id="35e6a-153">Windows Communication Foundation (WCF) には、SOAP メッセージのエンコードの 3 つの種類が含まれます。テキスト、バイナリ、および Message Transmission Optimization Mechanism (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="35e6a-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="35e6a-154">`MtomMessageEncoding` 要素は、MTOM (Message Transmission Optimization Mechanism) エンコーディングを使用するメッセージの文字エンコーディング、メッセージのバージョン管理、およびその他の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="35e6a-155">MTOM は、WCF メッセージでバイナリ データを転送するための効率的なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="35e6a-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="35e6a-156">MTOM エンコーダーは、効率と相互運用性のバランスをとろうとします。</span><span class="sxs-lookup"><span data-stu-id="35e6a-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="35e6a-157">MTOM エンコーディングは、ほとんどの XML をテキスト形式で転送しますが、大きいサイズのバイナリ データ ブロックは、base64 でエンコードされた形式に変換せずに、そのまま転送することによって最適化します。</span><span class="sxs-lookup"><span data-stu-id="35e6a-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35e6a-158">例</span><span class="sxs-lookup"><span data-stu-id="35e6a-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="35e6a-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="35e6a-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="35e6a-160">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="35e6a-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="35e6a-161">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="35e6a-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="35e6a-162">バインディング</span><span class="sxs-lookup"><span data-stu-id="35e6a-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="35e6a-163">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="35e6a-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="35e6a-164">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="35e6a-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="35e6a-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="35e6a-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
