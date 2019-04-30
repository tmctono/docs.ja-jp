---
title: SQL Server における行レベルの権限の付与
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: 891b5114551c5784b11504f2463525087125131f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033905"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="aa09c-102">SQL Server における行レベルの権限の付与</span><span class="sxs-lookup"><span data-stu-id="aa09c-102">Granting Row-Level Permissions in SQL Server</span></span>

<span data-ttu-id="aa09c-103">権限を単に付与、取り消し、拒否するよりも細かなレベルで、データに対するアクセスを制御することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa09c-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="aa09c-104">たとえば、医療施設のデータベース アプリケーションでは、各医師がアクセスできるのは、自分が担当している患者の情報のみに制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa09c-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="aa09c-105">同様の要件は、金融機関、司法機関、政府機関、軍事機関のアプリケーションなど、さまざまな環境で考えられます。</span><span class="sxs-lookup"><span data-stu-id="aa09c-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="aa09c-106">こうしたシナリオに対処するため SQL Server 2016 には、 [行レベルのセキュリティ](/sql/relational-databases/security/row-level-security) 機能が備わっています。この機能は、セキュリティ ポリシーにおける行レベルのアクセス ロジックを簡略化および一元化します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](/sql/relational-databases/security/row-level-security) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="aa09c-107">従来の SQL Server バージョンでは、同様の機能は行レベルのフィルター処理を行うビューを使用して実現できます。</span><span class="sxs-lookup"><span data-stu-id="aa09c-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>

## <a name="implementing-row-level-filtering"></a><span data-ttu-id="aa09c-108">行レベルのフィルター処理の実装</span><span class="sxs-lookup"><span data-stu-id="aa09c-108">Implementing Row-level Filtering</span></span>

<span data-ttu-id="aa09c-109">行レベルのフィルター処理は、前述の病院の例などのように、1 つのテーブルに情報を格納するアプリケーションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="aa09c-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="aa09c-110">行レベルのフィルター処理を実装するため、それぞれの行には、ユーザー名、ラベル、識別子など、区別するパラメーターを定義する列があります。</span><span class="sxs-lookup"><span data-stu-id="aa09c-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="aa09c-111">対象テーブルでセキュリティ ポリシーまたはビューを作成し、ユーザーがアクセスできる行をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="aa09c-112">その後、パラメーター化されたストアド プロシージャを作成し、ユーザーが実行できるクエリの種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>

<span data-ttu-id="aa09c-113">次の例は、ユーザー名またはログイン名に基づいて行レベルのフィルター処理を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="aa09c-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>

- <span data-ttu-id="aa09c-114">テーブルを作成し、名前を格納するための列を追加します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-114">Create the table, adding a column to store the name.</span></span>

- <span data-ttu-id="aa09c-115">行レベルのフィルター処理を以下のように有効にします。</span><span class="sxs-lookup"><span data-stu-id="aa09c-115">Enable row-level filtering:</span></span>

  - <span data-ttu-id="aa09c-116">SQL Server 2016 以降または [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/)を使用している場合は、表に関する述語を追加するセキュリティー ポリシーを作成します。このセキュリティー・ポリシーは、現在のデータベース ユーザー (CURRENT_USER() 組み込み関数を使用) または現在のログイン名 (SUSER_SNAME() 組み込み関数を使用) のいずれかに一致する行のみが返されるように制限します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](https://docs.microsoft.com/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>

      ```sql
      CREATE SCHEMA Security
      GO

      CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)
          RETURNS TABLE
          WITH SCHEMABINDING
      AS
          RETURN SELECT 1 AS accessResult
          WHERE @UserName = SUSER_SNAME()
      GO

      CREATE SECURITY POLICY Security.userAccessPolicy
          ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,
          ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable
      GO
      ```

  - <span data-ttu-id="aa09c-117">SQL Server 2016 より前のバージョンを使用している場合、同様の機能はビューを使用して実現できます。</span><span class="sxs-lookup"><span data-stu-id="aa09c-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- <span data-ttu-id="aa09c-118">データを選択、挿入、更新、削除するストアド プロシージャを作成します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="aa09c-119">フィルター処理を行うのにセキュリティ ポリシーを使用する場合には、ストアド プロシージャが基本テーブルでこれらの操作を直接実行する必要があります。フィルター処理がビューによって行われる場合、ストアド プロシージャがビューのためにビューに対して操作を行わなければなりません。</span><span class="sxs-lookup"><span data-stu-id="aa09c-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="aa09c-120">セキュリティ ポリシーまたはビューは、ユーザーのクエリによって返される行または変更された行を自動的にフィルター処理します。ストアド プロシージャは堅固なセキュリティ境界を設け、クエリに対して直接アクセスできるユーザーが、クエリを正常に実行し、フィルター対象データの存在を推論できてしまうという事態を回避します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>

- <span data-ttu-id="aa09c-121">データの挿入を行うストアド プロシージャの場合、セキュリティ ポリシーまたはビューで指定したのと同じ関数を使用してユーザー名を取得し、その値を UserName 列に挿入します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>

- <span data-ttu-id="aa09c-122">テーブル (該当する場合にはビューも) に設定されている `public` ロールの権限をすべて拒否します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="aa09c-123">フィルター処理の述語には、ロールではなくユーザー名またはログイン名が使用されているため、ユーザーは、他のデータベース ロールから権限を継承することはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="aa09c-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>

- <span data-ttu-id="aa09c-124">データベース ロールにストアド プロシージャの EXECUTE 権限を付与します。</span><span class="sxs-lookup"><span data-stu-id="aa09c-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="aa09c-125">ユーザーは、提供されているストアド プロシージャを使ってのみ、データにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="aa09c-125">Users can only access data through the stored procedures provided.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa09c-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa09c-126">See also</span></span>

- [<span data-ttu-id="aa09c-127">行レベル セキュリティ</span><span class="sxs-lookup"><span data-stu-id="aa09c-127">Row-Level Security</span></span>](/sql/relational-databases/security/row-level-security)
- [<span data-ttu-id="aa09c-128">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="aa09c-128">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [<span data-ttu-id="aa09c-129">SQL Server セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="aa09c-129">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [<span data-ttu-id="aa09c-130">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="aa09c-130">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="aa09c-131">SQL Server でのストアド プロシージャを使用したアクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="aa09c-131">Managing Permissions with Stored Procedures in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="aa09c-132">SQL Server での安全な動的 SQL の作成</span><span class="sxs-lookup"><span data-stu-id="aa09c-132">Writing Secure Dynamic SQL in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="aa09c-133">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="aa09c-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
