---
title: macOS Catalina の公証に対応する
description: macOS で、.NET Core ランタイム、SDK、および .Net Core でビルドされたアプリをインストールするときに、公証と、証明書に関する問題を処理する方法について説明します。
author: thraka
ms.author: adegeo
ms.date: 02/14/2020
ms.openlocfilehash: be39c1ea56699f84736a2b37bc958507b16e826b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146750"
---
# <a name="macos-catalina-notarization-and-the-impact-on-net-core-downloads-and-projects"></a><span data-ttu-id="44dd9-103">macOS Catalina の公証と、.NET Core のダウンロードおよびプロジェクトへの影響</span><span class="sxs-lookup"><span data-stu-id="44dd9-103">macOS Catalina Notarization and the impact on .NET Core downloads and projects</span></span>

<span data-ttu-id="44dd9-104">macOS Catalina (バージョン 10.15) 以降では、2019 年 6 月 1 日より後に作成され、Developer ID と共に配布されたすべてのソフトウェアは公証される必要があります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-104">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019, and distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="44dd9-105">この要件は、.NET Core ランタイム、.NET Core SDK、および .NET Core を使用して作成されたソフトウェアに適用されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-105">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span> <span data-ttu-id="44dd9-106">この記事では、.NET Core と macOS の公証に関して発生する可能性のある一般的なシナリオについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44dd9-106">This article describes the common scenarios you may face with .NET Core and macOS notarization.</span></span>

## <a name="installing-net-core"></a><span data-ttu-id="44dd9-107">.NET Core のインストール</span><span class="sxs-lookup"><span data-stu-id="44dd9-107">Installing .NET Core</span></span>

<span data-ttu-id="44dd9-108">.NET Core (ランタイムと SDK の両方) バージョン 3.1、3.0、2.1 のインストーラーは、2020 年 2 月 18 日から公証されています。</span><span class="sxs-lookup"><span data-stu-id="44dd9-108">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="44dd9-109">それより前にリリースされたバージョンは、公証されていません。</span><span class="sxs-lookup"><span data-stu-id="44dd9-109">Prior released versions aren't notarized.</span></span> <span data-ttu-id="44dd9-110">公証されていないバージョンの .NET Core は、最初にインストーラーをダウンロードしてから、`sudo installer` コマンドを使用することにより、手動でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-110">You can manually install a non-notarized version of .NET Core by first downloading the installer, and then using the `sudo installer` command.</span></span> <span data-ttu-id="44dd9-111">詳しくは、[macOS でのダウンロードと手動インストール](sdk.md?pivots=os-macos#download-and-manually-install)に関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44dd9-111">For more information, see [Download and manually install for macOS](sdk.md?pivots=os-macos#download-and-manually-install).</span></span>

<span data-ttu-id="44dd9-112">次のバージョン以降では、.NET Core インストーラーは公証されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="44dd9-112">Beginning with the following versions, the .NET Core installers are notarized:</span></span>

- <span data-ttu-id="44dd9-113">.NET Core ランタイム</span><span class="sxs-lookup"><span data-stu-id="44dd9-113">.NET Core Runtime</span></span>
  - <span data-ttu-id="44dd9-114">2.1.16</span><span class="sxs-lookup"><span data-stu-id="44dd9-114">2.1.16</span></span>
  - <span data-ttu-id="44dd9-115">3.0.3</span><span class="sxs-lookup"><span data-stu-id="44dd9-115">3.0.3</span></span>
  - <span data-ttu-id="44dd9-116">3.1.2</span><span class="sxs-lookup"><span data-stu-id="44dd9-116">3.1.2</span></span>

- <span data-ttu-id="44dd9-117">.NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="44dd9-117">.NET Core SDK</span></span>
  - <span data-ttu-id="44dd9-118">2.1.512</span><span class="sxs-lookup"><span data-stu-id="44dd9-118">2.1.512</span></span>
  - <span data-ttu-id="44dd9-119">3.0.103</span><span class="sxs-lookup"><span data-stu-id="44dd9-119">3.0.103</span></span>
  - <span data-ttu-id="44dd9-120">3.1.102</span><span class="sxs-lookup"><span data-stu-id="44dd9-120">3.1.102</span></span>

## <a name="apphost-is-disabled-by-default"></a><span data-ttu-id="44dd9-121">appHost は既定で無効になる</span><span class="sxs-lookup"><span data-stu-id="44dd9-121">appHost is disabled by default</span></span>

<span data-ttu-id="44dd9-122">既定では、プロジェクトでコンパイル、発行、または実行を行うと、.NET Core SDK 3.0 以降の公証されていないバージョンで、ネイティブの Mach-O 実行可能ファイル (**appHost** と呼ばれます) が生成されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-122">By default, non-notarized versions of the .NET Core SDK 3.0 and above produce a native Mach-O executable (known as the **appHost**) when your project compiles, publishes, or is run.</span></span> <span data-ttu-id="44dd9-123">この実行可能ファイルは、アプリを実行するための便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="44dd9-123">This executable is a convenient way to run your app.</span></span> <span data-ttu-id="44dd9-124">それ以外の場合は、`dotnet <filename.dll>` を実行することによってアプリを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-124">Otherwise, your app must be started by running `dotnet <filename.dll>`.</span></span> <span data-ttu-id="44dd9-125">appHost が有効になっていると、`dotnet run` コマンドは appHost のコンテキストで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-125">When the appHost is enabled, the `dotnet run` command is invoked in the context of the appHost.</span></span> <span data-ttu-id="44dd9-126">詳しくは、「[appHost のコンテキスト](#context-of-the-apphost)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44dd9-126">For more information, see [Context of the appHost](#context-of-the-apphost).</span></span>

<span data-ttu-id="44dd9-127">公証されたバージョンの .NET Core SDK 3.0 以降では、appHost 実行可能ファイルは既定では生成されません。</span><span class="sxs-lookup"><span data-stu-id="44dd9-127">Starting with the notarized versions of the .NET Core SDK 3.0 and above, the appHost executable isn't generated by default.</span></span> <span data-ttu-id="44dd9-128">プロジェクト ファイルの [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) ブール値の設定を使用して、appHost の生成を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-128">You can turn on appHost generation with the [`UseAppHost`](../project-sdk/msbuild-props.md#useapphost) boolean setting in the project file.</span></span> <span data-ttu-id="44dd9-129">また、コマンド ラインで `-p:UseAppHost` パラメーターを使用することにより、実行する特定の `dotnet` コマンドについて appHost を切り替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-129">You can also toggle the appHost with the `-p:UseAppHost` parameter on the command line for the specific `dotnet` command you run:</span></span>

- <span data-ttu-id="44dd9-130">プロジェクト ファイル</span><span class="sxs-lookup"><span data-stu-id="44dd9-130">Project file</span></span>

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- <span data-ttu-id="44dd9-131">コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="44dd9-131">Command-line parameter</span></span>

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

<span data-ttu-id="44dd9-132">[自己完結型](../deploying/index.md#publish-self-contained)のアプリを発行すると、常に appHost が作成されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-132">An appHost is always created when you publish your app [self-contained](../deploying/index.md#publish-self-contained).</span></span>

<span data-ttu-id="44dd9-133">`UseAppHost` 設定の詳細については、[Microsoft.NET.Sdk の MSBuild プロパティ](../project-sdk/msbuild-props.md#useapphost)に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44dd9-133">For more information about the `UseAppHost` setting, see [MSBuild properties for Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).</span></span>

### <a name="context-of-the-apphost"></a><span data-ttu-id="44dd9-134">appHost のコンテキスト</span><span class="sxs-lookup"><span data-stu-id="44dd9-134">Context of the appHost</span></span>

<span data-ttu-id="44dd9-135">プロジェクトで appHost が有効になっている場合、`dotnet run` コマンドを使用してアプリを実行すると、アプリは、既定のホスト (既定のホストは `dotnet` コマンドです) ではなく、appHost のコンテキストで呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-135">When the appHost is enabled in your project, and you use the `dotnet run` command to run your app, the app is invoked in the context of the appHost and not the default host (the default host is the `dotnet` command).</span></span> <span data-ttu-id="44dd9-136">プロジェクトで appHost が無効になっている場合は、`dotnet run` コマンドを使用すると、既定のホストのコンテキストでアプリが実行されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-136">If the appHost is disabled in your project, the `dotnet run` command runs your app in the context of the default host.</span></span> <span data-ttu-id="44dd9-137">appHost が無効になっている場合でも、自己完結型としてアプリを発行すると、appHost 実行可能ファイルが生成され、ユーザーはその実行可能ファイルを使用してアプリを実行します。</span><span class="sxs-lookup"><span data-stu-id="44dd9-137">Even if the appHost is disabled, publishing your app as self-contained generates an appHost executable, and users use that executable to run your app.</span></span> <span data-ttu-id="44dd9-138">`dotnet <filename.dll>` でアプリを実行すると、共有ランタイムである既定のホストを使用してアプリが呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-138">Running your app with `dotnet <filename.dll>` invokes the app with the default host, the shared runtime.</span></span>

<span data-ttu-id="44dd9-139">appHost を使用するアプリが呼び出されるときは、アプリによってアクセスされる証明書パーティションが、公証された既定のホストとは異なります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-139">When an app using the appHost is invoked, the certificate partition accessed by the app is different from the notarized default host.</span></span> <span data-ttu-id="44dd9-140">既定のホストによってインストールされた証明書にアクセスする必要があるアプリの場合は、`dotnet run` コマンドを使用してプロジェクト ファイルからアプリを実行するか、`dotnet <filename.dll>` コマンドを使用してアプリを直接起動します。</span><span class="sxs-lookup"><span data-stu-id="44dd9-140">If your app must access the certificates installed through the default host, use the `dotnet run` command to run your app from its project file, or use the `dotnet <filename.dll>` command to start the app directly.</span></span>

<span data-ttu-id="44dd9-141">このシナリオについて詳しくは、「[ASP.NET Core と macOS および証明書](#aspnet-core-and-macos-and-certificates)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44dd9-141">More information about this scenario is provided in the [ASP.NET Core and macOS and certificates](#aspnet-core-and-macos-and-certificates) section.</span></span>

## <a name="aspnet-core-and-macos-and-certificates"></a><span data-ttu-id="44dd9-142">ASP.NET Core と macOS および証明書</span><span class="sxs-lookup"><span data-stu-id="44dd9-142">ASP.NET Core and macOS and certificates</span></span>

<span data-ttu-id="44dd9-143">.NET Core には、<xref:System.Security.Cryptography.X509Certificates> クラスを使用して macOS キーチェーンの証明書を管理する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="44dd9-143">.NET Core provides the ability to manage certificates in the macOS Keychain with the <xref:System.Security.Cryptography.X509Certificates> class.</span></span> <span data-ttu-id="44dd9-144">macOS キーチェーンへのアクセスでは、考慮するパーティションを決定するときに、アプリケーション ID が主キーとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-144">Access to the macOS Keychain uses the applications identity as the primary key when deciding which partition to consider.</span></span> <span data-ttu-id="44dd9-145">たとえば、署名されていないアプリケーションでは、署名されていないパーティションにシークレットが格納されますが、署名されたアプリケーションでは、そのアプリケーションだけがアクセスできるパーティションにシークレットが格納されます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-145">For example, unsigned applications store secrets in the unsigned partition, but signed applications store their secrets in partitions only they can access.</span></span> <span data-ttu-id="44dd9-146">アプリを呼び出す実行のソースによって、使用するパーティションが決まります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-146">The source of execution that invokes your app decides which partition to use.</span></span>

<span data-ttu-id="44dd9-147">.NET Core では、実行のソースとして、[appHost](#apphost-is-disabled-by-default)、既定のホスト (`dotnet` コマンド)、カスタム ホストの 3 種類が提供されています。</span><span class="sxs-lookup"><span data-stu-id="44dd9-147">.NET Core provides three sources of execution: [appHost](#apphost-is-disabled-by-default), default host (the `dotnet` command), and a custom host.</span></span> <span data-ttu-id="44dd9-148">各実行モデルでは、異なる ID を使用でき (署名あり、または署名なし)、キーチェーン内の異なるパーティションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-148">Each execution model may have different identities, either signed or unsigned, and has access to different partitions within the Keychain.</span></span> <span data-ttu-id="44dd9-149">あるモードでインポートされた証明書には、別のモードからはアクセスできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-149">Certificates imported by one mode may not be accessible from another.</span></span> <span data-ttu-id="44dd9-150">たとえば、.NET Core の公証されたバージョンには、署名された既定のホストがあります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-150">For example, the notarized versions of .NET Core have a default host that is signed.</span></span> <span data-ttu-id="44dd9-151">証明書は、その ID に基づいて、セキュリティで保護されたパーティションにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-151">Certificates are imported into a secure partition based on its identity.</span></span> <span data-ttu-id="44dd9-152">appHost が署名されていないため、これらの証明書には、生成された appHost からはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="44dd9-152">These certificates aren't accessible from a generated appHost, as the appHost is unsigned.</span></span>

<span data-ttu-id="44dd9-153">別の例として、既定では、ASP.NET Core によって既定のホストから既定の SSL 証明書がインポートされます。</span><span class="sxs-lookup"><span data-stu-id="44dd9-153">Another example, by default, ASP.NET Core imports a default SSL certificate through the default host.</span></span> <span data-ttu-id="44dd9-154">appHost を使用する ASP.NET Core アプリケーションでは、この証明書にアクセスできないため、証明書にアクセスできないことが .NET Core で検出されたときにエラーを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-154">ASP.NET Core applications that use an appHost won't have access to this certificate and will receive an error when .NET Core detects the certificate isn't accessible.</span></span> <span data-ttu-id="44dd9-155">エラー メッセージでは、この問題を解決するための方法が示されています。</span><span class="sxs-lookup"><span data-stu-id="44dd9-155">The error message provides instructions on how to fix this problem.</span></span>

<span data-ttu-id="44dd9-156">証明書の共有が必要な場合、macOS では `security` ユーティリティで構成オプションが提供されています。</span><span class="sxs-lookup"><span data-stu-id="44dd9-156">If certificate sharing is required, macOS provides configuration options with the `security` utility.</span></span>

<span data-ttu-id="44dd9-157">ASP.NET Core 証明書の問題をトラブルシューティングする方法について詳しくは、「[ASP.NET Core に HTTPS を適用する](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44dd9-157">For more information on how to troubleshoot ASP.NET Core certificate issues, see [Enforce HTTPS in ASP.NET Core](/aspnet/core/security/enforcing-ssl?view=aspnetcore-3.1&tabs=visual-studio#troubleshoot-certificate-problems).</span></span>

## <a name="default-entitlements"></a><span data-ttu-id="44dd9-158">既定の権利</span><span class="sxs-lookup"><span data-stu-id="44dd9-158">Default entitlements</span></span>

<span data-ttu-id="44dd9-159">.NET Core の既定のホスト (`dotnet` コマンド) には、一連の既定の権利があります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-159">.NET Core’s default host (the `dotnet` command) has a set of default entitlements.</span></span> <span data-ttu-id="44dd9-160">.NET Core が適切に動作するには、これらの権利が必要です。</span><span class="sxs-lookup"><span data-stu-id="44dd9-160">These entitlements are required for proper operation of .NET Core.</span></span> <span data-ttu-id="44dd9-161">アプリケーションでは追加の権利が必要になることがあり、その場合は、[appHost](#apphost-is-disabled-by-default) を生成して使用し、必要な権利をローカルに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-161">It's possible that your application may need additional entitlements, in which case you'll need to generate and use an [appHost](#apphost-is-disabled-by-default) and then add the necessary entitlements locally.</span></span>

<span data-ttu-id="44dd9-162">.NET Core の既定の権利セット:</span><span class="sxs-lookup"><span data-stu-id="44dd9-162">Default set of entitlements for .NET Core:</span></span>

- `com.apple.security.cs.allow-jit`
- `com.apple.security.cs.allow-unsigned-executable-memory`
- `com.apple.security.cs.allow-dyld-environment-variables`
- `com.apple.security.cs.disable-library-validation`

## <a name="notarize-a-net-core-app"></a><span data-ttu-id="44dd9-163">.NET Core アプリを公証する</span><span class="sxs-lookup"><span data-stu-id="44dd9-163">Notarize a .NET Core app</span></span>

<span data-ttu-id="44dd9-164">macOS Catalina (バージョン 10.15) 以降でアプリケーションを実行する場合は、アプリを公証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44dd9-164">If you want your application to run on macOS Catalina (version 10.15) or higher, you'll want to notarize your app.</span></span> <span data-ttu-id="44dd9-165">公証のためにアプリケーションと共に送信する appHost は、少なくとも .NET Core と同じ[既定の権利](#default-entitlements)で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44dd9-165">The appHost you submit with your application for notarization should be used with at least the same [default entitlements](#default-entitlements) for .NET Core.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44dd9-166">次の手順</span><span class="sxs-lookup"><span data-stu-id="44dd9-166">Next steps</span></span>

- <span data-ttu-id="44dd9-167">[.NET Core の依存関係と要件](dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="44dd9-167">[.NET Core dependencies and requirements](dependencies.md).</span></span>
- <span data-ttu-id="44dd9-168">[.NET Core SDK をインストール](sdk.md)します。</span><span class="sxs-lookup"><span data-stu-id="44dd9-168">[Install the .NET Core SDK](sdk.md).</span></span>
- [<span data-ttu-id="44dd9-169">.NET Core ランタイムをインストールする</span><span class="sxs-lookup"><span data-stu-id="44dd9-169">Install the .NET Core Runtime</span></span>](runtime.md)
