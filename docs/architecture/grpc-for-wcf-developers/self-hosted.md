---
title: 自己ホスト型 gRPC アプリケーション - WCF 開発者向け gRPC
description: コア gRPC アプリケーションASP.NET自己ホスト型サービスとして展開します。
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147803"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="b8bc4-103">自己ホスト型 gRPC アプリケーション</span><span class="sxs-lookup"><span data-stu-id="b8bc4-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="b8bc4-104">ASP.NET Core 3.0 アプリケーションは Windows Server 上の IIS でホストできますが、HTTP/2 の機能の一部がサポートされていないため、現在 IIS で gRPC アプリケーションをホストすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="b8bc4-105">この機能は、Windows サーバーの将来の更新の目標です。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="b8bc4-106">アプリケーションは、Windows サービスとして実行できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="b8bc4-107">または、.NET Core 3.0 ホスティング拡張機能の新機能により[、 systemd](https://en.wikipedia.org/wiki/Systemd)によって制御される Linux サービスとして実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="b8bc4-108">アプリを Windows サービスとして実行する</span><span class="sxs-lookup"><span data-stu-id="b8bc4-108">Run your app as a Windows service</span></span>

<span data-ttu-id="b8bc4-109">Windows サービスとして実行するようにASP.NETコア アプリケーションを構成するには、NuGet から[Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices)パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="b8bc4-110">次に、 の`UseWindowsService`メソッドへの`CreateHostBuilder`呼び`Program.cs`出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="b8bc4-111">アプリケーションが Windows サービスとして実行されていない場合、`UseWindowsService`メソッドは何も実行しません。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="b8bc4-112">次のいずれかの方法を使用してアプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="b8bc4-113">プロジェクトを右クリックし、ショートカット メニューの **[発行**] を選択して、Visual Studio から。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="b8bc4-114">NET コア CLI から。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="b8bc4-115">NET Core アプリケーションを発行する場合は、*フレームワークに依存*する展開または*自己完結型*の展開を作成できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="b8bc4-116">フレームワークに依存する展開では、.NET Core 共有ランタイムを実行するホストにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="b8bc4-117">自己完結型の展開は、.NET Core ランタイムとフレームワークの完全なコピーと共に公開され、任意のホストで実行できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="b8bc4-118">各方法の長所と短所など、詳細については[、.NET Core アプリケーションの展開](../../core/deploying/index.md)に関するドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="b8bc4-119">NET Core 3.0 ランタイムをホストにインストールする必要のない、アプリケーションの自己完結型ビルドを発行するには、アプリケーションに含めるランタイムを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="b8bc4-120">(または`-r``--runtime`) フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="b8bc4-121">フレームワークに依存するビルドを発行するには、フラグ`-r`を省略します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="b8bc4-122">ディレクトリの完全な内容を`publish`インストール フォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="b8bc4-123">次に[、sc ツール](/windows/desktop/services/controlling-a-service-using-sc)を使用して、実行可能ファイル用の Windows サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="b8bc4-124">Windows イベント ログにログを記録する</span><span class="sxs-lookup"><span data-stu-id="b8bc4-124">Log to the Windows event log</span></span>

<span data-ttu-id="b8bc4-125">この`UseWindowsService`メソッドは、ログ メッセージを Windows イベント ログに書き込む[ログ](/aspnet/core/fundamentals/logging/)プロバイダを自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="b8bc4-126">このプロバイダのログ記録は、エントリを`EventLog`セクションまたは別の`Logging``appsettings.json`構成ソースに追加することで構成できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="b8bc4-127">これらの設定でプロパティを設定することで、イベント ログで使用される`SourceName`ソース名を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="b8bc4-128">名前を指定しない場合は、既定のアプリケーション名 (通常は実行可能アセンブリ名) が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="b8bc4-129">ログの詳細については、この章の最後に説明します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="b8bc4-130">システムを使用して Linux サービスとしてアプリを実行する</span><span class="sxs-lookup"><span data-stu-id="b8bc4-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="b8bc4-131">ASP.NETコア アプリケーションを Linux サービス (または Linux パーランスの*デーモン*) として実行するように構成するには、NuGet から[Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd)パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="b8bc4-132">次に、 の`UseSystemd`メソッドへの`CreateHostBuilder`呼び`Program.cs`出しを追加します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="b8bc4-133">アプリケーションが Linux サービスとして実行されていない場合、メソッド`UseSystemd`は何も実行しません。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="b8bc4-134">次に、アプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-134">Now publish your application.</span></span> <span data-ttu-id="b8bc4-135">アプリケーションは、関連する Linux ランタイム (たとえば) に応じてフレームワークに依存`linux-x64`するか、自己完結型にすることができます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="b8bc4-136">次のいずれかの方法を使用して発行できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="b8bc4-137">プロジェクトを右クリックし、ショートカット メニューの **[発行**] を選択して、Visual Studio から。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="b8bc4-138">NET コア CLI から、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="b8bc4-139">ディレクトリの完全な内容を`publish`Linux ホストのインストールフォルダにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="b8bc4-140">サービスを登録するには、`/etc/systemd/system`ユニットファイルと呼ばれる特別な*ファイル*をディレクトリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="b8bc4-141">このフォルダにファイルを作成するには、ルートアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="b8bc4-142">使用する識別子と拡張子を持つファイル`systemd`に名前を付`.service`けます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="b8bc4-143">たとえば、 `/etc/systemd/system/myapp.service`を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="b8bc4-144">サービス ファイルは、次の例に示すように INI 形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="b8bc4-145">この`Type=notify`プロパティは`systemd`、アプリケーションが起動時とシャットダウン時に通知することを示します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="b8bc4-146">この`WantedBy=multi-user.target`設定では、Linux システムが "runlevel 2" に達するとサービスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="b8bc4-147">前`systemd`にサービスを認識し、その構成を再読み込みする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="b8bc4-148">コマンドを`systemd`使用して制御します。 `systemctl`</span><span class="sxs-lookup"><span data-stu-id="b8bc4-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="b8bc4-149">再ロード後、サブコマンド`status`を使用して、アプリケーションが正常に登録されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="b8bc4-150">サービスを正しく構成すると、次の出力が得られます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="b8bc4-151">このコマンド`start`を使用して、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="b8bc4-152">を`.service`使用`systemctl start`している場合、この拡張子はオプションです。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="b8bc4-153">システムの`systemd`起動時にサービスを自動的に開始するように指示するには、`enable`コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="b8bc4-154">ジャーナル処理にログ記録</span><span class="sxs-lookup"><span data-stu-id="b8bc4-154">Log to journald</span></span>

<span data-ttu-id="b8bc4-155">Windows イベント ログに相当する`journald`Linux は、 の一部である構造化ログ`systemd`システム サービスです。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="b8bc4-156">Linux デーモンによって標準出力に書き込まれたログメッセージは自動的`journald`に に に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="b8bc4-157">ログレベルを設定するには、ログ`Console`設定のセクションを使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="b8bc4-158">ホスト`UseSystemd`・ビルダー方式では、ジャーナルに合わせてコンソール出力形式が自動的に構成されます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="b8bc4-159">Linux`journald`ログの標準であるため、さまざまなツールが統合されています。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="b8bc4-160">ログは、外部ログ`journald`システムに簡単にルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="b8bc4-161">ホスト上でローカルに作業する場合は、`journalctl`コマンドラインからログを表示できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="b8bc4-162">ホストで GUI 環境を使用できる場合は、Linux で*QJournalctl*や*gnome-logs*などのいくつかのグラフィカルログビューアを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="b8bc4-163">を使用`journalctl`してコマンド ラインから`systemd`ジャーナルを照会する方法の詳細については、[マニュアル ページを参照してください](https://manpages.debian.org/buster/systemd/journalctl.1)。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="b8bc4-164">自己ホスト型アプリケーションの HTTPS 証明書</span><span class="sxs-lookup"><span data-stu-id="b8bc4-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="b8bc4-165">実稼働環境で gRPC アプリケーションを実行する場合は、信頼された認証局 (CA) の TLS 証明書を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="b8bc4-166">この CA は、パブリック CA または組織の内部 CA である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="b8bc4-167">Windows ホストでは、クラスを使用して、セキュリティで保護された[証明書ストア](/windows/win32/seccrypto/managing-certificates-with-certificate-stores)から<xref:System.Security.Cryptography.X509Certificates.X509Store>証明書を読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="b8bc4-168">一部の Linux`X509Store`ホストでは OpenSSL キー ストアでクラスを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="b8bc4-169">また、次のいずれかの方法で[、X509Certificate2 コンストラクタ](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)のいずれかを使用して証明書を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="b8bc4-170">強力なパスワードで保護された`.pfx`ファイルなどのファイル</span><span class="sxs-lookup"><span data-stu-id="b8bc4-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="b8bc4-171">[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)などのセキュリティで保護されたストレージ サービスから取得されたバイナリ データ</span><span class="sxs-lookup"><span data-stu-id="b8bc4-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="b8bc4-172">証明書を使用するように Kestrel を構成するには、構成とコードの 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="b8bc4-173">構成を使用して HTTPS 証明書を設定する</span><span class="sxs-lookup"><span data-stu-id="b8bc4-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="b8bc4-174">構成方法では、証明書`.pfx`ファイルへのパスと Kestrel 構成セクションのパスワードを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="b8bc4-175">では`appsettings.json`、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="b8bc4-176">Azure Key Vault やハシコープ Vault などのセキュリティで保護された構成ソースを使用してパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8bc4-177">暗号化されていないパスワードを設定ファイルに保存しないでください。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="b8bc4-178">コードで HTTPS 証明書を設定する</span><span class="sxs-lookup"><span data-stu-id="b8bc4-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="b8bc4-179">コード内の Kestrel で HTTPS`ConfigureKestrel`を設定`IWebHostBuilder`するには、`Program`クラスでメソッドを on を使用します。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="b8bc4-180">ここでも、ファイルのパスワードを`.pfx`安全な構成ソースに保存し、そのパスワードを取得してください。</span><span class="sxs-lookup"><span data-stu-id="b8bc4-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b8bc4-181">[前次](grpc-in-production.md)
>[Next](docker.md)</span><span class="sxs-lookup"><span data-stu-id="b8bc4-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
