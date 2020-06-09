---
title: System.ServiceModel.Channels.ConnectionPoolCloseException
ms.date: 03/30/2017
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
ms.openlocfilehash: 0a312d192546655dc327667c00f4f2bbc0c15fdb
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602051"
---
# <a name="systemservicemodelchannelsconnectionpoolcloseexception"></a><span data-ttu-id="c5e28-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span><span class="sxs-lookup"><span data-stu-id="c5e28-102">System.ServiceModel.Channels.ConnectionPoolCloseException</span></span>
<span data-ttu-id="c5e28-103">この接続プールの接続を閉じている間に例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="c5e28-103">An exception occurred while closing the connections in this connection pool.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c5e28-104">説明</span><span class="sxs-lookup"><span data-stu-id="c5e28-104">Description</span></span>  
 <span data-ttu-id="c5e28-105">このエラーレベルのトレースは、Windows Communication Foundation (WCF) の接続プール機能によって使用される接続プールを閉じるときにエラーが発生したことを示します。</span><span class="sxs-lookup"><span data-stu-id="c5e28-105">This error level trace indicates that an error has occurred while closing the connection pools used by Windows Communication Foundation (WCF)’s connection pooling feature.</span></span> <span data-ttu-id="c5e28-106">このエラーの原因としては、プールされた接続を閉じることに失敗した、またはプールされた接続で CloseTimeout が設定されていることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="c5e28-106">One possible reason for this is an unsuccessful closure of a pooled connection, or a set of pooled connections within the CloseTimeout.</span></span> <span data-ttu-id="c5e28-107">この例外がスローされると、このプール内でまだ閉じられていない接続はすべて中断され、他のプールにある閉じられていない接続は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="c5e28-107">When this exception is thrown, any remaining unclosed connections within that pool are aborted; unclosed connections within other pools are abandoned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e28-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5e28-108">See also</span></span>

- [<span data-ttu-id="c5e28-109">トレース</span><span class="sxs-lookup"><span data-stu-id="c5e28-109">Tracing</span></span>](index.md)
- [<span data-ttu-id="c5e28-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c5e28-110">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="c5e28-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="c5e28-111">Administration and Diagnostics</span></span>](../index.md)
