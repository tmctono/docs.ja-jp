---
title: 自己ホスト型 gRPC アプリケーション-WCF 開発者向け gRPC
description: ASP.NET Core gRPC アプリケーションを自己ホスト型サービスとして展開する。
ms.date: 09/02/2019
ms.openlocfilehash: 2244f161ad4b5d60138ae0f7b4d6a9c8c8829aa8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503404"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="fb63e-103">自己ホスト型 gRPC アプリケーション</span><span class="sxs-lookup"><span data-stu-id="fb63e-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="fb63e-104">ASP.NET Core 3.0 アプリケーションは Windows Server の IIS でホストできますが、HTTP/2 機能の一部がサポートされていないため、現在、IIS で gRPC アプリケーションをホストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fb63e-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="fb63e-105">この機能は、Windows Server の今後の更新プログラムの目的です。</span><span class="sxs-lookup"><span data-stu-id="fb63e-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="fb63e-106">アプリケーションを Windows サービスとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="fb63e-107">または、.NET Core 3.0 ホスト拡張機能の新機能により、 [systemd](https://en.wikipedia.org/wiki/Systemd)によって制御される Linux サービスとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="fb63e-108">Windows サービスとしてのアプリの実行</span><span class="sxs-lookup"><span data-stu-id="fb63e-108">Run your app as a Windows service</span></span>

<span data-ttu-id="fb63e-109">Windows サービスとして実行するように ASP.NET Core アプリケーションを構成する[には、NuGet からパッケージを](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)インストールします。</span><span class="sxs-lookup"><span data-stu-id="fb63e-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="fb63e-110">次に、`Program.cs`の `CreateHostBuilder` メソッドに `UseWindowsService` の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="fb63e-111">アプリケーションが Windows サービスとして実行されていない場合、`UseWindowsService` 方法では何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="fb63e-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="fb63e-112">ここで、次のいずれかの方法を使用してアプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="fb63e-113">Visual Studio で、プロジェクトを右クリックし、ショートカットメニューの **[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="fb63e-114">.NET Core CLI からです。</span><span class="sxs-lookup"><span data-stu-id="fb63e-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="fb63e-115">.NET Core アプリケーションを発行するときに、*フレームワークに依存*する展開と*自己完結*型の展開のどちらを作成するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="fb63e-116">フレームワークに依存する展開では、.NET Core 共有ランタイムが実行されているホストにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="fb63e-117">自己完結型の展開は、.NET Core ランタイムとフレームワークの完全なコピーを使用して発行され、任意のホストで実行できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="fb63e-118">各方法の長所と短所を含む詳細については、 [.Net Core アプリケーションの展開](../../core/deploying/index.md)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63e-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="fb63e-119">.NET Core 3.0 ランタイムをホストにインストールする必要がないアプリケーションの自己完結型のビルドを発行するには、アプリケーションに含めるランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="fb63e-120">`-r` (または `--runtime`) フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="fb63e-121">フレームワークに依存するビルドを発行するには、`-r` フラグを省略します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="fb63e-122">`publish` ディレクトリの完全な内容をインストールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fb63e-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="fb63e-123">次に、 [sc ツール](/windows/desktop/services/controlling-a-service-using-sc)を使用して、実行可能ファイルの Windows サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="fb63e-124">Windows イベントログにログを記録する</span><span class="sxs-lookup"><span data-stu-id="fb63e-124">Log to the Windows event log</span></span>

<span data-ttu-id="fb63e-125">`UseWindowsService` メソッドは、ログメッセージを Windows イベントログに書き込むログ[記録](/aspnet/core/fundamentals/logging/)プロバイダーを自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="fb63e-126">`appsettings.json` または別の構成ソースの `Logging` セクションに `EventLog` エントリを追加することによって、このプロバイダーのログ記録を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span> 

<span data-ttu-id="fb63e-127">イベントログで使用するソース名をオーバーライドするには、これらの設定で `SourceName` プロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="fb63e-128">名前を指定しない場合は、既定のアプリケーション名 (通常は実行可能アセンブリ名) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="fb63e-129">ログ記録の詳細については、この章の最後を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63e-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="fb63e-130">Systemd を使用してアプリを Linux サービスとして実行する</span><span class="sxs-lookup"><span data-stu-id="fb63e-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="fb63e-131">Linux サービス (Linux 用語の*デーモン*) として実行するように ASP.NET Core アプリケーションを構成するには、NuGet から[パッケージをインストールします](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)。</span><span class="sxs-lookup"><span data-stu-id="fb63e-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="fb63e-132">次に、`Program.cs`の `CreateHostBuilder` メソッドに `UseSystemd` の呼び出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="fb63e-133">アプリケーションが Linux サービスとして実行されていない場合、`UseSystemd` 方法では何も実行されません。</span><span class="sxs-lookup"><span data-stu-id="fb63e-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="fb63e-134">次に、アプリケーションを発行します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-134">Now publish your application.</span></span> <span data-ttu-id="fb63e-135">アプリケーションは、フレームワークに依存しているか、関連する Linux ランタイム (`linux-x64`など) に対して自己完結している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="fb63e-136">次のいずれかの方法を使用して発行できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="fb63e-137">Visual Studio で、プロジェクトを右クリックし、ショートカットメニューの **[発行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span> 
* <span data-ttu-id="fb63e-138">.NET Core CLI から、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
<span data-ttu-id="fb63e-139">`publish` ディレクトリの完全な内容を、Linux ホストのインストールフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="fb63e-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="fb63e-140">サービスを登録するには、`/etc/systemd/system` ディレクトリに追加する、*ユニットファイル*と呼ばれる特殊なファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="fb63e-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="fb63e-141">このフォルダーにファイルを作成するには、ルートアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb63e-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="fb63e-142">ファイルに、使用する `systemd` する識別子と、`.service` 拡張機能の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="fb63e-143">たとえば、 `/etc/systemd/system/myapp.service`を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="fb63e-144">次の例に示すように、サービスファイルは INI 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="fb63e-145">`Type=notify` プロパティは、アプリケーションが起動時およびシャットダウン時に通知する `systemd` を示します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="fb63e-146">`WantedBy=multi-user.target` 設定を行うと、Linux システムが "ランダウン 2" に達したときにサービスが開始されます。これは、グラフィカルでないマルチユーザーシェルがアクティブであることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="fb63e-147">`systemd` がサービスを認識する前に、その構成を再読み込みする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="fb63e-148">`systemd` は、`systemctl` コマンドを使用して制御します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="fb63e-149">再読み込みが完了したら、`status` サブコマンドを使用して、アプリケーションが正常に登録されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="fb63e-150">サービスが正しく構成されている場合は、次の出力が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="fb63e-151">サービスを開始するには、`start` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="fb63e-152">`systemctl start`を使用している場合、`.service` の拡張機能は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="fb63e-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="fb63e-153">システムの起動時にサービスを自動的に開始するように `systemd` するには、`enable` コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="fb63e-154">Journald にログを記録する</span><span class="sxs-lookup"><span data-stu-id="fb63e-154">Log to journald</span></span>

<span data-ttu-id="fb63e-155">Linux と同等の Windows イベントログは、`systemd`の一部である構造化されたログ記録システムサービスで `journald`です。</span><span class="sxs-lookup"><span data-stu-id="fb63e-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="fb63e-156">Linux デーモンによって標準出力に書き込まれたログメッセージは、`journald`に自動的に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="fb63e-157">ログ記録レベルを構成するには、ログ構成の `Console` セクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="fb63e-158">`UseSystemd` host builder メソッドは、journal に合わせてコンソールの出力形式を自動的に構成します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="fb63e-159">`journald` は Linux ログの標準であるため、さまざまなツールが統合されています。</span><span class="sxs-lookup"><span data-stu-id="fb63e-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="fb63e-160">ログは、`journald` から外部ログシステムに簡単にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="fb63e-161">ホストでローカルに作業している場合は、`journalctl` コマンドを使用して、コマンドラインからのログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="fb63e-162">ホストで使用できる GUI 環境がある場合は、 *QJournalctl*や*gnome ログ*など、Linux で使用できるグラフィカルなログビューアーがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="fb63e-163">`journalctl`を使用してコマンドラインから `systemd` ジャーナルを照会する方法の詳細については、 [man ページ](https://manpages.debian.org/buster/systemd/journalctl.1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63e-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="fb63e-164">自己ホスト型アプリケーションの HTTPS 証明書</span><span class="sxs-lookup"><span data-stu-id="fb63e-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="fb63e-165">運用環境で gRPC アプリケーションを実行している場合は、信頼された証明機関 (CA) からの TLS 証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="fb63e-166">この CA は、パブリック CA である場合もあれば、組織の内部の ca である場合もあります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="fb63e-167">Windows ホストでは、<xref:System.Security.Cryptography.X509Certificates.X509Store> クラスを使用して、セキュリティで保護された[証明書ストア](/windows/win32/seccrypto/managing-certificates-with-certificate-stores)から証明書を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="fb63e-168">一部の Linux ホストでは、`X509Store` クラスを OpenSSL キーストアと共に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="fb63e-169">また、いずれかの[X509Certificate2 コンストラクター](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)を使用して証明書を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb63e-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="fb63e-170">強力なパスワードで保護された `.pfx` ファイルなどのファイル</span><span class="sxs-lookup"><span data-stu-id="fb63e-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="fb63e-171">[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)などのセキュリティで保護されたストレージサービスから取得したバイナリデータ</span><span class="sxs-lookup"><span data-stu-id="fb63e-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="fb63e-172">証明書を使用するように Kestrel を構成するには、構成とコードの2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="fb63e-173">構成を使用して HTTPS 証明書を設定する</span><span class="sxs-lookup"><span data-stu-id="fb63e-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="fb63e-174">構成方法では、証明書 `.pfx` ファイルのパスと Kestrel 構成セクションのパスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="fb63e-175">`appsettings.json`では、これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fb63e-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="fb63e-176">Azure Key Vault または Hashicorp Vault などのセキュリティで保護された構成ソースを使用して、パスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb63e-177">暗号化されていないパスワードを構成ファイルに保存しないでください。</span><span class="sxs-lookup"><span data-stu-id="fb63e-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="fb63e-178">コードでの HTTPS 証明書の設定</span><span class="sxs-lookup"><span data-stu-id="fb63e-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="fb63e-179">コードで Kestrel の HTTPS を構成するには、`Program` クラスの `IWebHostBuilder` で `ConfigureKestrel` メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb63e-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="fb63e-180">ここでも、`.pfx` ファイルのパスワードをに保存し、セキュリティで保護された構成ソースから取得するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="fb63e-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fb63e-181">[前へ](grpc-in-production.md)
>[次へ](docker.md)</span><span class="sxs-lookup"><span data-stu-id="fb63e-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
