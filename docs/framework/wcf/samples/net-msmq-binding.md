---
title: ネット MSMQ バインディング
ms.date: 03/30/2017
ms.assetid: fe4bb696-f57c-4cb3-9b7e-9d95fe6b8323
ms.openlocfilehash: ee32ea09eed28c1c7cd5df2df2d13fd5f41f4b22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972381"
---
# <a name="net-msmq-binding"></a><span data-ttu-id="0d3dc-102">ネット MSMQ バインディング</span><span class="sxs-lookup"><span data-stu-id="0d3dc-102">Net MSMQ Binding</span></span>
<span data-ttu-id="0d3dc-103">このセクションには、エンドポイント要素の MSMQ バインディング属性の使用方法を示すサンプルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-103">This section contains samples that demonstrate using MSMQ binding attributes of an endpoint element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d3dc-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0d3dc-104">In This Section</span></span>  
 [<span data-ttu-id="0d3dc-105">トランザクション MSMQ バインディング</span><span class="sxs-lookup"><span data-stu-id="0d3dc-105">Transacted MSMQ Binding</span></span>](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)  
 <span data-ttu-id="0d3dc-106">メッセージ キュー (MSMQ) を使用して、トランザクション キューによる通信を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-106">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="0d3dc-107">揮発性キューによる通信</span><span class="sxs-lookup"><span data-stu-id="0d3dc-107">Volatile Queued Communication</span></span>](../../../../docs/framework/wcf/samples/volatile-queued-communication.md)  
 <span data-ttu-id="0d3dc-108">メッセージ キュー (MSMQ) トランスポートで揮発性キューによる通信を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-108">Demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="0d3dc-109">配信不能キュー</span><span class="sxs-lookup"><span data-stu-id="0d3dc-109">Dead Letter Queues</span></span>](../../../../docs/framework/wcf/samples/dead-letter-queues.md)  
 <span data-ttu-id="0d3dc-110">配信できなかったメッセージの処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-110">Demonstrates how to handle and process messages that have failed delivery.</span></span>  
  
 [<span data-ttu-id="0d3dc-111">MSMQ 4.0 での有害メッセージ処理</span><span class="sxs-lookup"><span data-stu-id="0d3dc-111">Poison Message Handling in MSMQ 4.0</span></span>](../../../../docs/framework/wcf/samples/poison-message-handling-in-msmq-4-0.md)  
 <span data-ttu-id="0d3dc-112">MSMQ 4.0 を使用して、サービスで有害メッセージの処理を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-112">Demonstrates how to perform poison message handling in a service using MSMQ 4.0.</span></span>  
  
 [<span data-ttu-id="0d3dc-113">セッションとキュー</span><span class="sxs-lookup"><span data-stu-id="0d3dc-113">Sessions and Queues</span></span>](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
 <span data-ttu-id="0d3dc-114">メッセージ キュー (MSMQ) トランスポートを介して、キュー通信で一連の関連メッセージを送受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-114">Demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="0d3dc-115">双方向通信</span><span class="sxs-lookup"><span data-stu-id="0d3dc-115">Two-Way Communication</span></span>](../../../../docs/framework/wcf/samples/two-way-communication.md)  
 <span data-ttu-id="0d3dc-116">MSMQ を介して、トランザクション キューによる双方向通信を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-116">Demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span>
  
 [<span data-ttu-id="0d3dc-117">SRMP</span><span class="sxs-lookup"><span data-stu-id="0d3dc-117">SRMP</span></span>](../../../../docs/framework/wcf/samples/srmp.md)  
 <span data-ttu-id="0d3dc-118">HTTP 経由でメッセージ キュー (MSMQ) を使用して、トランザクション キューによる通信を実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-118">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 [<span data-ttu-id="0d3dc-119">メッセージ キューを介したメッセージ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="0d3dc-119">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)  
 <span data-ttu-id="0d3dc-120">クライアントの認証で X.509v3 証明書による WS-Security を使用するアプリケーションを実装する方法を示します。このアプリケーションでは、MSMQ 経由でサーバーの X.509v3 証明書を使用するサーバー認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="0d3dc-120">Demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span>
