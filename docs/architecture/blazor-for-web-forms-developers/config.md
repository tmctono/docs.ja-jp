---
title: アプリの構成
description: 構成マネージャーを使用せずに Blazor アプリを構成する方法について説明します。
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588249"
---
# <a name="app-configuration"></a><span data-ttu-id="6e2fa-103">アプリの構成</span><span class="sxs-lookup"><span data-stu-id="6e2fa-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="6e2fa-104">Web フォームでアプリ構成を読み込む主な方法は、サーバー上の*web.config*ファイル&mdash;または*web.config*によって参照される関連する構成ファイルのエントリを使用することです。静的`ConfigurationManager`オブジェクトを使用して、アプリ設定、データ リポジトリ接続文字列、およびアプリに追加されるその他の拡張構成プロバイダーと対話できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="6e2fa-105">次のコードに示すように、アプリの構成との相互作用を確認するのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="6e2fa-106">ASP.NETコアとサーバー側の Blazor を使用すると、アプリが Windows IIS サーバーでホストされている場合 *、web.config*ファイルが存在する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="6e2fa-107">ただし、この構成との`ConfigurationManager`対話は行われず、他のソースからより構造化されたアプリ構成を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="6e2fa-108">構成がどのように収集され *、web.config*ファイルから構成情報にアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="6e2fa-109">構成元</span><span class="sxs-lookup"><span data-stu-id="6e2fa-109">Configuration sources</span></span>

<span data-ttu-id="6e2fa-110">ASP.NET Core では、アプリに使用する構成ソースが多数あると認識しています。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="6e2fa-111">フレームワークは、既定でこれらの機能を最大限に提供しようとします。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="6e2fa-112">構成は、ASP.NET Core によってこれらのさまざまなソースから読み取られ、集計されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="6e2fa-113">後で同じコンフィギュレーション キーに対して読み込まれた値は、以前の値よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="6e2fa-114">ASP.NET Core は、クラウド対応で、オペレーターと開発者の両方にとってアプリの構成を容易にするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="6e2fa-115">ASP.NET Core は環境に対応しており、お客様または`Production``Development`環境で実行されているかどうかを認識します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="6e2fa-116">システム環境変数に環境標識が`ASPNETCORE_ENVIRONMENT`設定されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="6e2fa-117">値が設定されていない場合、アプリはデフォルトで`Production`環境内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="6e2fa-118">アプリは、環境名に基づいて複数のソースから構成をトリガーし、追加できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="6e2fa-119">デフォルトでは、以下のリソースから構成がリストされた順にロードされます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="6e2fa-120">*存在する場合は、ファイルを指定*します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="6e2fa-121">*アプリ設定。{ENVIRONMENT_NAME}.json*ファイルが存在する場合</span><span class="sxs-lookup"><span data-stu-id="6e2fa-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="6e2fa-122">ディスク上のユーザー シークレット ファイル (存在する場合)</span><span class="sxs-lookup"><span data-stu-id="6e2fa-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="6e2fa-123">環境変数</span><span class="sxs-lookup"><span data-stu-id="6e2fa-123">Environment variables</span></span>
1. <span data-ttu-id="6e2fa-124">コマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="6e2fa-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="6e2fa-125">フォーマットとアクセス</span><span class="sxs-lookup"><span data-stu-id="6e2fa-125">appsettings.json format and access</span></span>

<span data-ttu-id="6e2fa-126">*appsettings.json*ファイルは、次の JSON のように構造化された値を使用して階層構造にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

<span data-ttu-id="6e2fa-127">上記の JSON と共に提供された場合、構成システムは子の値を平坦化し、その完全に修飾された階層パスを参照します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="6e2fa-128">コロン (`:`) 文字は、階層内の各プロパティを区切ります。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="6e2fa-129">たとえば、コンフィギュレーション キー`section1:key0`はオブジェクト リテラル`section1`の`key0`値にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="6e2fa-130">ユーザーシークレット</span><span class="sxs-lookup"><span data-stu-id="6e2fa-130">User secrets</span></span>

<span data-ttu-id="6e2fa-131">ユーザーの秘密は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-131">User secrets are:</span></span>

* <span data-ttu-id="6e2fa-132">開発者のワークステーションの JSON ファイルに格納される構成値 (アプリ開発フォルダーの外部)。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="6e2fa-133">環境で実行されている場合にのみ`Development`ロードされます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="6e2fa-134">特定のアプリに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-134">Associated with a specific app.</span></span>
* <span data-ttu-id="6e2fa-135">.NET Core CLI の`user-secrets`コマンドで管理されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="6e2fa-136">次のコマンドを実行して、シークレット ストレージ`user-secrets`用にアプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="6e2fa-137">上記のコマンドは、プロジェクト`UserSecretsId`ファイルに要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="6e2fa-138">要素には、アプリにシークレットを関連付けるために使用される GUID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="6e2fa-139">その後、コマンドを使用してシークレット`set`を定義できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="6e2fa-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="6e2fa-141">上記のコマンドは、値`Parent:ApiKey`を持つ開発者のワークステーションでコンフィギュレーション キーを使用`12345`できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="6e2fa-142">ユーザー シークレットの作成、保存、および管理の詳細については[、「ASP.NET Core ドキュメントの開発におけるアプリ シークレットの安全な保管](/aspnet/core/security/app-secrets)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="6e2fa-143">環境変数</span><span class="sxs-lookup"><span data-stu-id="6e2fa-143">Environment variables</span></span>

<span data-ttu-id="6e2fa-144">アプリ構成に読み込まれる値の次のセットは、システムの環境変数です。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="6e2fa-145">システムのすべての環境変数設定に、構成 API を通じてアクセスできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="6e2fa-146">階層値は、アプリ内で読み取るときに、フラット化され、コロン文字で区切られます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="6e2fa-147">ただし、一部のオペレーティング システムでは、コロン文字環境変数名を使用できません。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="6e2fa-148">ASP.NET Core は、二重アンダースコア ( )`__`を持つ値がアクセスされたときにコロンに変換することで、この制限に対処します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="6e2fa-149">上記`Parent:ApiKey`のユーザー シークレット セクションの値は、環境変数`Parent__ApiKey`で上書きできます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="6e2fa-150">コマンド ライン引数</span><span class="sxs-lookup"><span data-stu-id="6e2fa-150">Command-line arguments</span></span>

<span data-ttu-id="6e2fa-151">アプリの起動時に、構成をコマンド ライン引数として指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="6e2fa-152">設定する構成値の名前`--`と構成する値を示`/`すには、ダブルダッシュ () またはスラッシュ () を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="6e2fa-153">構文は、次のコマンドに似ています。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="6e2fa-154">web.config の戻り値</span><span class="sxs-lookup"><span data-stu-id="6e2fa-154">The return of web.config</span></span>

<span data-ttu-id="6e2fa-155">IIS 上の Windows にアプリを展開した場合でも *、web.config*ファイルは引き続き IIS を構成してアプリを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="6e2fa-156">既定では、IIS は ASP.NET コア モジュール (ANCM) への参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="6e2fa-157">ANCM は、Kestrel Web サーバーの代わりにアプリをホストするネイティブ IIS モジュールです。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="6e2fa-158">この*web.config*セクションは、次の XML マークアップに似ています。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-158">This *web.config* section resembles the following XML markup:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

<span data-ttu-id="6e2fa-159">アプリケーション固有の構成は、`environmentVariables``aspNetCore`要素内の要素を入れ子にすることで定義できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="6e2fa-160">このセクションで定義された値は、ASP.NET Core アプリに環境変数として表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="6e2fa-161">環境変数は、アプリの起動のそのセグメント中に適切に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-161">The environment variables load appropriately during that segment of app startup.</span></span>

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="6e2fa-162">アプリでの構成の読み取り</span><span class="sxs-lookup"><span data-stu-id="6e2fa-162">Read configuration in the app</span></span>

<span data-ttu-id="6e2fa-163">ASP.NET Core は、インターフェイス<xref:Microsoft.Extensions.Configuration.IConfiguration>を通じてアプリの構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="6e2fa-164">この構成インターフェイスは、Blazor コンポーネント、Blazor ページ、および構成にアクセスする必要があるその他のASP.NETコア管理クラスによって要求される必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="6e2fa-165">ASP.NET Core フレームワークは、このインターフェイスに、先ほど構成された解決済みの構成を自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="6e2fa-166">Blazor ページまたはコンポーネントの Razor マークアップで *、.razor*ファイル`IConfiguration`の先頭に`@inject`次のようなディレクティブをオブジェクトに挿入できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="6e2fa-167">このステートメントを使用すると、Razor テンプレート`IConfiguration`の`Configuration`残りの部分でオブジェクトを変数として使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="6e2fa-168">個々の構成設定は、インデクサー パラメーターとして求める構成設定階層を指定することによって読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="6e2fa-169">このメソッドを使用して、前の<xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A>例から section1 の構成を取得`GetSection("section1")`する構文と類似した構文を使用して、特定の場所にあるキーのコレクションを取得することにより、構成セクション全体をフェッチできます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="6e2fa-170">厳密に型指定された構成</span><span class="sxs-lookup"><span data-stu-id="6e2fa-170">Strongly typed configuration</span></span>

<span data-ttu-id="6e2fa-171">Web フォームでは、型と関連付けられた型から継承した厳密に型指定<xref:System.Configuration.ConfigurationSection>された構成型を作成できました。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="6e2fa-172">では`ConfigurationSection`、いくつかのビジネス ルールと、それらの構成値の処理を構成できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="6e2fa-173">ASP.NET Core では、構成値を受け取るクラス階層を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="6e2fa-174">これらのクラス:</span><span class="sxs-lookup"><span data-stu-id="6e2fa-174">These classes:</span></span>

* <span data-ttu-id="6e2fa-175">親クラスから継承する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="6e2fa-176">キャプチャする`public`構成構造のプロパティと型参照に一致するプロパティを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="6e2fa-177">以前の*appsettings.json*サンプルでは、値をキャプチャする次のクラスを定義できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

<span data-ttu-id="6e2fa-178">このクラス階層は、`Startup.ConfigureServices`メソッドに次の行を追加することで設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="6e2fa-179">アプリの残りの部分では、厳密に型指定された構成設定を受け`@inject`取る入力パラメーターをクラス`IOptions<MyConfig>`または Razor テンプレートの型のディレクティブに追加できます。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="6e2fa-180">プロパティ`IOptions<MyConfig>.Value`は、構成設定`MyConfig`から設定された値を生成します。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="6e2fa-181">オプション機能の詳細については、core ドキュメントの[オプション パターンASP.NET](/aspnet/core/fundamentals/configuration/options#options-interfaces)参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e2fa-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6e2fa-182">[前へ](middleware.md)
>[次へ](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="6e2fa-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
