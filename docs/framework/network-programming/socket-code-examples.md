---
title: ソケットのコード例
description: 次の例から、クライアントの Socket クラスを使用してネットワーク サービスに接続し、サーバーとしてクライアントからの接続を待ち受ける方法を確認してください。
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- Socket class, asynchronous server sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- sockets, code examples
- receiving data, sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: f3fc7533-6956-42c6-bbc3-73e5a221027d
ms.openlocfilehash: 0a0911a779ed3d4938ad7ff57f048c176cf677fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502159"
---
# <a name="socket-code-examples"></a><span data-ttu-id="3d5ea-103">ソケットのコード例</span><span class="sxs-lookup"><span data-stu-id="3d5ea-103">Socket Code Examples</span></span>
<span data-ttu-id="3d5ea-104">次のコード例は、リモート ネットワーク サービスに接続するためのクライアントとして、また、リモート クライアントからの接続を待ち受けるためのサーバーとして <xref:System.Net.Sockets.Socket> クラスを利用する方法を示すものです。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-104">The following code examples demonstrate how to use the <xref:System.Net.Sockets.Socket> class as a client to connect to remote network services and as a server to listen for connections from remote clients.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3d5ea-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3d5ea-105">In This Section</span></span>  
 [<span data-ttu-id="3d5ea-106">同期クライアント ソケットの例</span><span class="sxs-lookup"><span data-stu-id="3d5ea-106">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)  
 <span data-ttu-id="3d5ea-107">サーバーに接続し、サーバーから返されたデータを表示する同期 <xref:System.Net.Sockets.Socket> クライアントを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-107">Shows how to implement a synchronous <xref:System.Net.Sockets.Socket> client that connects to a server and displays the data returned from the server.</span></span>  
  
 [<span data-ttu-id="3d5ea-108">同期サーバー ソケットの例</span><span class="sxs-lookup"><span data-stu-id="3d5ea-108">Synchronous Server Socket Example</span></span>](synchronous-server-socket-example.md)  
 <span data-ttu-id="3d5ea-109">クライアントからの接続を受け付け、クライアントから受け取ったデータをエコー バックする同期 <xref:System.Net.Sockets.Socket> サーバーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-109">Shows how to implement a synchronous <xref:System.Net.Sockets.Socket> server that accepts connections from a client and echoes back the data received from the client.</span></span>  
  
 [<span data-ttu-id="3d5ea-110">非同期クライアント ソケットの例</span><span class="sxs-lookup"><span data-stu-id="3d5ea-110">Asynchronous Client Socket Example</span></span>](asynchronous-client-socket-example.md)  
 <span data-ttu-id="3d5ea-111">サーバーに接続し、サーバーから返されたデータを表示する非同期 <xref:System.Net.Sockets.Socket> クライアントを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-111">Shows how to implement an asynchronous <xref:System.Net.Sockets.Socket> client that connects to a server and displays the data returned from the server.</span></span>  
  
 [<span data-ttu-id="3d5ea-112">非同期サーバー ソケットの例</span><span class="sxs-lookup"><span data-stu-id="3d5ea-112">Asynchronous Server Socket Example</span></span>](asynchronous-server-socket-example.md)  
 <span data-ttu-id="3d5ea-113">クライアントからの接続を受け付け、クライアントから受け取ったデータをエコー バックする非同期 <xref:System.Net.Sockets.Socket> サーバーを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-113">Shows how to implement an asynchronous <xref:System.Net.Sockets.Socket> server that accepts connections from a client and echoes back the data received from the client.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3d5ea-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="3d5ea-114">Related Sections</span></span>  
 [<span data-ttu-id="3d5ea-115">ソケット</span><span class="sxs-lookup"><span data-stu-id="3d5ea-115">Sockets</span></span>](sockets.md)  
 <span data-ttu-id="3d5ea-116"><xref:System.Net.Sockets> 名前空間と <xref:System.Net.Sockets.Socket> クラスに関する基本情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-116">Provides basic information about the <xref:System.Net.Sockets> namespace and the <xref:System.Net.Sockets.Socket> class.</span></span>  
  
 [<span data-ttu-id="3d5ea-117">ネットワーク プログラミングにおけるセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3d5ea-117">Security in Network Programming</span></span>](security-in-network-programming.md)  
 <span data-ttu-id="3d5ea-118">標準のインターネット セキュリティと認証の手法を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3d5ea-118">Describes how to use standard Internet security and authentication techniques.</span></span>
