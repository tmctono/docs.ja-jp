---
title: System.ServiceModel.Activation.WebHostServiceCloseFailed
ms.date: 03/30/2017
ms.assetid: 3cab9856-a5cf-4f0e-a0cb-89425e368f8e
ms.openlocfilehash: af24847d5174475103340725c86ff44024556671
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84588861"
---
# <a name="systemservicemodelactivationwebhostserviceclosefailed"></a><span data-ttu-id="333ae-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span><span class="sxs-lookup"><span data-stu-id="333ae-102">System.ServiceModel.Activation.WebHostServiceCloseFailed</span></span>
<span data-ttu-id="333ae-103">サービスが正常に閉じられず、中止された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="333ae-103">Occurs when a service cannot be closed gracefully and is aborted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="333ae-104">説明</span><span class="sxs-lookup"><span data-stu-id="333ae-104">Description</span></span>  
 <span data-ttu-id="333ae-105">このエラー コードはログ ファイルにのみ記録されます。</span><span class="sxs-lookup"><span data-stu-id="333ae-105">This error code only appears in the log file.</span></span> <span data-ttu-id="333ae-106">通常は、Abort を既に呼び出した後でサービスを閉じようとした場合などの、プログラミング エラーを示します。</span><span class="sxs-lookup"><span data-stu-id="333ae-106">It usually indicates a programming error, for example, when you try to close a service after Abort has already been called.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="333ae-107">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="333ae-107">Troubleshooting</span></span>  
 <span data-ttu-id="333ae-108">アプリケーションのソース コードをチェックしてください。</span><span class="sxs-lookup"><span data-stu-id="333ae-108">Check the application source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="333ae-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="333ae-109">See also</span></span>

- [<span data-ttu-id="333ae-110">トレース</span><span class="sxs-lookup"><span data-stu-id="333ae-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="333ae-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="333ae-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="333ae-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="333ae-112">Administration and Diagnostics</span></span>](../index.md)
