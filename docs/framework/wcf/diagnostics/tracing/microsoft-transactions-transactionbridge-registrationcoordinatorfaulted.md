---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.date: 03/30/2017
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
ms.openlocfilehash: f634816b2459d2e0b6137e2e87fef907824af017
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163034"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="0c3f4-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="0c3f4-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="0c3f4-103">WS-AT プロトコル サービスは、Register メッセージへの応答として、コーディネーターからエラーを受信しました。</span><span class="sxs-lookup"><span data-stu-id="0c3f4-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0c3f4-104">説明</span><span class="sxs-lookup"><span data-stu-id="0c3f4-104">Description</span></span>  
 <span data-ttu-id="0c3f4-105">エラーが返されたためにローカルの TransactionManager がその上位の TransactionManager に登録できない場合に、トレースされます。</span><span class="sxs-lookup"><span data-stu-id="0c3f4-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="0c3f4-106">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0c3f4-106">Troubleshooting</span></span>  
 <span data-ttu-id="0c3f4-107">トレース メッセージを調べて、返されたエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0c3f4-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3f4-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="0c3f4-108">See also</span></span>

- [<span data-ttu-id="0c3f4-109">トレース</span><span class="sxs-lookup"><span data-stu-id="0c3f4-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="0c3f4-110">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0c3f4-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="0c3f4-111">管理と診断</span><span class="sxs-lookup"><span data-stu-id="0c3f4-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
