---
title: 接続文字列の構文
description: ADO.NET の接続文字列の構文について説明します。 各プロバイダーの構文は、対応する ConnectionString プロパティのトピックで説明されています。
ms.date: 05/22/2018
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
ms.openlocfilehash: bb29365a4729e731ddeffc7cfa61e379c3144a46
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287052"
---
# <a name="connection-string-syntax"></a><span data-ttu-id="6170c-104">接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="6170c-104">Connection String Syntax</span></span>
<span data-ttu-id="6170c-105">すべての .NET Framework データ プロバイダーは、`Connection` を継承する <xref:System.Data.Common.DbConnection> オブジェクトに加え、プロバイダー固有の <xref:System.Data.Common.DbConnection.ConnectionString%2A> プロパティを持ちます。</span><span class="sxs-lookup"><span data-stu-id="6170c-105">Each .NET Framework data provider has a `Connection` object that inherits from <xref:System.Data.Common.DbConnection> as well as a provider-specific <xref:System.Data.Common.DbConnection.ConnectionString%2A> property.</span></span> <span data-ttu-id="6170c-106">それぞれのプロバイダーに固有の接続文字列の構文は、対応する `ConnectionString` プロパティのトピックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="6170c-106">The specific connection string syntax for each provider is documented in its `ConnectionString` property.</span></span> <span data-ttu-id="6170c-107">次の表は、.NET Framework に含まれている 4 つのデータ プロバイダーを一覧にしたものです。</span><span class="sxs-lookup"><span data-stu-id="6170c-107">The following table lists the four data providers that are included in the .NET Framework.</span></span>  
  
|<span data-ttu-id="6170c-108">.NET Framework データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6170c-108">.NET Framework data provider</span></span>|<span data-ttu-id="6170c-109">説明</span><span class="sxs-lookup"><span data-stu-id="6170c-109">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|<span data-ttu-id="6170c-110">Microsoft SQL Server へのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6170c-110">Provides data access for Microsoft SQL Server.</span></span> <span data-ttu-id="6170c-111">接続文字列の構文の詳細については、「<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-111">For more information on connection string syntax, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.OleDb>|<span data-ttu-id="6170c-112">OLE DB を使って公開されたデータ ソースへのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6170c-112">Provides data access for data sources exposed using OLE DB.</span></span> <span data-ttu-id="6170c-113">接続文字列の構文の詳細については、「<xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-113">For more information on connection string syntax, see <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.Odbc>|<span data-ttu-id="6170c-114">ODBC を使って公開されたデータ ソースへのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6170c-114">Provides data access for data sources exposed using ODBC.</span></span> <span data-ttu-id="6170c-115">接続文字列の構文の詳細については、「<xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-115">For more information on connection string syntax, see <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.OracleClient>|<span data-ttu-id="6170c-116">Oracle バージョン 8.1.7 以降へのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6170c-116">Provides data access for Oracle version 8.1.7 or later.</span></span> <span data-ttu-id="6170c-117">接続文字列の構文の詳細については、「<xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-117">For more information on connection string syntax, see <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.</span></span>|  
  
## <a name="connection-string-builders"></a><span data-ttu-id="6170c-118">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="6170c-118">Connection String Builders</span></span>  
 <span data-ttu-id="6170c-119">ADO.NET 2.0 では、.NET Framework データ プロバイダー用の次の接続文字列ビルダーが導入されました。</span><span class="sxs-lookup"><span data-stu-id="6170c-119">ADO.NET 2.0 introduced the following connection string builders for the .NET Framework data providers.</span></span>  
  
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
- <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
- <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
- <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 <span data-ttu-id="6170c-120">接続文字列ビルダーを使用すると、構文的に正しい接続文字列を実行時に構築できるため、コード内で接続文字列値を手動で連結する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6170c-120">The connection string builders allow you to construct syntactically valid connection strings at run time, so you do not have to manually concatenate connection string values in your code.</span></span> <span data-ttu-id="6170c-121">詳細については、「[接続文字列ビルダー](connection-string-builders.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6170c-121">For more information, see [Connection String Builders](connection-string-builders.md).</span></span>  

## <a name="windows-authentication"></a><span data-ttu-id="6170c-122">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="6170c-122">Windows Authentication</span></span>  
 <span data-ttu-id="6170c-123">データ ソースでサポートされている場合は、Windows 認証 ("*統合セキュリティ*" とも呼ばれます) を使用して接続することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6170c-123">We recommend using Windows Authentication (sometimes referred to as *integrated security*) to connect to data sources that support it.</span></span> <span data-ttu-id="6170c-124">接続文字列の構文は、プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="6170c-124">The syntax employed in the connection string varies by provider.</span></span> <span data-ttu-id="6170c-125">.NET Framework データ プロバイダーで使用されている Windows 認証の構文を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6170c-125">The following table shows the Windows Authentication syntax used with the .NET Framework data providers.</span></span>  
  
|<span data-ttu-id="6170c-126">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6170c-126">Provider</span></span>|<span data-ttu-id="6170c-127">構文</span><span class="sxs-lookup"><span data-stu-id="6170c-127">Syntax</span></span>|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
> <span data-ttu-id="6170c-128">`Integrated Security=true` プロバイダーで `OleDb` に設定すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="6170c-128">`Integrated Security=true` throws an exception when used with the `OleDb` provider.</span></span>  
  
## <a name="sqlclient-connection-strings"></a><span data-ttu-id="6170c-129">SqlClient 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6170c-129">SqlClient Connection Strings</span></span>  
<span data-ttu-id="6170c-130"><xref:System.Data.SqlClient.SqlConnection> 接続文字列の構文については、<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> プロパティで説明されています。</span><span class="sxs-lookup"><span data-stu-id="6170c-130">The syntax for a <xref:System.Data.SqlClient.SqlConnection> connection string is documented in the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6170c-131"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> プロパティを使用すると、SQL Server データベースの接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6170c-131">You can use the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property to get or set a connection string for a SQL Server database.</span></span> <span data-ttu-id="6170c-132">以前のバージョンの SQL Server に接続する必要がある場合は、.NET Framework Data Provider for OleDb (<xref:System.Data.OleDb>) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6170c-132">If you need to connect to an earlier version of SQL Server, you must use the .NET Framework Data Provider for OleDb (<xref:System.Data.OleDb>).</span></span> <span data-ttu-id="6170c-133">接続文字列のほとんどのキーワードは、<xref:System.Data.SqlClient.SqlConnectionStringBuilder> のプロパティにマップされています。</span><span class="sxs-lookup"><span data-stu-id="6170c-133">Most connection string keywords also map to properties in the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="6170c-134">`Persist Security Info` キーワードの既定の設定は `false` です。</span><span class="sxs-lookup"><span data-stu-id="6170c-134">The default setting for the `Persist Security Info` keyword is `false`.</span></span> <span data-ttu-id="6170c-135">このキーワードを `true` または `yes` に設定すると、ユーザー ID やパスワードなどのセキュリティ関連情報を、接続を開いた後にその接続から取得できます。</span><span class="sxs-lookup"><span data-stu-id="6170c-135">Setting it to `true` or `yes` allows security-sensitive information, including the user ID and password, to be obtained from the connection after the connection has been opened.</span></span> <span data-ttu-id="6170c-136">機密を要する接続文字列情報が、信頼できないソースによってアクセスされることのないよう、`Persist Security Info` は必ず `false` にしてください。</span><span class="sxs-lookup"><span data-stu-id="6170c-136">Keep `Persist Security Info` set to `false` to ensure that an untrusted source does not have access to sensitive connection string information.</span></span>  

### <a name="windows-authentication-with-sqlclient"></a><span data-ttu-id="6170c-137">SqlClient での Windows 認証</span><span class="sxs-lookup"><span data-stu-id="6170c-137">Windows authentication with SqlClient</span></span>
 <span data-ttu-id="6170c-138">次の構文のフォームはそれぞれ、Windows 認証を使用してローカル サーバー上の **AdventureWorks** データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="6170c-138">Each of the following forms of syntax uses Windows Authentication to connect to the **AdventureWorks** database on a local server.</span></span>  
  
```csharp  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a><span data-ttu-id="6170c-139">SqlClient での SQL Server 認証</span><span class="sxs-lookup"><span data-stu-id="6170c-139">SQL Server authentication with SqlClient</span></span>
 <span data-ttu-id="6170c-140">SQL Server への接続には Windows 認証の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6170c-140">Windows Authentication is preferred for connecting to SQL Server.</span></span> <span data-ttu-id="6170c-141">ただし、どうしても SQL Server 認証を使用する必要がある場合は、次の構文に従ってユーザー名とパスワードを指定してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-141">However, if SQL Server Authentication is required, use the following syntax to specify a user name and password.</span></span> <span data-ttu-id="6170c-142">この例では、アスタリスクを使用して有効なユーザー名とパスワードを表しています。</span><span class="sxs-lookup"><span data-stu-id="6170c-142">In this example, asterisks are used to represent a valid user name and password.</span></span>  
  
```csharp  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

<span data-ttu-id="6170c-143">Azure SQL Database または Azure SQL Data Warehouse に接続し、`user@servername` の形式でログインを指定する場合は、ログインの `servername` の値が `Server=` に指定されている値と一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="6170c-143">When you connect to Azure SQL Database or to Azure SQL Data Warehouse and provide a login in the format `user@servername`, make sure that the `servername` value in the login matches the value provided for `Server=`.</span></span>

> [!NOTE]
> <span data-ttu-id="6170c-144">Windows 認証は SQL Server ログインよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-144">Windows authentication takes precedence over SQL Server logins.</span></span> <span data-ttu-id="6170c-145">Integrated Security を true に指定し、ユーザー名とパスワードも指定した場合、ユーザー名とパスワードは無視され、Windows 認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-145">If you specify both Integrated Security=true as well as a user name and password, the user name and password will be ignored and Windows authentication will be used.</span></span>  

### <a name="connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="6170c-146">SQL Server の名前付きインスタンスに接続する</span><span class="sxs-lookup"><span data-stu-id="6170c-146">Connect to a named instance of SQL Server</span></span>
<span data-ttu-id="6170c-147">SQL Server の名前付きインスタンスに接続するには、*server name\instance name* 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="6170c-147">To connect to a named instance of SQL Server, use the *server name\instance name* syntax.</span></span>  
  
```csharp  
"Data Source=MySqlServer\MSSQL1;"  
```  

<span data-ttu-id="6170c-148">接続文字列の作成時に、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> の `SqlConnectionStringBuilder` プロパティをインスタンス名に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6170c-148">You can also set the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> property of the `SqlConnectionStringBuilder` to the instance name when building a connection string.</span></span> <span data-ttu-id="6170c-149"><xref:System.Data.SqlClient.SqlConnection.DataSource%2A> オブジェクトの <xref:System.Data.SqlClient.SqlConnection> プロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="6170c-149">The <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> property of a <xref:System.Data.SqlClient.SqlConnection> object is read-only.</span></span>  
  
### <a name="type-system-version-changes"></a><span data-ttu-id="6170c-150">Type System Version の変更</span><span class="sxs-lookup"><span data-stu-id="6170c-150">Type System Version Changes</span></span>  
 <span data-ttu-id="6170c-151"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> の `Type System Version` キーワードは、クライアント側での SQL Server 型の表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="6170c-151">The `Type System Version` keyword in a <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> specifies the client-side representation of SQL Server types.</span></span> <span data-ttu-id="6170c-152"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> キーワードの詳細については、`Type System Version` のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-152">See <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> for more information about the `Type System Version` keyword.</span></span>  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a><span data-ttu-id="6170c-153">SQL Server Express ユーザー インスタンスへの接続とアタッチ</span><span class="sxs-lookup"><span data-stu-id="6170c-153">Connecting and Attaching to SQL Server Express User Instances</span></span>  
 <span data-ttu-id="6170c-154">ユーザー インスタンスは、SQL Server Express の機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="6170c-154">User instances are a feature in SQL Server Express.</span></span> <span data-ttu-id="6170c-155">最小限の特権しか持たないローカル Windows アカウントで実行しているユーザーが、SQL Server データベースにアタッチできます。この場合、管理特権は不要です。</span><span class="sxs-lookup"><span data-stu-id="6170c-155">They allow a user running on a least-privileged local Windows account to attach and run a SQL Server database without requiring administrative privileges.</span></span> <span data-ttu-id="6170c-156">ユーザー インスタンスは、サービスとしてではなく、ユーザーの Windows 資格情報で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-156">A user instance executes with the user's Windows credentials, not as a service.</span></span>  
  
 <span data-ttu-id="6170c-157">ユーザー インスタンスの使用について詳しくは、「[SQL Server Express ユーザー インスタンス](./sql/sql-server-express-user-instances.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6170c-157">For more information on working with user instances, see [SQL Server Express User Instances](./sql/sql-server-express-user-instances.md).</span></span>  
  
## <a name="using-trustservercertificate"></a><span data-ttu-id="6170c-158">TrustServerCertificate の使用</span><span class="sxs-lookup"><span data-stu-id="6170c-158">Using TrustServerCertificate</span></span>  
 <span data-ttu-id="6170c-159">`TrustServerCertificate` キーワードは、有効な証明書を使用して SQL Server インスタンスに接続する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6170c-159">The `TrustServerCertificate` keyword is valid only when connecting to a SQL Server instance with a valid certificate.</span></span> <span data-ttu-id="6170c-160">`TrustServerCertificate` を `true` に設定した場合、トランスポート層に SSL が使用されてチャネルが暗号化されます。また、証明書チェーンをたどることによる信頼性の検証は省略されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-160">When `TrustServerCertificate` is set to `true`, the transport layer will use SSL to encrypt the channel and bypass walking the certificate chain to validate trust.</span></span>  
  
```csharp  
"TrustServerCertificate=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="6170c-161">`TrustServerCertificate` を `true` に設定して暗号化を有効にした場合、接続文字列で `Encrypt` を `false` に設定したとしても、サーバーで指定された暗号化レベルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-161">If `TrustServerCertificate` is set to `true` and encryption is turned on, the encryption level specified on the server will be used even if `Encrypt` is set to `false` in the connection string.</span></span> <span data-ttu-id="6170c-162">それ以外の場合、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="6170c-162">The connection will fail otherwise.</span></span>  
  
### <a name="enabling-encryption"></a><span data-ttu-id="6170c-163">暗号化の有効化</span><span class="sxs-lookup"><span data-stu-id="6170c-163">Enabling Encryption</span></span>  
 <span data-ttu-id="6170c-164">サーバー証明書がプロビジョニングされていない場合、暗号化を有効にするには、SQL Server 構成マネージャーで **[プロトコルの暗号化を設定する]** オプションと **[サーバー証明書を信頼する]** オプションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6170c-164">To enable encryption when a certificate has not been provisioned on the server, the **Force Protocol Encryption** and the **Trust Server Certificate** options must be set in SQL Server Configuration Manager.</span></span> <span data-ttu-id="6170c-165">このように、検証可能なサーバー証明書がプロビジョニングされていない場合、暗号化には検証を伴わない自己署名入りのサーバー証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-165">In this case, encryption will use a self-signed server certificate without validation if no verifiable certificate has been provisioned on the server.</span></span>  
  
 <span data-ttu-id="6170c-166">SQL Server で構成されたセキュリティのレベルを、アプリケーションの設定によって緩和することはできません。ただし、必要に応じて厳密にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="6170c-166">Application settings cannot reduce the level of security configured in SQL Server, but can optionally strengthen it.</span></span> <span data-ttu-id="6170c-167">アプリケーションから暗号化を要求するには、`TrustServerCertificate` キーワードおよび `Encrypt` キーワードを `true` に設定します。こうすることで、サーバー証明書がプロビジョニングされておらず、なおかつ、クライアントで **[プロトコルの暗号化を設定する]** が構成されていない場合でも常に暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="6170c-167">An application can request encryption by setting the `TrustServerCertificate` and `Encrypt` keywords to `true`, guaranteeing that encryption takes place even when a server certificate has not been provisioned and **Force Protocol Encryption** has not been configured for the client.</span></span> <span data-ttu-id="6170c-168">ただし、クライアントの構成で `TrustServerCertificate` を有効にしなかった場合は、プロビジョニングされたサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="6170c-168">However, if `TrustServerCertificate` is not enabled in the client configuration, a provisioned server certificate is still required.</span></span>  
  
 <span data-ttu-id="6170c-169">次の表ですべてのケースを説明します。</span><span class="sxs-lookup"><span data-stu-id="6170c-169">The following table describes all cases.</span></span>  
  
|<span data-ttu-id="6170c-170">[プロトコルの暗号化を設定する] クライアント設定</span><span class="sxs-lookup"><span data-stu-id="6170c-170">Force Protocol Encryption client setting</span></span>|<span data-ttu-id="6170c-171">[サーバー証明書を信頼する] クライアント設定</span><span class="sxs-lookup"><span data-stu-id="6170c-171">Trust Server Certificate client setting</span></span>|<span data-ttu-id="6170c-172">Encrypt/Use Encryption for Data 接続文字列/属性</span><span class="sxs-lookup"><span data-stu-id="6170c-172">Encrypt/Use Encryption for Data connection string/attribute</span></span>|<span data-ttu-id="6170c-173">Trust Server Certificate 接続文字列/属性</span><span class="sxs-lookup"><span data-stu-id="6170c-173">Trust Server Certificate connection string/attribute</span></span>|<span data-ttu-id="6170c-174">結果</span><span class="sxs-lookup"><span data-stu-id="6170c-174">Result</span></span>|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|<span data-ttu-id="6170c-175">いいえ</span><span class="sxs-lookup"><span data-stu-id="6170c-175">No</span></span>|<span data-ttu-id="6170c-176">N/A</span><span class="sxs-lookup"><span data-stu-id="6170c-176">N/A</span></span>|<span data-ttu-id="6170c-177">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6170c-177">No (default)</span></span>|<span data-ttu-id="6170c-178">無視</span><span class="sxs-lookup"><span data-stu-id="6170c-178">Ignored</span></span>|<span data-ttu-id="6170c-179">暗号化は行われません。</span><span class="sxs-lookup"><span data-stu-id="6170c-179">No encryption occurs.</span></span>|  
|<span data-ttu-id="6170c-180">いいえ</span><span class="sxs-lookup"><span data-stu-id="6170c-180">No</span></span>|<span data-ttu-id="6170c-181">N/A</span><span class="sxs-lookup"><span data-stu-id="6170c-181">N/A</span></span>|<span data-ttu-id="6170c-182">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-182">Yes</span></span>|<span data-ttu-id="6170c-183">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6170c-183">No (default)</span></span>|<span data-ttu-id="6170c-184">暗号化は、検証可能なサーバー証明書が提供されている場合にのみ行われます。それ以外の場合は、接続試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="6170c-184">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="6170c-185">いいえ</span><span class="sxs-lookup"><span data-stu-id="6170c-185">No</span></span>|<span data-ttu-id="6170c-186">N/A</span><span class="sxs-lookup"><span data-stu-id="6170c-186">N/A</span></span>|<span data-ttu-id="6170c-187">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-187">Yes</span></span>|<span data-ttu-id="6170c-188">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-188">Yes</span></span>|<span data-ttu-id="6170c-189">暗号化は常に行われますが、自己署名入りのサーバー証明書を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="6170c-189">Encryption always occurs, but may use a self-signed server certificate.</span></span>|  
|<span data-ttu-id="6170c-190">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-190">Yes</span></span>|<span data-ttu-id="6170c-191">いいえ</span><span class="sxs-lookup"><span data-stu-id="6170c-191">No</span></span>|<span data-ttu-id="6170c-192">無視</span><span class="sxs-lookup"><span data-stu-id="6170c-192">Ignored</span></span>|<span data-ttu-id="6170c-193">無視</span><span class="sxs-lookup"><span data-stu-id="6170c-193">Ignored</span></span>|<span data-ttu-id="6170c-194">暗号化は、検証可能なサーバー証明書が提供されている場合にのみ行われます。それ以外の場合は、接続試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="6170c-194">Encryption occurs only if there is a verifiable server certificate; otherwise, the connection attempt fails.</span></span>|  
|<span data-ttu-id="6170c-195">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-195">Yes</span></span>|<span data-ttu-id="6170c-196">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-196">Yes</span></span>|<span data-ttu-id="6170c-197">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6170c-197">No (default)</span></span>|<span data-ttu-id="6170c-198">無視</span><span class="sxs-lookup"><span data-stu-id="6170c-198">Ignored</span></span>|<span data-ttu-id="6170c-199">暗号化は常に行われますが、自己署名入りのサーバー証明書を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="6170c-199">Encryption always occurs, but may use a self-signed server certificate.</span></span>|  
|<span data-ttu-id="6170c-200">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-200">Yes</span></span>|<span data-ttu-id="6170c-201">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-201">Yes</span></span>|<span data-ttu-id="6170c-202">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-202">Yes</span></span>|<span data-ttu-id="6170c-203">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="6170c-203">No (default)</span></span>|<span data-ttu-id="6170c-204">暗号化は、検証可能なサーバー証明書が提供されている場合にのみ行われます。それ以外の場合は、接続試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="6170c-204">Encryption occurs only if there is a verifiable server certificate; otherwise, the connection attempt fails.</span></span>|  
|<span data-ttu-id="6170c-205">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-205">Yes</span></span>|<span data-ttu-id="6170c-206">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-206">Yes</span></span>|<span data-ttu-id="6170c-207">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-207">Yes</span></span>|<span data-ttu-id="6170c-208">はい</span><span class="sxs-lookup"><span data-stu-id="6170c-208">Yes</span></span>|<span data-ttu-id="6170c-209">暗号化は常に行われますが、自己署名入りのサーバー証明書を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="6170c-209">Encryption always occurs, but may use a self-signed server certificate.</span></span>|  
  
 <span data-ttu-id="6170c-210">詳細については、「[検証を伴わない暗号化の使用](/sql/relational-databases/native-client/features/using-encryption-without-validation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-210">For more information, see [Using Encryption Without Validation](/sql/relational-databases/native-client/features/using-encryption-without-validation).</span></span>
  
## <a name="oledb-connection-strings"></a><span data-ttu-id="6170c-211">OleDb 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6170c-211">OleDb Connection Strings</span></span>  
 <span data-ttu-id="6170c-212"><xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> の <xref:System.Data.OleDb.OleDbConnection> プロパティを使用すると、Microsoft Access などの OLE DB データ ソースの接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6170c-212">The <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> property of a <xref:System.Data.OleDb.OleDbConnection> allows you to get or set a connection string for an OLE DB data source, such as Microsoft Access.</span></span> <span data-ttu-id="6170c-213">`OleDb` クラスを使用して、実行時に <xref:System.Data.OleDb.OleDbConnectionStringBuilder> 接続文字列を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="6170c-213">You can also create an `OleDb` connection string at run time by using the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> class.</span></span>  
  
### <a name="oledb-connection-string-syntax"></a><span data-ttu-id="6170c-214">OleDb 接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="6170c-214">OleDb Connection String Syntax</span></span>  
 <span data-ttu-id="6170c-215"><xref:System.Data.OleDb.OleDbConnection> 接続文字列では、プロバイダー名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6170c-215">You must specify a provider name for an <xref:System.Data.OleDb.OleDbConnection> connection string.</span></span> <span data-ttu-id="6170c-216">次の接続文字列は、Jet プロバイダーを使用して Microsoft Access データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="6170c-216">The following connection string connects to a Microsoft Access database using the Jet provider.</span></span> <span data-ttu-id="6170c-217">`User ID` および `Password` キーワードは、データベースがセキュリティ保護されていない場合は省略できます (既定)。</span><span class="sxs-lookup"><span data-stu-id="6170c-217">Note that the `User ID` and `Password` keywords are optional if the database is unsecured (the default).</span></span>  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;
```  
  
 <span data-ttu-id="6170c-218">ユーザー レベルのセキュリティを使用して Jet データベースがセキュリティ保護されている場合は、ワークグループ情報ファイル (.mdw) の場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6170c-218">If the Jet database is secured using user-level security, you must provide the location of the workgroup information file (.mdw).</span></span> <span data-ttu-id="6170c-219">ワークグループ情報ファイルを使用して接続文字列に表示された資格情報を検証します。</span><span class="sxs-lookup"><span data-stu-id="6170c-219">The workgroup information file is used to validate the credentials presented in the connection string.</span></span>  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="6170c-220">**OleDbConnection** の接続情報は、UDL (Universal Data Link) ファイルを使用して提供できますが、このファイルは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6170c-220">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="6170c-221">UDL ファイルは暗号化されないため、接続文字列をテキスト形式で表現してしまいます。</span><span class="sxs-lookup"><span data-stu-id="6170c-221">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="6170c-222">UDL ファイルは、アプリケーションにとって外部ファイルをベースにしたリソースであるため、.NET Framework でセキュリティ保護できません。</span><span class="sxs-lookup"><span data-stu-id="6170c-222">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span> <span data-ttu-id="6170c-223">UDL ファイルは **SqlClient** ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="6170c-223">UDL files are not supported for **SqlClient**.</span></span>  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a><span data-ttu-id="6170c-224">DataDirectory を使用した Access/Jet との接続</span><span class="sxs-lookup"><span data-stu-id="6170c-224">Using DataDirectory to Connect to Access/Jet</span></span>  
 <span data-ttu-id="6170c-225">`DataDirectory` の使用は `SqlClient` に限定されません。</span><span class="sxs-lookup"><span data-stu-id="6170c-225">`DataDirectory` is not exclusive to `SqlClient`.</span></span> <span data-ttu-id="6170c-226"><xref:System.Data.OleDb> および <xref:System.Data.Odbc> .NET データ プロバイダーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="6170c-226">It can also be used with the <xref:System.Data.OleDb> and <xref:System.Data.Odbc> .NET data providers.</span></span> <span data-ttu-id="6170c-227">アプリケーションの app_data フォルダーに格納された Northwind.mdb に接続するための <xref:System.Data.OleDb.OleDbConnection> 文字列の構文を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="6170c-227">The following sample <xref:System.Data.OleDb.OleDbConnection> string demonstrates the syntax required to connect to the Northwind.mdb located in the application's app_data folder.</span></span> <span data-ttu-id="6170c-228">この場所には、システム データベース (System.mdw) も格納されています。</span><span class="sxs-lookup"><span data-stu-id="6170c-228">The system database (System.mdw) is also stored in that location.</span></span>  
  
```csharp  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="6170c-229">Access/Jet データベースをセキュリティで保護しない場合は、接続文字列にシステム データベースの場所を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6170c-229">Specifying the location of the system database in the connection string is not required if the Access/Jet database is unsecured.</span></span> <span data-ttu-id="6170c-230">既定では、セキュリティが無効になります。すべてのユーザーが、空のパスワードで組み込みの Admin ユーザーとして接続することになります。</span><span class="sxs-lookup"><span data-stu-id="6170c-230">Security is off by default, with all users connecting as the built-in Admin user with a blank password.</span></span> <span data-ttu-id="6170c-231">ユーザー レベルのセキュリティを正しく実装したとしても、Jet データベースは攻撃に対して無防備です。</span><span class="sxs-lookup"><span data-stu-id="6170c-231">Even when user-level security is correctly implemented, a Jet database remains vulnerable to attack.</span></span> <span data-ttu-id="6170c-232">ファイル ベースのセキュリティでは克服できない限界があるため、Access/Jet データベースに機密情報を格納することはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="6170c-232">Therefore, storing sensitive information in an Access/Jet database is not recommended because of the inherent weakness of its file-based security scheme.</span></span>  
  
### <a name="connecting-to-excel"></a><span data-ttu-id="6170c-233">Excel への接続</span><span class="sxs-lookup"><span data-stu-id="6170c-233">Connecting to Excel</span></span>  
 <span data-ttu-id="6170c-234">Excel ワークブックへの接続には、Microsoft Jet プロバイダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6170c-234">The Microsoft Jet provider is used to connect to an Excel workbook.</span></span> <span data-ttu-id="6170c-235">次の接続文字列では、`Extended Properties` キーワードは Excel に固有のプロパティを設定しています。</span><span class="sxs-lookup"><span data-stu-id="6170c-235">In the following connection string, the `Extended Properties` keyword sets properties that are specific to Excel.</span></span> <span data-ttu-id="6170c-236">「HDR=Yes;」は最初の列にデータではなく行の名前が含まれていることを示し、「IMEX=1;」は "intermixed" データ行を常にテキストとして読み取ることをドライバーに指示しています。</span><span class="sxs-lookup"><span data-stu-id="6170c-236">"HDR=Yes;" indicates that the first row contains column names, not data, and "IMEX=1;" tells the driver to always read "intermixed" data columns as text.</span></span>  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 <span data-ttu-id="6170c-237">`Extended Properties` を二重引用符で囲む必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-237">Note that the double quotation character required for the `Extended Properties` must also be enclosed in double quotation marks.</span></span>  
  
### <a name="data-shape-provider-connection-string-syntax"></a><span data-ttu-id="6170c-238">Data Shape プロバイダーの接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="6170c-238">Data Shape Provider Connection String Syntax</span></span>  
 <span data-ttu-id="6170c-239">Microsoft Data Shape プロバイダーを使用するときは、`Provider` および `Data Provider` キーワードを両方使用してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-239">Use both the `Provider` and the `Data Provider` keywords when using the Microsoft Data Shape provider.</span></span> <span data-ttu-id="6170c-240">Shape プロバイダーを使用して SQL Server のローカル インスタンスに接続する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6170c-240">The following example uses the Shape provider to connect to a local instance of SQL Server.</span></span>  
  
```csharp  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"
```  
  
## <a name="odbc-connection-strings"></a><span data-ttu-id="6170c-241">Odbc 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6170c-241">Odbc Connection Strings</span></span>  
 <span data-ttu-id="6170c-242"><xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> の <xref:System.Data.Odbc.OdbcConnection> プロパティを使用すると、OLE DB データベースで接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6170c-242">The <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> property of a <xref:System.Data.Odbc.OdbcConnection> allows you to get or set a connection string for an OLE DB data source.</span></span> <span data-ttu-id="6170c-243"><xref:System.Data.Odbc.OdbcConnectionStringBuilder> は、Odbc の接続文字列もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6170c-243">Odbc connection strings are also supported by the <xref:System.Data.Odbc.OdbcConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="6170c-244">次の接続文字列では、Microsoft Text Driver を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6170c-244">The following connection string uses the Microsoft Text Driver.</span></span>  
  
```csharp  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a><span data-ttu-id="6170c-245">DataDirectory を使用した Visual FoxPro との接続</span><span class="sxs-lookup"><span data-stu-id="6170c-245">Using DataDirectory to Connect to Visual FoxPro</span></span>  
 <span data-ttu-id="6170c-246">次の <xref:System.Data.Odbc.OdbcConnection> 接続文字列は、`DataDirectory` を使用して Microsoft Visual FoxPro ファイルに接続する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="6170c-246">The following <xref:System.Data.Odbc.OdbcConnection> connection string sample demonstrates using `DataDirectory` to connect to a Microsoft Visual FoxPro file.</span></span>  
  
```csharp  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a><span data-ttu-id="6170c-247">Oracle 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6170c-247">Oracle Connection Strings</span></span>  
 <span data-ttu-id="6170c-248"><xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> の <xref:System.Data.OracleClient.OracleConnection> プロパティを使用すると、OLE DB データベースで接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6170c-248">The <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> property of a <xref:System.Data.OracleClient.OracleConnection> allows you to get or set a connection string for an OLE DB data source.</span></span> <span data-ttu-id="6170c-249"><xref:System.Data.OracleClient.OracleConnectionStringBuilder> は、Oracle の接続文字列もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6170c-249">Oracle connection strings are also supported by the <xref:System.Data.OracleClient.OracleConnectionStringBuilder> .</span></span>  
  
```csharp
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 <span data-ttu-id="6170c-250">ODBC 接続文字列の構文の詳細については、「<xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6170c-250">For more information on ODBC connection string syntax, see <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6170c-251">関連項目</span><span class="sxs-lookup"><span data-stu-id="6170c-251">See also</span></span>

- [<span data-ttu-id="6170c-252">接続文字列</span><span class="sxs-lookup"><span data-stu-id="6170c-252">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="6170c-253">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="6170c-253">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="6170c-254">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="6170c-254">ADO.NET Overview</span></span>](ado-net-overview.md)
