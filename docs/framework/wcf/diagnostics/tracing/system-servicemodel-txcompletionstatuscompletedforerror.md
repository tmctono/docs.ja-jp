---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: 2bc71d18480fa19be66cbfa1687a7b63eb548309
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601453"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="02848-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="02848-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="02848-103">処理されない実行例外が発生したため、指定された操作の指定されたトランザクションが完了しました。</span><span class="sxs-lookup"><span data-stu-id="02848-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="02848-104">説明</span><span class="sxs-lookup"><span data-stu-id="02848-104">Description</span></span>  
 <span data-ttu-id="02848-105">現在のトランザクションを完了しようとしているときにエラーが発生した場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="02848-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="02848-106">これは、応答またはエラーが呼び出し元に送信される前に発生します。</span><span class="sxs-lookup"><span data-stu-id="02848-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="02848-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02848-107">Troubleshooting</span></span>  
 <span data-ttu-id="02848-108">トレース メッセージを調べて、例外メッセージとアクション可能な項目を確認してください。</span><span class="sxs-lookup"><span data-stu-id="02848-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02848-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="02848-109">See also</span></span>

- [<span data-ttu-id="02848-110">トレース</span><span class="sxs-lookup"><span data-stu-id="02848-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="02848-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="02848-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="02848-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="02848-112">Administration and Diagnostics</span></span>](../index.md)
