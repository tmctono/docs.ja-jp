---
title: オンライン ステータスとオフライン ステータスの追加
ms.date: 03/30/2017
ms.assetid: 05e5f51d-81b6-4c17-b364-9dda447a5fce
ms.openlocfilehash: 15a963d4de0dcf1d7f0162b0a3266e17d4073ecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857741"
---
# <a name="adding-online-and-offline-status"></a><span data-ttu-id="c04e3-102">オンライン ステータスとオフライン ステータスの追加</span><span class="sxs-lookup"><span data-stu-id="c04e3-102">Adding Online and Offline Status</span></span>
<span data-ttu-id="c04e3-103">多くの場合、アプリケーションではピア チャネル接続のステータスについて明確な詳細情報を監視することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c04e3-103">In many cases, it is important for an application to monitor specific details about the status of a Peer Channel connection.</span></span> <span data-ttu-id="c04e3-104">この情報は、`GetProperty` インターフェイスの実装で <xref:System.ServiceModel.IOnlineStatus> メソッドを呼び出すことで取得できます。</span><span class="sxs-lookup"><span data-stu-id="c04e3-104">You can obtain this information by calling the `GetProperty` method on an implementation of the <xref:System.ServiceModel.IOnlineStatus> interface.</span></span> <span data-ttu-id="c04e3-105">このインターフェイスを実装するオブジェクトは、接続ステータスを監視したり、`OnOnline` や `OnOffline` などのイベント ハンドラーを登録したりできるため、オンライン ステータスに変化があると即座に反応できます。</span><span class="sxs-lookup"><span data-stu-id="c04e3-105">An object with an implementation of this interface can monitor connection status or register for event handlers, such as `OnOnline` and `OnOffline`, and react immediately as changes to online status occur.</span></span>  
  
 <span data-ttu-id="c04e3-106">ピア チャネル インフラストラクチャでは、クライアントが少なくとも 1 つのピアに接続されているとオンラインと見なされ、そうでない場合はオフラインと見なされます。</span><span class="sxs-lookup"><span data-stu-id="c04e3-106">In the Peer Channel infrastructure, a client is considered to be online if it is connected to at least one other peer and offline otherwise.</span></span> <span data-ttu-id="c04e3-107">このことは、開発中のアプリケーションをデバッグする際や、エンド ユーザーに詳細情報を表示する際に特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c04e3-107">This can be particularly useful in both debugging a developing applications or displaying detailed information to the end user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c04e3-108">オンライン イベント ハンドラーでは、メッセージを送信する前に、まず、ノードが開いていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c04e3-108">An online event handler should first ensure that the node is open before sending any messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c04e3-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="c04e3-109">See also</span></span>

- [<span data-ttu-id="c04e3-110">ピア チャネル アプリケーションの構築</span><span class="sxs-lookup"><span data-stu-id="c04e3-110">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
