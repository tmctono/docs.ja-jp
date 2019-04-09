---
title: System.ServiceModel.Channels.TcpConnectError
ms.date: 03/30/2017
ms.assetid: 22d93797-072e-405d-a3e0-5c519ddf290b
ms.openlocfilehash: 0bfd35e2b3ca421745701a91f2a5bfc91f3063aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091448"
---
# <a name="systemservicemodelchannelstcpconnecterror"></a><span data-ttu-id="d75c9-102">System.ServiceModel.Channels.TcpConnectError</span><span class="sxs-lookup"><span data-stu-id="d75c9-102">System.ServiceModel.Channels.TcpConnectError</span></span>
<span data-ttu-id="d75c9-103">TCP 接続の操作に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="d75c9-103">The TCP connect operation failed.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d75c9-104">説明</span><span class="sxs-lookup"><span data-stu-id="d75c9-104">Description</span></span>  
 <span data-ttu-id="d75c9-105">この警告レベルのトレースは、TCP エンドポイントへの接続に失敗したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="d75c9-105">This warning level trace indicates a failure to connect to a TCP endpoint.</span></span> <span data-ttu-id="d75c9-106">これは、リモート エンドポイントが指定された IP アドレスとポートで応答していない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="d75c9-106">This could happen if the remote endpoint is not responding at a given IP address and port.</span></span> <span data-ttu-id="d75c9-107">別の有効な IP アドレス (IPv4 アドレスや IPv6 アドレス、または指定のホスト名を表す別の IP アドレスなど) への後続する接続試行が成功した場合、このトレースは無視できます。</span><span class="sxs-lookup"><span data-stu-id="d75c9-107">This trace can be ignored if subsequent attempts to connect to other valid IP addresses (such as IPv4 or IPv6 addresses, or other IP addresses representing a given hostname) succeed.</span></span> <span data-ttu-id="d75c9-108">このトレースに含まれる例外により、エラーに関する追加情報が公開されることがあります。</span><span class="sxs-lookup"><span data-stu-id="d75c9-108">The exception within this trace can reveal additional information about the error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75c9-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="d75c9-109">See also</span></span>

- [<span data-ttu-id="d75c9-110">トレース</span><span class="sxs-lookup"><span data-stu-id="d75c9-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="d75c9-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d75c9-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="d75c9-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="d75c9-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
