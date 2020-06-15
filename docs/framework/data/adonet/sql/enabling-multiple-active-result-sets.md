---
title: 複数のアクティブな結果セットの有効化
description: 接続文字列で MARS を有効または無効にする方法について説明します。MARS は、SQL Server で動作し、複数のバッチを ADO.NET の単一の接続で実行できます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 576079e4-debe-4ab5-9204-fcbe2ca7a5e2
ms.openlocfilehash: 43bdfebce291c3c1d6c90104c5fef440b295934b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286482"
---
# <a name="enabling-multiple-active-result-sets"></a><span data-ttu-id="22e67-103">複数のアクティブな結果セットの有効化</span><span class="sxs-lookup"><span data-stu-id="22e67-103">Enabling Multiple Active Result Sets</span></span>
<span data-ttu-id="22e67-104">複数のアクティブな結果セット (MARS : Multiple Active Result Set) は、SQL Server で動作する機能であり、複数のバッチを単一の接続で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="22e67-104">Multiple Active Result Sets (MARS) is a feature that works with SQL Server to allow the execution of multiple batches on a single connection.</span></span> <span data-ttu-id="22e67-105">SQL Server で使用できるように MARS が有効になっているときは、使用中の各コマンド オブジェクトは接続にセッションを追加します。</span><span class="sxs-lookup"><span data-stu-id="22e67-105">When MARS is enabled for use with SQL Server, each command object used adds a session to the connection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22e67-106">単一の MARS セッションは、MARS 用に 1 つの論理接続を開いた後、アクティブな各コマンドにつき 1 つの論理接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="22e67-106">A single MARS session opens one logical connection for MARS to use and then one logical connection for each active command.</span></span>  
  
## <a name="enabling-and-disabling-mars-in-the-connection-string"></a><span data-ttu-id="22e67-107">接続文字列で MARS を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="22e67-107">Enabling and Disabling MARS in the Connection String</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22e67-108">次の接続文字列では、SQL Server に含まれるサンプルの **AdventureWorks** データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e67-108">The following connection strings use the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="22e67-109">指定されている接続文字列は、データベースが MSSQL1 という名前のサーバーにインストールされているものとします。</span><span class="sxs-lookup"><span data-stu-id="22e67-109">The connection strings provided assume that the database is installed on a server named MSSQL1.</span></span> <span data-ttu-id="22e67-110">実際の環境では必要に応じて接続文字列を変更してください。</span><span class="sxs-lookup"><span data-stu-id="22e67-110">Modify the connection string as necessary for your environment.</span></span>  
  
 <span data-ttu-id="22e67-111">既定では、MARS 機能は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="22e67-111">The MARS feature is disabled by default.</span></span> <span data-ttu-id="22e67-112">これは、接続文字列に "MultipleActiveResultSets=True" キーワード ペアを追加することによって有効にできます。</span><span class="sxs-lookup"><span data-stu-id="22e67-112">It can be enabled by adding the "MultipleActiveResultSets=True" keyword pair to your connection string.</span></span> <span data-ttu-id="22e67-113">"True" は、MARS を有効にするための唯一の有効な値です。</span><span class="sxs-lookup"><span data-stu-id="22e67-113">"True" is the only valid value for enabling MARS.</span></span> <span data-ttu-id="22e67-114">次の例は、SQL Server のインスタンスに接続する方法、および MARS を有効にすることを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="22e67-114">The following example demonstrates how to connect to an instance of SQL Server and how to specify that MARS should be enabled.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=True"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=True";  
```  
  
 <span data-ttu-id="22e67-115">MARS は、接続文字列に "MultipleActiveResultSets=False" キーワード ペアを追加することによって無効にできます。</span><span class="sxs-lookup"><span data-stu-id="22e67-115">You can disable MARS by adding the "MultipleActiveResultSets=False" keyword pair to your connection string.</span></span> <span data-ttu-id="22e67-116">"False" は、MARS を無効にするための唯一の有効な値です。</span><span class="sxs-lookup"><span data-stu-id="22e67-116">"False" is the only valid value for disabling MARS.</span></span> <span data-ttu-id="22e67-117">次の接続文字列では、MARS を無効にしています。</span><span class="sxs-lookup"><span data-stu-id="22e67-117">The following connection string demonstrates how to disable MARS.</span></span>  
  
```vb  
Dim connectionString As String = "Data Source=MSSQL1;" & _  
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" & _  
    "MultipleActiveResultSets=False"  
```  
  
```csharp  
string connectionString = "Data Source=MSSQL1;" +
    "Initial Catalog=AdventureWorks;Integrated Security=SSPI;" +  
    "MultipleActiveResultSets=False";  
```  
  
## <a name="special-considerations-when-using-mars"></a><span data-ttu-id="22e67-118">MARS の使用に関する特記事項</span><span class="sxs-lookup"><span data-stu-id="22e67-118">Special Considerations When Using MARS</span></span>  
 <span data-ttu-id="22e67-119">一般に、MARS の有効な接続を使用するために、既存のアプリケーションを修正する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="22e67-119">In general, existing applications should not need modification to use a MARS-enabled connection.</span></span> <span data-ttu-id="22e67-120">ただし、MARS 機能をご自分のアプリケーションで使用する場合、次の特記事項について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e67-120">However, if you wish to use MARS features in your applications, you should understand the following special considerations.</span></span>  
  
### <a name="statement-interleaving"></a><span data-ttu-id="22e67-121">ステートメント インタリーブ</span><span class="sxs-lookup"><span data-stu-id="22e67-121">Statement Interleaving</span></span>  
 <span data-ttu-id="22e67-122">MARS 操作は、サーバー上で同期して実行されます。</span><span class="sxs-lookup"><span data-stu-id="22e67-122">MARS operations execute synchronously on the server.</span></span> <span data-ttu-id="22e67-123">SELECT および BULK INSERT ステートメントのステートメントのインターリーブが許可されます。</span><span class="sxs-lookup"><span data-stu-id="22e67-123">Statement interleaving of SELECT and BULK INSERT statements is allowed.</span></span> <span data-ttu-id="22e67-124">ただし、データ操作言語 (DML) およびデータ定義言語 (DDL) ステートメントはアトミックに実行されます。</span><span class="sxs-lookup"><span data-stu-id="22e67-124">However, data manipulation language (DML) and data definition language (DDL) statements execute atomically.</span></span> <span data-ttu-id="22e67-125">アトミック バッチの実行中にステートメントを実行しようとすると、すべてブロックされます。</span><span class="sxs-lookup"><span data-stu-id="22e67-125">Any statements attempting to execute while an atomic batch is executing are blocked.</span></span> <span data-ttu-id="22e67-126">サーバーでの並列実行は MARS 機能ではありません。</span><span class="sxs-lookup"><span data-stu-id="22e67-126">Parallel execution at the server is not a MARS feature.</span></span>  
  
 <span data-ttu-id="22e67-127">MARS 接続のもとで 2 つのバッチが送信され、そのうちの 1 つに SELECT ステートメントが含まれ、もう一方に DML ステートメントが含まれている場合は、SELECT ステートメントの実行内で DML の実行を開始できます。</span><span class="sxs-lookup"><span data-stu-id="22e67-127">If two batches are submitted under a MARS connection, one of them containing a SELECT statement, the other containing a DML statement, the DML can begin execution within execution of the SELECT statement.</span></span> <span data-ttu-id="22e67-128">ただし、SELECT ステートメントが先に進むには、DML ステートメントが実行を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e67-128">However, the DML statement must run to completion before the SELECT statement can make progress.</span></span> <span data-ttu-id="22e67-129">両方のステートメントが同じトランザクションのもとで実行されている場合、SELECT ステートメントが実行を開始した後で DML ステートメントが行ったすべての変更は読み取り操作に表示されません。</span><span class="sxs-lookup"><span data-stu-id="22e67-129">If both statements are running under the same transaction, any changes made by a DML statement after the SELECT statement has started execution are not visible to the read operation.</span></span>  
  
 <span data-ttu-id="22e67-130">SELECT ステートメント内の WAITFOR ステートメントは、待機中、つまり最初の行が生成されるまではトランザクションを生成しません。</span><span class="sxs-lookup"><span data-stu-id="22e67-130">A WAITFOR statement inside a SELECT statement does not yield the transaction while it is waiting, that is, until the first row is produced.</span></span> <span data-ttu-id="22e67-131">これは、WAITFOR ステートメントが待機している間は、同一の接続内では他のいかなるバッチも実行されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="22e67-131">This implies that no other batches can execute within the same connection while a WAITFOR statement is waiting.</span></span>  
  
### <a name="mars-session-cache"></a><span data-ttu-id="22e67-132">MARS セッションのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="22e67-132">MARS Session Cache</span></span>  
 <span data-ttu-id="22e67-133">MARS を有効にして接続が開かれている場合、論理セッションが作成されます。このセッションによってオーバーヘッドが増加します。</span><span class="sxs-lookup"><span data-stu-id="22e67-133">When a connection is opened with MARS enabled, a logical session is created, which adds additional overhead.</span></span> <span data-ttu-id="22e67-134">オーバーヘッドを最小化してパフォーマンスを向上させるため、**SqlClient** は接続内の MARS セッションをキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="22e67-134">To minimize overhead and enhance performance, **SqlClient** caches the MARS session within a connection.</span></span> <span data-ttu-id="22e67-135">このキャッシュには、最大で 10 個の MARS セッションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="22e67-135">The cache contains at most 10 MARS sessions.</span></span> <span data-ttu-id="22e67-136">この値をユーザーが調整することはできません。</span><span class="sxs-lookup"><span data-stu-id="22e67-136">This value is not user adjustable.</span></span> <span data-ttu-id="22e67-137">セッションの制限に達した場合は、新しいセッションが作成され、エラーは生成されません。</span><span class="sxs-lookup"><span data-stu-id="22e67-137">If the session limit is reached, a new session is created—an error is not generated.</span></span> <span data-ttu-id="22e67-138">キャッシュとそこに含まれているセッションは接続ごとに保持され、接続間では共有されません。</span><span class="sxs-lookup"><span data-stu-id="22e67-138">The cache and sessions contained in it are per-connection; they are not shared across connections.</span></span> <span data-ttu-id="22e67-139">セッションが解放されると、プールの上限に達していない限り、そのセッションはプールに返されます。</span><span class="sxs-lookup"><span data-stu-id="22e67-139">When a session is released, it is returned to the pool unless the pool's upper limit has been reached.</span></span> <span data-ttu-id="22e67-140">キャッシュ プールがいっぱいになると、セッションは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="22e67-140">If the cache pool is full, the session is closed.</span></span> <span data-ttu-id="22e67-141">MARS セッションに有効期限はありません。</span><span class="sxs-lookup"><span data-stu-id="22e67-141">MARS sessions do not expire.</span></span> <span data-ttu-id="22e67-142">これらは、接続オブジェクトが破棄された場合にのみクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="22e67-142">They are only cleaned up when the connection object is disposed.</span></span> <span data-ttu-id="22e67-143">MARS セッションのキャッシュは事前には読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="22e67-143">The MARS session cache is not preloaded.</span></span> <span data-ttu-id="22e67-144">アプリケーションがさらに多くのセッションを要求したときに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="22e67-144">It is loaded as the application requires more sessions.</span></span>  
  
### <a name="thread-safety"></a><span data-ttu-id="22e67-145">スレッド セーフ</span><span class="sxs-lookup"><span data-stu-id="22e67-145">Thread Safety</span></span>  
 <span data-ttu-id="22e67-146">MARS 操作は、スレッド セーフではありません。</span><span class="sxs-lookup"><span data-stu-id="22e67-146">MARS operations are not thread-safe.</span></span>  
  
### <a name="connection-pooling"></a><span data-ttu-id="22e67-147">接続プール</span><span class="sxs-lookup"><span data-stu-id="22e67-147">Connection Pooling</span></span>  
 <span data-ttu-id="22e67-148">MARS の有効な接続は、その他の接続と同じようにプールされます。</span><span class="sxs-lookup"><span data-stu-id="22e67-148">MARS-enabled connections are pooled like any other connection.</span></span> <span data-ttu-id="22e67-149">アプリケーションが 2 つの接続を開き、その一方は MARS が有効で他方は MARS が無効になっている場合、それら 2 つの接続は別々のプールに入れられます。</span><span class="sxs-lookup"><span data-stu-id="22e67-149">If an application opens two connections, one with MARS enabled and one with MARS disabled, the two connections are in separate pools.</span></span> <span data-ttu-id="22e67-150">詳しくは、「[SQL Server の接続プール (ADO.NET)](../sql-server-connection-pooling.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="22e67-150">For more information, see [SQL Server Connection Pooling (ADO.NET)](../sql-server-connection-pooling.md).</span></span>  
  
### <a name="sql-server-batch-execution-environment"></a><span data-ttu-id="22e67-151">SQL Server のバッチ実行環境</span><span class="sxs-lookup"><span data-stu-id="22e67-151">SQL Server Batch Execution Environment</span></span>  
 <span data-ttu-id="22e67-152">接続を開くとき、既定の環境が定義されます。</span><span class="sxs-lookup"><span data-stu-id="22e67-152">When a connection is opened, a default environment is defined.</span></span> <span data-ttu-id="22e67-153">その後、この環境が論理 MARS セッションにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22e67-153">This environment is then copied into a logical MARS session.</span></span>  
  
 <span data-ttu-id="22e67-154">バッチ実行環境には、次のコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22e67-154">The batch execution environment includes the following components:</span></span>  
  
- <span data-ttu-id="22e67-155">Set オプション (ANSI_NULLS、DATE_FORMAT、LANGUAGE、TEXTSIZE など)</span><span class="sxs-lookup"><span data-stu-id="22e67-155">Set options (for example, ANSI_NULLS, DATE_FORMAT, LANGUAGE, TEXTSIZE)</span></span>  
  
- <span data-ttu-id="22e67-156">セキュリティ コンテキスト (ユーザー/アプリケーション ロール)</span><span class="sxs-lookup"><span data-stu-id="22e67-156">Security context (user/application role)</span></span>  
  
- <span data-ttu-id="22e67-157">データベース コンテキスト (現在のデータベース)</span><span class="sxs-lookup"><span data-stu-id="22e67-157">Database context (current database)</span></span>  
  
- <span data-ttu-id="22e67-158">実行状態変数 (@@ERROR、@@ROWCOUNT、@@FETCH_STATUS @@IDENTITY など)</span><span class="sxs-lookup"><span data-stu-id="22e67-158">Execution state variables (for example, @@ERROR, @@ROWCOUNT, @@FETCH_STATUS @@IDENTITY)</span></span>  
  
- <span data-ttu-id="22e67-159">最上位の一時テーブル</span><span class="sxs-lookup"><span data-stu-id="22e67-159">Top-level temporary tables</span></span>  
  
 <span data-ttu-id="22e67-160">MARS では、既定の実行環境が接続に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="22e67-160">With MARS, a default execution environment is associated to a connection.</span></span> <span data-ttu-id="22e67-161">所定の接続で実行を開始する新しいバッチは、いずれも既定の環境のコピーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="22e67-161">Every new batch that starts executing under a given connection receives a copy of the default environment.</span></span> <span data-ttu-id="22e67-162">特定のバッチのもとでコードが実行された場合は、常に環境に加えられたすべての変更がその特定のバッチにスコープ指定されます。</span><span class="sxs-lookup"><span data-stu-id="22e67-162">Whenever code is executed under a given batch, all changes made to the environment are scoped to the specific batch.</span></span> <span data-ttu-id="22e67-163">実行が完了すると、実行の設定は既定の環境にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="22e67-163">Once execution finishes, the execution settings are copied into the default environment.</span></span> <span data-ttu-id="22e67-164">単一のバッチが複数のコマンドを発行し、それらが同じトランザクションで連続して実行される場合、そのセマンティクスは、以前のクライアントやサーバーを含む接続で公開されているときのセマンティクスと同じです。</span><span class="sxs-lookup"><span data-stu-id="22e67-164">In the case of a single batch issuing several commands to be executed sequentially under the same transaction, semantics are the same as those exposed by connections involving earlier clients or servers.</span></span>  
  
### <a name="parallel-execution"></a><span data-ttu-id="22e67-165">並列実行</span><span class="sxs-lookup"><span data-stu-id="22e67-165">Parallel Execution</span></span>  
 <span data-ttu-id="22e67-166">MARS は、アプリケーション内で複数の接続に対するすべての要件を削除するようには設計されていません。</span><span class="sxs-lookup"><span data-stu-id="22e67-166">MARS is not designed to remove all requirements for multiple connections in an application.</span></span> <span data-ttu-id="22e67-167">あるアプリケーションで、サーバーに対するコマンドの真の並列実行が必要な場合は、複数の接続を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e67-167">If an application needs true parallel execution of commands against a server, multiple connections should be used.</span></span>  
  
 <span data-ttu-id="22e67-168">たとえば、次のようなシナリオがあるとします。</span><span class="sxs-lookup"><span data-stu-id="22e67-168">For example, consider the following scenario.</span></span> <span data-ttu-id="22e67-169">結果セットを処理するためのコマンド オブジェクトと、データを更新するための別のコマンド オブジェクトの 2 つが作成されます。これらは、MARS 経由で共通の接続を共有します。</span><span class="sxs-lookup"><span data-stu-id="22e67-169">Two command objects are created, one for processing a result set and another for updating data; they share a common connection via MARS.</span></span> <span data-ttu-id="22e67-170">最初のコマンド オブジェクトの結果をすべて読み取るまで、`Transaction`.`Commit` による</span><span class="sxs-lookup"><span data-stu-id="22e67-170">In this scenario, the `Transaction`.`Commit`</span></span> <span data-ttu-id="22e67-171">更新に失敗し、次の例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="22e67-171">fails on the update until all the results have been read on the first command object, yielding the following exception:</span></span>  
  
 <span data-ttu-id="22e67-172">メッセージ:トランザクション コンテキストを他のセッションが使用中です。</span><span class="sxs-lookup"><span data-stu-id="22e67-172">Message: Transaction context in use by another session.</span></span>  
  
 <span data-ttu-id="22e67-173">ソース: .NET SqlClient Data Provider</span><span class="sxs-lookup"><span data-stu-id="22e67-173">Source: .NET SqlClient Data Provider</span></span>  
  
 <span data-ttu-id="22e67-174">期待される出力: (null)</span><span class="sxs-lookup"><span data-stu-id="22e67-174">Expected: (null)</span></span>  
  
 <span data-ttu-id="22e67-175">受信: System.Data.SqlClient.SqlException</span><span class="sxs-lookup"><span data-stu-id="22e67-175">Received: System.Data.SqlClient.SqlException</span></span>  
  
 <span data-ttu-id="22e67-176">このシナリオに対応するには、次の 3 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="22e67-176">There are three options for handling this scenario:</span></span>  
  
1. <span data-ttu-id="22e67-177">リーダーが作成された後にトランザクションを開始し、それがトランザクションの一部にならないようにします。</span><span class="sxs-lookup"><span data-stu-id="22e67-177">Start the transaction after the reader is created, so that it is not part of the transaction.</span></span> <span data-ttu-id="22e67-178">それにより、すべての更新が独自のトランザクションになります。</span><span class="sxs-lookup"><span data-stu-id="22e67-178">Every update then becomes its own transaction.</span></span>  
  
2. <span data-ttu-id="22e67-179">リーダーが終了した後ですべての作業をコミットします。</span><span class="sxs-lookup"><span data-stu-id="22e67-179">Commit all work after the reader is closed.</span></span> <span data-ttu-id="22e67-180">この場合は、大量の更新バッチが生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e67-180">This has the potential for a substantial batch of updates.</span></span>  
  
3. <span data-ttu-id="22e67-181">MARS を使用せず、代わりに MARS が導入される以前に行っていたように、コマンド オブジェクトごとに別々の接続を使用します。</span><span class="sxs-lookup"><span data-stu-id="22e67-181">Don't use MARS; instead use a separate connection for each command object as you would have before MARS.</span></span>  
  
### <a name="detecting-mars-support"></a><span data-ttu-id="22e67-182">MARS サポートの検出</span><span class="sxs-lookup"><span data-stu-id="22e67-182">Detecting MARS Support</span></span>  
 <span data-ttu-id="22e67-183">アプリケーションは、`SqlConnection.ServerVersion` の値を読み取って MARS サポートを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="22e67-183">An application can check for MARS support by reading the `SqlConnection.ServerVersion` value.</span></span> <span data-ttu-id="22e67-184">SQL Server 2005 のメジャー番号は 9、SQL Server 2008 のメジャー番号は 10 です。</span><span class="sxs-lookup"><span data-stu-id="22e67-184">The major number should be 9 for SQL Server 2005 and 10 for SQL Server 2008.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22e67-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e67-185">See also</span></span>

- [<span data-ttu-id="22e67-186">複数のアクティブな結果セット (MARS)</span><span class="sxs-lookup"><span data-stu-id="22e67-186">Multiple Active Result Sets (MARS)</span></span>](multiple-active-result-sets-mars.md)
- [<span data-ttu-id="22e67-187">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="22e67-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
