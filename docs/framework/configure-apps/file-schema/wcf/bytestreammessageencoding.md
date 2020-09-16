---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: e2b92b88c3e2a8abb14f58af90aab6e2e58ce14a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557295"
---
# \<byteStreamMessageEncoding>
<span data-ttu-id="99749-101">文字エンコーディングを指定するオプションを使用し、メッセージ エンコーディングをバイト ストリームとして指定します。</span><span class="sxs-lookup"><span data-stu-id="99749-101">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**  
  
## <a name="syntax"></a><span data-ttu-id="99749-102">構文</span><span class="sxs-lookup"><span data-stu-id="99749-102">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99749-103">属性および要素</span><span class="sxs-lookup"><span data-stu-id="99749-103">Attributes and Elements</span></span>  
 <span data-ttu-id="99749-104">以降のセクションでは、属性、子要素、および親要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="99749-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99749-105">属性</span><span class="sxs-lookup"><span data-stu-id="99749-105">Attributes</span></span>  
  
|<span data-ttu-id="99749-106">属性</span><span class="sxs-lookup"><span data-stu-id="99749-106">Attribute</span></span>|<span data-ttu-id="99749-107">説明</span><span class="sxs-lookup"><span data-stu-id="99749-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99749-108">messageVersion</span><span class="sxs-lookup"><span data-stu-id="99749-108">messageVersion</span></span>|<span data-ttu-id="99749-109">バインディングを使用して送信されたメッセージの SOAP バージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="99749-109">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="99749-110">このプロパティは、<xref:System.ServiceModel.Channels.MessageVersion.None%2A> のメッセージ バージョン値にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="99749-110">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="99749-111">バイト ストリーム メッセージ エンコーダーは、他のメッセージ バージョンをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="99749-111">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="99749-112">この属性は <xref:System.ServiceModel.Channels.MessageVersion> 型です。</span><span class="sxs-lookup"><span data-stu-id="99749-112">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99749-113">子要素</span><span class="sxs-lookup"><span data-stu-id="99749-113">Child Elements</span></span>  
  
|<span data-ttu-id="99749-114">要素</span><span class="sxs-lookup"><span data-stu-id="99749-114">Element</span></span>|<span data-ttu-id="99749-115">説明</span><span class="sxs-lookup"><span data-stu-id="99749-115">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="99749-116">このバインドを使用して設定されるエンドポイントにより処理可能な、SOAP メッセージの複雑さに対する制約を定義します。</span><span class="sxs-lookup"><span data-stu-id="99749-116">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="99749-117">この要素は <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 型です。</span><span class="sxs-lookup"><span data-stu-id="99749-117">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99749-118">親要素</span><span class="sxs-lookup"><span data-stu-id="99749-118">Parent Elements</span></span>  
  
|<span data-ttu-id="99749-119">要素</span><span class="sxs-lookup"><span data-stu-id="99749-119">Element</span></span>|<span data-ttu-id="99749-120">説明</span><span class="sxs-lookup"><span data-stu-id="99749-120">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="99749-121">カスタム バインドのすべてのバインド機能を定義します。</span><span class="sxs-lookup"><span data-stu-id="99749-121">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99749-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="99749-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="99749-123">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="99749-123">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="99749-124">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="99749-124">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="99749-125">バインド</span><span class="sxs-lookup"><span data-stu-id="99749-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="99749-126">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="99749-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="99749-127">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="99749-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
