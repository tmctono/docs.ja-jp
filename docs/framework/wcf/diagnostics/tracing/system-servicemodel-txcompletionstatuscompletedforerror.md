---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 591e1a1dcb6746d79ff5eceba7e74e890f327354
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779497"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="676c7-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="676c7-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="676c7-103">処理されない実行例外が発生したため、指定された操作の指定されたトランザクションが完了しました。</span><span class="sxs-lookup"><span data-stu-id="676c7-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="676c7-104">説明</span><span class="sxs-lookup"><span data-stu-id="676c7-104">Description</span></span>  
 <span data-ttu-id="676c7-105">現在のトランザクションを完了しようとしているときにエラーが発生した場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="676c7-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="676c7-106">これは、応答またはエラーが呼び出し元に送信される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="676c7-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="676c7-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="676c7-107">Troubleshooting</span></span>  
 <span data-ttu-id="676c7-108">トレース メッセージを調べて、例外メッセージとアクション可能な項目を確認してください。</span><span class="sxs-lookup"><span data-stu-id="676c7-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676c7-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="676c7-109">See also</span></span>

- [<span data-ttu-id="676c7-110">トレース</span><span class="sxs-lookup"><span data-stu-id="676c7-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="676c7-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="676c7-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="676c7-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="676c7-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
