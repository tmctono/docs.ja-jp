---
ms.openlocfilehash: 4ffef401c07dbb27db7c0225acdc6817d95bfe11
ms.sourcegitcommit: b4a46f6d7ebf44c0035627d00924164bcae2db30
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91451586"
---
## <a name="available-counters"></a>利用できるカウンター

さまざまな .NET パッケージを通じて、ガベージ コレクション (GC) の基本メトリック、Just-in-time (JIT)、アセンブリ、例外、スレッド処理、ネットワーク、Web 要求が、EventCounters を使用して公開されます。

### <a name="systemruntime-counters"></a>"System.Runtime" カウンター

次のカウンターは、.NET ランタイムの一部として公開され、[`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs) に保持されます。

| カウンター | 説明 |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | 最後の GC からの GC の時間 (パーセント) |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | 割り当ての比率 (バイト単位) |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | プロセスの CPU 使用率 (パーセント) |
| :::no-loc text="Exception Count"::: (`exception-count`) | 発生した例外の数 |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType> に基づいて割り当てられていると考えられるバイト数 |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Gen 0 に対して GC が発生した回数 |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Gen 0 GC のバイト数 |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Gen 1 に対して GC が発生した回数 |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Gen 1 GC のバイト数 |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Gen 2 に対して GC が発生した回数 |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Gen 2 GC のバイト数 |
| :::no-loc text="LOH Size"::: (`loh-size`) | Gen 3 GC のバイト数 |
| :::no-loc text="POH Size"::: (`poh-size`) | ピン留めされたオブジェクト ヒープのバイト数 (.NET 5 以降のバージョンで取得可能) |
| :::no-loc text="GC Fragmentation"::: (`gc-fragmentation`) | GC ヒープの断片化 (.NET 5 以降のバージョンで取得可能) |
| :::no-loc text="Monitor Lock Contention Count"::: (`monitor-lock-contention-count`) | <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType> に基づく、モニターのロックを取得しようとするときに競合があった回数 |
| :::no-loc text="Number of Active Timers"::: (`active-timer-count`) | <xref:System.Threading.Timer.ActiveCount?displayProperty=nameWithType> に基づく、現在アクティブになっている <xref:System.Threading.Timer> インスタンスの数 |
| :::no-loc text="Number of Assemblies Loaded"::: (`assembly-count`) | 特定の時点でプロセスに読み込まれた <xref:System.Reflection.Assembly> インスタンスの数 |
| :::no-loc text="ThreadPool Completed Work Item Count"::: (`threadpool-completed-items-count`) | <xref:System.Threading.ThreadPool> で、これまでに処理された作業項目の数 |
| :::no-loc text="ThreadPool Queue Length"::: (`threadpool-queue-length`) | <xref:System.Threading.ThreadPool> 内の処理対象のキューに現在登録されている作業項目の数 |
| :::no-loc text="ThreadPool Thread Count"::: (`threadpool-thread-count`) | <xref:System.Threading.ThreadPool.ThreadCount?displayProperty=nameWithType> に基づく、<xref:System.Threading.ThreadPool> に現在存在しているスレッド プールのスレッドの数 |
| :::no-loc text="Working Set"::: (`working-set`) | <xref:System.Environment.WorkingSet?displayProperty=nameWithType> に基づく、ある時点でプロセス コンテキストにマップされた物理メモリの量 |
| :::no-loc text="IL Bytes Jitted"::: (`il-bytes-jitted`) | JIT コンパイルされる IL のバイト単位の合計サイズ (.NET 5 以降のバージョンで取得可能) |
| :::no-loc text="Method Jitted Count"::: (`method-jitted-count`) | JIT コンパイルされるメソッドの数 (.NET 5 以降のバージョンで取得可能) |

### <a name="microsoftaspnetcorehosting-counters"></a>"Microsoft.AspNetCore.Hosting" カウンター

次のカウンターは、[ASP.NET Core](/aspnet/core) の一部として公開され、[`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs) に保持されます。

| カウンター | 説明 |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | 開始したが、まだ停止していない要求の合計数 |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | アプリの有効期間中に発生した、失敗した要求の合計数 |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | 1 秒あたりに発生した要求の数 |
| :::no-loc text="Total Requests"::: (`total-requests`) | アプリの有効期間中に発生した要求の合計数 |

### <a name="microsoftaspnetcorehttpconnections-counters"></a>"Microsoft.AspNetCore.Http.Connections" カウンター

次のカウンターは、[ASP.NET Core SignalR](/aspnet/core/signalr/introduction) の一部として公開され、[`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs) に保持されます。

| カウンター | 説明 |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | 接続の平均継続時間 (ミリ秒) |
| :::no-loc text="Current Connections"::: (`current-connections`) | 開始したが、まだ停止していないアクティブな接続の数 |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | 開始した接続の合計数 |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | 停止した接続の合計数 |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | タイム アウトした接続の合計数 |

### <a name="microsoft-aspnetcore-server-kestrel-counters"></a>"Microsoft-AspNetCore-Server-Kestrel" カウンター

次のカウンターは、[ASP.NET Core Kestrel Web サーバー](/aspnet/core/fundamentals/servers/kestrel)の一部として公開され、[`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs) に保持されます。

| カウンター | 説明 |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | 接続キューの現在の長さ |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | 1 秒あたりの Web サーバーへの接続の数 |
| :::no-loc text="Current Connections"::: (`current-connections`) | Web サーバーへのアクティブな接続の現在の数 |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | TLS ハンドシェイクの現在の数 |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | アップグレードされた要求の現在の数 (WebSocket) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | 失敗した TLS ハンドシェイクの合計数 |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | 要求キューの現在の長さ |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | 1 秒あたりの TLS ハンドシェイクの数 |
| :::no-loc text="Total Connections"::: (`total-connections`) | Web サーバーへの接続の合計数 |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | Web サーバーとの TLS ハンドシェイクの合計数 |
