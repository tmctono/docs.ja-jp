---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 5d78aed78a5c3a10aecac53bda02d6c640bc71ae
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400584"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="c60a2-101">\<byteStreamMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="c60a2-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="c60a2-102">文字エンコーディングを指定するオプションを使用し、メッセージ エンコーディングをバイト ストリームとして指定します。</span><span class="sxs-lookup"><span data-stu-id="c60a2-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="c60a2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c60a2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c60a2-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c60a2-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c60a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<バインド >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c60a2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c60a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c60a2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c60a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<バインド >** </span><span class="sxs-lookup"><span data-stu-id="c60a2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c60a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<byteStreamMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="c60a2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c60a2-109">構文</span><span class="sxs-lookup"><span data-stu-id="c60a2-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c60a2-110">属性および要素</span><span class="sxs-lookup"><span data-stu-id="c60a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c60a2-111">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c60a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c60a2-112">属性</span><span class="sxs-lookup"><span data-stu-id="c60a2-112">Attributes</span></span>  
  
|<span data-ttu-id="c60a2-113">属性</span><span class="sxs-lookup"><span data-stu-id="c60a2-113">Attribute</span></span>|<span data-ttu-id="c60a2-114">説明</span><span class="sxs-lookup"><span data-stu-id="c60a2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c60a2-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="c60a2-115">messageVersion</span></span>|<span data-ttu-id="c60a2-116">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="c60a2-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="c60a2-117">このプロパティは、<xref:System.ServiceModel.Channels.MessageVersion.None%2A> のメッセージ バージョン値にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="c60a2-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="c60a2-118">バイト ストリーム メッセージ エンコーダーは、他のメッセージ バージョンをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="c60a2-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="c60a2-119">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="c60a2-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c60a2-120">子要素</span><span class="sxs-lookup"><span data-stu-id="c60a2-120">Child Elements</span></span>  
  
|<span data-ttu-id="c60a2-121">要素</span><span class="sxs-lookup"><span data-stu-id="c60a2-121">Element</span></span>|<span data-ttu-id="c60a2-122">説明</span><span class="sxs-lookup"><span data-stu-id="c60a2-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c60a2-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c60a2-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="c60a2-124">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="c60a2-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="c60a2-125">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="c60a2-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c60a2-126">親要素</span><span class="sxs-lookup"><span data-stu-id="c60a2-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c60a2-127">要素</span><span class="sxs-lookup"><span data-stu-id="c60a2-127">Element</span></span>|<span data-ttu-id="c60a2-128">説明</span><span class="sxs-lookup"><span data-stu-id="c60a2-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c60a2-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="c60a2-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c60a2-130">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="c60a2-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c60a2-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c60a2-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="c60a2-132">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="c60a2-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="c60a2-133">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="c60a2-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="c60a2-134">バインディング</span><span class="sxs-lookup"><span data-stu-id="c60a2-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c60a2-135">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="c60a2-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c60a2-136">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="c60a2-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c60a2-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c60a2-137">\<customBinding></span></span>](custombinding.md)
