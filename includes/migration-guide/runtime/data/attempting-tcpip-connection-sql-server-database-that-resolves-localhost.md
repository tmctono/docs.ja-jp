---
ms.openlocfilehash: bbeca87b3f498213b91d942cc4f197c9d80457a8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496730"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="2c284-101">`localhost` に解決される SQL Server データベースへの TCP/IP 接続の試みが失敗します</span><span class="sxs-lookup"><span data-stu-id="2c284-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="2c284-102">説明</span><span class="sxs-lookup"><span data-stu-id="2c284-102">Details</span></span>

<span data-ttu-id="2c284-103">.NET Framework 4.6 および 4.6.1 で、<code>localhost</code> に解決される SQL Server データベースへの TCP/IP 接続の試みが次のエラーで失敗していました: &quot;SQL Server への接続を確立しているときにネットワーク関連またはインスタンス固有のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="2c284-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="2c284-104">サーバーが見つからないかアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="2c284-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="2c284-105">インスタンス名が正しいこと、および SQL Server がリモート接続を許可するように構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2c284-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="2c284-106">(プロバイダー:SQL ネットワーク インターフェイス、エラー:26 - 指定されたサーバーまたはインスタンスの位置を特定しているときにエラーが発生しました)&quot;</span><span class="sxs-lookup"><span data-stu-id="2c284-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2c284-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2c284-107">Suggestion</span></span>

<span data-ttu-id="2c284-108">この問題は修正済みであり、.NET Framework 4.6.2 では以前の動作に戻っています。</span><span class="sxs-lookup"><span data-stu-id="2c284-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="2c284-109"><code>localhost</code> に解決される SQL Server データベースに接続するには、.NET Framework 4.6.2 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="2c284-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="2c284-110">名前</span><span class="sxs-lookup"><span data-stu-id="2c284-110">Name</span></span>    | <span data-ttu-id="2c284-111">[値]</span><span class="sxs-lookup"><span data-stu-id="2c284-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2c284-112">スコープ</span><span class="sxs-lookup"><span data-stu-id="2c284-112">Scope</span></span>   |<span data-ttu-id="2c284-113">マイナー</span><span class="sxs-lookup"><span data-stu-id="2c284-113">Minor</span></span>|
|<span data-ttu-id="2c284-114">バージョン</span><span class="sxs-lookup"><span data-stu-id="2c284-114">Version</span></span>|<span data-ttu-id="2c284-115">4.6</span><span class="sxs-lookup"><span data-stu-id="2c284-115">4.6</span></span>|
|<span data-ttu-id="2c284-116">種類</span><span class="sxs-lookup"><span data-stu-id="2c284-116">Type</span></span>|<span data-ttu-id="2c284-117">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2c284-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="2c284-118">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="2c284-118">Affected APIs</span></span>

<span data-ttu-id="2c284-119">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="2c284-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
