---
title: 自己ホスト型 gRPC アプリケーション-WCF 開発者向け gRPC
description: ASP.NET Core gRPC アプリケーションを自己ホスト型サービスとして展開する。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 4983cad1dd075480c6d83a5350a323ab348cdaaf
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841367"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="fd53f-103">自己ホスト型 gRPC アプリケーション</span><span class="sxs-lookup"><span data-stu-id="fd53f-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="fd53f-104">ASP.NET Core 3.0 アプリケーションは Windows Server の IIS でホストできますが、HTTP/2 機能の一部がまだサポートされていないため、IIS で gRPC アプリケーションをホストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fd53f-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't yet supported.</span></span> <span data-ttu-id="fd53f-105">この機能は、Windows Server の今後の更新プログラムで想定されています。</span><span class="sxs-lookup"><span data-stu-id="fd53f-105">This functionality is expected in a future update to Windows Server.</span></span>

<span data-ttu-id="fd53f-106">.NET Core 3.0 ホスト拡張機能のいくつかの新機能により、アプリケーションを Windows サービスとして、または[systemd](https://en.wikipedia.org/wiki/Systemd)によって制御される Linux サービスとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-106">You can run your application as a Windows Service, or as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), thanks to some new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="fd53f-107">Windows サービスとしてのアプリの実行</span><span class="sxs-lookup"><span data-stu-id="fd53f-107">Run your app as a Windows service</span></span>

<span data-ttu-id="fd53f-108">Windows サービスとして実行するように ASP.NET Core アプリケーションを構成する[には、NuGet からパッケージを](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)インストールします。</span><span class="sxs-lookup"><span data-stu-id="fd53f-108">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="fd53f-109">次に、`Program.cs`の `CreateHostBuilder` メソッドに `UseWindowsService` の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-109">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="fd53f-110">アプリケーションが Windows サービスとして実行されていない場合、`UseWindowsService` 方法では何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="fd53f-110">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="fd53f-111">次に、Visual Studio でプロジェクトを右クリックし、コンテキストメニューから [発行] を選択するか、.NET Core CLI から [*発行*] を選択して、アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-111">Now publish your application, either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI.</span></span>

<span data-ttu-id="fd53f-112">.NET Core アプリケーションを発行するときに、*フレームワークに依存*する展開と*自己完結*型の展開のどちらを作成するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-112">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="fd53f-113">フレームワークに依存する展開では、.NET Core 共有ランタイムが実行されているホストにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-113">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="fd53f-114">自己完結型の展開は、.NET Core ランタイムとフレームワークの完全なコピーを使用して発行され、任意のホストで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-114">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="fd53f-115">各方法の長所と短所を含む詳細については、 [.Net Core アプリケーションの展開](https://docs.microsoft.com/dotnet/core/deploying/)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd53f-115">For more information, including the advantages and disadvantages of each approach, refer to the [.NET Core application deployment](https://docs.microsoft.com/dotnet/core/deploying/) documentation.</span></span>

<span data-ttu-id="fd53f-116">.NET Core 3.0 ランタイムをホストにインストールする必要がないアプリケーションの自己完結型のビルドを発行するには、`-r` (または `--runtime`) フラグを使用して、アプリケーションに含めるランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-116">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application using the `-r` (or `--runtime`) flag.</span></span>

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="fd53f-117">フレームワークに依存するビルドを発行するには、`-r` フラグを省略します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-117">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```console
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="fd53f-118">`publish` ディレクトリの完全な内容をインストールフォルダーにコピーし、 [sc ユーティリティ](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc)を使用して、実行可能ファイルの Windows サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-118">Copy the complete contents of the `publish` directory to an installation folder, and use the [sc utility](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a><span data-ttu-id="fd53f-119">Windows イベントログに記録する</span><span class="sxs-lookup"><span data-stu-id="fd53f-119">Log to Windows Event Log</span></span>

<span data-ttu-id="fd53f-120">`UseWindowsService` メソッドは、ログメッセージを Windows イベントログに書き込むログ[記録](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0)プロバイダーを自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-120">The `UseWindowsService` method automatically adds a [Logging](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) provider that writes log messages to the Windows Event Log.</span></span> <span data-ttu-id="fd53f-121">`appsettings.json` またはその他の構成ソースの `Logging` セクションに `EventLog` エントリを追加することによって、このプロバイダーのログ記録を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-121">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or other configuration source.</span></span> <span data-ttu-id="fd53f-122">イベントログで使用されるソース名は、これらの設定の `SourceName` プロパティを設定することによってオーバーライドできます。名前を指定しない場合は、既定のアプリケーション名 (通常は実行可能アセンブリ名) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-122">The source name used in Event Log can be overridden by setting a `SourceName` property in these settings; if you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="fd53f-123">ログ記録の詳細については、この章の最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd53f-123">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="fd53f-124">Systemd を使用してアプリを Linux サービスとして実行する</span><span class="sxs-lookup"><span data-stu-id="fd53f-124">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="fd53f-125">Linux サービス (Linux 用語の*デーモン*) として実行するように ASP.NET Core アプリケーションを構成するには、NuGet から[パッケージをインストールします](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)。</span><span class="sxs-lookup"><span data-stu-id="fd53f-125">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="fd53f-126">次に、`Program.cs`の `CreateHostBuilder` メソッドに `UseSystemd` の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-126">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="fd53f-127">アプリケーションが Linux サービスとして実行されていない場合、`UseSystemd` 方法では何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="fd53f-127">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="fd53f-128">次に、Visual Studio からプロジェクトを右クリックし、コンテキストメニューから [*発行*] を選択して、または .NET Core CLI から次のコマンドを使用して、アプリケーション (フレームワークに依存する、または、`linux-x64`など) を発行します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-128">Now publish your application (either framework-dependent, or self-contained for the relevant Linux runtime, e.g. `linux-x64`), either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI using the following command.</span></span>

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

<span data-ttu-id="fd53f-129">`publish` ディレクトリの完全な内容を、Linux ホストのインストールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fd53f-129">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="fd53f-130">サービスを登録するには、"ユニットファイル" と呼ばれる特殊なファイルを `/etc/systemd/system` ディレクトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-130">Registering the service requires a special file, called a "unit file", to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="fd53f-131">このフォルダーにファイルを作成するには、ルートアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="fd53f-131">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="fd53f-132">使用する `systemd` する識別子と `.service` 拡張子をファイルに付けます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-132">Name the file with the identifier you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="fd53f-133">たとえば、`/etc/systemd/system/myapp.service` のようにします。</span><span class="sxs-lookup"><span data-stu-id="fd53f-133">For example, `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="fd53f-134">この例に示すように、サービスファイルは INI 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-134">The service file uses INI format, as shown in this example.</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="fd53f-135">`Type=notify` プロパティは、アプリケーションが起動時およびシャットダウン時に通知する `systemd` を示します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-135">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="fd53f-136">`WantedBy=multi-user.target` 設定を行うと、Linux システムが "ランレベル 2" に達したときにサービスが開始されます。これは、グラフィカルでないマルチユーザーシェルがアクティブであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-136">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2", meaning a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="fd53f-137">`systemd` がサービスを認識する前に、その構成を再読み込みする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-137">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="fd53f-138">`systemctl` コマンドを使用して、`systemd` を制御します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-138">You control `systemd` using the `systemctl` command.</span></span> <span data-ttu-id="fd53f-139">再読み込みが完了したら、`status` サブコマンドを使用して、アプリケーションが正常に登録されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-139">After reloading, use the `status` subcommand to confirm the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="fd53f-140">サービスが正しく構成されている場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-140">If you've configured the service correctly, the following output will be shown:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="fd53f-141">サービスを開始するには、`start` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-141">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="fd53f-142">`systemctl start`を使用する場合、`.service` の拡張機能は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fd53f-142">The `.service` extension is optional when using `systemctl start`.</span></span>

<span data-ttu-id="fd53f-143">システムの起動時にサービスを自動的に開始するように `systemd` するには、`enable` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-143">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="fd53f-144">Journald にログを記録する</span><span class="sxs-lookup"><span data-stu-id="fd53f-144">Log to journald</span></span>

<span data-ttu-id="fd53f-145">Linux と同等の Windows イベントログは `journald`であり、`systemd`に含まれる構造化されたログ記録システムサービスです。</span><span class="sxs-lookup"><span data-stu-id="fd53f-145">The Linux equivalent of the Windows Event Log is `journald`, a structured logging system service that is part of `systemd`.</span></span> <span data-ttu-id="fd53f-146">Linux デーモンによって標準出力に書き込まれたログメッセージは `journald`に自動的に書き込まれます。そのため、ログ記録レベルを構成するには、ログ構成の `Console` セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-146">Log messages written to the standard output by a Linux daemon are automatically written to `journald`, so to configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="fd53f-147">`UseSystemd` host builder メソッドは、journal に合わせてコンソールの出力形式を自動的に構成します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-147">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="fd53f-148">`journald` は Linux ログの標準であるため、統合されたさまざまなツールがあり、`journald` から外部ログシステムにログを簡単にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-148">Because `journald` is the standard for Linux logs, there are a variety of tools that integrate with it, and you can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="fd53f-149">ホストでローカルに作業している場合は、`journalctl` コマンドを使用して、コマンドラインからのログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-149">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="fd53f-150">ホストで使用できる GUI 環境がある場合は、 *QJournalctl*や*gnome ログ*など、Linux で使用できるグラフィカルなログビューアーがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-150">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="fd53f-151">`journalctl`を使用してコマンドラインから systemd journal にクエリを実行する方法の詳細については、 [man ページ](https://manpages.debian.org/buster/systemd/journalctl.1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd53f-151">To learn more about querying the systemd journal from the command line with `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="fd53f-152">自己ホスト型アプリケーションの HTTPS 証明書</span><span class="sxs-lookup"><span data-stu-id="fd53f-152">HTTPS Certificates for self-hosted applications</span></span>

<span data-ttu-id="fd53f-153">運用環境で gRPC アプリケーションを実行する場合は、信頼された証明機関 (CA) からの TLS 証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-153">When running a gRPC application in production, you should use a TLS certificate from a trusted Certificate Authority (CA).</span></span> <span data-ttu-id="fd53f-154">この CA は、パブリック CA、または組織の内部の ca のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-154">This CA could be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="fd53f-155">Windows ホストでは、 [X509Store クラス](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0)を使用して、セキュリティで保護された[証明書ストア](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores)から証明書を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-155">On Windows hosts, the certificate may be loaded from a secure [Certificate Store](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) using the [X509Store class](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0).</span></span> <span data-ttu-id="fd53f-156">`X509Store` クラスは、一部の Linux ホスト上の OpenSSL キーストアでも使用できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-156">The `X509Store` class can also be used with the OpenSSL key-store on some Linux hosts.</span></span>

<span data-ttu-id="fd53f-157">証明書は、 [X509Certificate2 コンストラクター](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0)のいずれかを使用して作成することもできます。これには、ファイル (強力なパスワードで保護されたファイル `.pfx` など) から、またはセキュリティで保護されたストレージサービスから取得したバイナリデータ (たとえば、 [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)) を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-157">Certificates may also be created using one of the [X509Certificate2 constructors](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), either from a file (for example a `.pfx` file protected by a strong password), or from binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="fd53f-158">Kestrel は、構成から、またはコード内の2つの方法で証明書を使用するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="fd53f-158">Kestrel can be configured to use a certificate in two ways: from configuration, or in code.</span></span>

### <a name="set-https-certificates-using-configuration"></a><span data-ttu-id="fd53f-159">構成を使用して HTTPS 証明書を設定する</span><span class="sxs-lookup"><span data-stu-id="fd53f-159">Set HTTPS certificates using configuration</span></span>

<span data-ttu-id="fd53f-160">構成方法では、証明書 `.pfx` ファイルのパスと Kestrel 構成セクションのパスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-160">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="fd53f-161">`appsettings.json` では、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-161">In `appsettings.json` that would look like this.</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="fd53f-162">パスワードは、Azure KeyVault や Hashicorp Vault などのセキュリティで保護された構成ソースを使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-162">The password should be provided using a secure configuration source such as Azure KeyVault or Hashicorp Vault.</span></span>

<span data-ttu-id="fd53f-163">暗号化されていないパスワードを構成ファイルに格納しないでください。</span><span class="sxs-lookup"><span data-stu-id="fd53f-163">You SHOULD NOT store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="fd53f-164">コードでの HTTPS 証明書の設定</span><span class="sxs-lookup"><span data-stu-id="fd53f-164">Set HTTPS certificates in code</span></span>

<span data-ttu-id="fd53f-165">コードで Kestrel の HTTPS を構成するには、`Program` クラスの `IWebHostBuilder` で `ConfigureKestrel` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd53f-165">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="fd53f-166">ここでも、`.pfx` ファイルのパスワードを格納し、セキュリティで保護された構成ソースから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd53f-166">Again, the password for the `.pfx` file should be stored in and retrieved from a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fd53f-167">[前へ](grpc-in-production.md)
>[次へ](docker.md)</span><span class="sxs-lookup"><span data-stu-id="fd53f-167">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
