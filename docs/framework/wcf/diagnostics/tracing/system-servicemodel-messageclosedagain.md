---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: a18355d55359df665d0e936ce95da34bf07aec6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761508"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="bddc5-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="bddc5-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="bddc5-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="bddc5-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="bddc5-104">説明</span><span class="sxs-lookup"><span data-stu-id="bddc5-104">Description</span></span>  
 <span data-ttu-id="bddc5-105">メッセージがもう一度閉じられました。</span><span class="sxs-lookup"><span data-stu-id="bddc5-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="bddc5-106">メッセージを閉じることができるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="bddc5-106">A message should be closed only once.</span></span> <span data-ttu-id="bddc5-107">このトレースがユーザー拡張コード内で出力されている場合は、ユーザー拡張コードは既に閉じられているメッセージをさらに閉じようとしていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="bddc5-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="bddc5-108">このトレースが製品のコード内で出力されている場合は、ユーザー拡張コードがメッセージを閉じるのが早すぎる可能性があることが示されています。</span><span class="sxs-lookup"><span data-stu-id="bddc5-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddc5-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="bddc5-109">See also</span></span>

- [<span data-ttu-id="bddc5-110">トレース</span><span class="sxs-lookup"><span data-stu-id="bddc5-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="bddc5-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="bddc5-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="bddc5-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="bddc5-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
