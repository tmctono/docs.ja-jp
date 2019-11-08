---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: bd38bf812e6d8d9e57d99bf1a5b77ebb776193a5
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738845"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="9e91a-101">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="9e91a-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="9e91a-102">SOAP Message Transmission Optimization Mechanism (MTOM) ベースのメッセージに使用されるエンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
<span data-ttu-id="9e91a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e91a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e91a-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="9e91a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9e91a-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9e91a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9e91a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="9e91a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="9e91a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="9e91a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9e91a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**mtomMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="9e91a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mtomMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e91a-109">構文</span><span class="sxs-lookup"><span data-stu-id="9e91a-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e91a-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="9e91a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9e91a-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e91a-112">属性</span><span class="sxs-lookup"><span data-stu-id="9e91a-112">Attributes</span></span>  
  
|<span data-ttu-id="9e91a-113">属性</span><span class="sxs-lookup"><span data-stu-id="9e91a-113">Attribute</span></span>|<span data-ttu-id="9e91a-114">説明</span><span class="sxs-lookup"><span data-stu-id="9e91a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e91a-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="9e91a-115">maxBufferSize</span></span>|<span data-ttu-id="9e91a-116">使用できるバッファーの最大サイズを指定する整数。</span><span class="sxs-lookup"><span data-stu-id="9e91a-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="9e91a-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="9e91a-117">maxReadPoolSize</span></span>|<span data-ttu-id="9e91a-118">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="9e91a-119">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="9e91a-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="9e91a-120">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-120">The default is 64.</span></span>|  
|<span data-ttu-id="9e91a-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="9e91a-121">maxWritePoolSize</span></span>|<span data-ttu-id="9e91a-122">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="9e91a-123">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="9e91a-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="9e91a-124">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-124">The default is 16.</span></span>|  
|<span data-ttu-id="9e91a-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="9e91a-125">messageVersion</span></span>|<span data-ttu-id="9e91a-126">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="9e91a-127">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e91a-127">Valid values are</span></span><br /><br /> <span data-ttu-id="9e91a-128">- Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="9e91a-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="9e91a-129">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="9e91a-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="9e91a-130">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="9e91a-131">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="9e91a-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="9e91a-132">writeEncoding</span></span>|<span data-ttu-id="9e91a-133">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="9e91a-134">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9e91a-134">Valid values are</span></span><br /><br /> <span data-ttu-id="9e91a-135">-UnicodeFffeTextEncoding: Unicode BigEndian エンコード</span><span class="sxs-lookup"><span data-stu-id="9e91a-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="9e91a-136">-Utf16TextEncoding: Unicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="9e91a-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="9e91a-137">-Utf8TextEncoding: 8 ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="9e91a-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="9e91a-138">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="9e91a-139">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e91a-140">子要素</span><span class="sxs-lookup"><span data-stu-id="9e91a-140">Child Elements</span></span>  
  
|<span data-ttu-id="9e91a-141">要素</span><span class="sxs-lookup"><span data-stu-id="9e91a-141">Element</span></span>|<span data-ttu-id="9e91a-142">説明</span><span class="sxs-lookup"><span data-stu-id="9e91a-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9e91a-143">[readerQuotas > の \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9e91a-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="9e91a-144">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="9e91a-145">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="9e91a-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e91a-146">親要素</span><span class="sxs-lookup"><span data-stu-id="9e91a-146">Parent Elements</span></span>  
  
|<span data-ttu-id="9e91a-147">要素</span><span class="sxs-lookup"><span data-stu-id="9e91a-147">Element</span></span>|<span data-ttu-id="9e91a-148">説明</span><span class="sxs-lookup"><span data-stu-id="9e91a-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e91a-149">\<binding ></span><span class="sxs-lookup"><span data-stu-id="9e91a-149">\<binding></span></span>](bindings.md)|<span data-ttu-id="9e91a-150">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e91a-151">Remarks</span><span class="sxs-lookup"><span data-stu-id="9e91a-151">Remarks</span></span>  
 <span data-ttu-id="9e91a-152">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="9e91a-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="9e91a-153">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="9e91a-153">Decoding is the reverse process.</span></span> <span data-ttu-id="9e91a-154">WCF (Windows Communication Foundation) には、SOAP メッセージのエンコードとして、テキスト、バイナリ、および MTOM (Message Transmission Optimization Mechanism) の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="9e91a-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="9e91a-155">`MtomMessageEncoding` 要素は、MTOM (Message Transmission Optimization Mechanism) エンコーディングを使用するメッセージの文字エンコーディング、メッセージのバージョン管理、およびその他の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="9e91a-156">MTOM は、WCF メッセージでバイナリ データを転送するための効率的なテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="9e91a-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="9e91a-157">MTOM エンコーダーは、効率と相互運用性のバランスをとろうとします。</span><span class="sxs-lookup"><span data-stu-id="9e91a-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="9e91a-158">MTOM エンコーディングは、ほとんどの XML をテキスト形式で転送しますが、大きいサイズのバイナリ データ ブロックは、base64 でエンコードされた形式に変換せずに、そのまま転送することによって最適化します。</span><span class="sxs-lookup"><span data-stu-id="9e91a-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e91a-159">例</span><span class="sxs-lookup"><span data-stu-id="9e91a-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="9e91a-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e91a-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="9e91a-161">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="9e91a-161">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="9e91a-162">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="9e91a-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="9e91a-163">バインディング</span><span class="sxs-lookup"><span data-stu-id="9e91a-163">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9e91a-164">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="9e91a-164">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9e91a-165">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="9e91a-165">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9e91a-166">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="9e91a-166">\<customBinding></span></span>](custombinding.md)
