---
title: SQL Server のサーバー ロールとデータベース ロール
description: 固定された一連のアクセス許可が割り当てられている、固定サーバー ロールおよび固定データベース ロールについて説明します。 SQL Server では、ロール ベース セキュリティが使用されます。
ms.date: 03/30/2017
ms.assetid: 5482dfdb-e498-4614-8652-b174829eed13
ms.openlocfilehash: 3babf6b249da6e67a6a48bcad647e4674650c348
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177333"
---
# <a name="server-and-database-roles-in-sql-server"></a><span data-ttu-id="640b3-104">SQL Server のサーバー ロールとデータベース ロール</span><span class="sxs-lookup"><span data-stu-id="640b3-104">Server and Database Roles in SQL Server</span></span>

<span data-ttu-id="640b3-105">SQL Server では、すべてのバージョンで、個々のユーザーではなくロール (つまり、ユーザーのグループ) に対して権限を割り当てることのできるロール ベースのセキュリティが使用されています。</span><span class="sxs-lookup"><span data-stu-id="640b3-105">All versions of SQL Server use role-based security, which allows you to assign permissions to a role, or group of users, instead of to individual users.</span></span> <span data-ttu-id="640b3-106">固定サーバー ロールおよび固定データベース ロールには、固定された一連の権限が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="640b3-106">Fixed server and fixed database roles have a fixed set of permissions assigned to them.</span></span>  
  
## <a name="fixed-server-roles"></a><span data-ttu-id="640b3-107">固定サーバー ロール</span><span class="sxs-lookup"><span data-stu-id="640b3-107">Fixed Server Roles</span></span>  

 <span data-ttu-id="640b3-108">固定サーバー ロールは、固定された一連の権限とサーバー規模のスコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="640b3-108">Fixed server roles have a fixed set of permissions and server-wide scope.</span></span> <span data-ttu-id="640b3-109">SQL Server の管理を目的としており、このロールに割り当てられた権限を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="640b3-109">They are intended for use in administering SQL Server and the permissions assigned to them cannot be changed.</span></span> <span data-ttu-id="640b3-110">固定サーバー ロールには、データベースにユーザー アカウントがなくても、ログインを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="640b3-110">Logins can be assigned to fixed server roles without having a user account in a database.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="640b3-111">`sysadmin` 固定サーバー ロールは他のすべてのロールを内包し、無制限のスコープを持ちます。</span><span class="sxs-lookup"><span data-stu-id="640b3-111">The `sysadmin` fixed server role encompasses all other roles and has unlimited scope.</span></span> <span data-ttu-id="640b3-112">本当に信頼できる場合以外は、このロールにプリンシパルを追加することは避けてください。</span><span class="sxs-lookup"><span data-stu-id="640b3-112">Do not add principals to this role unless they are highly trusted.</span></span> <span data-ttu-id="640b3-113">`sysadmin` ロールのメンバーには、サーバーのすべてのデータベースおよびリソースに対する取り消し不可能な管理特権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="640b3-113">`sysadmin` role members have irrevocable administrative privileges on all server databases and resources.</span></span>  
  
 <span data-ttu-id="640b3-114">固定サーバー ロールに追加するユーザーは慎重に選ぶ必要があります。</span><span class="sxs-lookup"><span data-stu-id="640b3-114">Be selective when you add users to fixed server roles.</span></span> <span data-ttu-id="640b3-115">たとえば、`bulkadmin` ロールでは、ユーザーがローカル ファイルの内容をテーブルに挿入できるため、データの整合性が損なわれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="640b3-115">For example, the `bulkadmin` role allows users to insert the contents of any local file into a table, which could jeopardize data integrity.</span></span> <span data-ttu-id="640b3-116">固定サーバー ロールと権限を網羅した一覧については、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="640b3-116">See SQL Server Books Online for the complete list of fixed server roles and permissions.</span></span>  
  
## <a name="fixed-database-roles"></a><span data-ttu-id="640b3-117">固定データベース ロール</span><span class="sxs-lookup"><span data-stu-id="640b3-117">Fixed Database Roles</span></span>  

 <span data-ttu-id="640b3-118">固定データベース ロールには、権限のグループを簡単に管理できるように、あらかじめ定義された一連の権限が割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="640b3-118">Fixed database roles have a pre-defined set of permissions that are designed to allow you to easily manage groups of permissions.</span></span> <span data-ttu-id="640b3-119">`db_owner` ロールのメンバーは、データベースに対するすべての構成作業とメンテナンス作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="640b3-119">Members of the `db_owner` role can perform all configuration and maintenance activities on the database.</span></span>  
  
 <span data-ttu-id="640b3-120">SQL Server の定義済みロールの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="640b3-120">For more information about SQL Server predefined roles, see the following resources.</span></span>  
  
|<span data-ttu-id="640b3-121">リソース</span><span class="sxs-lookup"><span data-stu-id="640b3-121">Resource</span></span>|<span data-ttu-id="640b3-122">説明</span><span class="sxs-lookup"><span data-stu-id="640b3-122">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="640b3-123">サーバーレベルのロール</span><span class="sxs-lookup"><span data-stu-id="640b3-123">Server-Level Roles</span></span>](/sql/relational-databases/security/authentication-access/server-level-roles)|<span data-ttu-id="640b3-124">SQL Server の固定サーバー ロールおよびそれに関連付けられている権限について説明されています。</span><span class="sxs-lookup"><span data-stu-id="640b3-124">Describes fixed server roles and the permissions associated with them in SQL Server.</span></span>|  
|[<span data-ttu-id="640b3-125">データベース レベルのロール</span><span class="sxs-lookup"><span data-stu-id="640b3-125">Database-Level Roles</span></span>](/sql/relational-databases/security/authentication-access/database-level-roles)|<span data-ttu-id="640b3-126">固定データベース ロールおよびそれに関連付けられている権限について説明します。</span><span class="sxs-lookup"><span data-stu-id="640b3-126">Describes fixed database roles and the permissions associated with them</span></span>|  
  
## <a name="database-roles-and-users"></a><span data-ttu-id="640b3-127">データベース ロールおよびユーザー</span><span class="sxs-lookup"><span data-stu-id="640b3-127">Database Roles and Users</span></span>  

 <span data-ttu-id="640b3-128">データベース ユーザー アカウントはデータベース オブジェクトを扱う関係上、ログインにマップされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="640b3-128">Logins must be mapped to database user accounts in order to work with database objects.</span></span> <span data-ttu-id="640b3-129">データベース ユーザーをデータベース ロールに追加すると、そのロールに関連付けられたすべての権限セットが継承されます。</span><span class="sxs-lookup"><span data-stu-id="640b3-129">Database users can then be added to database roles, inheriting any permission sets associated with those roles.</span></span> <span data-ttu-id="640b3-130">すべての権限を付与できます。</span><span class="sxs-lookup"><span data-stu-id="640b3-130">All permissions can be granted.</span></span>  
  
 <span data-ttu-id="640b3-131">アプリケーションのセキュリティを計画する際は、`public` ロール、`dbo` ユーザー アカウント、および `guest` アカウントも考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="640b3-131">You must also consider the `public` role, the `dbo` user account, and the `guest` account when you design security for your application.</span></span>  
  
### <a name="the-public-role"></a><span data-ttu-id="640b3-132">public ロール</span><span class="sxs-lookup"><span data-stu-id="640b3-132">The public Role</span></span>  

 <span data-ttu-id="640b3-133">`public` ロールは、システム データベースを含め、すべてのデータベースに存在します。</span><span class="sxs-lookup"><span data-stu-id="640b3-133">The `public` role is contained in every database, which includes system databases.</span></span> <span data-ttu-id="640b3-134">このロールは削除できません。また、ユーザーを追加したり削除したりすることもできません。</span><span class="sxs-lookup"><span data-stu-id="640b3-134">It cannot be dropped and you cannot add or remove users from it.</span></span> <span data-ttu-id="640b3-135">他のすべてのユーザーおよびロールは既定で `public` ロールに所属するため、`public` ロールに付与された権限を継承します。</span><span class="sxs-lookup"><span data-stu-id="640b3-135">Permissions granted to the `public` role are inherited by all other users and roles because they belong to the `public` role by default.</span></span> <span data-ttu-id="640b3-136">`public` には、すべてのユーザーに割り当てる必要のある権限だけを付与してください。</span><span class="sxs-lookup"><span data-stu-id="640b3-136">Grant `public` only the permissions you want all users to have.</span></span>  
  
### <a name="the-dbo-user-account"></a><span data-ttu-id="640b3-137">dbo ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="640b3-137">The dbo User Account</span></span>  

 <span data-ttu-id="640b3-138">`dbo` (データベース所有者) は、データベースのすべてのアクティビティを実行する暗黙権限を持ったユーザー アカウントです。</span><span class="sxs-lookup"><span data-stu-id="640b3-138">The `dbo`, or database owner, is a user account that has implied permissions to perform all activities in the database.</span></span> <span data-ttu-id="640b3-139">`sysadmin` 固定サーバー ロールのメンバーは、自動的に `dbo` にマップされます。</span><span class="sxs-lookup"><span data-stu-id="640b3-139">Members of the `sysadmin` fixed server role are automatically mapped to `dbo`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="640b3-140">「[SQL Server における所有権とユーザーとスキーマの分離](ownership-and-user-schema-separation-in-sql-server.md)」で説明されているように、`dbo` はスキーマの名前でもあります。</span><span class="sxs-lookup"><span data-stu-id="640b3-140">`dbo` is also the name of a schema, as discussed in [Ownership and User-Schema Separation in SQL Server](ownership-and-user-schema-separation-in-sql-server.md).</span></span>  
  
 <span data-ttu-id="640b3-141">`dbo` ユーザー アカウントは、よく `db_owner` 固定データベース ロールと混同されます。</span><span class="sxs-lookup"><span data-stu-id="640b3-141">The `dbo` user account is frequently confused with the `db_owner` fixed database role.</span></span> <span data-ttu-id="640b3-142">`db_owner` のスコープがサーバー全体であるのに対し、`sysadmin` のスコープはデータベースです。</span><span class="sxs-lookup"><span data-stu-id="640b3-142">The scope of `db_owner` is a database; the scope of `sysadmin` is the whole server.</span></span> <span data-ttu-id="640b3-143">`db_owner` ロールのメンバーであるからといって、`dbo` のユーザー権限があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="640b3-143">Membership in the `db_owner` role does not confer `dbo` user privileges.</span></span>  
  
### <a name="the-guest-user-account"></a><span data-ttu-id="640b3-144">guest ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="640b3-144">The guest User Account</span></span>  

 <span data-ttu-id="640b3-145">認証されて SQL Server のインスタンスへのログインが許可されたユーザーが、その後、データベースにアクセスするためには各データベースに別個のユーザー アカウントが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="640b3-145">After a user has been authenticated and allowed to log in to an instance of SQL Server, a separate user account must exist in each database the user has to access.</span></span> <span data-ttu-id="640b3-146">データベースごとにユーザー アカウントが要求されるため、SQL Server のインスタンスに接続したとしても、ユーザーは、サーバー上のすべてのデータベースにアクセスできるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="640b3-146">Requiring a user account in each database prevents users from connecting to an instance of SQL Server and accessing all the databases on a server.</span></span> <span data-ttu-id="640b3-147">この要件を回避するには、データベースに `guest` ユーザー アカウントを設定します。guest ユーザーは、データベースにユーザー アカウントがなくてもデータベースにログインしてアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="640b3-147">The existence of a `guest` user account in the database circumvents this requirement by allowing a login without a database user account to access a database.</span></span>  
  
 <span data-ttu-id="640b3-148">`guest` アカウントは、SQL Server のすべてのバージョンが備えている組み込みのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="640b3-148">The `guest` account is a built-in account in all versions of SQL Server.</span></span> <span data-ttu-id="640b3-149">新しいデータベースでは、既定で無効化されています。</span><span class="sxs-lookup"><span data-stu-id="640b3-149">By default, it is disabled in new databases.</span></span> <span data-ttu-id="640b3-150">このアカウントを有効にした場合でも、Transact-SQL の REVOKE CONNECT FROM GUEST ステートメントを実行して、CONNECT 権限を取り消すことによって無効にできます。</span><span class="sxs-lookup"><span data-stu-id="640b3-150">If it is enabled, you can disable it by revoking its CONNECT permission by executing the Transact-SQL REVOKE CONNECT FROM GUEST statement.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="640b3-151">`guest` アカウントはできるだけ使用しないようにしてください。ユーザーごとに割り当てられたデータベース権限がなくても、すべてのログイン ユーザーが、このアカウントに付与されているデータベース権限を取得できるようになります。</span><span class="sxs-lookup"><span data-stu-id="640b3-151">Avoid using the `guest` account; all logins without their own database permissions obtain the database permissions granted to this account.</span></span> <span data-ttu-id="640b3-152">`guest` アカウントを使用する必要がある場合は、最小限の権限を付与するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="640b3-152">If you must use the `guest` account, grant it minimum permissions.</span></span>  
  
 <span data-ttu-id="640b3-153">SQL Server のログイン、ユーザー、およびロールの詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="640b3-153">For more information about SQL Server logins, users and roles, see the following resources.</span></span>  
  
|<span data-ttu-id="640b3-154">リソース</span><span class="sxs-lookup"><span data-stu-id="640b3-154">Resource</span></span>|<span data-ttu-id="640b3-155">説明</span><span class="sxs-lookup"><span data-stu-id="640b3-155">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="640b3-156">データベース エンジンの権限の概要</span><span class="sxs-lookup"><span data-stu-id="640b3-156">Getting Started with Database Engine Permissions</span></span>](/sql/relational-databases/security/authentication-access/getting-started-with-database-engine-permissions)|<span data-ttu-id="640b3-157">プリンシパル、ロール、資格情報、セキュリティ保護可能なリソース、および権限について説明したトピックへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="640b3-157">Contains links to topics that describe principals, roles, credentials, securables and permissions.</span></span>|  
|[<span data-ttu-id="640b3-158">プリンシパル</span><span class="sxs-lookup"><span data-stu-id="640b3-158">Principals</span></span>](/sql/relational-databases/security/authentication-access/principals-database-engine)|<span data-ttu-id="640b3-159">プリンシパルの説明のほか、サーバー ロールとデータベース ロールについて説明したトピックへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="640b3-159">Describes principals and contains links to topics that describe server and database roles.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="640b3-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="640b3-160">See also</span></span>

- [<span data-ttu-id="640b3-161">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="640b3-161">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="640b3-162">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="640b3-162">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="640b3-163">SQL Server での認証</span><span class="sxs-lookup"><span data-stu-id="640b3-163">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="640b3-164">SQL Server における所有権とユーザーとスキーマの分離</span><span class="sxs-lookup"><span data-stu-id="640b3-164">Ownership and User-Schema Separation in SQL Server</span></span>](ownership-and-user-schema-separation-in-sql-server.md)
- [<span data-ttu-id="640b3-165">SQL Server の承認とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="640b3-165">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="640b3-166">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="640b3-166">ADO.NET Overview</span></span>](../ado-net-overview.md)
