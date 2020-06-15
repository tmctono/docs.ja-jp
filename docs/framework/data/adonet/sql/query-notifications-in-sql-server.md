---
title: SQL Server のクエリ通知
description: SQL Server データベースのデータが変更された場合にアプリケーションに通知して、アプリケーションの表示の更新などを行うために、クエリ通知を使用する方法について説明します。
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 1351c83b6cc5837115321d53e8779c0f364c3099
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286224"
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="a0781-103">SQL Server のクエリ通知</span><span class="sxs-lookup"><span data-stu-id="a0781-103">Query Notifications in SQL Server</span></span>
<span data-ttu-id="a0781-104">クエリ通知は Service Broker インフラストラクチャに基づいて構築されており、データが変更されたときにクエリ通知を使用してアプリケーションに通知できます。</span><span class="sxs-lookup"><span data-stu-id="a0781-104">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="a0781-105">この機能は、Web アプリケーションなど、データベースから情報のキャッシュを提供し、ソース データが変更された場合に通知を必要とするアプリケーションに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0781-105">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="a0781-106">ADO.NET を使用してクエリ通知を実装する方法には、次の 3 つがあります。</span><span class="sxs-lookup"><span data-stu-id="a0781-106">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1. <span data-ttu-id="a0781-107">低レベルの実装は、サーバー側の機能を公開する `SqlNotificationRequest` クラスによって提供されます。これにより、通知要求を使用してコマンドを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="a0781-107">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2. <span data-ttu-id="a0781-108">高レベルの実装は、`SqlDependency` クラスによって行われます。このクラスでは、ソース アプリケーションと SQL Server 間の通知機能が高度に抽象化され、その依存関係を使用してサーバー内の変更を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="a0781-108">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="a0781-109">マネージド クライアント アプリケーションが .NET Framework Data Provider for SQL Server を使用して SQL Server の通知機能を活用するには、ほとんどの場合、これが最も簡単かつ効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="a0781-109">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3. <span data-ttu-id="a0781-110">さらに、ASP.NET 2.0 以降を使用して構築された Web アプリケーションでは、`SqlCacheDependency` ヘルパー クラスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0781-110">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="a0781-111">クエリ通知は、基になるデータの変更に応じて表示またはキャッシュを更新する必要があるアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="a0781-111">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="a0781-112">Microsoft SQL Server では、最初に取得したものと異なる結果セットが同じコマンドで得られた場合には、.NET Framework アプリケーションから SQL Server にコマンドを送信して通知を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="a0781-112">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="a0781-113">サーバーで生成された通知は、キューを通じて送信された後に処理されます。</span><span class="sxs-lookup"><span data-stu-id="a0781-113">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="a0781-114">通知は、SELECT および EXECUTE ステートメントに対して設定できます。</span><span class="sxs-lookup"><span data-stu-id="a0781-114">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="a0781-115">EXECUTE ステートメントを使用している場合、SQL Server はその EXECUTE ステートメント自体ではなく、実行されるコマンドについて通知を登録します。</span><span class="sxs-lookup"><span data-stu-id="a0781-115">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="a0781-116">コマンドは、SELECT ステートメントの要件と制限を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a0781-116">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="a0781-117">通知を登録するコマンドに複数のステートメントが含まれている場合、データベース エンジンによりバッチ内のステートメントごとに通知が作成されます。</span><span class="sxs-lookup"><span data-stu-id="a0781-117">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="a0781-118">データ変更時に、信頼できる即時の通知が必要なアプリケーションを開発している場合は、「[通知の計画](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105))」記事の「**効率的なクエリ通知方法の計画**」および「**クエリ通知に代わる方法**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0781-118">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) article.</span></span> <span data-ttu-id="a0781-119">クエリ通知と SQL Server Service Broker の詳細については、SQL Server ドキュメントの記事への以下のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a0781-119">For more information about Query Notifications and SQL Server Service Broker, see the following links to articles in the SQL Server documentation.</span></span>  
  
 <span data-ttu-id="a0781-120">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="a0781-120">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="a0781-121">[クエリ通知の使用](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a0781-121">[Using Query Notifications](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span></span>  
  
- <span data-ttu-id="a0781-122">[通知のためのクエリの作成](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a0781-122">[Creating a Query for Notification](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="a0781-123">[開発 (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a0781-123">[Development (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span></span>  
  
- <span data-ttu-id="a0781-124">[Service Broker 開発者向けの情報](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a0781-124">[Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="a0781-125">[開発者ガイド (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="a0781-125">[Developer's Guide (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0781-126">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a0781-126">In This Section</span></span>  
 [<span data-ttu-id="a0781-127">クエリ通知の有効化</span><span class="sxs-lookup"><span data-stu-id="a0781-127">Enabling Query Notifications</span></span>](enabling-query-notifications.md)  
 <span data-ttu-id="a0781-128">クエリ通知を有効にするための要件を含め、クエリ通知の使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0781-128">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="a0781-129">ASP.NET アプリケーションでの SqlDependency</span><span class="sxs-lookup"><span data-stu-id="a0781-129">SqlDependency in an ASP.NET Application</span></span>](sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="a0781-130">ASP.NET アプリケーションからクエリ通知を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0781-130">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="a0781-131">SqlDependency を使用した変更の検出</span><span class="sxs-lookup"><span data-stu-id="a0781-131">Detecting Changes with SqlDependency</span></span>](detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="a0781-132">最初に取得された結果と異なるクエリ結果を検出する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a0781-132">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="a0781-133">SqlCommand の実行と SqlNotificationRequest</span><span class="sxs-lookup"><span data-stu-id="a0781-133">SqlCommand Execution with a SqlNotificationRequest</span></span>](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="a0781-134">クエリ通知を使用する <xref:System.Data.SqlClient.SqlCommand> オブジェクトの構成例を示します。</span><span class="sxs-lookup"><span data-stu-id="a0781-134">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a0781-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0781-135">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="a0781-136"><xref:System.Data.Sql.SqlNotificationRequest> クラスとそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0781-136">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="a0781-137"><xref:System.Data.SqlClient.SqlDependency> クラスとそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0781-137">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="a0781-138"><xref:System.Web.Caching.SqlCacheDependency> クラスおよびそのすべてのメンバーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a0781-138">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0781-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="a0781-139">See also</span></span>

- [<span data-ttu-id="a0781-140">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a0781-140">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="a0781-141">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="a0781-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
