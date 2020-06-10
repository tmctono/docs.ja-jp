---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata
ms.date: 03/30/2017
ms.assetid: a174bbf5-0ffe-4fda-969d-e7fbd1996123
ms.openlocfilehash: faa9fc98d5ba029fff5c221e870dd48712e152a3
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594284"
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorresponseinvalidmetadata"></a><span data-ttu-id="1b388-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span><span class="sxs-lookup"><span data-stu-id="1b388-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span></span>
<span data-ttu-id="1b388-103">WS-AtomicTransaction プロトコル サービスは、無効または互換性のないメタデータのあるエンドポイント参照を含むそのコーディネーターから、RegisterResponse メッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="1b388-103">The WS-Atomic Transaction protocol service received a RegisterResponse message from its coordinator that contains an endpoint reference with invalid or incompatible metadata.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1b388-104">説明</span><span class="sxs-lookup"><span data-stu-id="1b388-104">Description</span></span>  
 <span data-ttu-id="1b388-105">ローカルのトランザクション マネージャーが、その上位のトランザクション マネージャーに登録を試み、上位のトランザクション マネージャーが、RegisterResponse メッセージ内の無効なアドレスを返すときにトレースされます。</span><span class="sxs-lookup"><span data-stu-id="1b388-105">Traced when the local Transaction Manager tries to register with its superior Transaction Manager and the superior returns an invalid address within the RegisterResponse message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b388-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="1b388-106">See also</span></span>

- [<span data-ttu-id="1b388-107">トレース</span><span class="sxs-lookup"><span data-stu-id="1b388-107">Tracing</span></span>](index.md)
- [<span data-ttu-id="1b388-108">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1b388-108">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="1b388-109">管理と診断</span><span class="sxs-lookup"><span data-stu-id="1b388-109">Administration and Diagnostics</span></span>](../index.md)
