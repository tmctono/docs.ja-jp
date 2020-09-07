---
ms.openlocfilehash: 7f7e718d543a4abdf2b8a87e52d8c0e2ba28203f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497252"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="d81bf-101">ADO.NET では、切断された SQL 接続の再接続が自動的に試行されるようになりました</span><span class="sxs-lookup"><span data-stu-id="d81bf-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="d81bf-102">説明</span><span class="sxs-lookup"><span data-stu-id="d81bf-102">Details</span></span>

<span data-ttu-id="d81bf-103">.NET Framework 4.5.1 以降、.NET Framework では、切断された SQL 接続の再接続が自動的に試行されます。</span><span class="sxs-lookup"><span data-stu-id="d81bf-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="d81bf-104">通常、これはアプリの安定性を高めますが、再接続時に行動できるよう、接続が失われたことをアプリに認識させる必要があるという極端な状況があります。</span><span class="sxs-lookup"><span data-stu-id="d81bf-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d81bf-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d81bf-105">Suggestion</span></span>

<span data-ttu-id="d81bf-106">互換性の問題からこの機能が望ましくない場合、接続文字列 (または <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) の <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> プロパティを 0 に設定することで無効にできます。</span><span class="sxs-lookup"><span data-stu-id="d81bf-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="d81bf-107">名前</span><span class="sxs-lookup"><span data-stu-id="d81bf-107">Name</span></span>    | <span data-ttu-id="d81bf-108">[値]</span><span class="sxs-lookup"><span data-stu-id="d81bf-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d81bf-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="d81bf-109">Scope</span></span>   |<span data-ttu-id="d81bf-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="d81bf-110">Edge</span></span>|
|<span data-ttu-id="d81bf-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="d81bf-111">Version</span></span>|<span data-ttu-id="d81bf-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="d81bf-112">4.5.1</span></span>|
|<span data-ttu-id="d81bf-113">種類</span><span class="sxs-lookup"><span data-stu-id="d81bf-113">Type</span></span>|<span data-ttu-id="d81bf-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d81bf-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d81bf-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d81bf-115">Affected APIs</span></span>

- <xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)>

<!--

#### Affected APIs

- `P:System.Data.IDbConnection.ConnectionString`
- `P:System.Data.SqlClient.SqlConnection.ConnectionString`
- `P:System.Configuration.ConnectionStringSettings.ConnectionString`
- `P:System.Data.Common.DbConnection.ConnectionString`
- `P:System.Data.Common.DbConnectionStringBuilder.ConnectionString`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor(System.String)`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor(System.Boolean)`

-->
