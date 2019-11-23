---
title: WCF 開発者向けの新しい ASP.NET Core gRPC プロジェクト-gRPC を作成する
description: Visual Studio またはコマンドラインを使用して gRPC プロジェクトを作成する方法について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 992c3f57be25ae2517d41437170dc287f58934b6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967894"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="20ded-103">新しい ASP.NET Core gRPC プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="20ded-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="20ded-104">.NET Core には、強力な CLI ツール `dotnet`が付属しています。このツールを使用すると、コマンドラインからプロジェクトとソリューションを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="20ded-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="20ded-105">このツールは Visual Studio と密接に統合されているため、使い慣れた GUI インターフェイスを通じてすべてを使用できます。</span><span class="sxs-lookup"><span data-stu-id="20ded-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="20ded-106">この章では、新しい ASP.NET Core gRPC プロジェクトを作成する両方の方法について説明します。最初に Visual Studio を使用し、次に .NET Core CLI を使用します。</span><span class="sxs-lookup"><span data-stu-id="20ded-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="20ded-107">Visual Studio を使用してプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="20ded-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20ded-108">ASP.NET Core 3.0 アプリを開発するには、 **ASP.NET および web 開発**ワークロードがインストールされた Visual Studio 2019.3 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="20ded-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="20ded-109">空の*ソリューション*テンプレートから、 **TraderSys**という名前の空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="20ded-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="20ded-110">`src`という名前のソリューションフォルダーを追加し、フォルダーを右クリックして、コンテキストメニューから [ > **新しいプロジェクト**の**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="20ded-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="20ded-111">[テンプレート検索] ボックスに「`grpc`」と入力すると、`gRPC Service`という名前のプロジェクトテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="20ded-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![GRPC サービスプロジェクトテンプレートを表示する [新しいプロジェクトの追加] ダイアログ](media/create-project/new-grpc-project.png)

<span data-ttu-id="20ded-113">**[次]** へ をクリックして **[プロジェクトの構成]** ダイアログに進み、プロジェクトに `TraderSys.Portfolios`という名前を設定して、`src` サブディレクトリを**場所**に追加します。</span><span class="sxs-lookup"><span data-stu-id="20ded-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![プロジェクトの構成ダイアログ](media/create-project/configure-project.png)

<span data-ttu-id="20ded-115">**[次]** へ をクリックして、 **[新しい grpc プロジェクト]** ダイアログボックスに進みます。</span><span class="sxs-lookup"><span data-stu-id="20ded-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![新しい gRPC プロジェクトダイアログ](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="20ded-117">現時点では、サービスを作成するためのオプションは限られています。</span><span class="sxs-lookup"><span data-stu-id="20ded-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="20ded-118">Docker は後でブックに導入されるため、このチェックボックスはオンのままにして **[作成]** をクリックするだけです。</span><span class="sxs-lookup"><span data-stu-id="20ded-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="20ded-119">最初の ASP.NET Core 3.0 gRPC プロジェクトが生成され、ソリューションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="20ded-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="20ded-120">`dotnet CLI`の操作について知りたくない場合は、「[コード例のクリーンアップ](#clean-up-the-example-code)」のセクションに進んでください。</span><span class="sxs-lookup"><span data-stu-id="20ded-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="20ded-121">.NET Core CLI を使用してプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="20ded-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="20ded-122">ここでは、コマンドラインからのソリューションとプロジェクトの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="20ded-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="20ded-123">次に示すように、ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="20ded-123">Create the solution as shown below.</span></span> <span data-ttu-id="20ded-124">`-o` (または `--output`) フラグは、出力ディレクトリを指定します。これは、現在のディレクトリに作成されます (存在しない場合)。</span><span class="sxs-lookup"><span data-stu-id="20ded-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="20ded-125">このソリューションには、ディレクトリと同じ名前が付けられます (つまり、`TraderSys.sln`)。`-n` (または `--name`) フラグを使用して別の名前を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="20ded-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="20ded-126">ASP.NET Core 3.0 には、gRPC サービス用の CLI テンプレートが付属しています。</span><span class="sxs-lookup"><span data-stu-id="20ded-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="20ded-127">このテンプレートを使用して新しいプロジェクトを作成し、ASP.NET Core プロジェクトの規則と同様に `src` サブディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="20ded-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="20ded-128">`-n` フラグを使用して別の名前を指定しない限り、プロジェクトはディレクトリ (つまり `TraderSys.Portfolios.csproj`) の後に名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="20ded-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="20ded-129">最後に、`dotnet sln` コマンドを使用して、ソリューションにプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="20ded-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="20ded-130">指定されたディレクトリに含まれるのは1つの `.csproj` ファイルのみであるため、入力を保存するディレクトリだけを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="20ded-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="20ded-131">このソリューションは、Visual Studio 2019、Visual Studio Code、または任意のエディターで開くことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="20ded-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="20ded-132">コード例をクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="20ded-132">Clean up the example code</span></span>

<span data-ttu-id="20ded-133">これで、予約済みの gRPC テンプレートを使用してサンプルサービスが作成されました。このテンプレートは、本で既に確認されています。</span><span class="sxs-lookup"><span data-stu-id="20ded-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="20ded-134">これは、株価取引のコンテキストでは役に立たないので、最初のプロジェクトの内容を編集します。</span><span class="sxs-lookup"><span data-stu-id="20ded-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="20ded-135">プロトコルファイルの名前を変更して編集する</span><span class="sxs-lookup"><span data-stu-id="20ded-135">Rename and edit the proto file</span></span>

<span data-ttu-id="20ded-136">`Protos/greet.proto` ファイルの名前を `Protos/portfolios.proto` に変更し、エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="20ded-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="20ded-137">`package` 行の後のすべてを削除し、`option csharp_namespace`、`package`、および `service` の名前を変更して、既定の `SayHello` サービスを削除します。そのため、コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="20ded-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="20ded-138">テンプレートでは、既定では `Protos` 名前空間の部分は追加されませんが、これを追加すると、gRPC によって生成されたクラスと独自のクラスをコード内で明確に区別しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="20ded-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="20ded-139">Visual Studio などの統合開発環境 (IDE) で `greet.proto` ファイルの名前を変更すると、このファイルへの参照が `.csproj` ファイルで自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="20ded-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="20ded-140">ただし、Visual Studio Code などの他のエディターでは、この参照は自動的に更新されないため、プロジェクトファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ded-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="20ded-141">GRPC ビルドターゲットには、`Protobuf` item 要素があります。この要素を使用して、コンパイルする `.proto` ファイルと、必要なコード生成の形式 ("サーバー" または "クライアント") を指定できます。</span><span class="sxs-lookup"><span data-stu-id="20ded-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="20ded-142">GreeterService クラスの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="20ded-142">Rename the GreeterService class</span></span>

<span data-ttu-id="20ded-143">`GreeterService` クラスは `Services` フォルダーにあり、`Greeter.GreeterBase`から継承されます。</span><span class="sxs-lookup"><span data-stu-id="20ded-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="20ded-144">名前を `PortfolioService` に変更し、基本クラスを `Portfolios.PortfoliosBase`に変更します。</span><span class="sxs-lookup"><span data-stu-id="20ded-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="20ded-145">`override` メソッドを削除します。</span><span class="sxs-lookup"><span data-stu-id="20ded-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="20ded-146">`Startup` クラスの `Configure` メソッドに `GreeterService` クラスへの参照がありました。</span><span class="sxs-lookup"><span data-stu-id="20ded-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="20ded-147">リファクタリングを使用してクラスの名前を変更した場合は、この参照が自動的に更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ded-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="20ded-148">ただし、使用していない場合は、手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="20ded-148">However, if you didn't, you need to edit it manually.</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

<span data-ttu-id="20ded-149">次のセクションでは、この新しいサービスに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="20ded-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="20ded-150">[前へ](migrate-wcf-to-grpc.md)
>[次へ](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="20ded-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
