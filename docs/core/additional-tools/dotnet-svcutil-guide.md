---
title: WCF svcutil ツールの概要
description: .NET Framework プロジェクトの WCF svcutil ツールと同様に、.NET Core プロジェクトと ASP.NET Core プロジェクトの機能を追加する Microsoft WCF dotnet-svcutil ツールの概要。
author: mlacouture
ms.date: 02/22/2019
ms.custom: seodec18
ms.openlocfilehash: c6eb17ca6cd4ce920cd358a87d2a4a6759dc3439
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117210"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a><span data-ttu-id="22e7a-103">.NET Core 用 WCF dotnet-svcutil ツール</span><span class="sxs-lookup"><span data-stu-id="22e7a-103">WCF dotnet-svcutil tool for .NET Core</span></span>

<span data-ttu-id="22e7a-104">Windows Communication Foundation (WCF) **dotnet-svcutil** ツールは、ネットワーク上の場所で Web サービスから、あるいは WSDL ファイルからメタデータを取得し、Web サービス操作にアクセスするクライアント プロキシ メソッドを格納する WCF クラスを生成する .NET Core CLI ツールです。</span><span class="sxs-lookup"><span data-stu-id="22e7a-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET Core CLI tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="22e7a-105">.NET Framework プロジェクトの [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) ツールと同様に、**dotnet-svcutil** は、.NET Core プロジェクトおよび .NET Standard プロジェクトと互換性のある Web サービス参照を生成するためのコマンドライン ツールです。</span><span class="sxs-lookup"><span data-stu-id="22e7a-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="22e7a-106">**dotnet-svcutil** ツールは、Visual Studio 2017 v15.5 で最初に用意された Visual Studio 接続済みサービス プロバイダーである、[**WCF Web Service Reference**](wcf-web-service-reference-guide.md) に対する代わりのオプションです。</span><span class="sxs-lookup"><span data-stu-id="22e7a-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 v15.5.</span></span> <span data-ttu-id="22e7a-107">.NET Core CLI ツールとしての **dotnet-svcutil** ツールは、Linux、macOS、および Windows 上で利用可能なクロスプラットフォームです。</span><span class="sxs-lookup"><span data-stu-id="22e7a-107">The **dotnet-svcutil** tool as a .NET Core CLI tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="22e7a-108">信頼できるソースのサービスのみを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e7a-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="22e7a-109">信頼できないソースの参照を追加すると、セキュリティが損なわれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e7a-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22e7a-110">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="22e7a-110">Prerequisites</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="22e7a-111">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-111">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

* <span data-ttu-id="22e7a-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="22e7a-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
* <span data-ttu-id="22e7a-113">任意のコード エディター</span><span class="sxs-lookup"><span data-stu-id="22e7a-113">Your favorite code editor</span></span>

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="22e7a-114">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-114">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

* <span data-ttu-id="22e7a-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="22e7a-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
* <span data-ttu-id="22e7a-116">任意のコード エディター</span><span class="sxs-lookup"><span data-stu-id="22e7a-116">Your favorite code editor</span></span>

---

## <a name="getting-started"></a><span data-ttu-id="22e7a-117">作業の開始</span><span class="sxs-lookup"><span data-stu-id="22e7a-117">Getting started</span></span>

<span data-ttu-id="22e7a-118">次の例では、Web サービス参照を .NET Core Web プロジェクトに追加してサービスを呼び出すために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-118">The following example walks you through the steps required to add a web service reference to a .NET Core web project and invoke the service.</span></span> <span data-ttu-id="22e7a-119">_HelloSvcutil_ という名前の .NET Core Web アプリケーションを作成し、次のコントラクトを実装する Web サービスへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-119">You'll create a .NET Core web application named _HelloSvcutil_ and add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="22e7a-120">この例では、Web サービスが次のアドレスでホストされると仮定します: `http://contoso.com/SayHello.svc`</span><span class="sxs-lookup"><span data-stu-id="22e7a-120">For this example, let's assume the web service will be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="22e7a-121">Windows、macOS、または Linux のコマンド ウィンドウから次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-121">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="22e7a-122">次の例に示すように、_HelloSvcutil_ という名前のディレクトリをプロジェクト用に作成し、現在のディレクトリに指定します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-122">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

    ```console
    mkdir HelloSvcutil
    cd HelloSvcutil
    ```

2. <span data-ttu-id="22e7a-123">次に示すように、[`dotnet new`](../tools/dotnet-new.md) コマンドを使用して、このディレクトリに新しい C# Web プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-123">Create a new C# web project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

    ```dotnetcli
    dotnet new web
    ```

3. <span data-ttu-id="22e7a-124">CLI ツールとして [`dotnet-svcutil`NuGet パッケージ](https://nuget.org/packages/dotnet-svcutil)をインストールします。 </span><span class="sxs-lookup"><span data-stu-id="22e7a-124">Install the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool:  </span></span><!-- markdownlint-disable MD023 -->
    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="22e7a-125">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-125">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet tool install --global dotnet-svcutil
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="22e7a-126">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-126">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)
    <span data-ttu-id="22e7a-127">`HelloSvcutil.csproj` プロジェクト ファイルをエディターで開いて `Project` 要素を編集し、次のコードを使用して [`dotnet-svcutil` NuGet パッケージ](https://nuget.org/packages/dotnet-svcutil)を CLI ツールの参照として追加します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-127">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
    </ItemGroup>
    ```

    <span data-ttu-id="22e7a-128">その後、次に示すように、[`dotnet restore`](../tools/dotnet-restore.md) コマンドを使用して _dotnet-svcutil_ パッケージを復元します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-128">Then restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

    ---

4. <span data-ttu-id="22e7a-129">次に示すように、_dotnet-svcutil_ コマンドを実行して、Web サービス参照ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-129">Run the _dotnet-svcutil_ command to generate the web service reference file as follows:</span></span>

    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="22e7a-130">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-130">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet-svcutil http://contoso.com/SayHello.svc
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="22e7a-131">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-131">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

    ```dotnetcli
    dotnet svcutil http://contoso.com/SayHello.svc
    ```

    ---

<span data-ttu-id="22e7a-132">生成されたファイルは、_HelloSvcutil/ServiceReference/Reference.cs_ として保存されます。</span><span class="sxs-lookup"><span data-stu-id="22e7a-132">The generated file is saved as _HelloSvcutil/ServiceReference/Reference.cs_.</span></span> <span data-ttu-id="22e7a-133">また、_dotnet-svcutil_ ツールでは、プロキシ コードで必要な適切な WCF パッケージが、パッケージ参照としてプロジェクトに追加されます。</span><span class="sxs-lookup"><span data-stu-id="22e7a-133">The _dotnet-svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

## <a name="using-the-service-reference"></a><span data-ttu-id="22e7a-134">サービス参照の使用</span><span class="sxs-lookup"><span data-stu-id="22e7a-134">Using the Service Reference</span></span>

1. <span data-ttu-id="22e7a-135">次に示すように、[`dotnet restore`](../tools/dotnet-restore.md) コマンドを使用して WCF パッケージを復元します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-135">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

2. <span data-ttu-id="22e7a-136">使用するクライアント クラスと操作の名前を検索します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-136">Find the name of the client class and operation you want to use.</span></span> <span data-ttu-id="22e7a-137">`Reference.cs` には `System.ServiceModel.ClientBase` を継承するクラスが含まれており、そのメソッドを使用してサービスで操作を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="22e7a-137">`Reference.cs` will contain a class that inherits from `System.ServiceModel.ClientBase`, with methods that can be used to call operations on the service.</span></span> <span data-ttu-id="22e7a-138">この例では、_SayHello_ サービスの _Hello_ 操作を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-138">In this example, you want to call the _SayHello_ service's _Hello_ operation.</span></span> <span data-ttu-id="22e7a-139">`ServiceReference.SayHelloClient` はクライアント クラスの名前であり、操作の呼び出しに使用できる `HelloAsync` という名前のメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="22e7a-139">`ServiceReference.SayHelloClient` is the name of the client class, and has a method called `HelloAsync` that can be used to call the operation.</span></span>

3. <span data-ttu-id="22e7a-140">エディターで `Startup.cs` ファイルを開き、先頭にサービス参照名前空間に対する using ステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-140">Open the `Startup.cs` file in your editor, and add a using statement for the service reference namespace at the top:</span></span>

    ```csharp
    using ServiceReference;
    ```

4. <span data-ttu-id="22e7a-141">Web サービスを呼び出すように、`Configure` メソッドを編集します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-141">Edit the `Configure` method to invoke the web service.</span></span> <span data-ttu-id="22e7a-142">これを行うには、`ClientBase` を継承するクラスのインスタンスを作成し、クライアント オブジェクトでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-142">You do this by creating an instance of the class that inherits from `ClientBase` and calling the method on the client object:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            var client = new SayHelloClient();
            var response = await client.HelloAsync();
            await context.Response.WriteAsync(response);
        });
    }

    ```

5. <span data-ttu-id="22e7a-143">次に示すように、[`dotnet run`](../tools/dotnet-run.md) コマンドを使用してアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="22e7a-143">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

    ```dotnetcli
    dotnet run
    ```

6. <span data-ttu-id="22e7a-144">Web ブラウザーでコンソールに表示されている URL に移動します (たとえば、`http://localhost:5000`)。</span><span class="sxs-lookup"><span data-stu-id="22e7a-144">Navigate to the URL listed in the console (for example, `http://localhost:5000`) in your web browser.</span></span>

<span data-ttu-id="22e7a-145">次の出力が表示されます。"Hello dotnet-svcutil!"</span><span class="sxs-lookup"><span data-stu-id="22e7a-145">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="22e7a-146">`dotnet-svcutil` ツールのパラメーターの詳細な説明については、次に示すように、help パラメーターを渡してツールを呼び出してください。</span><span class="sxs-lookup"><span data-stu-id="22e7a-146">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>
# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="22e7a-147">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-147">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

```dotnetcli
dotnet-svcutil --help
```

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="22e7a-148">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="22e7a-148">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

```dotnetcli
dotnet svcutil --help
```

---

## <a name="feedback--questions"></a><span data-ttu-id="22e7a-149">フィードバックと質問</span><span class="sxs-lookup"><span data-stu-id="22e7a-149">Feedback & questions</span></span>

<span data-ttu-id="22e7a-150">質問やフィードバックがありましたら、[GitHub で問題を提起してください](https://github.com/dotnet/wcf/issues/new)。</span><span class="sxs-lookup"><span data-stu-id="22e7a-150">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="22e7a-151">[GitHub の WCF リポジトリ](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling)で既存の質問や問題を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e7a-151">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

## <a name="release-notes"></a><span data-ttu-id="22e7a-152">リリース ノート</span><span class="sxs-lookup"><span data-stu-id="22e7a-152">Release notes</span></span>

* <span data-ttu-id="22e7a-153">既知の問題を含む最新のリリース情報については、[リリース ノート](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md)のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e7a-153">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

## <a name="information"></a><span data-ttu-id="22e7a-154">情報</span><span class="sxs-lookup"><span data-stu-id="22e7a-154">Information</span></span>

* [<span data-ttu-id="22e7a-155">dotnet-svcutil NuGet パッケージ</span><span class="sxs-lookup"><span data-stu-id="22e7a-155">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)
