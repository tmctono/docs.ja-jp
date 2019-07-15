---
ms.openlocfilehash: 8ac6d50b192001f6d924b2ffe4a367a33fc2c689
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857610"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="8c94f-101">`localhost` に解決される SQL Server データベースへの TCP/IP 接続の試みが失敗します</span><span class="sxs-lookup"><span data-stu-id="8c94f-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8c94f-102">説明</span><span class="sxs-lookup"><span data-stu-id="8c94f-102">Details</span></span>|<span data-ttu-id="8c94f-103">.NET Framework 4.6 および 4.6.1 で、<code>localhost</code> に解決される SQL Server データベースへの TCP/IP 接続の試みが次のエラーで失敗していました: &quot;SQL Server への接続を確立しているときにネットワーク関連またはインスタンス固有のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="8c94f-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="8c94f-104">サーバーが見つからないかアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="8c94f-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="8c94f-105">インスタンス名が正しいこと、および SQL Server がリモート接続を許可するように構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8c94f-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="8c94f-106">(プロバイダー:SQL ネットワーク インターフェイス、エラー:26 - 指定されたサーバーまたはインスタンスの位置を特定しているときにエラーが発生しました)&quot;</span><span class="sxs-lookup"><span data-stu-id="8c94f-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>|
|<span data-ttu-id="8c94f-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="8c94f-107">Suggestion</span></span>|<span data-ttu-id="8c94f-108">この問題は修正済みであり、.NET Framework 4.6.2 では以前の動作に戻っています。</span><span class="sxs-lookup"><span data-stu-id="8c94f-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="8c94f-109"><code>localhost</code> に解決される SQL Server データベースに接続するには、.NET Framework 4.6.2 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="8c94f-109">To connect to a SQL Server databsae that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>|
|<span data-ttu-id="8c94f-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="8c94f-110">Scope</span></span>|<span data-ttu-id="8c94f-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="8c94f-111">Minor</span></span>|
|<span data-ttu-id="8c94f-112">Version</span><span class="sxs-lookup"><span data-stu-id="8c94f-112">Version</span></span>|<span data-ttu-id="8c94f-113">4.6</span><span class="sxs-lookup"><span data-stu-id="8c94f-113">4.6</span></span>|
|<span data-ttu-id="8c94f-114">型</span><span class="sxs-lookup"><span data-stu-id="8c94f-114">Type</span></span>|<span data-ttu-id="8c94f-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="8c94f-115">Runtime</span></span>|

