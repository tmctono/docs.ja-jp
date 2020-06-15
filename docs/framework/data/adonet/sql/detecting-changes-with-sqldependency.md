---
title: SqlDependency を使用した変更の検出
description: SqlDependency オブジェクトを SqlCommand に関連付けて、クエリ結果が ADO.NET で最初に取得したものと異なる場合を検出することができます。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: b196d42477e1778c45df64b1390502645fdd649d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286469"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="94920-103">SqlDependency を使用した変更の検出</span><span class="sxs-lookup"><span data-stu-id="94920-103">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="94920-104">クエリ結果が最初に取得されたクエリ結果と異なることを検出するために、<xref:System.Data.SqlClient.SqlDependency> オブジェクトを <xref:System.Data.SqlClient.SqlCommand> に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="94920-104">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="94920-105">`OnChange` イベントにデリゲートを割り当てることもできます。これは、関連付けられたコマンドの結果が変更されたときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="94920-105">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="94920-106">コマンドを実行する前に、<xref:System.Data.SqlClient.SqlDependency> をコマンドに関連付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="94920-106">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="94920-107">また、`HasChanges` の <xref:System.Data.SqlClient.SqlDependency> プロパティを使用しても、データが最初に取得されて以降にクエリ結果が変化したかどうかを判別できます。</span><span class="sxs-lookup"><span data-stu-id="94920-107">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="94920-108">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="94920-108">Security Considerations</span></span>

<span data-ttu-id="94920-109">指定されたコマンドについて基になるデータが変更されたという通知を受け取るために、依存関係を持つインフラストラクチャでは <xref:System.Data.SqlClient.SqlConnection> が呼び出されると、<xref:System.Data.SqlClient.SqlDependency.Start%2A> が開かれることを利用します。</span><span class="sxs-lookup"><span data-stu-id="94920-109">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="94920-110">クライアントが `SqlDependency.Start` の呼び出しを開始できるかどうかは、<xref:System.Data.SqlClient.SqlClientPermission> を使用し、コード アクセス セキュリティ属性を利用することで制御します。</span><span class="sxs-lookup"><span data-stu-id="94920-110">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="94920-111">詳しくは、「[クエリ通知の有効化](enabling-query-notifications.md)」および「[コード アクセス セキュリティと ADO.NET](../code-access-security.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="94920-111">For more information, see [Enabling Query Notifications](enabling-query-notifications.md) and [Code Access Security and ADO.NET](../code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="94920-112">例</span><span class="sxs-lookup"><span data-stu-id="94920-112">Example</span></span>

<span data-ttu-id="94920-113">次の手順では、依存関係を宣言し、コマンドを実行し、結果セットが変更されたときに通知を受け取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="94920-113">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="94920-114">サーバーへの `SqlDependency` 接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="94920-114">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="94920-115">サーバーに接続して Transact-SQL ステートメントを定義するための <xref:System.Data.SqlClient.SqlConnection> および <xref:System.Data.SqlClient.SqlCommand> オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="94920-115">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="94920-116">新しい `SqlDependency` オブジェクトを作成するか、既存のオブジェクトを使用して、それを `SqlCommand` オブジェクトにバインドします。</span><span class="sxs-lookup"><span data-stu-id="94920-116">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="94920-117">内部では、これによって <xref:System.Data.Sql.SqlNotificationRequest> オブジェクトが作成され、必要に応じてコマンド オブジェクトにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="94920-117">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="94920-118">この通知要求には、この `SqlDependency` オブジェクトを一意に識別する内部識別子が含まれます。</span><span class="sxs-lookup"><span data-stu-id="94920-118">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="94920-119">また、これにより、クライアント リスナーがまだアクティブになっていない場合に起動されます。</span><span class="sxs-lookup"><span data-stu-id="94920-119">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="94920-120">イベント ハンドラーを `SqlDependency` オブジェクトの `OnChange` イベントにサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="94920-120">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="94920-121">`SqlCommand` オブジェクトの任意の `Execute` メソッドを使用して、コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="94920-121">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="94920-122">コマンドは通知オブジェクトにバインドされているため、サーバーで通知を生成する必要があることが認識され、キュー情報が依存関係キューを指します。</span><span class="sxs-lookup"><span data-stu-id="94920-122">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="94920-123">サーバーへの `SqlDependency` 接続を停止します。</span><span class="sxs-lookup"><span data-stu-id="94920-123">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="94920-124">その後ユーザーが基になるデータを変更した場合、Microsoft SQL Server でその変更に対して保留中の通知があることが検出され、`SqlDependency.Start` を呼び出して作成された、基になる `SqlConnection` を介して処理され、クライアントに転送される通知が送信されます。</span><span class="sxs-lookup"><span data-stu-id="94920-124">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="94920-125">クライアント リスナーで、無効化メッセージが受信されます。</span><span class="sxs-lookup"><span data-stu-id="94920-125">The client listener receives the invalidation message.</span></span> <span data-ttu-id="94920-126">次にクライアント リスナーで、関連付けられている `SqlDependency` オブジェクトが検索され、`OnChange` イベントが起動されます。</span><span class="sxs-lookup"><span data-stu-id="94920-126">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="94920-127">次のコード フラグメントに、サンプル アプリケーションの作成に利用されるデザイン パターンを示します。</span><span class="sxs-lookup"><span data-stu-id="94920-127">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

```vb
Sub Initialization()
    ' Create a dependency connection.
    SqlDependency.Start(connectionString, queueName)
End Sub

Sub SomeMethod()
    ' Assume connection is an open SqlConnection.
    ' Create a new SqlCommand object.
    Using command As New SqlCommand( _
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _
      connection)

        ' Create a dependency and associate it with the SqlCommand.
        Dim dependency As New SqlDependency(command)
        ' Maintain the refernce in a class member.
        ' Subscribe to the SqlDependency event.
        AddHandler dependency.OnChange, AddressOf OnDependencyChange

        ' Execute the command.
        Using reader = command.ExecuteReader()
            ' Process the DataReader.
        End Using
    End Using
End Sub

' Handler method
Sub OnDependencyChange(ByVal sender As Object, _
    ByVal e As SqlNotificationEventArgs)
    ' Handle the event (for example, invalidate this cache entry).
End Sub

Sub Termination()
    ' Release the dependency
    SqlDependency.Stop(connectionString, queueName)
End Sub
```

```csharp
void Initialization()
{
    // Create a dependency connection.
    SqlDependency.Start(connectionString, queueName);
}

void SomeMethod()
{
    // Assume connection is an open SqlConnection.

    // Create a new SqlCommand object.
    using (SqlCommand command=new SqlCommand(
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",
        connection))
    {

        // Create a dependency and associate it with the SqlCommand.
        SqlDependency dependency=new SqlDependency(command);
        // Maintain the reference in a class member.

        // Subscribe to the SqlDependency event.
        dependency.OnChange+=new
           OnChangeEventHandler(OnDependencyChange);

        // Execute the command.
        using (SqlDataReader reader = command.ExecuteReader())
        {
            // Process the DataReader.
        }
    }
}

// Handler method
void OnDependencyChange(object sender,
   SqlNotificationEventArgs e )
{
  // Handle the event (for example, invalidate this cache entry).
}

void Termination()
{
    // Release the dependency.
    SqlDependency.Stop(connectionString, queueName);
}
```

## <a name="see-also"></a><span data-ttu-id="94920-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="94920-128">See also</span></span>

- [<span data-ttu-id="94920-129">SQL Server のクエリ通知</span><span class="sxs-lookup"><span data-stu-id="94920-129">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="94920-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="94920-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
