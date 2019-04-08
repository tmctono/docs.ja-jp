---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
ms.date: 03/30/2017
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
ms.openlocfilehash: 3745c542986d405312a308fcf50ba6d7b6f93a1c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074184"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfailed"></a><span data-ttu-id="59080-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span><span class="sxs-lookup"><span data-stu-id="59080-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed</span></span>
<span data-ttu-id="59080-103">WS-AT プロトコル サービスは、Register メッセージをコーディネーターに送信できませんでした。</span><span class="sxs-lookup"><span data-stu-id="59080-103">The WS-AT protocol service failed to send a Register message to its coordinator</span></span>  
  
## <a name="description"></a><span data-ttu-id="59080-104">説明</span><span class="sxs-lookup"><span data-stu-id="59080-104">Description</span></span>  
 <span data-ttu-id="59080-105">メッセージを送信できないために、ローカルの TransactionManager がその上位の TransactionManager に登録できない場合にトレースされます。</span><span class="sxs-lookup"><span data-stu-id="59080-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to the inability to send a message.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="59080-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="59080-106">Troubleshooting</span></span>  
 <span data-ttu-id="59080-107">トレース メッセージを調べて、メッセージの送信エラーの原因となった例外を確認してください。</span><span class="sxs-lookup"><span data-stu-id="59080-107">Inspect the trace message for the exception causing the message send failure</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59080-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="59080-108">See also</span></span>

- [<span data-ttu-id="59080-109">トレース</span><span class="sxs-lookup"><span data-stu-id="59080-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="59080-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="59080-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="59080-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="59080-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
