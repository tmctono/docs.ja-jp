---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 1b72b73f0d9d312fd54ea6a5517d55bf251c0e05
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201474"
---
# \<binaryMessageEncoding>

<span data-ttu-id="1421f-101">ネットワーク上で Windows Communication Foundation (WCF) メッセージをバイナリにエンコードするバイナリ メッセージ エンコーダーを定義します。</span><span class="sxs-lookup"><span data-stu-id="1421f-101">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binaryMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="1421f-102">構文</span><span class="sxs-lookup"><span data-stu-id="1421f-102">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1421f-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="1421f-103">Attributes and Elements</span></span>  

 <span data-ttu-id="1421f-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="1421f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1421f-105">属性</span><span class="sxs-lookup"><span data-stu-id="1421f-105">Attributes</span></span>  
  
|<span data-ttu-id="1421f-106">属性</span><span class="sxs-lookup"><span data-stu-id="1421f-106">Attribute</span></span>|<span data-ttu-id="1421f-107">[説明]</span><span class="sxs-lookup"><span data-stu-id="1421f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1421f-108">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="1421f-108">maxReadPoolSize</span></span>|<span data-ttu-id="1421f-109">新しいリーダーを割り当てずに同時に読み取り可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="1421f-109">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="1421f-110">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="1421f-110">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1421f-111">既定値は、64 です。</span><span class="sxs-lookup"><span data-stu-id="1421f-111">The default is 64.</span></span>|  
|<span data-ttu-id="1421f-112">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="1421f-112">maxSessionSize</span></span>|<span data-ttu-id="1421f-113">エンコーディングに使用されるバッファーのサイズをバイト単位で設定する正の整数。</span><span class="sxs-lookup"><span data-stu-id="1421f-113">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="1421f-114">バッファーが大きくなると、作業セットのサイズの増加時に、エンコーディングの速度が高まります。</span><span class="sxs-lookup"><span data-stu-id="1421f-114">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="1421f-115">既定値は 2048 です。</span><span class="sxs-lookup"><span data-stu-id="1421f-115">The default is 2048.</span></span>|  
|<span data-ttu-id="1421f-116">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="1421f-116">maxWritePoolSize</span></span>|<span data-ttu-id="1421f-117">新しいライターを割り当てずに同時に送信可能なメッセージの数を定義する整数です。</span><span class="sxs-lookup"><span data-stu-id="1421f-117">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="1421f-118">プール サイズを大きくすると、システムでは、比較的大きい作業セットで、アクティビティの急増に対する許容度が高まります。</span><span class="sxs-lookup"><span data-stu-id="1421f-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="1421f-119">既定値は 16 です。</span><span class="sxs-lookup"><span data-stu-id="1421f-119">The default is 16.</span></span>|  
|<span data-ttu-id="1421f-120">messageVersion</span><span class="sxs-lookup"><span data-stu-id="1421f-120">messageVersion</span></span>|<span data-ttu-id="1421f-121">使用または予想される SOAP メッセージおよび WS-Addressing のバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="1421f-121">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1421f-122">子要素</span><span class="sxs-lookup"><span data-stu-id="1421f-122">Child Elements</span></span>  
  
|<span data-ttu-id="1421f-123">要素</span><span class="sxs-lookup"><span data-stu-id="1421f-123">Element</span></span>|<span data-ttu-id="1421f-124">説明</span><span class="sxs-lookup"><span data-stu-id="1421f-124">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="1421f-125">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="1421f-125">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="1421f-126">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="1421f-126">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1421f-127">親要素</span><span class="sxs-lookup"><span data-stu-id="1421f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1421f-128">要素</span><span class="sxs-lookup"><span data-stu-id="1421f-128">Element</span></span>|<span data-ttu-id="1421f-129">説明</span><span class="sxs-lookup"><span data-stu-id="1421f-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="1421f-130">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="1421f-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1421f-131">解説</span><span class="sxs-lookup"><span data-stu-id="1421f-131">Remarks</span></span>  

 <span data-ttu-id="1421f-132">エンコーディングは、メッセージをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1421f-132">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="1421f-133">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="1421f-133">Decoding is the reverse process.</span></span> <span data-ttu-id="1421f-134">WCF (Windows Communication Foundation) には、SOAP メッセージのエンコードとして、テキスト、バイナリ、および MTOM (Message Transmission Optimization Mechanism) の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="1421f-134">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="1421f-135">`binaryMessageEncoding` 要素は、XML 用の .NET バイナリ形式を指定します。この要素には、使用する文字エンコーディング、SOAP バージョン、および WS-Addressing バージョンを指定するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1421f-135">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="1421f-136">バイナリ メッセージ エンコーダーは、ネットワーク上で Windows Communication Foundation (WCF) メッセージをバイナリにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="1421f-136">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="1421f-137">このエンコーディングによりメッセージ転送は非常に高速になりますが、WS-\* 標準に基づいた相互運用性は失われます。</span><span class="sxs-lookup"><span data-stu-id="1421f-137">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1421f-138">例</span><span class="sxs-lookup"><span data-stu-id="1421f-138">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="1421f-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="1421f-139">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="1421f-140">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="1421f-140">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="1421f-141">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="1421f-141">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="1421f-142">バインド</span><span class="sxs-lookup"><span data-stu-id="1421f-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1421f-143">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="1421f-143">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1421f-144">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="1421f-144">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
