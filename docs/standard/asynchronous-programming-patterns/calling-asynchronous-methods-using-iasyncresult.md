---
title: IAsyncResult を使用した非同期メソッドの呼び出し
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
ms.openlocfilehash: 2a9ce8bc2d2edd09ef79c060b9bb173d4d054d02
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121313"
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a><span data-ttu-id="3693d-102">IAsyncResult を使用した非同期メソッドの呼び出し</span><span class="sxs-lookup"><span data-stu-id="3693d-102">Calling Asynchronous Methods Using IAsyncResult</span></span>
<span data-ttu-id="3693d-103">.NET Framework とサードパーティのさまざま種類のクラス ライブラリが提供するメソッドを利用することで、アプリケーションはメインのアプリケーション スレッド以外のスレッドで非同期操作を実行しながら実行を継続できます。</span><span class="sxs-lookup"><span data-stu-id="3693d-103">Types in the .NET Framework and third-party class libraries can provide methods that allow an application to continue executing while performing asynchronous operations in threads other than the main application thread.</span></span> <span data-ttu-id="3693d-104">次のセクションでは、コード例を取り上げ、<xref:System.IAsyncResult> 設計パターンを使用する非同期メソッドをさまざまな方法で呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3693d-104">The following sections describe and provide code examples that demonstrate the different ways you can call asynchronous methods that use the <xref:System.IAsyncResult> design pattern.</span></span>  
  
- <span data-ttu-id="3693d-105">[非同期操作の終了によるアプリケーション実行のブロック](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="3693d-105">[Blocking Application Execution by Ending an Async Operation](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md).</span></span>  
  
- <span data-ttu-id="3693d-106">[AsyncWaitHandle の使用によるアプリケーション実行のブロック](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)。</span><span class="sxs-lookup"><span data-stu-id="3693d-106">[Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md).</span></span>  
  
- <span data-ttu-id="3693d-107">[非同期操作のステータスのポーリング](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="3693d-107">[Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md).</span></span>  
  
- <span data-ttu-id="3693d-108">[AsyncCallback デリゲートの使用による非同期操作の終了](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)。</span><span class="sxs-lookup"><span data-stu-id="3693d-108">[Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3693d-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="3693d-109">See also</span></span>

- [<span data-ttu-id="3693d-110">イベント ベースの非同期パターン (EAP)</span><span class="sxs-lookup"><span data-stu-id="3693d-110">Event-based Asynchronous Pattern (EAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
- [<span data-ttu-id="3693d-111">イベントベースの非同期パターンの概要</span><span class="sxs-lookup"><span data-stu-id="3693d-111">Event-based Asynchronous Pattern Overview</span></span>](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
