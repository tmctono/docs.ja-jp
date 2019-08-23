---
title: メッセージ エンコーディング
ms.date: 03/30/2017
ms.assetid: f30ee941-aca9-4c67-82a5-421568496f07
ms.openlocfilehash: 8e5a71095ba62e0e2e6592c8b7b83b67602ef7e7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931591"
---
# <a name="message-encoding"></a><span data-ttu-id="45ab7-102">メッセージ エンコーディング</span><span class="sxs-lookup"><span data-stu-id="45ab7-102">Message Encoding</span></span>
<span data-ttu-id="45ab7-103">エンコーディングは、Unicode 文字のセットをバイト シーケンスに変換するプロセスです。</span><span class="sxs-lookup"><span data-stu-id="45ab7-103">Encoding is the process of transforming a set of Unicode characters into a sequence of bytes.</span></span> <span data-ttu-id="45ab7-104">デコードは、その逆のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="45ab7-104">Decoding is the reverse process.</span></span> <span data-ttu-id="45ab7-105">Windows Communication Foundation (WCF) には、SOAP メッセージの3種類のエンコードが含まれています。テキスト、バイナリ、およびメッセージ転送の最適化メカニズム (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="45ab7-105">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="45ab7-106">`binaryMessageEncoding` 構成セクションでは、バイナリ ベースの XML メッセージに使用される文字エンコーディングおよびメッセージ バージョン管理が指定されます。</span><span class="sxs-lookup"><span data-stu-id="45ab7-106">The `binaryMessageEncoding` configuration section specifies the character encoding and message versioning used for binary-based XML messages.</span></span> <span data-ttu-id="45ab7-107">バイナリ メッセージ エンコーダーは、ネットワーク上で Windows Communication Foundation (WCF) メッセージをバイナリにエンコードします。</span><span class="sxs-lookup"><span data-stu-id="45ab7-107">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="45ab7-108">このエンコーディングによりメッセージ転送は非常に高速になりますが、WS-\* 標準に基づいた相互運用性は失われます。</span><span class="sxs-lookup"><span data-stu-id="45ab7-108">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
 <span data-ttu-id="45ab7-109">`mtomMessageEncoding` 構成セクションでは、Message Transmission Optimization Mechanism (MTOM) エンコーディングを使用したメッセージの文字エンコーディングおよびメッセージ バージョン管理が指定されます。</span><span class="sxs-lookup"><span data-stu-id="45ab7-109">The `mtomMessageEncoding` configuration section specifies the character encoding and message versioning used for a message using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="45ab7-110">(MTOM) は、Windows Communication Foundation (WCF) メッセージでバイナリ データを送信する効率的な技術です。</span><span class="sxs-lookup"><span data-stu-id="45ab7-110">(MTOM) is an efficient technology for transmitting binary data in Windows Communication Foundation (WCF) messages.</span></span> <span data-ttu-id="45ab7-111">MTOM エンコーダーは、効率と相互運用性のバランスをとろうとします。</span><span class="sxs-lookup"><span data-stu-id="45ab7-111">The MTOM encoder attempts to strike a balance between efficiency and interoperability.</span></span> <span data-ttu-id="45ab7-112">MTOM エンコーディングは、ほとんどの XML をテキスト形式で転送しますが、大きいサイズのバイナリ データ ブロックはテキストに変換せずにそのまま転送することによって最適化します。</span><span class="sxs-lookup"><span data-stu-id="45ab7-112">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to text.</span></span>  
  
 <span data-ttu-id="45ab7-113">`textMessageEncoding` 構成セクションは、ネットワーク上でテキストベースのメッセージの作成に使用されるテキスト エンコーダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="45ab7-113">The `textMessageEncoding` configuration section specifies a text encoder used to create text-based messages on the wire.</span></span> <span data-ttu-id="45ab7-114">このエンコーダーにより生成されるメッセージは、WS-\* ベースの相互運用に適しています。</span><span class="sxs-lookup"><span data-stu-id="45ab7-114">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="45ab7-115">Web サービスまたは Web サービス クライアントは、一般に、テキスト形式の XML を認識できます。</span><span class="sxs-lookup"><span data-stu-id="45ab7-115">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="45ab7-116">ただし、バイナリ データの大きいブロックをテキストとして送信することは、XML メッセージをエンコードする最も効率の悪い方法です。</span><span class="sxs-lookup"><span data-stu-id="45ab7-116">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ab7-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="45ab7-117">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- [<span data-ttu-id="45ab7-118">バインディング</span><span class="sxs-lookup"><span data-stu-id="45ab7-118">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="45ab7-119">バインディングの拡張</span><span class="sxs-lookup"><span data-stu-id="45ab7-119">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="45ab7-120">カスタム バインディング</span><span class="sxs-lookup"><span data-stu-id="45ab7-120">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="45ab7-121">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="45ab7-121">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="45ab7-122">メッセージ エンコーダーを選択する</span><span class="sxs-lookup"><span data-stu-id="45ab7-122">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
