---
title: System.ServiceModel.MessageClosedAgain
ms.date: 03/30/2017
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
ms.openlocfilehash: d341953b8e12b14e6a3fe8a477c16a1b3a4454ae
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84580438"
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="760a2-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="760a2-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="760a2-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="760a2-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="760a2-104">説明</span><span class="sxs-lookup"><span data-stu-id="760a2-104">Description</span></span>  
 <span data-ttu-id="760a2-105">メッセージがもう一度閉じられました。</span><span class="sxs-lookup"><span data-stu-id="760a2-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="760a2-106">メッセージを閉じることができるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="760a2-106">A message should be closed only once.</span></span> <span data-ttu-id="760a2-107">このトレースがユーザー拡張コード内で出力されている場合は、ユーザー拡張コードは既に閉じられているメッセージをさらに閉じようとしていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="760a2-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="760a2-108">このトレースが製品のコード内で出力されている場合は、ユーザー拡張コードがメッセージを閉じるのが早すぎる可能性があることが示されています。</span><span class="sxs-lookup"><span data-stu-id="760a2-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="760a2-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="760a2-109">See also</span></span>

- [<span data-ttu-id="760a2-110">トレース</span><span class="sxs-lookup"><span data-stu-id="760a2-110">Tracing</span></span>](index.md)
- [<span data-ttu-id="760a2-111">トレースを使用したアプリケーションのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="760a2-111">Using Tracing to Troubleshoot Your Application</span></span>](using-tracing-to-troubleshoot-your-application.md)
- [<span data-ttu-id="760a2-112">管理と診断</span><span class="sxs-lookup"><span data-stu-id="760a2-112">Administration and Diagnostics</span></span>](../index.md)
