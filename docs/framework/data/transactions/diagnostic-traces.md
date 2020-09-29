---
title: 診断トレース
description: .NET の診断トレースについて説明します。 トレースとは、アプリケーションの実行中に生成される特定のメッセージの発行です。
ms.date: 03/30/2017
ms.assetid: 28e77a63-d20d-4b6a-9caf-ddad86550427
ms.openlocfilehash: 1999cd922b9e7299cbf3c10a702eb4d2dc6c3fbb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177242"
---
# <a name="diagnostic-traces"></a><span data-ttu-id="14f3a-104">診断トレース</span><span class="sxs-lookup"><span data-stu-id="14f3a-104">Diagnostic Traces</span></span>

<span data-ttu-id="14f3a-105">トレースとは、アプリケーションの実行中に生成される特定のメッセージの発行です。</span><span class="sxs-lookup"><span data-stu-id="14f3a-105">Traces are the publishing of specific messages that are generated during application execution.</span></span> <span data-ttu-id="14f3a-106">トレースを使用するときには、送信されたメッセージを収集して記録するための機構が必要です。</span><span class="sxs-lookup"><span data-stu-id="14f3a-106">When using tracing, you must have a mechanism for collecting and recording the messages that are sent.</span></span> <span data-ttu-id="14f3a-107">トレース メッセージは "リスナー" によって受け取られます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-107">Trace messages are received by listeners.</span></span> <span data-ttu-id="14f3a-108">リスナーの目的は、トレース メッセージの収集、格納、およびルーティングを行うことです。</span><span class="sxs-lookup"><span data-stu-id="14f3a-108">The purpose of a listener is to collect, store, and route tracing messages.</span></span> <span data-ttu-id="14f3a-109">リスナーにより、トレース出力が適切な場所 (ログ、ウィンドウ、またはテキスト ファイル) に送られます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-109">Listeners direct the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="14f3a-110">トレースを有効にすると、こうしたリスナーの 1 つである <xref:System.Diagnostics.DefaultTraceListener> が自動的に作成および初期化されます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-110">One such listener, the <xref:System.Diagnostics.DefaultTraceListener>, is automatically created and initialized when tracing is enabled.</span></span> <span data-ttu-id="14f3a-111">トレース出力を別のソースに送るには、別のトレース リスナーを作成して初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-111">If you want trace output to be directed to any additional sources, you must create and initialize additional trace listeners.</span></span> <span data-ttu-id="14f3a-112">作成するリスナーには、個別の要求が反映されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-112">The listeners you create should reflect your individual needs.</span></span> <span data-ttu-id="14f3a-113">たとえば、すべてのトレース出力のテキスト レコードが必要である場合は、</span><span class="sxs-lookup"><span data-stu-id="14f3a-113">For example, you might want a text record of all trace output.</span></span> <span data-ttu-id="14f3a-114">有効になったときにすべての出力を新しいテキスト ファイルに書き込むリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f3a-114">In this case, you would create a listener that wrote all output to a new text file when enabled.</span></span> <span data-ttu-id="14f3a-115">また、アプリケーションの実行時に出力を表示するだけでよい場合は、</span><span class="sxs-lookup"><span data-stu-id="14f3a-115">On the other hand, you might only want to view output during application execution.</span></span> <span data-ttu-id="14f3a-116">すべての出力をコンソール ウィンドウに送るリスナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="14f3a-116">In that case, you might create a listener that directed all output to a console window.</span></span> <span data-ttu-id="14f3a-117"><xref:System.Diagnostics.EventLogTraceListener> はイベント ログにトレース出力を転送し、<xref:System.Diagnostics.TextWriterTraceListener> はストリームにトレース出力を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-117">The <xref:System.Diagnostics.EventLogTraceListener> can direct trace output to an event log, and the <xref:System.Diagnostics.TextWriterTraceListener> can write trace output to a stream.</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="14f3a-118">トレースの有効化</span><span class="sxs-lookup"><span data-stu-id="14f3a-118">Enabling Tracing</span></span>  

 <span data-ttu-id="14f3a-119">トランザクション処理中にトレースを有効にするには、アプリケーションの構成ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-119">To enable traces during transaction processing, you should edit your application’s configuration file.</span></span> <span data-ttu-id="14f3a-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="14f3a-120">The following is an example.</span></span>  
  
```xml  
<configuration>  
<system.diagnostics>  
     <sources>  
          <source name="System.Transactions" switchValue="Warning">  
               <listeners>  
                    <add name="tx"
                     type="System.Diagnostics.XmlWriterTraceListener"
                     initializeData= "tx.log" />  
               </listeners>  
          </source>  
     </sources>  
</system.diagnostics>  
</configuration>  
```  
  
 <span data-ttu-id="14f3a-121"><xref:System.Transactions> トレースは、"System.Transactions" という名前のソースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-121"><xref:System.Transactions> traces are written to the source named "System.Transactions".</span></span> <span data-ttu-id="14f3a-122">`add` を使用して、使用するトレース リスナーの名前と種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-122">You can use `add` to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="14f3a-123">この例の構成では、リスナーに "tx" という名前を付け、使用する種類として標準の .NET Framework トレース リスナー (<xref:System.Diagnostics.XmlWriterTraceListener>) を追加しています。</span><span class="sxs-lookup"><span data-stu-id="14f3a-123">In our example configuration, we named the Listener "tx" and added the standard .NET Framework trace listener (<xref:System.Diagnostics.XmlWriterTraceListener>) as the type we want to use.</span></span> <span data-ttu-id="14f3a-124">`initializeData` を使用して、リスナーのログ ファイルの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="14f3a-124">Use `initializeData` to set the name of the log file for that listener.</span></span> <span data-ttu-id="14f3a-125">さらに、単純なファイル名と完全修飾パスを置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-125">In addition, you can substitute a fully qualified path for a simple file name.</span></span>  
  
 <span data-ttu-id="14f3a-126">各トレース メッセージの種類は、その重大度を示すレベルに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-126">Each trace message type is assigned a level to indicate its degree of importance.</span></span> <span data-ttu-id="14f3a-127">アプリケーション ドメインのトレース レベルがイベント タイプのレベル以下である場合、そのメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-127">If the app-domain’s trace level is equal or lower than the level of an event type, then that message is generated.</span></span> <span data-ttu-id="14f3a-128">トレース レベルは、構成ファイルの `switchValue` 設定で制御します。</span><span class="sxs-lookup"><span data-stu-id="14f3a-128">The tracing level is controlled by the `switchValue` setting in the configuration file.</span></span> <span data-ttu-id="14f3a-129">次の表に、診断トレース メッセージに関連するレベルの定義を示します。</span><span class="sxs-lookup"><span data-stu-id="14f3a-129">The levels that are associated with diagnostic trace messages are defined in the following table.</span></span>  
  
|<span data-ttu-id="14f3a-130">トレース レベル</span><span class="sxs-lookup"><span data-stu-id="14f3a-130">Trace Level</span></span>|<span data-ttu-id="14f3a-131">説明</span><span class="sxs-lookup"><span data-stu-id="14f3a-131">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="14f3a-132">重大</span><span class="sxs-lookup"><span data-stu-id="14f3a-132">Critical</span></span>|<span data-ttu-id="14f3a-133">次のような重大な障害が発生しました。</span><span class="sxs-lookup"><span data-stu-id="14f3a-133">Serious failures, such as the following, have occurred:</span></span><br /><br /> <span data-ttu-id="14f3a-134">-   ユーザー機能が即座に失われる可能性のあるエラー。</span><span class="sxs-lookup"><span data-stu-id="14f3a-134">-   An error that can cause an immediate loss in user functionality.</span></span><br /><span data-ttu-id="14f3a-135">-   機能が失われるのを防ぐために管理者が対処する必要のあるイベント。</span><span class="sxs-lookup"><span data-stu-id="14f3a-135">-   An event that requires an administrator to take action to avoid loss of functionality.</span></span><br /><span data-ttu-id="14f3a-136">-   コードのハング。</span><span class="sxs-lookup"><span data-stu-id="14f3a-136">-   Code hangs.</span></span><br /><span data-ttu-id="14f3a-137">-   このトレース レベルでは、他の重大なトレースを解釈するための十分なコンテキストも提供できます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-137">-   This tracing level can also provide sufficient context for interpreting other critical traces.</span></span> <span data-ttu-id="14f3a-138">これは、重大なエラーにつながる操作シーケンスの特定に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-138">This can help to identify the sequence of operations leading to a serious failure.</span></span>|  
|<span data-ttu-id="14f3a-139">Error</span><span class="sxs-lookup"><span data-stu-id="14f3a-139">Error</span></span>|<span data-ttu-id="14f3a-140">ユーザー機能の損失につながるエラー (無効な設定、ネットワークの動作など) が発生しました。</span><span class="sxs-lookup"><span data-stu-id="14f3a-140">An error (for example, invalid configuration or network behavior) has occurred that can result in a loss of user functionality.</span></span>|  
|<span data-ttu-id="14f3a-141">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-141">Warning</span></span>|<span data-ttu-id="14f3a-142">後続の処理でエラーまたは重大なエラーが起こる可能性のある状態が存在します (割り当ての失敗、制限への接近など)。</span><span class="sxs-lookup"><span data-stu-id="14f3a-142">A condition exists that can subsequently result in an error or critical failure (for example, allocation failing or approaching a limit).</span></span> <span data-ttu-id="14f3a-143">ユーザー コードからのエラーの通常処理 (トランザクションの中止、タイムアウト、認証の失敗など) が警告を生成する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-143">Normal processing of errors from user code (for example, transaction aborted, timeouts, authentication failed) can also generate a warning.</span></span>|  
|<span data-ttu-id="14f3a-144">情報</span><span class="sxs-lookup"><span data-stu-id="14f3a-144">Information</span></span>|<span data-ttu-id="14f3a-145">システム ステータスの監視と診断、パフォーマンスの計測、またはプロファイリングに有用なメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-145">Messages helpful for monitoring and diagnosing system status, measuring performance, or profiling are generated.</span></span> <span data-ttu-id="14f3a-146">これには、トランザクションの作成またはコミット、重要な境界の超過、重要なリソースの割り当てなど、トランザクションと参加の有効期間イベントが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-146">These can include transaction and enlistment lifetime events, such as a transaction being created or committed, the crossing of a significant boundary, or the allocation of significant resources.</span></span> <span data-ttu-id="14f3a-147">このような情報は、後で開発者が容量設計やパフォーマンス管理に利用できます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-147">A developer can then utilize such information for capacity planning and performance management.</span></span>|  
  
## <a name="trace-codes"></a><span data-ttu-id="14f3a-148">トレース コード</span><span class="sxs-lookup"><span data-stu-id="14f3a-148">Trace Codes</span></span>  

 <span data-ttu-id="14f3a-149">次の表は、<xref:System.Transactions> インフラストラクチャで生成されるトレース コードの一覧です。</span><span class="sxs-lookup"><span data-stu-id="14f3a-149">The following table lists the trace codes that are generated by the <xref:System.Transactions> infrastructure.</span></span> <span data-ttu-id="14f3a-150">この表には、トレース コード識別子、トレースの <xref:System.Diagnostics.EventTypeFilter.EventType%2A> 列挙レベル、およびトレースの **TraceRecord** に含まれる追加データが示されています。</span><span class="sxs-lookup"><span data-stu-id="14f3a-150">Included in the table are the trace code identifier, the <xref:System.Diagnostics.EventTypeFilter.EventType%2A> enumeration level for the trace, and the extra data contained in the **TraceRecord** for the trace.</span></span> <span data-ttu-id="14f3a-151">さらに、そのトレースに対応するトレース レベルも **TraceRecord** に保存されます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-151">In addition, the corresponding trace level of the trace is also stored in the **TraceRecord**.</span></span>  
  
|<span data-ttu-id="14f3a-152">TraceCode</span><span class="sxs-lookup"><span data-stu-id="14f3a-152">TraceCode</span></span>|<span data-ttu-id="14f3a-153">EventType</span><span class="sxs-lookup"><span data-stu-id="14f3a-153">EventType</span></span>|<span data-ttu-id="14f3a-154">TraceRecord の追加データ</span><span class="sxs-lookup"><span data-stu-id="14f3a-154">Extra data in TraceRecord</span></span>|  
|---------------|---------------|-------------------------------|  
|<span data-ttu-id="14f3a-155">TransactionCreated</span><span class="sxs-lookup"><span data-stu-id="14f3a-155">TransactionCreated</span></span>|<span data-ttu-id="14f3a-156">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-156">Info</span></span>|<span data-ttu-id="14f3a-157">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-157">TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-158">TransactionPromoted</span><span class="sxs-lookup"><span data-stu-id="14f3a-158">TransactionPromoted</span></span>|<span data-ttu-id="14f3a-159">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-159">Info</span></span>|<span data-ttu-id="14f3a-160">Local TransactionTraceId、Distributed TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-160">Local TransactionTraceId, Distributed TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-161">EnlistmentCreated</span><span class="sxs-lookup"><span data-stu-id="14f3a-161">EnlistmentCreated</span></span>|<span data-ttu-id="14f3a-162">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-162">Info</span></span>|<span data-ttu-id="14f3a-163">TransactionTraceId、EnlistmentTraceId、EnlistmentType (durable/volatile)、EnlistmentOptions</span><span class="sxs-lookup"><span data-stu-id="14f3a-163">TransactionTraceId, EnlistmentTraceId, EnlistmentType (durable/volatile), EnlistmentOptions</span></span>|  
|<span data-ttu-id="14f3a-164">EnlistmentCallbackNegative</span><span class="sxs-lookup"><span data-stu-id="14f3a-164">EnlistmentCallbackNegative</span></span>|<span data-ttu-id="14f3a-165">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-165">Warning</span></span>|<span data-ttu-id="14f3a-166">TransactionTraceId、EnlistmentTraceId、</span><span class="sxs-lookup"><span data-stu-id="14f3a-166">TransactionTraceId, EnlistmentTraceId,</span></span><br /><br /> <span data-ttu-id="14f3a-167">Callback (forcerollback/aborted/indoubt)</span><span class="sxs-lookup"><span data-stu-id="14f3a-167">Callback (forcerollback/aborted/indoubt)</span></span>|  
|<span data-ttu-id="14f3a-168">TransactionRollbackCalled</span><span class="sxs-lookup"><span data-stu-id="14f3a-168">TransactionRollbackCalled</span></span>|<span data-ttu-id="14f3a-169">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-169">Warning</span></span>|<span data-ttu-id="14f3a-170">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-170">TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-171">TransactionAborted</span><span class="sxs-lookup"><span data-stu-id="14f3a-171">TransactionAborted</span></span>|<span data-ttu-id="14f3a-172">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-172">Warning</span></span>|<span data-ttu-id="14f3a-173">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-173">TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-174">TransactionInDoubt</span><span class="sxs-lookup"><span data-stu-id="14f3a-174">TransactionInDoubt</span></span>|<span data-ttu-id="14f3a-175">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-175">Warning</span></span>|<span data-ttu-id="14f3a-176">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-176">TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-177">TransactionScopeCreated</span><span class="sxs-lookup"><span data-stu-id="14f3a-177">TransactionScopeCreated</span></span>|<span data-ttu-id="14f3a-178">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-178">Info</span></span>|<span data-ttu-id="14f3a-179">TransactionScopeResult (次のようになります)</span><span class="sxs-lookup"><span data-stu-id="14f3a-179">TransactionScopeResult, which can be the following:</span></span><br /><br /> <span data-ttu-id="14f3a-180">-   新しいトランザクション。</span><span class="sxs-lookup"><span data-stu-id="14f3a-180">-   New transaction.</span></span><br /><span data-ttu-id="14f3a-181">-   渡されたトランザクション。</span><span class="sxs-lookup"><span data-stu-id="14f3a-181">-   Transaction passed.</span></span><br /><span data-ttu-id="14f3a-182">-   渡された依存トランザクション。</span><span class="sxs-lookup"><span data-stu-id="14f3a-182">-   Dependent transaction passed.</span></span><br /><span data-ttu-id="14f3a-183">-   現在のトランザクションを使用。</span><span class="sxs-lookup"><span data-stu-id="14f3a-183">-   Using current transaction.</span></span><br /><span data-ttu-id="14f3a-184">-   トランザクションなし</span><span class="sxs-lookup"><span data-stu-id="14f3a-184">-   No transaction.</span></span><br /><br /> <span data-ttu-id="14f3a-185">新しい現在の TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-185">new current TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-186">TransactionScopeDisposed</span><span class="sxs-lookup"><span data-stu-id="14f3a-186">TransactionScopeDisposed</span></span>|<span data-ttu-id="14f3a-187">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-187">Info</span></span>|<span data-ttu-id="14f3a-188">スコープの "想定される" 現在のトランザクションの TransactionTraceId。</span><span class="sxs-lookup"><span data-stu-id="14f3a-188">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="14f3a-189">TransactionScopeIncomplete</span><span class="sxs-lookup"><span data-stu-id="14f3a-189">TransactionScopeIncomplete</span></span>|<span data-ttu-id="14f3a-190">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-190">Warning</span></span>|<span data-ttu-id="14f3a-191">スコープの "想定される" 現在のトランザクションの TransactionTraceId。</span><span class="sxs-lookup"><span data-stu-id="14f3a-191">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="14f3a-192">TransactionScopeNestedIncorrectly</span><span class="sxs-lookup"><span data-stu-id="14f3a-192">TransactionScopeNestedIncorrectly</span></span>|<span data-ttu-id="14f3a-193">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-193">Warning</span></span>|<span data-ttu-id="14f3a-194">スコープの "想定される" 現在のトランザクションの TransactionTraceId。</span><span class="sxs-lookup"><span data-stu-id="14f3a-194">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="14f3a-195">TransactionScopeCurrentTransactionChanged</span><span class="sxs-lookup"><span data-stu-id="14f3a-195">TransactionScopeCurrentTransactionChanged</span></span>|<span data-ttu-id="14f3a-196">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-196">Warning</span></span>|<span data-ttu-id="14f3a-197">古い (現在の) TransactionTraceId、他の TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-197">Old current TransactionTraceId, other TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-198">TransactionScopeTimeout</span><span class="sxs-lookup"><span data-stu-id="14f3a-198">TransactionScopeTimeout</span></span>|<span data-ttu-id="14f3a-199">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-199">Warning</span></span>|<span data-ttu-id="14f3a-200">スコープの "想定される" 現在のトランザクションの TransactionTraceId。</span><span class="sxs-lookup"><span data-stu-id="14f3a-200">TransactionTraceId of the scope’s "expected" current transaction.</span></span>|  
|<span data-ttu-id="14f3a-201">DependentCloneCreated</span><span class="sxs-lookup"><span data-stu-id="14f3a-201">DependentCloneCreated</span></span>|<span data-ttu-id="14f3a-202">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-202">Info</span></span>|<span data-ttu-id="14f3a-203">TransactionTraceId、作成される依存トランザクションの種類 (RollbackIfNotComplete/BlockCommitUntilComplete)</span><span class="sxs-lookup"><span data-stu-id="14f3a-203">TransactionTraceId, type of dependent transaction created (RollbackIfNotComplete/BlockCommitUntilComplete)</span></span>|  
|<span data-ttu-id="14f3a-204">DependentCloneComplete</span><span class="sxs-lookup"><span data-stu-id="14f3a-204">DependentCloneComplete</span></span>|<span data-ttu-id="14f3a-205">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-205">Info</span></span>|<span data-ttu-id="14f3a-206">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-206">TransactionTraceId</span></span>|  
|<span data-ttu-id="14f3a-207">RecoveryComplete</span><span class="sxs-lookup"><span data-stu-id="14f3a-207">RecoveryComplete</span></span>|<span data-ttu-id="14f3a-208">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-208">Info</span></span>|<span data-ttu-id="14f3a-209">リソース マネージャー GUID (ベースから)</span><span class="sxs-lookup"><span data-stu-id="14f3a-209">Resource Manager GUID (from base)</span></span>|  
|<span data-ttu-id="14f3a-210">Reenlist</span><span class="sxs-lookup"><span data-stu-id="14f3a-210">Reenlist</span></span>|<span data-ttu-id="14f3a-211">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-211">Info</span></span>|<span data-ttu-id="14f3a-212">リソース マネージャー GUID (ベースから)</span><span class="sxs-lookup"><span data-stu-id="14f3a-212">Resource Manager GUID (from base)</span></span>|  
|<span data-ttu-id="14f3a-213">TransactionSerialized</span><span class="sxs-lookup"><span data-stu-id="14f3a-213">TransactionSerialized</span></span>|<span data-ttu-id="14f3a-214">Info</span><span class="sxs-lookup"><span data-stu-id="14f3a-214">Info</span></span>|<span data-ttu-id="14f3a-215">TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-215">TransactionTraceId.</span></span>|  
|<span data-ttu-id="14f3a-216">TransactionException</span><span class="sxs-lookup"><span data-stu-id="14f3a-216">TransactionException</span></span>|<span data-ttu-id="14f3a-217">Error</span><span class="sxs-lookup"><span data-stu-id="14f3a-217">Error</span></span>|<span data-ttu-id="14f3a-218">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="14f3a-218">Exception message</span></span>|  
|<span data-ttu-id="14f3a-219">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="14f3a-219">InvalidOperationException</span></span>|<span data-ttu-id="14f3a-220">Error</span><span class="sxs-lookup"><span data-stu-id="14f3a-220">Error</span></span>|<span data-ttu-id="14f3a-221">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="14f3a-221">Exception message</span></span>|  
|<span data-ttu-id="14f3a-222">InternalError</span><span class="sxs-lookup"><span data-stu-id="14f3a-222">InternalError</span></span>|<span data-ttu-id="14f3a-223">重大</span><span class="sxs-lookup"><span data-stu-id="14f3a-223">Critical</span></span>|<span data-ttu-id="14f3a-224">例外メッセージ</span><span class="sxs-lookup"><span data-stu-id="14f3a-224">Exception message</span></span>|  
|<span data-ttu-id="14f3a-225">TransferEvent</span><span class="sxs-lookup"><span data-stu-id="14f3a-225">TransferEvent</span></span>||<span data-ttu-id="14f3a-226">トランザクションが逆シリアル化されるか、または <xref:System.Transactions> トランザクションから分散トランザクションに昇格される場合、ExecutionContext の現在の ActivityID および分散トランザクション ID が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-226">When a transaction is deserialized, or promoted from a <xref:System.Transactions> transaction to a distributed one, the current ActivityID from the ExecutionContext and the distributed transaction ID are written.</span></span><br /><br /> <span data-ttu-id="14f3a-227">DTC がマネージド コードにコールバックする場合、コールバックの間、分散トランザクション ID が ExecutionContext の ActivityID として設定されます。</span><span class="sxs-lookup"><span data-stu-id="14f3a-227">When the DTC calls back into managed code, the distributed transaction ID is set as the ActivityID in the ExecutionContext for the duration of the callback.</span></span>|  
|<span data-ttu-id="14f3a-228">ConfiguredDefaultTimeoutAdjusted</span><span class="sxs-lookup"><span data-stu-id="14f3a-228">ConfiguredDefaultTimeoutAdjusted</span></span>|<span data-ttu-id="14f3a-229">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-229">Warning</span></span>|<span data-ttu-id="14f3a-230">追加データなし</span><span class="sxs-lookup"><span data-stu-id="14f3a-230">No extra data</span></span>|  
|<span data-ttu-id="14f3a-231">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="14f3a-231">TransactionTimeout</span></span>|<span data-ttu-id="14f3a-232">警告</span><span class="sxs-lookup"><span data-stu-id="14f3a-232">Warning</span></span>|<span data-ttu-id="14f3a-233">タイムアウトするトランザクションの TransactionTraceId</span><span class="sxs-lookup"><span data-stu-id="14f3a-233">The TransactionTraceId of the transaction being timed out.</span></span>|  
  
 <span data-ttu-id="14f3a-234">上の各追加データ項目に対する XML スキーマの形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14f3a-234">The XML schema for each of the preceding extra data items has the following format.</span></span>  
  
### <a name="transactiontraceidentifier"></a><span data-ttu-id="14f3a-235">TransactionTraceIdentifier</span><span class="sxs-lookup"><span data-stu-id="14f3a-235">TransactionTraceIdentifier</span></span>  

 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `< CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `</TransactionTraceIdentifier>`  
  
### <a name="enlistmenttraceidentifier"></a><span data-ttu-id="14f3a-236">EnlistmentTraceIdentifier</span><span class="sxs-lookup"><span data-stu-id="14f3a-236">EnlistmentTraceIdentifier</span></span>  

 `<EnlistmentTraceIdentifier>`  
  
 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<TransactionIdentifier >`  
  
 `string representation of transaction id`  
  
 `</TransactionIdentifier>`  
  
 `<CloneIdentifier >`  
  
 `the clone id number`  
  
 `</CloneIdentifier>`  
  
 `<TransactionTraceIdentifier>`  
  
 `<EnlistmentIdentifier>`  
  
 `the enlistment id number`  
  
 `</EnlistmentIdentifier>`  
  
 `</EnlistmentTraceIdentifier>`  
  
### <a name="resource-manager-identifier"></a><span data-ttu-id="14f3a-237">リソース マネージャー識別子</span><span class="sxs-lookup"><span data-stu-id="14f3a-237">Resource Manager Identifier</span></span>  

 `<ResourceManagerId>`  
  
 `string form of guid`  
  
 `</ResourceManagerId>`  
  
## <a name="security-issues-for-tracing"></a><span data-ttu-id="14f3a-238">トレースのセキュリティに関する問題</span><span class="sxs-lookup"><span data-stu-id="14f3a-238">Security Issues For Tracing</span></span>  

 <span data-ttu-id="14f3a-239">管理者がトレース機能を有効にすると、既定で、パブリックに表示可能なトレース ログに機密情報が書き込まれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-239">When you as an administrator turn on tracing, sensitive information might be written to a trace log that is publicly viewable by default.</span></span> <span data-ttu-id="14f3a-240">潜在的なセキュリティの脅威を緩和するため、共有およびファイル システムのアクセス許可によって管理される安全な場所にトレース ログを保存することを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14f3a-240">To mitigate any possible security threat, you should consider storing the trace log in a secure location controlled by share and file system access permissions.</span></span>
