---
title: 開発時にアプリケーションの機密情報を安全に格納する
description: .NET マイクロサービスと Web アプリケーションのセキュリティ - パスワード、接続文字列、API キーなどのアプリケーションのシークレットはソース管理に保存しないでください。ASP.NET Core で使用できるオプションを理解してください。特に、"ユーザーのシークレット" の処理方法を理解する必要があります。
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 1ef2246746b9165f1564fa7be64ff7eb28eb1d32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501793"
---
# <a name="store-application-secrets-safely-during-development"></a><span data-ttu-id="2c195-103">開発時にアプリケーションのシークレットを安全に格納する</span><span class="sxs-lookup"><span data-stu-id="2c195-103">Store application secrets safely during development</span></span>

<span data-ttu-id="2c195-104">保護されたリソースおよびその他のサービスに接続する場合、ASP.NET Core アプリケーションは、通常、接続文字列やパスワードなど、機密情報を含む資格情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c195-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="2c195-105">このような機密情報は、"*シークレット*" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2c195-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="2c195-106">ソース コードにシークレットを含めないこと、さらに決してソース管理にシークレットを格納しないことがベスト プラクティスです。</span><span class="sxs-lookup"><span data-stu-id="2c195-106">It's a best practice to not include secrets in source code and making sure not to store secrets in source control.</span></span> <span data-ttu-id="2c195-107">ASP.NET Core 構成モデルを使用して、安全な場所からシークレットを読み取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c195-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="2c195-108">開発リソースおよびステージング リソースにアクセスするためのシークレットは、運用環境のリソースにアクセスするために使用するシークレットとは区別する必要があります。さまざまな人が、そのようなさまざまなシークレット セットへのアクセスを必要とするからです。</span><span class="sxs-lookup"><span data-stu-id="2c195-108">You must separate the secrets for accessing development and staging resources from the ones used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="2c195-109">開発時に使用するシークレットを格納するには、環境変数にシークレットを格納するか、または ASP.NET Core Secret Manager ツールを使用してシークレットを格納する方法が一般的です。</span><span class="sxs-lookup"><span data-stu-id="2c195-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="2c195-110">運用環境でのストレージの安全性を高めるには、マイクロサービスで Azure Key Vault にシークレットを格納することができます。</span><span class="sxs-lookup"><span data-stu-id="2c195-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="store-secrets-in-environment-variables"></a><span data-ttu-id="2c195-111">環境変数にシークレットを格納する</span><span class="sxs-lookup"><span data-stu-id="2c195-111">Store secrets in environment variables</span></span>

<span data-ttu-id="2c195-112">ソース コードの外部にシークレットを保持する方法の 1 つは、開発者用が開発用コンピューター上で文字列ベースのシークレットを[環境変数](/aspnet/core/security/app-secrets#environment-variables)として設定するというものです。</span><span class="sxs-lookup"><span data-stu-id="2c195-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="2c195-113">環境変数を使用して、階層型の名前 (構成セクションで入れ子にされている名前など) を付けてシークレットを格納する場合は、そのセクションの完全な階層をコロン (:) 区切りで含めるように変数名を付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c195-113">When you use environment variables to store secrets with hierarchical names, such as the ones nested in configuration sections, you must name the variables to include the complete hierarchy of its sections, delimited with colons (:).</span></span>

<span data-ttu-id="2c195-114">たとえば、環境変数 `Logging:LogLevel:Default` を `Debug` 値に設定する場合、それは次の JSON ファイルから構成値を取得することと等価になります。</span><span class="sxs-lookup"><span data-stu-id="2c195-114">For example, setting an environment variable `Logging:LogLevel:Default` to `Debug` value would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="2c195-115">環境変数からこれらの値にアクセスするためには、アプリケーションは IConfigurationRoot オブジェクトを構築する際に ConfigurationBuilder 上で AddEnvironmentVariables を呼び出す必要があるだけです。</span><span class="sxs-lookup"><span data-stu-id="2c195-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="2c195-116">環境変数は一般にプレーン テキストとして格納されるため、環境変数が設定されたコンピューターまたはプロセスのセキュリティが侵害されると、環境変数の値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2c195-116">Note that environment variables are commonly stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a><span data-ttu-id="2c195-117">ASP.NET Core Secret Manager を使用してシークレットを格納する</span><span class="sxs-lookup"><span data-stu-id="2c195-117">Store secrets with the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="2c195-118">[開発時に](/aspnet/core/security/app-secrets#secret-manager)ソース コードの外部にシークレットを保持する別の方法として、ASP.NET Core の **Secret Manager** ツールを使用するやり方があります。</span><span class="sxs-lookup"><span data-stu-id="2c195-118">The ASP.NET Core [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code **during development**.</span></span> <span data-ttu-id="2c195-119">Secret Manager ツールを使用するには、プロジェクト ファイルにパッケージ **Microsoft.Extensions.Configuration.SecretManager** を組み込みます。</span><span class="sxs-lookup"><span data-stu-id="2c195-119">To use the Secret Manager tool, install the package **Microsoft.Extensions.Configuration.SecretManager** in your project file.</span></span> <span data-ttu-id="2c195-120">その依存関係が存在し、それが復元されたら、`dotnet user-secrets` コマンドを使用して、コマンド ラインからシークレットの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="2c195-120">Once that dependency is present and has been restored, the `dotnet user-secrets` command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="2c195-121">これらのシークレットは、ユーザーのプロファイル ディレクトリにある JSON ファイルに格納され (OS によって詳細は異なる)、ソース コードから離れた場所に置かれます。</span><span class="sxs-lookup"><span data-stu-id="2c195-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="2c195-122">Secret Manager ツールによって設定されたシークレットは、シークレットを使用するプロジェクトの `UserSecretsId` プロパティによって編成されます。</span><span class="sxs-lookup"><span data-stu-id="2c195-122">Secrets set by the Secret Manager tool are organized by the `UserSecretsId` property of the project that's using the secrets.</span></span> <span data-ttu-id="2c195-123">そのため、次のスニペットに示すように、プロジェクト ファイルに UserSecretsId プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c195-123">Therefore, you must be sure to set the UserSecretsId property in your project file, as shown in the snippet below.</span></span> <span data-ttu-id="2c195-124">既定値は Visual Studio によって割り当てられた GUID ですが、お使いのコンピューター内で一意である限り、実際の文字列は重要ではありません。</span><span class="sxs-lookup"><span data-stu-id="2c195-124">The default value is a GUID assigned by Visual Studio, but the actual string is not important as long as it's unique in your computer.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="2c195-125">Secret Manager で格納されたシークレットをアプリケーションで使用するには、ConfigurationBuilder インスタンス上で `AddUserSecrets<T>` を呼び出して、アプリケーション用のシークレットをその構成に含めます。</span><span class="sxs-lookup"><span data-stu-id="2c195-125">Using secrets stored with Secret Manager in an application is accomplished by calling `AddUserSecrets<T>` on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="2c195-126">ジェネリック パラメーター T は、UserSecretId が適用されたアセンブリからの型である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c195-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="2c195-127">通常は、`AddUserSecrets<Startup>` を使用しても問題ありません。</span><span class="sxs-lookup"><span data-stu-id="2c195-127">Usually using `AddUserSecrets<Startup>` is fine.</span></span>

<span data-ttu-id="2c195-128">`AddUserSecrets<Startup>()`Program.cs`CreateDefaultBuilder` の  *メソッドを使用する場合、* は開発環境の既定のオプションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="2c195-128">The `AddUserSecrets<Startup>()` is included in the default options for the Development environment when using the `CreateDefaultBuilder` method in *Program.cs*.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2c195-129">[前へ](authorization-net-microservices-web-applications.md)
>[次へ](azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="2c195-129">[Previous](authorization-net-microservices-web-applications.md)
[Next](azure-key-vault-protects-secrets.md)</span></span>
