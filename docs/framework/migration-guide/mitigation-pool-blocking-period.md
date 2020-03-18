---
title: '軽減策: プールのロック期間'
ms.date: 03/30/2017
ms.assetid: 92d2de20-79be-4df1-b182-144143a8866a
ms.openlocfilehash: 98396d4254975d1806a8477cbcd2380cb52ceaf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457844"
---
# <a name="mitigation-pool-blocking-period"></a><span data-ttu-id="c89d8-102">軽減策: プールのロック期間</span><span class="sxs-lookup"><span data-stu-id="c89d8-102">Mitigation: Pool Blocking Period</span></span>
<span data-ttu-id="c89d8-103">Azure SQL データベースへの接続に関して、接続プールのブロック期間が削除されました。</span><span class="sxs-lookup"><span data-stu-id="c89d8-103">The connection pool blocking period has been removed for connections to Azure SQL databases.</span></span>  
  
## <a name="additional-description"></a><span data-ttu-id="c89d8-104">その他の説明</span><span class="sxs-lookup"><span data-stu-id="c89d8-104">Additional description</span></span>  
 <span data-ttu-id="c89d8-105">.NET Framework 4.6.1 以前のバージョンでは、データベースへの接続時にアプリで一時的な接続エラーが発生した場合、接続はすぐに再試行されません。接続プールがエラーをキャッシュし、5 秒間から 1 分間エラーを再スローするためです。詳細については、「[SQL Server の接続プール (ADO.NET)](../data/adonet/sql-server-connection-pooling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c89d8-105">In the .NET Framework 4.6.1 and earlier versions, when an app encounters a transient connection failure when connecting to a database, the connection attempt cannot be retried quickly, because the connection pool caches the error and re-throws it for 5 seconds to 1 min. For more information, see [SQL Server Connection Pooling (ADO.NET)](../data/adonet/sql-server-connection-pooling.md).</span></span> <span data-ttu-id="c89d8-106">この動作は、Azure SQL データベースへの接続時に問題となります。多くの場合、一時的なエラーが発生し、通常数秒内に回復します。</span><span class="sxs-lookup"><span data-stu-id="c89d8-106">This behavior is problematic for connections to Azure SQL databases, which often fail with transient errors that are typically recovered from within a few seconds.</span></span> <span data-ttu-id="c89d8-107">接続プールのブロック機能を使用すると、データベースが使用可能な場合でも、長い期間にわたってアプリがデータベースに接続できなくなるということです。</span><span class="sxs-lookup"><span data-stu-id="c89d8-107">The connection pool blocking feature means that the app cannot connect to the database for an extensive period, even though the database is available.</span></span> <span data-ttu-id="c89d8-108">この動作が特に問題となるのは、Azure SQL データベースに接続し、数秒内でレンダリングする必要がある Web アプリの場合です。</span><span class="sxs-lookup"><span data-stu-id="c89d8-108">This behavior is particularly problematic for web apps that connect to Azure SQL databases and that need to render within a few seconds.</span></span>  
  
 <span data-ttu-id="c89d8-109">.NET Framework 4.6.2 以降では、既知の Azure SQL データベースへの接続確立要求 (\*.database.windows.net、\*.database.chinacloudapi.cn、\*.database.usgovcloudapi.net、\*.database.cloudapi.de) の場合、接続確立のエラーはキャッシュされません。</span><span class="sxs-lookup"><span data-stu-id="c89d8-109">Starting with the .NET Framework 4.6.2, for connection open requests to known Azure SQL databases (\*.database.windows.net, \*.database.chinacloudapi.cn, \*.database.usgovcloudapi.net, \*.database.cloudapi.de), connection open errors are not cached.</span></span> <span data-ttu-id="c89d8-110">他のすべての接続を試みる場合は、接続プールのブロック期間が引き続き適用されます。</span><span class="sxs-lookup"><span data-stu-id="c89d8-110">For all other connection attempts, the connection pool blocking period continues to be enforced.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="c89d8-111">影響</span><span class="sxs-lookup"><span data-stu-id="c89d8-111">Impact</span></span>  
 <span data-ttu-id="c89d8-112">この変更により、Azure SQL データベースへの接続確立がすぐに再試行するされるため、クラウド対応アプリケーションのパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="c89d8-112">This change allows the connection open attempt to be retried immediately for Azure SQL databases, thereby improving the performance of cloud-enabled apps.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="c89d8-113">対応策</span><span class="sxs-lookup"><span data-stu-id="c89d8-113">Mitigation</span></span>  
 <span data-ttu-id="c89d8-114">この変更から悪影響を受けるアプリの場合、新しい <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType> プロパティを設定することで、接続プールのブロック期間を構成できます。</span><span class="sxs-lookup"><span data-stu-id="c89d8-114">For apps that are adversely affected by this change, the connection pool blocking period can be configured by setting the new <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="c89d8-115">プロパティ値が <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> 列挙型のメンバーである場合、次の 3 つの値のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="c89d8-115">The value of the property is a member of the <xref:System.Data.SqlClient.PoolBlockingPeriod?displayProperty=nameWithType> enumeration that can take either of three values:</span></span>  
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.Auto?displayProperty=nameWithType>
  
- <xref:System.Data.SqlClient.PoolBlockingPeriod.NeverBlock?displayProperty=nameWithType>
  
 <span data-ttu-id="c89d8-116"><xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> プロパティを <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType> に設定して、以前の動作を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="c89d8-116">The previous behavior can be restored by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.PoolBlockingPeriod%2A> property to <xref:System.Data.SqlClient.PoolBlockingPeriod.AlwaysBlock?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89d8-117">参照</span><span class="sxs-lookup"><span data-stu-id="c89d8-117">See also</span></span>

- [<span data-ttu-id="c89d8-118">アプリケーションの互換性</span><span class="sxs-lookup"><span data-stu-id="c89d8-118">Application compatibility</span></span>](application-compatibility.md)
