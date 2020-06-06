---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739068"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="d1dde-101">文字エンコーディングを指定するオプションを使用し、メッセージ エンコーディングをバイト ストリームとして指定します。</span><span class="sxs-lookup"><span data-stu-id="d1dde-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="d1dde-102">構文</span><span class="sxs-lookup"><span data-stu-id="d1dde-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1dde-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="d1dde-103">Attributes and Elements</span></span>  
 <span data-ttu-id="d1dde-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1dde-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1dde-105">属性</span><span class="sxs-lookup"><span data-stu-id="d1dde-105">Attributes</span></span>  
  
|<span data-ttu-id="d1dde-106">属性</span><span class="sxs-lookup"><span data-stu-id="d1dde-106">Attribute</span></span>|<span data-ttu-id="d1dde-107">説明</span><span class="sxs-lookup"><span data-stu-id="d1dde-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1dde-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="d1dde-108">messageVersion</span></span>|<span data-ttu-id="d1dde-109">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="d1dde-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="d1dde-110">このプロパティは、<xref:System.ServiceModel.Channels.MessageVersion.None%2A> のメッセージ バージョン値にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="d1dde-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="d1dde-111">バイト ストリーム メッセージ エンコーダーは、他のメッセージ バージョンをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="d1dde-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="d1dde-112">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="d1dde-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1dde-113">子要素</span><span class="sxs-lookup"><span data-stu-id="d1dde-113">Child Elements</span></span>  
  
|<span data-ttu-id="d1dde-114">要素</span><span class="sxs-lookup"><span data-stu-id="d1dde-114">Element</span></span>|<span data-ttu-id="d1dde-115">Description</span><span class="sxs-lookup"><span data-stu-id="d1dde-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="d1dde-116">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1dde-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="d1dde-117">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="d1dde-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1dde-118">親要素</span><span class="sxs-lookup"><span data-stu-id="d1dde-118">Parent Elements</span></span>  
  
|<span data-ttu-id="d1dde-119">要素</span><span class="sxs-lookup"><span data-stu-id="d1dde-119">Element</span></span>|<span data-ttu-id="d1dde-120">Description</span><span class="sxs-lookup"><span data-stu-id="d1dde-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="d1dde-121">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="d1dde-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1dde-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1dde-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="d1dde-123">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="d1dde-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="d1dde-124">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="d1dde-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="d1dde-125">バインド</span><span class="sxs-lookup"><span data-stu-id="d1dde-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d1dde-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="d1dde-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d1dde-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="d1dde-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
