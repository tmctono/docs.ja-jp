---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 159c581955336575af87a66a796cb78dd35d09c7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158657"
---
# \<textMessageEncoding>

<span data-ttu-id="e5e1f-101">テキストベースの XML メッセージに使用される文字エンコーディングおよびメッセージ バージョン管理を指定します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-101">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="e5e1f-102">構文</span><span class="sxs-lookup"><span data-stu-id="e5e1f-102">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5e1f-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="e5e1f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="e5e1f-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5e1f-105">属性</span><span class="sxs-lookup"><span data-stu-id="e5e1f-105">Attributes</span></span>  
  
|<span data-ttu-id="e5e1f-106">属性</span><span class="sxs-lookup"><span data-stu-id="e5e1f-106">Attribute</span></span>|<span data-ttu-id="e5e1f-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="e5e1f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5e1f-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e5e1f-108">maxReadPoolSize</span></span>|<span data-ttu-id="e5e1f-109">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-109">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e5e1f-110">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e5e1f-111">既定値は、64 です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-111">The default is 64.</span></span>|  
|<span data-ttu-id="e5e1f-112">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e5e1f-112">maxWritePoolSize</span></span>|<span data-ttu-id="e5e1f-113">新しいライターを割り当てずに同時に送信可能なメッセージの数を指定する整数です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-113">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e5e1f-114">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-114">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e5e1f-115">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-115">The default is 16.</span></span>|  
|<span data-ttu-id="e5e1f-116">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e5e1f-116">messageVersion</span></span>|<span data-ttu-id="e5e1f-117">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-117">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="e5e1f-118">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-118">Valid values are</span></span><br /><br /> <span data-ttu-id="e5e1f-119">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="e5e1f-119">-   Soap11Addressing10</span></span><br /><span data-ttu-id="e5e1f-120">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="e5e1f-120">-   Soap12Addressing10</span></span><br /><span data-ttu-id="e5e1f-121">- Soap11</span><span class="sxs-lookup"><span data-stu-id="e5e1f-121">-   Soap11</span></span><br /><span data-ttu-id="e5e1f-122">- Soap12</span><span class="sxs-lookup"><span data-stu-id="e5e1f-122">-  Soap12</span></span><br /><br /><span data-ttu-id="e5e1f-123">既定値は Soap12Addressing10 です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-123">The default is Soap12Addressing10.</span></span> <span data-ttu-id="e5e1f-124">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-124">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="e5e1f-125">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="e5e1f-125">writeEncoding</span></span>|<span data-ttu-id="e5e1f-126">バインドでメッセージの発行に使用される文字セット エンコーディングを指定します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-126">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="e5e1f-127">有効な値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-127">Valid values are</span></span><br /><br /> <span data-ttu-id="e5e1f-128">-UnicodeFffeTextEncoding: Unicode BigEndian エンコード</span><span class="sxs-lookup"><span data-stu-id="e5e1f-128">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="e5e1f-129">-Utf16TextEncoding: Unicode エンコーディング</span><span class="sxs-lookup"><span data-stu-id="e5e1f-129">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="e5e1f-130">-Utf8TextEncoding: 8 ビットエンコード</span><span class="sxs-lookup"><span data-stu-id="e5e1f-130">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="e5e1f-131">既定値は Utf8TextEncoding です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-131">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="e5e1f-132">この属性は <xref:System.Text.Encoding> 型です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-132">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5e1f-133">子要素</span><span class="sxs-lookup"><span data-stu-id="e5e1f-133">Child Elements</span></span>  
  
|<span data-ttu-id="e5e1f-134">要素</span><span class="sxs-lookup"><span data-stu-id="e5e1f-134">Element</span></span>|<span data-ttu-id="e5e1f-135">説明</span><span class="sxs-lookup"><span data-stu-id="e5e1f-135">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="e5e1f-136">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-136">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e5e1f-137">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-137">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5e1f-138">親要素</span><span class="sxs-lookup"><span data-stu-id="e5e1f-138">Parent Elements</span></span>  
  
|<span data-ttu-id="e5e1f-139">要素</span><span class="sxs-lookup"><span data-stu-id="e5e1f-139">Element</span></span>|<span data-ttu-id="e5e1f-140">説明</span><span class="sxs-lookup"><span data-stu-id="e5e1f-140">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="e5e1f-141">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-141">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5e1f-142">解説</span><span class="sxs-lookup"><span data-stu-id="e5e1f-142">Remarks</span></span>  

 <span data-ttu-id="e5e1f-143">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-143">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e5e1f-144">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-144">Decoding is the reverse process.</span></span> <span data-ttu-id="e5e1f-145">WCF (Windows Communication Foundation) には、SOAP メッセージのエンコードとして、テキスト、バイナリ、および MTOM (Message Transmission Optimization Mechanism) の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-145">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e5e1f-146">`textMessageEncoding` 要素で表されるテキスト エンコーディングでは相互運用性が最も高くなりますが、XML メッセージのエンコーダーとしての効率は最も低くなります。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-146">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="e5e1f-147">テキスト エンコーダーは、ネットワーク上でテキストベースのメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-147">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="e5e1f-148">このエンコーダーにより生成されるメッセージは、WS-\* ベースの相互運用に適しています。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-148">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="e5e1f-149">Web サービスまたは Web サービス クライアントは、一般に、テキスト形式の XML を認識できます。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-149">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="e5e1f-150">しかし、大きいブロックのバイナリ データをテキストとして転送するのは、XML メッセージをエンコードする上では、最も非効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="e5e1f-150">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5e1f-151">例</span><span class="sxs-lookup"><span data-stu-id="e5e1f-151">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="e5e1f-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5e1f-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="e5e1f-153">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="e5e1f-153">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="e5e1f-154">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="e5e1f-154">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="e5e1f-155">バインド</span><span class="sxs-lookup"><span data-stu-id="e5e1f-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e5e1f-156">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="e5e1f-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e5e1f-157">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="e5e1f-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
