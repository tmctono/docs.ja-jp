---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: e02ed6ef79fcf52bbe9c33bd9b36a14113e19d1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673447"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="27ff0-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="27ff0-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="27ff0-102">ネットワーク上で Windows Communication Foundation (WCF) メッセージをバイナリにエンコードするバイナリ メッセージ エンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="27ff0-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="27ff0-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="27ff0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="27ff0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="27ff0-104">\<bindings></span></span>  
<span data-ttu-id="27ff0-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="27ff0-105">\<customBinding></span></span>  
<span data-ttu-id="27ff0-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="27ff0-106">\<binding></span></span>  
<span data-ttu-id="27ff0-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="27ff0-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27ff0-108">構文</span><span class="sxs-lookup"><span data-stu-id="27ff0-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27ff0-109">属性および要素</span><span class="sxs-lookup"><span data-stu-id="27ff0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="27ff0-110">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="27ff0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27ff0-111">属性</span><span class="sxs-lookup"><span data-stu-id="27ff0-111">Attributes</span></span>  
  
|<span data-ttu-id="27ff0-112">属性</span><span class="sxs-lookup"><span data-stu-id="27ff0-112">Attribute</span></span>|<span data-ttu-id="27ff0-113">説明</span><span class="sxs-lookup"><span data-stu-id="27ff0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27ff0-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="27ff0-114">maxReadPoolSize</span></span>|<span data-ttu-id="27ff0-115">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="27ff0-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="27ff0-116">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="27ff0-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="27ff0-117">既定値は 64 です。</span><span class="sxs-lookup"><span data-stu-id="27ff0-117">The default is 64.</span></span>|  
|<span data-ttu-id="27ff0-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="27ff0-118">maxSessionSize</span></span>|<span data-ttu-id="27ff0-119">エンコーディングに使用されるバッファーのサイズをバイト単位で設定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="27ff0-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="27ff0-120">バッファーが大きくなると、作業セットのサイズの増加時に、エンコーディングの速度が高まります。</span><span class="sxs-lookup"><span data-stu-id="27ff0-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="27ff0-121">既定値は 2048 です。</span><span class="sxs-lookup"><span data-stu-id="27ff0-121">The default is 2048.</span></span>|  
|<span data-ttu-id="27ff0-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="27ff0-122">maxWritePoolSize</span></span>|<span data-ttu-id="27ff0-123">新しいライターを割り当てずに同時に送信可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="27ff0-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="27ff0-124">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="27ff0-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="27ff0-125">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="27ff0-125">The default is 16.</span></span>|  
|<span data-ttu-id="27ff0-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="27ff0-126">messageVersion</span></span>|<span data-ttu-id="27ff0-127">使用または予想される SOAP メッセージおよび WS-Addressing のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="27ff0-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27ff0-128">子要素</span><span class="sxs-lookup"><span data-stu-id="27ff0-128">Child Elements</span></span>  
  
|<span data-ttu-id="27ff0-129">要素</span><span class="sxs-lookup"><span data-stu-id="27ff0-129">Element</span></span>|<span data-ttu-id="27ff0-130">説明</span><span class="sxs-lookup"><span data-stu-id="27ff0-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27ff0-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="27ff0-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="27ff0-132">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="27ff0-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="27ff0-133">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="27ff0-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27ff0-134">親要素</span><span class="sxs-lookup"><span data-stu-id="27ff0-134">Parent Elements</span></span>  
  
|<span data-ttu-id="27ff0-135">要素</span><span class="sxs-lookup"><span data-stu-id="27ff0-135">Element</span></span>|<span data-ttu-id="27ff0-136">説明</span><span class="sxs-lookup"><span data-stu-id="27ff0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27ff0-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="27ff0-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="27ff0-138">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="27ff0-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27ff0-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="27ff0-139">Remarks</span></span>  
 <span data-ttu-id="27ff0-140">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="27ff0-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="27ff0-141">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="27ff0-141">Decoding is the reverse process.</span></span> <span data-ttu-id="27ff0-142">Windows Communication Foundation (WCF) には、SOAP メッセージのエンコードの 3 つの種類が含まれます。テキスト、バイナリ、および Message Transmission Optimization Mechanism (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="27ff0-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="27ff0-143">`binaryMessageEncoding` 要素は、XML 用の .NET バイナリ形式を指定します。この要素には、使用する文字エンコーディング、SOAP バージョン、および WS-Addressing バージョンを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="27ff0-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="27ff0-144">バイナリ メッセージ エンコーダーは、ネットワーク上で Windows Communication Foundation (WCF) メッセージをバイナリにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="27ff0-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="27ff0-145">このエンコーディングによりメッセージ転送は非常に高速になりますが、WS-\* 標準に基づいた相互運用性は失われます。</span><span class="sxs-lookup"><span data-stu-id="27ff0-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27ff0-146">例</span><span class="sxs-lookup"><span data-stu-id="27ff0-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="27ff0-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="27ff0-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="27ff0-148">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="27ff0-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="27ff0-149">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="27ff0-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="27ff0-150">バインディング</span><span class="sxs-lookup"><span data-stu-id="27ff0-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="27ff0-151">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="27ff0-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="27ff0-152">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="27ff0-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="27ff0-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="27ff0-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
