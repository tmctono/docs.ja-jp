---
title: SQL Server のプロバイダー統計情報
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: 5e37a04ff731a99664d636e0d4175f99214c2646
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174512"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="e5efd-102">SQL Server のプロバイダー統計情報</span><span class="sxs-lookup"><span data-stu-id="e5efd-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="e5efd-103">.NET Framework version 2.0 以降では、.NET Framework Data Provider for SQL Server によって実行時の統計がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e5efd-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="e5efd-104">有効な接続オブジェクトが作成されたら、<xref:System.Data.SqlClient.SqlConnection> オブジェクトの <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> プロパティを `True` に設定して、統計を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5efd-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="e5efd-105">統計情報が有効になったら、<xref:System.Data.SqlClient.SqlConnection> オブジェクトの <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> メソッドを使用して、<xref:System.Collections.IDictionary> 参照を取得することにより、それらを "特定の時点のスナップショット" として確認できます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="e5efd-106">名前と値のペアの辞書エントリのセットとしてリストを列挙します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="e5efd-107">これらの名前と値のペアは順不同です。</span><span class="sxs-lookup"><span data-stu-id="e5efd-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="e5efd-108">カウンターはいつでも、<xref:System.Data.SqlClient.SqlConnection> オブジェクトの <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> メソッドを呼び出してリセットできます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="e5efd-109">統計情報の収集が有効にされていない場合、例外は生成されません。</span><span class="sxs-lookup"><span data-stu-id="e5efd-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="e5efd-110">さらに、最初に <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> を呼び出すことなく <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> が呼び出された場合、取得される値は各エントリの初期値になります。</span><span class="sxs-lookup"><span data-stu-id="e5efd-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="e5efd-111">統計を有効にし、アプリケーションをしばらく実行してから統計を無効にした場合、取得される値には、統計を無効にした時点までに収集された値が反映されます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="e5efd-112">すべての統計値は接続ごとに収集されます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="e5efd-113">使用できる統計情報の値</span><span class="sxs-lookup"><span data-stu-id="e5efd-113">Statistical Values Available</span></span>  
 <span data-ttu-id="e5efd-114">現在、Microsoft SQL Server プロバイダーから 18 種類の項目を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="e5efd-115">使用できる項目の数を確認するには、<xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> により返される <xref:System.Collections.IDictionary> インターフェイス参照の **Count** プロパティを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="e5efd-116">プロバイダーの統計情報のカウンターはすべて、64 ビット幅である共通言語ランタイムの <xref:System.Int64> 型 (C# と Visual Basic の場合は **long**) を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="e5efd-117">**int64** データ型の最大値は、**int64.MaxValue** フィールドにより定義されているように、((2^63)-1)) です。</span><span class="sxs-lookup"><span data-stu-id="e5efd-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="e5efd-118">カウンターの値がこの最大値に達すると、正確であると見なされなくなります。</span><span class="sxs-lookup"><span data-stu-id="e5efd-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="e5efd-119">つまり、**int64.MaxValue**-1((2^63)-2) は、事実上、すべての統計情報について有効な値の最大値になります。</span><span class="sxs-lookup"><span data-stu-id="e5efd-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5efd-120">返される統計の数、名前、および順序は将来変更される可能性があるため、プロバイダー統計情報を返す場合には、辞書を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="e5efd-121">アプリケーションでは、辞書にある特定の値に依存しないようにする必要がありますが、その値が存在するかどうかを確認し、それに応じて分岐する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5efd-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="e5efd-122">次の表では、使用可能な現在の統計値について説明します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="e5efd-123">個々の値のキー名は、Microsoft .NET Framework の地域別バージョン全体でローカライズされているわけではないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5efd-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="e5efd-124">キーの名前</span><span class="sxs-lookup"><span data-stu-id="e5efd-124">Key Name</span></span>|<span data-ttu-id="e5efd-125">説明</span><span class="sxs-lookup"><span data-stu-id="e5efd-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="e5efd-126">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、SQL Server からプロバイダーが受信した表形式データ ストリーム (TDS) パケットの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="e5efd-127">統計が有効になった後にプロバイダーから SQL Server に送信された TDS パケットの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="e5efd-128">大規模なコマンドでは、複数のバッファーが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5efd-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="e5efd-129">たとえば、大規模なコマンドがサーバーに送信され、6 個のパケットが必要な場合、`ServerRoundtrips` は 1 ずつ増え、`BuffersSent` は 6 ずつ増えます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="e5efd-130">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、SQL Server からプロバイダーが受信した TDS パケット内のデータのバイト数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="e5efd-131">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、TDS パケットで SQL Server に送信されるデータのバイト数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="e5efd-132">統計情報が有効になった後に接続が開かれている時間の長さ (ミリ秒単位) を示します (接続が開かれる前に統計情報が有効になっていた場合は、合計接続時間を示します)。</span><span class="sxs-lookup"><span data-stu-id="e5efd-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="e5efd-133">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由でカーソルが開かれた回数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="e5efd-134">SELECT ステートメントから返された読み取り専用/順方向専用の結果は、カーソルとは見なされないため、このカウンターには影響しません。</span><span class="sxs-lookup"><span data-stu-id="e5efd-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="e5efd-135">統計情報が有効になってから、プロバイダーが処理に費やした累計時間 (ミリ秒単位) を返します。この時間には、サーバーからの応答を待つために費やされた時間と、プロバイダー自体がコードを実行するために費やした時間が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="e5efd-136">タイミング コードを含むクラスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e5efd-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="e5efd-137">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="e5efd-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="e5efd-138">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="e5efd-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="e5efd-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="e5efd-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="e5efd-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="e5efd-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="e5efd-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="e5efd-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="e5efd-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="e5efd-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="e5efd-143">パフォーマンス クリティカルなメンバーを可能な限り小さく維持するために、次のメンバーは時間指定されません。</span><span class="sxs-lookup"><span data-stu-id="e5efd-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="e5efd-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="e5efd-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="e5efd-145">this[] 演算子 (すべてのオーバーロード)</span><span class="sxs-lookup"><span data-stu-id="e5efd-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="e5efd-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="e5efd-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="e5efd-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="e5efd-147">GetChar</span></span><br /><br /> <span data-ttu-id="e5efd-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="e5efd-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="e5efd-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="e5efd-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="e5efd-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="e5efd-150">GetDouble</span></span><br /><br /> <span data-ttu-id="e5efd-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="e5efd-151">GetFloat</span></span><br /><br /> <span data-ttu-id="e5efd-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="e5efd-152">GetGuid</span></span><br /><br /> <span data-ttu-id="e5efd-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="e5efd-153">GetInt16</span></span><br /><br /> <span data-ttu-id="e5efd-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="e5efd-154">GetInt32</span></span><br /><br /> <span data-ttu-id="e5efd-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="e5efd-155">GetInt64</span></span><br /><br /> <span data-ttu-id="e5efd-156">GetName</span><span class="sxs-lookup"><span data-stu-id="e5efd-156">GetName</span></span><br /><br /> <span data-ttu-id="e5efd-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="e5efd-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="e5efd-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="e5efd-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="e5efd-159">GetSqlBoolean</span><span class="sxs-lookup"><span data-stu-id="e5efd-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="e5efd-160">GetSqlByte</span><span class="sxs-lookup"><span data-stu-id="e5efd-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="e5efd-161">GetSqlDateTime</span><span class="sxs-lookup"><span data-stu-id="e5efd-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="e5efd-162">GetSqlDecimal</span><span class="sxs-lookup"><span data-stu-id="e5efd-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="e5efd-163">GetSqlDouble</span><span class="sxs-lookup"><span data-stu-id="e5efd-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="e5efd-164">GetSqlGuid</span><span class="sxs-lookup"><span data-stu-id="e5efd-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="e5efd-165">GetSqlInt16</span><span class="sxs-lookup"><span data-stu-id="e5efd-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="e5efd-166">GetSqlInt32</span><span class="sxs-lookup"><span data-stu-id="e5efd-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="e5efd-167">GetSqlInt64</span><span class="sxs-lookup"><span data-stu-id="e5efd-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="e5efd-168">GetSqlMoney</span><span class="sxs-lookup"><span data-stu-id="e5efd-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="e5efd-169">GetSqlSingle</span><span class="sxs-lookup"><span data-stu-id="e5efd-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="e5efd-170">GetSqlString</span><span class="sxs-lookup"><span data-stu-id="e5efd-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="e5efd-171">GetString</span><span class="sxs-lookup"><span data-stu-id="e5efd-171">GetString</span></span><br /><br /> <span data-ttu-id="e5efd-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="e5efd-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="e5efd-173">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由で実行された INSERT、DELETE、および UPDATE ステートメントの合計数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="e5efd-174">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由で実行された INSERT、DELETE、および UPDATE ステートメントによって影響を受ける行の合計数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="e5efd-175">アプリケーションがプロバイダーを使って開始され、統計情報が有効になった後にプロバイダーがサーバーからの応答を待つために費やした累計時間 (ミリ秒単位) を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="e5efd-176">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由で実行された準備済みコマンドの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="e5efd-177">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由で準備されたステートメントの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="e5efd-178">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由で実行された SELECT ステートメントの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="e5efd-179">これには、カーソルから行を取得するための FETCH ステートメントが含まれ、<xref:System.Data.SqlClient.SqlDataReader> の末尾に達したときに SELECT ステートメントの数が更新されます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="e5efd-180">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、選択された行の数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="e5efd-181">この数には、SQL ステートメントによって生成されたすべての行が反映され、呼び出し元によって実際に使用されなかった行も含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="e5efd-182">たとえば、結果セット全体を読み取る前にデータ リーダーを終了しても、数には影響しません。</span><span class="sxs-lookup"><span data-stu-id="e5efd-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="e5efd-183">これには、FETCH ステートメントによってカーソルから取得された行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="e5efd-184">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続によってコマンドがサーバーに送信され、応答が返された回数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="e5efd-185">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、使用された結果セットの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="e5efd-186">たとえば、これにはクライアントに返される結果セットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="e5efd-187">カーソルの場合、各フェッチまたはブロックフェッチ操作は、独立した結果セットと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="e5efd-188">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、ロールバックを含む開始されたユーザー トランザクションの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="e5efd-189">自動コミットをオンにして接続が実行されている場合、各コマンドはトランザクションと見なされます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="e5efd-190">このカウンターでは、後でトランザクションがコミットされるか、ロール バックされるかに関係なく、BEGIN TRAN ステートメントが実行されるとすぐにトランザクション数が増えます。</span><span class="sxs-lookup"><span data-stu-id="e5efd-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="e5efd-191">アプリケーションがプロバイダーの使用を開始し、統計情報が有効になった後に、接続経由で実行された準備解除されたステートメントの数を返します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="e5efd-192">値の取得</span><span class="sxs-lookup"><span data-stu-id="e5efd-192">Retrieving a Value</span></span>  
 <span data-ttu-id="e5efd-193">次のコンソール アプリケーションでは、接続についての統計を有効にし、4 つの各統計値を取得して、それらをコンソール ウィンドウに書き込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5efd-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5efd-194">次の例では、SQL Server に含まれるサンプルの **AdventureWorks** データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-194">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="e5efd-195">サンプル コードに示されている接続文字列は、データベースがローカル コンピューターにインストールされ、使用可能であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e5efd-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="e5efd-196">実際の環境の必要に応じて接続文字列を変更してください。</span><span class="sxs-lookup"><span data-stu-id="e5efd-196">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="e5efd-197">すべての値の取得</span><span class="sxs-lookup"><span data-stu-id="e5efd-197">Retrieving All Values</span></span>  
 <span data-ttu-id="e5efd-198">次のコンソール アプリケーションでは、接続についての統計を有効にし、列挙子を使用して使用可能なすべての統計値を取得して、それらをコンソール ウィンドウに書き込む方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e5efd-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5efd-199">次の例では、SQL Server に含まれるサンプルの **AdventureWorks** データベースを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5efd-199">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="e5efd-200">サンプル コードに示されている接続文字列は、データベースがローカル コンピューターにインストールされ、使用可能であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="e5efd-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="e5efd-201">実際の環境の必要に応じて接続文字列を変更してください。</span><span class="sxs-lookup"><span data-stu-id="e5efd-201">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrieve it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5efd-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5efd-202">See also</span></span>

- [<span data-ttu-id="e5efd-203">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e5efd-203">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="e5efd-204">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="e5efd-204">ADO.NET Overview</span></span>](../ado-net-overview.md)
