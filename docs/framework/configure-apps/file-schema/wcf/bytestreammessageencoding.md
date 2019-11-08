---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739068"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="f1a68-101">\<byteStreamMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="f1a68-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="f1a68-102">文字エンコーディングを指定するオプションを使用し、メッセージ エンコーディングをバイト ストリームとして指定します。</span><span class="sxs-lookup"><span data-stu-id="f1a68-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="f1a68-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f1a68-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f1a68-104">&nbsp; &nbsp;[ **\<system >** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="f1a68-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f1a68-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**バインド**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f1a68-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="f1a68-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="f1a68-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="f1a68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**バインド >** </span><span class="sxs-lookup"><span data-stu-id="f1a68-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f1a68-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**byteStreamMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="f1a68-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a68-109">構文</span><span class="sxs-lookup"><span data-stu-id="f1a68-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1a68-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="f1a68-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f1a68-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="f1a68-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1a68-112">属性</span><span class="sxs-lookup"><span data-stu-id="f1a68-112">Attributes</span></span>  
  
|<span data-ttu-id="f1a68-113">属性</span><span class="sxs-lookup"><span data-stu-id="f1a68-113">Attribute</span></span>|<span data-ttu-id="f1a68-114">説明</span><span class="sxs-lookup"><span data-stu-id="f1a68-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f1a68-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="f1a68-115">messageVersion</span></span>|<span data-ttu-id="f1a68-116">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="f1a68-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="f1a68-117">このプロパティは、<xref:System.ServiceModel.Channels.MessageVersion.None%2A> のメッセージ バージョン値にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="f1a68-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="f1a68-118">バイト ストリーム メッセージ エンコーダーは、他のメッセージ バージョンをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="f1a68-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="f1a68-119">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="f1a68-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f1a68-120">子要素</span><span class="sxs-lookup"><span data-stu-id="f1a68-120">Child Elements</span></span>  
  
|<span data-ttu-id="f1a68-121">要素</span><span class="sxs-lookup"><span data-stu-id="f1a68-121">Element</span></span>|<span data-ttu-id="f1a68-122">説明</span><span class="sxs-lookup"><span data-stu-id="f1a68-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1a68-123">[readerQuotas > の \<](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f1a68-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="f1a68-124">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="f1a68-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f1a68-125">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="f1a68-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1a68-126">親要素</span><span class="sxs-lookup"><span data-stu-id="f1a68-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f1a68-127">要素</span><span class="sxs-lookup"><span data-stu-id="f1a68-127">Element</span></span>|<span data-ttu-id="f1a68-128">説明</span><span class="sxs-lookup"><span data-stu-id="f1a68-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1a68-129">\<binding ></span><span class="sxs-lookup"><span data-stu-id="f1a68-129">\<binding></span></span>](bindings.md)|<span data-ttu-id="f1a68-130">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="f1a68-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f1a68-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f1a68-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="f1a68-132">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="f1a68-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="f1a68-133">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="f1a68-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="f1a68-134">バインディング</span><span class="sxs-lookup"><span data-stu-id="f1a68-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f1a68-135">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="f1a68-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f1a68-136">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="f1a68-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f1a68-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f1a68-137">\<customBinding></span></span>](custombinding.md)
