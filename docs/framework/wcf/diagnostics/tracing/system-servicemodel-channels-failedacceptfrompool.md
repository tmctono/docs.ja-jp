---
title: System.ServiceModel.Channels.FailedAcceptFromPool
ms.date: 03/30/2017
ms.assetid: d535b1b5-ee58-45e8-b400-7d9570f4eb9a
ms.openlocfilehash: de0bdd9e5ab922b09249bf550fde745042be8e58
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666756"
---
# <a name="systemservicemodelchannelsfailedacceptfrompool"></a><span data-ttu-id="f63ae-102">System.ServiceModel.Channels.FailedAcceptFromPool</span><span class="sxs-lookup"><span data-stu-id="f63ae-102">System.ServiceModel.Channels.FailedAcceptFromPool</span></span>
<span data-ttu-id="f63ae-103">プールされた接続を再使用できませんでした。</span><span class="sxs-lookup"><span data-stu-id="f63ae-103">An attempt to reuse a pooled connection failed.</span></span> <span data-ttu-id="f63ae-104">指定されたタイムアウト期間内に再試行します。</span><span class="sxs-lookup"><span data-stu-id="f63ae-104">Another attempt is made within the specified timeout period.</span></span>  
  
## <a name="description"></a><span data-ttu-id="f63ae-105">説明</span><span class="sxs-lookup"><span data-stu-id="f63ae-105">Description</span></span>  
 <span data-ttu-id="f63ae-106">この情報トレースは、プールされた接続の再使用を試みている間にエラーが発生したことを示しています。</span><span class="sxs-lookup"><span data-stu-id="f63ae-106">This informational trace indicates that an error has occurred while attempting to reuse a pooled connection.</span></span> <span data-ttu-id="f63ae-107">これは、プールされた接続に互換性がない、接続の準備ができていない、または接続がアクティブなままであるために発生します。</span><span class="sxs-lookup"><span data-stu-id="f63ae-107">This could happen because the pooled connection was not compatible, ready, or still active.</span></span> <span data-ttu-id="f63ae-108">所定のタイムアウト期間内に、他のプールされた接続を再使用する試みがさらに行われ、使用可能な接続が見つからない場合には、新しい接続が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f63ae-108">Additional attempts to reuse other pooled connection are made within a given timeout and a new connection is created in case no usable connections are found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63ae-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="f63ae-109">See also</span></span>

- [<span data-ttu-id="f63ae-110">トレース</span><span class="sxs-lookup"><span data-stu-id="f63ae-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="f63ae-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f63ae-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="f63ae-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="f63ae-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
