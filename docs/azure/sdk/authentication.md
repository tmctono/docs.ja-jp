---
title: .NET 用 Azure ライブラリを使った認証
description: .NET 用 Azure ライブラリを使って認証を行います
ms.date: 08/22/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: f6af813cd1423be8784b769b272756b2c8258392
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607871"
---
# <a name="authenticate-with-the-azure-libraries-for-net"></a><span data-ttu-id="a2cbc-103">.NET 用 Azure ライブラリを使った認証</span><span class="sxs-lookup"><span data-stu-id="a2cbc-103">Authenticate with the Azure Libraries for .NET</span></span>

## <a name="connect-to-services-with-connection-strings"></a><span data-ttu-id="a2cbc-104">接続文字列を使ってサービスに接続する</span><span class="sxs-lookup"><span data-stu-id="a2cbc-104">Connect to services with connection strings</span></span>

<span data-ttu-id="a2cbc-105">ほとんどの Azure サービス ライブラリでは、認証のために接続文字列またはキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-105">Most Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="a2cbc-106">たとえば、SQL Database は標準の SQL 接続文字列を使います。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-106">For example, SQL Database uses a standard SQL connection string:</span></span>

```csharp
var builder = new SqlConnectionStringBuilder();
builder.DataSource = "example.database.windows.net";
builder.InitialCatalog = "MyDatabase";
builder.UserID = "sampleuser@example"; // Format user ID as "user@server"
builder.Password = password;
builder.Encrypt = true;
builder.TrustServerCertificate = true;

using (var conn = new SqlConnection(builder.ConnectionString))
{
    conn.Open();
    // Do things with the connection...
    // ...
}
```

<span data-ttu-id="a2cbc-107">Azure Storage はストレージ キーを使います。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-107">Azure Storage uses a storage key:</span></span>

```csharp
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storageName
        + ";AccountKey=" + storageKey
        + ";EndpointSuffix=core.windows.net";

var account = CloudStorageAccount.Parse(storageConnectionString);
// Do things with the account here...
```

<span data-ttu-id="a2cbc-108">サービス接続文字列は[、CosmosDB](https://docs.microsoft.com/azure/cosmos-db/) [、Redis 用の Azure キャッシュ](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)、サービス[バス](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues)などの他の Azure サービスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-108">Service connection strings are used in other Azure services like [CosmosDB](https://docs.microsoft.com/azure/cosmos-db/), [Azure Cache for Redis](https://docs.microsoft.com/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="a2cbc-109">これらの文字列は、Azure ポータル、CLI、または PowerShell を使用して取得できます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-109">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="a2cbc-110">また、コード内から .NET 用 Azure 管理ライブラリを使い、リソースを照会することによって接続文字列を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-110">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="a2cbc-111">次のスニペットでは、管理ライブラリを使ってストレージ アカウントの接続文字列を作成しています。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-111">This snippet uses the management libraries to create a storage account connection string:</span></span>

```csharp
// Get a storage account
var storage = azure.StorageAccounts.GetByResourceGroup("myResourceGroup", "myStorageAccount");

// Extract the keys
var storageKeys = storage.GetKeys();

// Build the connection string
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storage.Name
        + ";AccountKey=" + storageKeys[0].Value
        + ";EndpointSuffix=core.windows.net";

// Connect
var account = CloudStorageAccount.Parse(storageConnectionString);

// Do things with the account here...
```

<span data-ttu-id="a2cbc-112">その他のライブラリでは、[サービス プリンシパル](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)を使ってアプリケーションを実行し、許可された資格情報で動作することをアプリケーションに承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-112">Other libraries require your application to run with a [service principal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) authorizing the application to run with granted credentials.</span></span> <span data-ttu-id="a2cbc-113">この構成は、以下に示した管理ライブラリのオブジェクト ベースの認証ステップと似ています。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-113">This configuration is similar to the object-based authentication steps for the management library listed below.</span></span>

## <a name="azure-management-libraries-for-net-authentication"></a><a name="mgmt-auth"></a><span data-ttu-id="a2cbc-114">.NET 認証のための Azure 管理ライブラリ</span><span class="sxs-lookup"><span data-stu-id="a2cbc-114">Azure management libraries for .NET authentication</span></span>

[!include[Create service principal](../includes/create-sp.md)]

<span data-ttu-id="a2cbc-115">サービス プリンシパルを作成した後は、リソースを作成および管理するサービス プリンシパルの認証に 2 つのオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-115">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="a2cbc-116">どちらのオプションでも、次の NuGet パッケージをプロジェクトに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-116">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="a2cbc-117">トークン資格情報で認証を行う</span><span class="sxs-lookup"><span data-stu-id="a2cbc-117">Authenticate with token credentials</span></span>

<span data-ttu-id="a2cbc-118">最初の方法では、コードでトークン資格情報オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-118">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="a2cbc-119">構成ファイル、レジストリ、または Azure Key Vault に、資格情報を安全に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-119">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
    clientSecret,
    tenantId,
    AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="a2cbc-120">サービス プリンシパル作成時の JSON 出力の *clientId*、*clientSecret*、および *tenantId* 値を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-120">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="a2cbc-121">その後、API を使うためのエントリ ポイントとなる `Azure` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-121">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="a2cbc-122">ファイルベースの認証</span><span class="sxs-lookup"><span data-stu-id="a2cbc-122">File-based authentication</span></span>

<span data-ttu-id="a2cbc-123">ファイルベースの認証を使うと、プレーンテキスト ファイルにサービス プリンシパルの資格情報を格納し、ファイル システム内で保護できます。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-123">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](../includes/file-based-auth.md)]

<span data-ttu-id="a2cbc-124">ファイルの内容を読み取り、API を使うためのエントリ ポイントとなる `Azure` オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2cbc-124">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
