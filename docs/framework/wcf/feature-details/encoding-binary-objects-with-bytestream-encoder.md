---
title: バイトストリーム エンコーダーを使用したバイナリ オブジェクトのエンコーディング
ms.date: 03/30/2017
ms.assetid: 020ee981-c889-4b12-a3ea-91823ef46444
ms.openlocfilehash: 09a919e11971f81bc76dca0e45a7eb0e70ef749e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626926"
---
# <a name="encoding-binary-objects-with-bytestream-encoder"></a><span data-ttu-id="00c93-102">バイトストリーム エンコーダーを使用したバイナリ オブジェクトのエンコーディング</span><span class="sxs-lookup"><span data-stu-id="00c93-102">Encoding Binary Objects with ByteStream Encoder</span></span>
<span data-ttu-id="00c93-103">Windows Communication Foundation (WCF) の生のバイナリ データを送受信することを使用してを構成、<xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>します。</span><span class="sxs-lookup"><span data-stu-id="00c93-103">Sending and receiving raw binary data with Windows Communication Foundation (WCF) is configured using <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>.</span></span>  
  
## <a name="byte-stream-message-encoder-architecture"></a><span data-ttu-id="00c93-104">バイト ストリーム メッセージ エンコーダーのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="00c93-104">Byte Stream Message Encoder Architecture</span></span>  
 <span data-ttu-id="00c93-105">WCF で使用されるバイナリ メッセージ エンコーダーには、処理、検証、またはメッセージの基になるバイナリ データを識別するための機能がありません。</span><span class="sxs-lookup"><span data-stu-id="00c93-105">The binary message encoder used by WCF has no facility for processing, validating, or identifying the underlying binary data in the message.</span></span> <span data-ttu-id="00c93-106">データ パッケージは、XML にエンコード、送受信、およびデコードされます。</span><span class="sxs-lookup"><span data-stu-id="00c93-106">The data package is encoded into XML, sent, received, and decoded.</span></span> <span data-ttu-id="00c93-107">エンコーダーは、トランスポートに渡された後に、メッセージがメッセージ キューに送られる前にデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="00c93-107">The encoder processes the data after being passed to the transport and before the message is sent to the message queue.</span></span> <span data-ttu-id="00c93-108">機能的には、バイナリ エンコーダーが、送信用にメッセージ データを `<binary>` 要素にラップし、そのメッセージが受信された後にこの要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="00c93-108">Functionally, the binary encoder wraps the message data in `<binary>` elements for sending and removes the elements after the message is received.</span></span>  
  
## <a name="using-the-byte-stream-message-encoder"></a><span data-ttu-id="00c93-109">バイト ストリーム メッセージ エンコーダーの使用</span><span class="sxs-lookup"><span data-stu-id="00c93-109">Using the Byte Stream Message Encoder</span></span>  
 <span data-ttu-id="00c93-110">次の例は、バイト ストリーム メッセージ エンコーダーを実装するサービス コントラクトを示しています。</span><span class="sxs-lookup"><span data-stu-id="00c93-110">The following example shows a service contract that implements the byte stream message encoder.</span></span>  
  
```csharp  
[OperationContract]  
Void Myfunction(Stream stream);  
```  
  
 <span data-ttu-id="00c93-111">次の例は、呼び出されたサービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="00c93-111">The following example shows the service being invoked.</span></span>  
  
```csharp  
proxy.MyFunction(stream);  
```  
  
 <span data-ttu-id="00c93-112">ルーターなどのメッセージ インフラストラクチャを実装するサービスを使用する場合、そのメッセージは、次の例に示すように、メッセージの検査、検証、およびメッセージとの対話操作のいずれも行うことなく処理されます。</span><span class="sxs-lookup"><span data-stu-id="00c93-112">In the case of using a service that implements a message infrastructure (such as a router), the message is processed without inspecting, validating, or otherwise interacting with the message, as shown in the following example.</span></span>  
  
```csharp  
[OperationContract]  
void ProcessMessage(Message message) ;  
```  
  
## <a name="scenarios"></a><span data-ttu-id="00c93-113">シナリオ</span><span class="sxs-lookup"><span data-stu-id="00c93-113">Scenarios</span></span>  
 <span data-ttu-id="00c93-114">バイト ストリーム エンコーダーは、次のシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="00c93-114">The Byte Stream Encoder is useful in the following scenarios.</span></span>  
  
- <span data-ttu-id="00c93-115">WCF を使用してコンピューター間で JPEG イメージを転送しています。</span><span class="sxs-lookup"><span data-stu-id="00c93-115">Transferring a JPEG image between computers using WCF.</span></span> <span data-ttu-id="00c93-116">このシナリオでは、イメージは外部ソースから転送によって到着し、送信されたデータはイメージを構成する生バイトになります。</span><span class="sxs-lookup"><span data-stu-id="00c93-116">In this scenario, the image will arrive through the transport from an outside source, and the data sent will be the raw bytes that make up the image.</span></span> <span data-ttu-id="00c93-117">サービスはバイナリ データを受信してイメージを表示します。</span><span class="sxs-lookup"><span data-stu-id="00c93-117">A service will receive the binary data and display the image.</span></span>  
  
- <span data-ttu-id="00c93-118">メッセージ キューからの情報の読み取りと処理。</span><span class="sxs-lookup"><span data-stu-id="00c93-118">Reading information out of a message queue and processing it.</span></span> <span data-ttu-id="00c93-119">メッセージはメッセージ キュー マネージャーから読み取られ、処理対象のメッセージ キュー チャネルに渡されます。</span><span class="sxs-lookup"><span data-stu-id="00c93-119">The message will be read from a message queue manager, and passed up the message queue channel to be handled.</span></span> <span data-ttu-id="00c93-120">メッセージ キュー チャネルは、WCF チャネル スタックのキュー マネージャーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="00c93-120">The message queue channel will act as a queue manager in the WCF channel stack.</span></span>  
  
 <span data-ttu-id="00c93-121">メッセージをメッセージ キュー チャネルを介して送信する場合、送信者はキュー マネージャーから受信したバイトを制御できません。</span><span class="sxs-lookup"><span data-stu-id="00c93-121">In the case of sending a message over a message queue channel, the sender has no control over the bytes received from the queue manager.</span></span> <span data-ttu-id="00c93-122">受信プロセスで生バイトを読み取ることができない場合、メッセージは不適切な書式として受信され処理されません。受信プロセスは受信したバイトを利用可能な形式に変換する機能があると見なされます。</span><span class="sxs-lookup"><span data-stu-id="00c93-122">If the receiving process has no capability to read raw bytes, the message will be received as badly formatted and will not be processed; it is assumed that the receiving process will have the capability of translating the received bytes back into a usable format.</span></span>
