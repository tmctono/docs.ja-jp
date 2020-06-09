---
title: System.ServiceModel.MessageProcessingPaused
ms.date: 03/30/2017
ms.assetid: 36b5302a-93cc-478a-9bb2-8a1601fba1df
ms.openlocfilehash: 85bec8255e0d20d6e76ea354e5b8c42b83d7d8e6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598152"
---
# <a name="systemservicemodelmessageprocessingpaused"></a><span data-ttu-id="bf58a-102">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="bf58a-102">System.ServiceModel.MessageProcessingPaused</span></span>
<span data-ttu-id="bf58a-103">System.ServiceModel.MessageProcessingPaused</span><span class="sxs-lookup"><span data-stu-id="bf58a-103">System.ServiceModel.MessageProcessingPaused</span></span>  
  
## <a name="description"></a><span data-ttu-id="bf58a-104">説明</span><span class="sxs-lookup"><span data-stu-id="bf58a-104">Description</span></span>  
 <span data-ttu-id="bf58a-105">メッセージの処理中にスレッドが切り替わりました。</span><span class="sxs-lookup"><span data-stu-id="bf58a-105">The threads were switched while processing a message.</span></span>  
  
 <span data-ttu-id="bf58a-106">メッセージ処理は、次の理由によって一時停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="bf58a-106">Message processing can be paused by the following reasons:</span></span>  
  
- <span data-ttu-id="bf58a-107">ConcurrencyMode が単一または再入可能で、サービスが別のメッセージを処理している。</span><span class="sxs-lookup"><span data-stu-id="bf58a-107">ConcurrencyMode is single or reentrant, and the service is processing another message.</span></span>  
  
- <span data-ttu-id="bf58a-108">トランザクションが有効で、サービスが別のトランザクションを処理している。</span><span class="sxs-lookup"><span data-stu-id="bf58a-108">Transaction is enabled and the service is processing another transaction.</span></span>  
  
- <span data-ttu-id="bf58a-109">同期コンテキストが最新ではない。</span><span class="sxs-lookup"><span data-stu-id="bf58a-109">Synchronization context is not current.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf58a-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="bf58a-110">See also</span></span>

- [<span data-ttu-id="bf58a-111">トレース</span><span class="sxs-lookup"><span data-stu-id="bf58a-111">Tracing</span></span>](index.md)
- [<span data-ttu-id="bf58a-112">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bf58a-112">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bf58a-113">管理と診断</span><span class="sxs-lookup"><span data-stu-id="bf58a-113">Administration and Diagnostics</span></span>](../index.md)
