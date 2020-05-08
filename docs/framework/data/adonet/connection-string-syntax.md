---
title: 接続文字列の構文
ms.date: 05/22/2018
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
ms.openlocfilehash: 3df97419391fe17ef77a3b8f24c4f0689a04602f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151651"
---
# <a name="connection-string-syntax"></a><span data-ttu-id="10ed1-102">接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="10ed1-102">Connection String Syntax</span></span>
<span data-ttu-id="10ed1-103">すべての .NET Framework データ プロバイダーは、`Connection` を継承する <xref:System.Data.Common.DbConnection> オブジェクトに加え、プロバイダー固有の <xref:System.Data.Common.DbConnection.ConnectionString%2A> プロパティを持ちます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-103">Each .NET Framework data provider has a `Connection` object that inherits from <xref:System.Data.Common.DbConnection> as well as a provider-specific <xref:System.Data.Common.DbConnection.ConnectionString%2A> property.</span></span> <span data-ttu-id="10ed1-104">それぞれのプロバイダーに固有の接続文字列の構文は、対応する `ConnectionString` プロパティのトピックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-104">The specific connection string syntax for each provider is documented in its `ConnectionString` property.</span></span> <span data-ttu-id="10ed1-105">次の表は、.NET Framework に含まれている 4 つのデータ プロバイダーを一覧にしたものです。</span><span class="sxs-lookup"><span data-stu-id="10ed1-105">The following table lists the four data providers that are included in the .NET Framework.</span></span>  
  
|<span data-ttu-id="10ed1-106">.NET Framework データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="10ed1-106">.NET Framework data provider</span></span>|<span data-ttu-id="10ed1-107">説明</span><span class="sxs-lookup"><span data-stu-id="10ed1-107">Description</span></span>|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|<span data-ttu-id="10ed1-108">Microsoft SQL Server へのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-108">Provides data access for Microsoft SQL Server.</span></span> <span data-ttu-id="10ed1-109">接続文字列の構文の詳細については、「<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-109">For more information on connection string syntax, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.OleDb>|<span data-ttu-id="10ed1-110">OLE DB を使って公開されたデータ ソースへのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-110">Provides data access for data sources exposed using OLE DB.</span></span> <span data-ttu-id="10ed1-111">接続文字列の構文の詳細については、「<xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-111">For more information on connection string syntax, see <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.Odbc>|<span data-ttu-id="10ed1-112">ODBC を使って公開されたデータ ソースへのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-112">Provides data access for data sources exposed using ODBC.</span></span> <span data-ttu-id="10ed1-113">接続文字列の構文の詳細については、「<xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-113">For more information on connection string syntax, see <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.</span></span>|  
|<xref:System.Data.OracleClient>|<span data-ttu-id="10ed1-114">Oracle バージョン 8.1.7 以降へのデータ アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-114">Provides data access for Oracle version 8.1.7 or later.</span></span> <span data-ttu-id="10ed1-115">接続文字列の構文の詳細については、「<xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-115">For more information on connection string syntax, see <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.</span></span>|  
  
## <a name="connection-string-builders"></a><span data-ttu-id="10ed1-116">接続文字列ビルダー</span><span class="sxs-lookup"><span data-stu-id="10ed1-116">Connection String Builders</span></span>  
 <span data-ttu-id="10ed1-117">ADO.NET 2.0 では、.NET Framework データ プロバイダー用の次の接続文字列ビルダーが導入されました。</span><span class="sxs-lookup"><span data-stu-id="10ed1-117">ADO.NET 2.0 introduced the following connection string builders for the .NET Framework data providers.</span></span>  
  
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
- <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
- <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
- <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 <span data-ttu-id="10ed1-118">接続文字列ビルダーを使用すると、構文的に正しい接続文字列を実行時に構築できるため、コード内で接続文字列値を手動で連結する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-118">The connection string builders allow you to construct syntactically valid connection strings at run time, so you do not have to manually concatenate connection string values in your code.</span></span> <span data-ttu-id="10ed1-119">詳細については、「[接続文字列ビルダー](connection-string-builders.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-119">For more information, see [Connection String Builders](connection-string-builders.md).</span></span>  

## <a name="windows-authentication"></a><span data-ttu-id="10ed1-120">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="10ed1-120">Windows Authentication</span></span>  
 <span data-ttu-id="10ed1-121">データ ソースでサポートされている場合は、Windows 認証 ("*統合セキュリティ*" とも呼ばれます) を使用して接続することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10ed1-121">We recommend using Windows Authentication (sometimes referred to as *integrated security*) to connect to data sources that support it.</span></span> <span data-ttu-id="10ed1-122">接続文字列の構文は、プロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-122">The syntax employed in the connection string varies by provider.</span></span> <span data-ttu-id="10ed1-123">.NET Framework データ プロバイダーで使用されている Windows 認証の構文を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-123">The following table shows the Windows Authentication syntax used with the .NET Framework data providers.</span></span>  
  
|<span data-ttu-id="10ed1-124">プロバイダー</span><span class="sxs-lookup"><span data-stu-id="10ed1-124">Provider</span></span>|<span data-ttu-id="10ed1-125">構文</span><span class="sxs-lookup"><span data-stu-id="10ed1-125">Syntax</span></span>|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
> <span data-ttu-id="10ed1-126">`Integrated Security=true` プロバイダーで `OleDb` に設定すると例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-126">`Integrated Security=true` throws an exception when used with the `OleDb` provider.</span></span>  
  
## <a name="sqlclient-connection-strings"></a><span data-ttu-id="10ed1-127">SqlClient 接続文字列</span><span class="sxs-lookup"><span data-stu-id="10ed1-127">SqlClient Connection Strings</span></span>  
<span data-ttu-id="10ed1-128"><xref:System.Data.SqlClient.SqlConnection> 接続文字列の構文については、<xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> プロパティで説明されています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-128">The syntax for a <xref:System.Data.SqlClient.SqlConnection> connection string is documented in the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="10ed1-129"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> プロパティを使用すると、SQL Server データベースの接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-129">You can use the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property to get or set a connection string for a SQL Server database.</span></span> <span data-ttu-id="10ed1-130">以前のバージョンの SQL Server に接続する必要がある場合は、.NET Framework Data Provider for OleDb (<xref:System.Data.OleDb>) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-130">If you need to connect to an earlier version of SQL Server, you must use the .NET Framework Data Provider for OleDb (<xref:System.Data.OleDb>).</span></span> <span data-ttu-id="10ed1-131">接続文字列のほとんどのキーワードは、<xref:System.Data.SqlClient.SqlConnectionStringBuilder> のプロパティにマップされています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-131">Most connection string keywords also map to properties in the <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="10ed1-132">`Persist Security Info` キーワードの既定の設定は `false` です。</span><span class="sxs-lookup"><span data-stu-id="10ed1-132">The default setting for the `Persist Security Info` keyword is `false`.</span></span> <span data-ttu-id="10ed1-133">このキーワードを `true` または `yes` に設定すると、ユーザー ID やパスワードなどのセキュリティ関連情報を、接続を開いた後にその接続から取得できます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-133">Setting it to `true` or `yes` allows security-sensitive information, including the user ID and password, to be obtained from the connection after the connection has been opened.</span></span> <span data-ttu-id="10ed1-134">機密を要する接続文字列情報が、信頼できないソースによってアクセスされることのないよう、`Persist Security Info` は必ず `false` にしてください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-134">Keep `Persist Security Info` set to `false` to ensure that an untrusted source does not have access to sensitive connection string information.</span></span>  

### <a name="windows-authentication-with-sqlclient"></a><span data-ttu-id="10ed1-135">SqlClient での Windows 認証</span><span class="sxs-lookup"><span data-stu-id="10ed1-135">Windows authentication with SqlClient</span></span>
 <span data-ttu-id="10ed1-136">次の構文のフォームはそれぞれ、Windows 認証を使用してローカル サーバー上の **AdventureWorks** データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-136">Each of the following forms of syntax uses Windows Authentication to connect to the **AdventureWorks** database on a local server.</span></span>  
  
```csharp  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a><span data-ttu-id="10ed1-137">SqlClient での SQL Server 認証</span><span class="sxs-lookup"><span data-stu-id="10ed1-137">SQL Server authentication with SqlClient</span></span>
 <span data-ttu-id="10ed1-138">SQL Server への接続には Windows 認証の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="10ed1-138">Windows Authentication is preferred for connecting to SQL Server.</span></span> <span data-ttu-id="10ed1-139">ただし、どうしても SQL Server 認証を使用する必要がある場合は、次の構文に従ってユーザー名とパスワードを指定してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-139">However, if SQL Server Authentication is required, use the following syntax to specify a user name and password.</span></span> <span data-ttu-id="10ed1-140">この例では、アスタリスクを使用して有効なユーザー名とパスワードを表しています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-140">In this example, asterisks are used to represent a valid user name and password.</span></span>  
  
```csharp  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

<span data-ttu-id="10ed1-141">Azure SQL Database または Azure SQL Data Warehouse に接続し、`user@servername` の形式でログインを指定する場合は、ログインの `servername` の値が `Server=` に指定されている値と一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-141">When you connect to Azure SQL Database or to Azure SQL Data Warehouse and provide a login in the format `user@servername`, make sure that the `servername` value in the login matches the value provided for `Server=`.</span></span>

> [!NOTE]
> <span data-ttu-id="10ed1-142">Windows 認証は SQL Server ログインよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-142">Windows authentication takes precedence over SQL Server logins.</span></span> <span data-ttu-id="10ed1-143">Integrated Security を true に指定し、ユーザー名とパスワードも指定した場合、ユーザー名とパスワードは無視され、Windows 認証が使用されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-143">If you specify both Integrated Security=true as well as a user name and password, the user name and password will be ignored and Windows authentication will be used.</span></span>  

### <a name="connect-to-a-named-instance-of-sql-server"></a><span data-ttu-id="10ed1-144">SQL Server の名前付きインスタンスに接続する</span><span class="sxs-lookup"><span data-stu-id="10ed1-144">Connect to a named instance of SQL Server</span></span>
<span data-ttu-id="10ed1-145">SQL Server の名前付きインスタンスに接続するには、*server name\instance name* 構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-145">To connect to a named instance of SQL Server, use the *server name\instance name* syntax.</span></span>  
  
```csharp  
"Data Source=MySqlServer\MSSQL1;"  
```  

<span data-ttu-id="10ed1-146">接続文字列の作成時に、<xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> の `SqlConnectionStringBuilder` プロパティをインスタンス名に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-146">You can also set the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> property of the `SqlConnectionStringBuilder` to the instance name when building a connection string.</span></span> <span data-ttu-id="10ed1-147"><xref:System.Data.SqlClient.SqlConnection.DataSource%2A> オブジェクトの <xref:System.Data.SqlClient.SqlConnection> プロパティは読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="10ed1-147">The <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> property of a <xref:System.Data.SqlClient.SqlConnection> object is read-only.</span></span>  
  
### <a name="type-system-version-changes"></a><span data-ttu-id="10ed1-148">Type System Version の変更</span><span class="sxs-lookup"><span data-stu-id="10ed1-148">Type System Version Changes</span></span>  
 <span data-ttu-id="10ed1-149"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> の `Type System Version` キーワードは、クライアント側での SQL Server 型の表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-149">The `Type System Version` keyword in a <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> specifies the client-side representation of SQL Server types.</span></span> <span data-ttu-id="10ed1-150"><xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> キーワードの詳細については、`Type System Version` のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-150">See <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> for more information about the `Type System Version` keyword.</span></span>  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a><span data-ttu-id="10ed1-151">SQL Server Express ユーザー インスタンスへの接続とアタッチ</span><span class="sxs-lookup"><span data-stu-id="10ed1-151">Connecting and Attaching to SQL Server Express User Instances</span></span>  
 <span data-ttu-id="10ed1-152">ユーザー インスタンスは、SQL Server Express の機能の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="10ed1-152">User instances are a feature in SQL Server Express.</span></span> <span data-ttu-id="10ed1-153">最小限の特権しか持たないローカル Windows アカウントで実行しているユーザーが、SQL Server データベースにアタッチできます。この場合、管理特権は不要です。</span><span class="sxs-lookup"><span data-stu-id="10ed1-153">They allow a user running on a least-privileged local Windows account to attach and run a SQL Server database without requiring administrative privileges.</span></span> <span data-ttu-id="10ed1-154">ユーザー インスタンスは、サービスとしてではなく、ユーザーの Windows 資格情報で実行されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-154">A user instance executes with the user's Windows credentials, not as a service.</span></span>  
  
 <span data-ttu-id="10ed1-155">ユーザー インスタンスの使用について詳しくは、「[SQL Server Express ユーザー インスタンス](./sql/sql-server-express-user-instances.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-155">For more information on working with user instances, see [SQL Server Express User Instances](./sql/sql-server-express-user-instances.md).</span></span>  
  
## <a name="using-trustservercertificate"></a><span data-ttu-id="10ed1-156">TrustServerCertificate の使用</span><span class="sxs-lookup"><span data-stu-id="10ed1-156">Using TrustServerCertificate</span></span>  
 <span data-ttu-id="10ed1-157">`TrustServerCertificate` キーワードは、有効な証明書を使用して SQL Server インスタンスに接続する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-157">The `TrustServerCertificate` keyword is valid only when connecting to a SQL Server instance with a valid certificate.</span></span> <span data-ttu-id="10ed1-158">`TrustServerCertificate` を `true` に設定した場合、トランスポート層に SSL が使用されてチャネルが暗号化されます。また、証明書チェーンをたどることによる信頼性の検証は省略されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-158">When `TrustServerCertificate` is set to `true`, the transport layer will use SSL to encrypt the channel and bypass walking the certificate chain to validate trust.</span></span>  
  
```csharp  
"TrustServerCertificate=true;"
```  
  
> [!NOTE]
> <span data-ttu-id="10ed1-159">`TrustServerCertificate` を `true` に設定して暗号化を有効にした場合、接続文字列で `Encrypt` を `false` に設定したとしても、サーバーで指定された暗号化レベルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-159">If `TrustServerCertificate` is set to `true` and encryption is turned on, the encryption level specified on the server will be used even if `Encrypt` is set to `false` in the connection string.</span></span> <span data-ttu-id="10ed1-160">それ以外の場合、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-160">The connection will fail otherwise.</span></span>  
  
### <a name="enabling-encryption"></a><span data-ttu-id="10ed1-161">暗号化の有効化</span><span class="sxs-lookup"><span data-stu-id="10ed1-161">Enabling Encryption</span></span>  
 <span data-ttu-id="10ed1-162">サーバー証明書がプロビジョニングされていない場合、暗号化を有効にするには、SQL Server 構成マネージャーで **[プロトコルの暗号化を設定する]** オプションと **[サーバー証明書を信頼する]** オプションを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-162">To enable encryption when a certificate has not been provisioned on the server, the **Force Protocol Encryption** and the **Trust Server Certificate** options must be set in SQL Server Configuration Manager.</span></span> <span data-ttu-id="10ed1-163">このように、検証可能なサーバー証明書がプロビジョニングされていない場合、暗号化には検証を伴わない自己署名入りのサーバー証明書が使用されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-163">In this case, encryption will use a self-signed server certificate without validation if no verifiable certificate has been provisioned on the server.</span></span>  
  
 <span data-ttu-id="10ed1-164">SQL Server で構成されたセキュリティのレベルを、アプリケーションの設定によって緩和することはできません。ただし、必要に応じて厳密にすることはできます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-164">Application settings cannot reduce the level of security configured in SQL Server, but can optionally strengthen it.</span></span> <span data-ttu-id="10ed1-165">アプリケーションから暗号化を要求するには、`TrustServerCertificate` キーワードおよび `Encrypt` キーワードを `true` に設定します。こうすることで、サーバー証明書がプロビジョニングされておらず、なおかつ、クライアントで **[プロトコルの暗号化を設定する]** が構成されていない場合でも常に暗号化が行われます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-165">An application can request encryption by setting the `TrustServerCertificate` and `Encrypt` keywords to `true`, guaranteeing that encryption takes place even when a server certificate has not been provisioned and **Force Protocol Encryption** has not been configured for the client.</span></span> <span data-ttu-id="10ed1-166">ただし、クライアントの構成で `TrustServerCertificate` を有効にしなかった場合は、プロビジョニングされたサーバー証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="10ed1-166">However, if `TrustServerCertificate` is not enabled in the client configuration, a provisioned server certificate is still required.</span></span>  
  
 <span data-ttu-id="10ed1-167">次の表ですべてのケースを説明します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-167">The following table describes all cases.</span></span>  
  
|<span data-ttu-id="10ed1-168">[プロトコルの暗号化を設定する] クライアント設定</span><span class="sxs-lookup"><span data-stu-id="10ed1-168">Force Protocol Encryption client setting</span></span>|<span data-ttu-id="10ed1-169">[サーバー証明書を信頼する] クライアント設定</span><span class="sxs-lookup"><span data-stu-id="10ed1-169">Trust Server Certificate client setting</span></span>|<span data-ttu-id="10ed1-170">Encrypt/Use Encryption for Data 接続文字列/属性</span><span class="sxs-lookup"><span data-stu-id="10ed1-170">Encrypt/Use Encryption for Data connection string/attribute</span></span>|<span data-ttu-id="10ed1-171">Trust Server Certificate 接続文字列/属性</span><span class="sxs-lookup"><span data-stu-id="10ed1-171">Trust Server Certificate connection string/attribute</span></span>|<span data-ttu-id="10ed1-172">結果</span><span class="sxs-lookup"><span data-stu-id="10ed1-172">Result</span></span>|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|<span data-ttu-id="10ed1-173">いいえ</span><span class="sxs-lookup"><span data-stu-id="10ed1-173">No</span></span>|<span data-ttu-id="10ed1-174">N/A</span><span class="sxs-lookup"><span data-stu-id="10ed1-174">N/A</span></span>|<span data-ttu-id="10ed1-175">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="10ed1-175">No (default)</span></span>|<span data-ttu-id="10ed1-176">無視</span><span class="sxs-lookup"><span data-stu-id="10ed1-176">Ignored</span></span>|<span data-ttu-id="10ed1-177">暗号化は行われません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-177">No encryption occurs.</span></span>|  
|<span data-ttu-id="10ed1-178">いいえ</span><span class="sxs-lookup"><span data-stu-id="10ed1-178">No</span></span>|<span data-ttu-id="10ed1-179">N/A</span><span class="sxs-lookup"><span data-stu-id="10ed1-179">N/A</span></span>|<span data-ttu-id="10ed1-180">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-180">Yes</span></span>|<span data-ttu-id="10ed1-181">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="10ed1-181">No (default)</span></span>|<span data-ttu-id="10ed1-182">暗号化は、検証可能なサーバー証明書が提供されている場合にのみ行われます。それ以外の場合は、接続試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-182">Encryption occurs only if there is a verifiable server certificate, otherwise the connection attempt fails.</span></span>|  
|<span data-ttu-id="10ed1-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="10ed1-183">No</span></span>|<span data-ttu-id="10ed1-184">N/A</span><span class="sxs-lookup"><span data-stu-id="10ed1-184">N/A</span></span>|<span data-ttu-id="10ed1-185">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-185">Yes</span></span>|<span data-ttu-id="10ed1-186">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-186">Yes</span></span>|<span data-ttu-id="10ed1-187">暗号化は常に行われますが、自己署名入りのサーバー証明書を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-187">Encryption always occurs, but may use a self-signed server certificate.</span></span>|  
|<span data-ttu-id="10ed1-188">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-188">Yes</span></span>|<span data-ttu-id="10ed1-189">いいえ</span><span class="sxs-lookup"><span data-stu-id="10ed1-189">No</span></span>|<span data-ttu-id="10ed1-190">無視</span><span class="sxs-lookup"><span data-stu-id="10ed1-190">Ignored</span></span>|<span data-ttu-id="10ed1-191">無視</span><span class="sxs-lookup"><span data-stu-id="10ed1-191">Ignored</span></span>|<span data-ttu-id="10ed1-192">暗号化は、検証可能なサーバー証明書が提供されている場合にのみ行われます。それ以外の場合は、接続試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-192">Encryption occurs only if there is a verifiable server certificate; otherwise, the connection attempt fails.</span></span>|  
|<span data-ttu-id="10ed1-193">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-193">Yes</span></span>|<span data-ttu-id="10ed1-194">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-194">Yes</span></span>|<span data-ttu-id="10ed1-195">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="10ed1-195">No (default)</span></span>|<span data-ttu-id="10ed1-196">無視</span><span class="sxs-lookup"><span data-stu-id="10ed1-196">Ignored</span></span>|<span data-ttu-id="10ed1-197">暗号化は常に行われますが、自己署名入りのサーバー証明書を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-197">Encryption always occurs, but may use a self-signed server certificate.</span></span>|  
|<span data-ttu-id="10ed1-198">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-198">Yes</span></span>|<span data-ttu-id="10ed1-199">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-199">Yes</span></span>|<span data-ttu-id="10ed1-200">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-200">Yes</span></span>|<span data-ttu-id="10ed1-201">無効 (既定値)</span><span class="sxs-lookup"><span data-stu-id="10ed1-201">No (default)</span></span>|<span data-ttu-id="10ed1-202">暗号化は、検証可能なサーバー証明書が提供されている場合にのみ行われます。それ以外の場合は、接続試行が失敗します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-202">Encryption occurs only if there is a verifiable server certificate; otherwise, the connection attempt fails.</span></span>|  
|<span data-ttu-id="10ed1-203">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-203">Yes</span></span>|<span data-ttu-id="10ed1-204">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-204">Yes</span></span>|<span data-ttu-id="10ed1-205">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-205">Yes</span></span>|<span data-ttu-id="10ed1-206">はい</span><span class="sxs-lookup"><span data-stu-id="10ed1-206">Yes</span></span>|<span data-ttu-id="10ed1-207">暗号化は常に行われますが、自己署名入りのサーバー証明書を使用することがあります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-207">Encryption always occurs, but may use a self-signed server certificate.</span></span>|  
  
 <span data-ttu-id="10ed1-208">詳細については、「[検証を伴わない暗号化の使用](/sql/relational-databases/native-client/features/using-encryption-without-validation)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-208">For more information, see [Using Encryption Without Validation](/sql/relational-databases/native-client/features/using-encryption-without-validation).</span></span>
  
## <a name="oledb-connection-strings"></a><span data-ttu-id="10ed1-209">OleDb 接続文字列</span><span class="sxs-lookup"><span data-stu-id="10ed1-209">OleDb Connection Strings</span></span>  
 <span data-ttu-id="10ed1-210"><xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> の <xref:System.Data.OleDb.OleDbConnection> プロパティを使用すると、Microsoft Access などの OLE DB データ ソースの接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-210">The <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> property of a <xref:System.Data.OleDb.OleDbConnection> allows you to get or set a connection string for an OLE DB data source, such as Microsoft Access.</span></span> <span data-ttu-id="10ed1-211">`OleDb` クラスを使用して、実行時に <xref:System.Data.OleDb.OleDbConnectionStringBuilder> 接続文字列を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-211">You can also create an `OleDb` connection string at run time by using the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> class.</span></span>  
  
### <a name="oledb-connection-string-syntax"></a><span data-ttu-id="10ed1-212">OleDb 接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="10ed1-212">OleDb Connection String Syntax</span></span>  
 <span data-ttu-id="10ed1-213"><xref:System.Data.OleDb.OleDbConnection> 接続文字列では、プロバイダー名を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-213">You must specify a provider name for an <xref:System.Data.OleDb.OleDbConnection> connection string.</span></span> <span data-ttu-id="10ed1-214">次の接続文字列は、Jet プロバイダーを使用して Microsoft Access データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-214">The following connection string connects to a Microsoft Access database using the Jet provider.</span></span> <span data-ttu-id="10ed1-215">`User ID` および `Password` キーワードは、データベースがセキュリティ保護されていない場合は省略できます (既定)。</span><span class="sxs-lookup"><span data-stu-id="10ed1-215">Note that the `User ID` and `Password` keywords are optional if the database is unsecured (the default).</span></span>  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;
```  
  
 <span data-ttu-id="10ed1-216">ユーザー レベルのセキュリティを使用して Jet データベースがセキュリティ保護されている場合は、ワークグループ情報ファイル (.mdw) の場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-216">If the Jet database is secured using user-level security, you must provide the location of the workgroup information file (.mdw).</span></span> <span data-ttu-id="10ed1-217">ワークグループ情報ファイルを使用して接続文字列に表示された資格情報を検証します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-217">The workgroup information file is used to validate the credentials presented in the connection string.</span></span>  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="10ed1-218">**OleDbConnection** の接続情報は、UDL (Universal Data Link) ファイルを使用して提供できますが、このファイルは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-218">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="10ed1-219">UDL ファイルは暗号化されないため、接続文字列をテキスト形式で表現してしまいます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-219">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="10ed1-220">UDL ファイルは、アプリケーションにとって外部ファイルをベースにしたリソースであるため、.NET Framework でセキュリティ保護できません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-220">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span> <span data-ttu-id="10ed1-221">UDL ファイルは **SqlClient** ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-221">UDL files are not supported for **SqlClient**.</span></span>  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a><span data-ttu-id="10ed1-222">DataDirectory を使用した Access/Jet との接続</span><span class="sxs-lookup"><span data-stu-id="10ed1-222">Using DataDirectory to Connect to Access/Jet</span></span>  
 <span data-ttu-id="10ed1-223">`DataDirectory` の使用は `SqlClient` に限定されません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-223">`DataDirectory` is not exclusive to `SqlClient`.</span></span> <span data-ttu-id="10ed1-224"><xref:System.Data.OleDb> および <xref:System.Data.Odbc> .NET データ プロバイダーでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-224">It can also be used with the <xref:System.Data.OleDb> and <xref:System.Data.Odbc> .NET data providers.</span></span> <span data-ttu-id="10ed1-225">アプリケーションの app_data フォルダーに格納された Northwind.mdb に接続するための <xref:System.Data.OleDb.OleDbConnection> 文字列の構文を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-225">The following sample <xref:System.Data.OleDb.OleDbConnection> string demonstrates the syntax required to connect to the Northwind.mdb located in the application's app_data folder.</span></span> <span data-ttu-id="10ed1-226">この場所には、システム データベース (System.mdw) も格納されています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-226">The system database (System.mdw) is also stored in that location.</span></span>  
  
```csharp  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="10ed1-227">Access/Jet データベースをセキュリティで保護しない場合は、接続文字列にシステム データベースの場所を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-227">Specifying the location of the system database in the connection string is not required if the Access/Jet database is unsecured.</span></span> <span data-ttu-id="10ed1-228">既定では、セキュリティが無効になります。すべてのユーザーが、空のパスワードで組み込みの Admin ユーザーとして接続することになります。</span><span class="sxs-lookup"><span data-stu-id="10ed1-228">Security is off by default, with all users connecting as the built-in Admin user with a blank password.</span></span> <span data-ttu-id="10ed1-229">ユーザー レベルのセキュリティを正しく実装したとしても、Jet データベースは攻撃に対して無防備です。</span><span class="sxs-lookup"><span data-stu-id="10ed1-229">Even when user-level security is correctly implemented, a Jet database remains vulnerable to attack.</span></span> <span data-ttu-id="10ed1-230">ファイル ベースのセキュリティでは克服できない限界があるため、Access/Jet データベースに機密情報を格納することはお勧めできません。</span><span class="sxs-lookup"><span data-stu-id="10ed1-230">Therefore, storing sensitive information in an Access/Jet database is not recommended because of the inherent weakness of its file-based security scheme.</span></span>  
  
### <a name="connecting-to-excel"></a><span data-ttu-id="10ed1-231">Excel への接続</span><span class="sxs-lookup"><span data-stu-id="10ed1-231">Connecting to Excel</span></span>  
 <span data-ttu-id="10ed1-232">Excel ワークブックへの接続には、Microsoft Jet プロバイダーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-232">The Microsoft Jet provider is used to connect to an Excel workbook.</span></span> <span data-ttu-id="10ed1-233">次の接続文字列では、`Extended Properties` キーワードは Excel に固有のプロパティを設定しています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-233">In the following connection string, the `Extended Properties` keyword sets properties that are specific to Excel.</span></span> <span data-ttu-id="10ed1-234">「HDR=Yes;」は最初の列にデータではなく行の名前が含まれていることを示し、「IMEX=1;」は "intermixed" データ行を常にテキストとして読み取ることをドライバーに指示しています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-234">"HDR=Yes;" indicates that the first row contains column names, not data, and "IMEX=1;" tells the driver to always read "intermixed" data columns as text.</span></span>  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 <span data-ttu-id="10ed1-235">`Extended Properties` を二重引用符で囲む必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-235">Note that the double quotation character required for the `Extended Properties` must also be enclosed in double quotation marks.</span></span>  
  
### <a name="data-shape-provider-connection-string-syntax"></a><span data-ttu-id="10ed1-236">Data Shape プロバイダーの接続文字列の構文</span><span class="sxs-lookup"><span data-stu-id="10ed1-236">Data Shape Provider Connection String Syntax</span></span>  
 <span data-ttu-id="10ed1-237">Microsoft Data Shape プロバイダーを使用するときは、`Provider` および `Data Provider` キーワードを両方使用してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-237">Use both the `Provider` and the `Data Provider` keywords when using the Microsoft Data Shape provider.</span></span> <span data-ttu-id="10ed1-238">Shape プロバイダーを使用して SQL Server のローカル インスタンスに接続する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="10ed1-238">The following example uses the Shape provider to connect to a local instance of SQL Server.</span></span>  
  
```csharp  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"
```  
  
## <a name="odbc-connection-strings"></a><span data-ttu-id="10ed1-239">Odbc 接続文字列</span><span class="sxs-lookup"><span data-stu-id="10ed1-239">Odbc Connection Strings</span></span>  
 <span data-ttu-id="10ed1-240"><xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> の <xref:System.Data.Odbc.OdbcConnection> プロパティを使用すると、OLE DB データベースで接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-240">The <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> property of a <xref:System.Data.Odbc.OdbcConnection> allows you to get or set a connection string for an OLE DB data source.</span></span> <span data-ttu-id="10ed1-241"><xref:System.Data.Odbc.OdbcConnectionStringBuilder> は、Odbc の接続文字列もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-241">Odbc connection strings are also supported by the <xref:System.Data.Odbc.OdbcConnectionStringBuilder>.</span></span>  
  
 <span data-ttu-id="10ed1-242">次の接続文字列では、Microsoft Text Driver を使用しています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-242">The following connection string uses the Microsoft Text Driver.</span></span>  
  
```csharp  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a><span data-ttu-id="10ed1-243">DataDirectory を使用した Visual FoxPro との接続</span><span class="sxs-lookup"><span data-stu-id="10ed1-243">Using DataDirectory to Connect to Visual FoxPro</span></span>  
 <span data-ttu-id="10ed1-244">次の <xref:System.Data.Odbc.OdbcConnection> 接続文字列は、`DataDirectory` を使用して Microsoft Visual FoxPro ファイルに接続する例を示しています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-244">The following <xref:System.Data.Odbc.OdbcConnection> connection string sample demonstrates using `DataDirectory` to connect to a Microsoft Visual FoxPro file.</span></span>  
  
```csharp  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a><span data-ttu-id="10ed1-245">Oracle 接続文字列</span><span class="sxs-lookup"><span data-stu-id="10ed1-245">Oracle Connection Strings</span></span>  
 <span data-ttu-id="10ed1-246"><xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> の <xref:System.Data.OracleClient.OracleConnection> プロパティを使用すると、OLE DB データベースで接続文字列を取得または設定することができます。</span><span class="sxs-lookup"><span data-stu-id="10ed1-246">The <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> property of a <xref:System.Data.OracleClient.OracleConnection> allows you to get or set a connection string for an OLE DB data source.</span></span> <span data-ttu-id="10ed1-247"><xref:System.Data.OracleClient.OracleConnectionStringBuilder> は、Oracle の接続文字列もサポートしています。</span><span class="sxs-lookup"><span data-stu-id="10ed1-247">Oracle connection strings are also supported by the <xref:System.Data.OracleClient.OracleConnectionStringBuilder> .</span></span>  
  
```csharp
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 <span data-ttu-id="10ed1-248">ODBC 接続文字列の構文の詳細については、「<xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10ed1-248">For more information on ODBC connection string syntax, see <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ed1-249">関連項目</span><span class="sxs-lookup"><span data-stu-id="10ed1-249">See also</span></span>

- [<span data-ttu-id="10ed1-250">接続文字列</span><span class="sxs-lookup"><span data-stu-id="10ed1-250">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="10ed1-251">データ ソースへの接続</span><span class="sxs-lookup"><span data-stu-id="10ed1-251">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="10ed1-252">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="10ed1-252">ADO.NET Overview</span></span>](ado-net-overview.md)
