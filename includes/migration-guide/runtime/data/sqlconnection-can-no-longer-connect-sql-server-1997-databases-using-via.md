---
ms.openlocfilehash: 8dc947f584d3433f0638a72f4db86ac2680c8dbf
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496813"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="c297f-101">SqlConnection は VIA アダプターを使用して SQL Server 1997 またはデータベースに接続できなくなりました</span><span class="sxs-lookup"><span data-stu-id="c297f-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="c297f-102">説明</span><span class="sxs-lookup"><span data-stu-id="c297f-102">Details</span></span>

<span data-ttu-id="c297f-103">[仮想インターフェイス アダプター (VIA) プロトコル](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105))を使用した SQL Server データベースへの接続はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c297f-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="c297f-104">SQL Server データベースへの接続に使用されるプロトコルは、接続文字列で表示されます。</span><span class="sxs-lookup"><span data-stu-id="c297f-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="c297f-105">VIA 接続には via:&lt;servername&gt; が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c297f-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="c297f-106">このアプリが VIA 以外のプロトコル (tcp: や np: など) を介して SQL に接続している場合、破壊的変更は発生しません。</span><span class="sxs-lookup"><span data-stu-id="c297f-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="c297f-107">また、SQL Server 7 (1997) への接続はサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="c297f-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c297f-108">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="c297f-108">Suggestion</span></span>

<span data-ttu-id="c297f-109">VIA プロトコルは推奨されていないので、SQL データベースに接続するには別のプロトコルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c297f-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="c297f-110">最も一般的に使用されるプロトコルは TCP/IP です。</span><span class="sxs-lookup"><span data-stu-id="c297f-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="c297f-111">TCP/IP での接続の詳細については、「[方法: データベース インスタンスの TCP/IP プロトコルを有効にする](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c297f-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="c297f-112">データベースへのアクセスがイントラネット内からに限定されていて、ネットワーク速度が遅い場合は、共有パイプ プロトコルがより優れたパフォーマンスを提供する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c297f-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="c297f-113">名前</span><span class="sxs-lookup"><span data-stu-id="c297f-113">Name</span></span>    | <span data-ttu-id="c297f-114">[値]</span><span class="sxs-lookup"><span data-stu-id="c297f-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c297f-115">スコープ</span><span class="sxs-lookup"><span data-stu-id="c297f-115">Scope</span></span>   |<span data-ttu-id="c297f-116">エッジ</span><span class="sxs-lookup"><span data-stu-id="c297f-116">Edge</span></span>|
|<span data-ttu-id="c297f-117">バージョン</span><span class="sxs-lookup"><span data-stu-id="c297f-117">Version</span></span>|<span data-ttu-id="c297f-118">4.5</span><span class="sxs-lookup"><span data-stu-id="c297f-118">4.5</span></span>|
|<span data-ttu-id="c297f-119">種類</span><span class="sxs-lookup"><span data-stu-id="c297f-119">Type</span></span>|<span data-ttu-id="c297f-120">ランタイム</span><span class="sxs-lookup"><span data-stu-id="c297f-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c297f-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="c297f-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
