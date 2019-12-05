---
title: ピアツーピア ネットワーク
ms.date: 03/30/2017
ms.assetid: ad6cb67b-fd1c-4ca1-a767-b410da2e16ca
ms.openlocfilehash: 74566d7bc7c8d817cedb0ff6f64590ba827ed4c4
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837364"
---
# <a name="peer-to-peer-networking"></a><span data-ttu-id="d1932-102">ピアツーピア ネットワーク</span><span class="sxs-lookup"><span data-stu-id="d1932-102">Peer-to-Peer Networking</span></span>
<span data-ttu-id="d1932-103">ピアチャネルは、Windows Communication Foundation (WCF) における、マルチパーティのピアツーピア (P2P) 通信テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="d1932-103">Peer Channel is a multiparty, peer-to-peer (P2P) communication technology in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="d1932-104">この技術によって、アプリケーション開発者は安全で拡張可能なメッセージ ベースの P2P 通信チャネルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="d1932-104">It provides a secure and scalable message-based P2P communication channel for application developers.</span></span> <span data-ttu-id="d1932-105">ピア チャネルのメリットを活用するマルチパーティ アプリケーションの一般的な例は、チャットなどの共同作業アプリケーションです。チャットでは、ユーザーのグループがサーバーなしのピアツーピア方式で互いに会話します。</span><span class="sxs-lookup"><span data-stu-id="d1932-105">One common example of a multiparty application that can benefit from Peer Channel is a collaborative application, such as chat, where a group of people chat with one another in a peer-to-peer manner without servers.</span></span> <span data-ttu-id="d1932-106">ピア チャネルを使用することで、顧客シナリオや企業シナリオでの P2P コラボレーション、コンテンツ配布、負荷分散、および分散処理が実現します。</span><span class="sxs-lookup"><span data-stu-id="d1932-106">Peer Channel enables P2P collaboration, content distribution, load balancing, and distributed processing for both consumer and enterprise scenarios.</span></span>  
  
 <span data-ttu-id="d1932-107">Windows Vista では、ピアチャネルが既定で有効になっています。これはすべて WCF です。</span><span class="sxs-lookup"><span data-stu-id="d1932-107">Peer Channel is enabled by default on Windows Vista, as is all of WCF.</span></span> <span data-ttu-id="d1932-108">ピア チャネルのクラスにアクセスするには、プロジェクトに System.ServiceModel.dll への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="d1932-108">To access Peer Channel classes, add references to System.ServiceModel.dll to your project.</span></span>  
  
 <span data-ttu-id="d1932-109">次の各セクションには、ピアツーピア ネットワークに関する情報と、ピア チャネルのクラスを使用してピア対応のネットワーク アプリケーションを作成する方法が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d1932-109">The following sections contain information about peer-to-peer networking and the use of Peer Channel classes to create peer-enabled network applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d1932-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d1932-110">In This Section</span></span>  
 <span data-ttu-id="d1932-111">[ピアチャネルのシナリオ](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md): パブリケーション/サブスクリプションメッセージング、コラボレーション、分散処理、ゲームなど、ピアチャネル api でサポートされる開発シナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1932-111">[Peer Channel Scenarios](../../../../docs/framework/wcf/feature-details/peer-channel-scenarios.md):  Describes development scenarios supported by the Peer Channel APIs, such as publication/subscription messaging, collaboration, distributed processing, and gaming.</span></span>  
  
 <span data-ttu-id="d1932-112">[ピアチャネルの概念](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md): ピアメッシュ、ピアノード、ピアチャネルのセキュリティ、およびピアリゾルバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d1932-112">[Peer Channel Concepts](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md):  Describes Peer Meshes, Peer Nodes, Peer Channel security, and Peer Resolvers.</span></span>  
  
 <span data-ttu-id="d1932-113">[ピアチャネルアプリケーションの構築](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md): ピアチャネルアプリケーションの開発に関するガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d1932-113">[Building a Peer Channel Application](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md):  Provides guidance on developing Peer Channel applications.</span></span>  
  
## <a name="peer-channel-code-examples"></a><span data-ttu-id="d1932-114">ピア チャネルのコード例</span><span class="sxs-lookup"><span data-stu-id="d1932-114">Peer Channel Code Examples</span></span>  
 <span data-ttu-id="d1932-115">[ピアチャネルカスタムピアリゾルバー](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d1932-115">[Peer Channel Custom Peer Resolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90))</span></span>  
  
## <a name="peer-channel-team-blog"></a><span data-ttu-id="d1932-116">ピア チャネル チームのブログ</span><span class="sxs-lookup"><span data-stu-id="d1932-116">Peer Channel Team blog</span></span>  
 [<span data-ttu-id="d1932-117">ピアチャネルチームのブログ</span><span class="sxs-lookup"><span data-stu-id="d1932-117">Peer Channel Team Blog</span></span>](https://go.microsoft.com/fwlink/?LinkID=114530)
