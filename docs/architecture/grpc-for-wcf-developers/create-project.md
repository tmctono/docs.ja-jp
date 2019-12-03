---
title: WCF 開発者向けの新しい ASP.NET Core gRPC プロジェクト-gRPC を作成する
description: Visual Studio またはコマンドラインを使用して gRPC プロジェクトを作成する方法について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: ea6d7658404f61fedb25d7de7ddedb7c51437383
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711446"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="67833-103">新しい ASP.NET Core gRPC プロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="67833-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="67833-104">.NET Core SDK には、`dotnet`の強力な CLI ツールが付属しています。このツールを使用すると、コマンドラインからプロジェクトとソリューションを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="67833-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="67833-105">SDK は Visual Studio と密接に統合されているので、使い慣れたグラフィカルユーザーインターフェイスを使用してすべてを利用できます。</span><span class="sxs-lookup"><span data-stu-id="67833-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="67833-106">この章では、新しい ASP.NET Core gRPC プロジェクトを作成する両方の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="67833-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="67833-107">Visual Studio を使用してプロジェクトを作成する</span><span class="sxs-lookup"><span data-stu-id="67833-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67833-108">ASP.NET Core 3.0 アプリを開発するには、 **ASP.NET と web 開発**ワークロードがインストールされた Visual Studio 2019 16.3 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="67833-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="67833-109">空の*ソリューション*テンプレートから、 **TraderSys**という名前の空のソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="67833-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="67833-110">`src`という名前のソリューションフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="67833-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="67833-111">次に、フォルダーを右クリックし、[**新しいプロジェクト**の**追加** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67833-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="67833-112">[テンプレート検索] ボックスに「`grpc`」と入力すると、`gRPC Service`という名前のプロジェクトテンプレートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="67833-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![[新しいプロジェクトの追加] ダイアログボックスのスクリーンショット](media/create-project/new-grpc-project.png)

<span data-ttu-id="67833-114">**[次]** へ を選択して、 **[新しいプロジェクトの構成]** ダイアログボックスに進みます。</span><span class="sxs-lookup"><span data-stu-id="67833-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="67833-115">プロジェクトに `TraderSys.Portfolios`という名前を指定し、その**場所**に `src` サブディレクトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="67833-115">Name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![[新しいプロジェクトの構成] ダイアログボックスのスクリーンショット](media/create-project/configure-project.png)

<span data-ttu-id="67833-117">**[次]** へ を選択して、 **[新しい Grpc サービスの作成]** ダイアログボックスに進みます。</span><span class="sxs-lookup"><span data-stu-id="67833-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![[新しい gRPC サービスの作成] ダイアログボックスのスクリーンショット](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="67833-119">現時点では、サービス作成のオプションは限られています。</span><span class="sxs-lookup"><span data-stu-id="67833-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="67833-120">Docker は後で導入されるため、このオプションをオフのままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="67833-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="67833-121">[作成] を選択**する**だけです。</span><span class="sxs-lookup"><span data-stu-id="67833-121">Just select **Create**.</span></span> <span data-ttu-id="67833-122">最初の ASP.NET Core 3.0 gRPC プロジェクトが生成され、ソリューションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="67833-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="67833-123">`dotnet CLI`の操作について知りたくない場合は、「[コード例のクリーンアップ](#clean-up-the-example-code)」のセクションに進んでください。</span><span class="sxs-lookup"><span data-stu-id="67833-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="67833-124">.NET Core CLI を使用してプロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="67833-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="67833-125">ここでは、コマンドラインからのソリューションとプロジェクトの作成について説明します。</span><span class="sxs-lookup"><span data-stu-id="67833-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="67833-126">次のコマンドに示すように、ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="67833-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="67833-127">`-o` (または `--output`) フラグは、現在のディレクトリに作成されている出力ディレクトリを指定します (まだ存在しない場合)。</span><span class="sxs-lookup"><span data-stu-id="67833-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="67833-128">このソリューションには、ディレクトリと同じ名前が付けられています: `TraderSys.sln`。</span><span class="sxs-lookup"><span data-stu-id="67833-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="67833-129">別の名前を指定するには、`-n` (または `--name`) フラグを使用します。</span><span class="sxs-lookup"><span data-stu-id="67833-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="67833-130">ASP.NET Core 3.0 には、gRPC サービス用の CLI テンプレートが付属しています。</span><span class="sxs-lookup"><span data-stu-id="67833-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="67833-131">このテンプレートを使用して新しいプロジェクトを作成し、ASP.NET Core プロジェクトの従来のように `src` サブディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="67833-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="67833-132">`-n` フラグを使用して別の名前を指定しない限り、プロジェクトにはディレクトリ (`TraderSys.Portfolios.csproj`) の後に名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="67833-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="67833-133">最後に、`dotnet sln` コマンドを使用して、ソリューションにプロジェクトを追加します。</span><span class="sxs-lookup"><span data-stu-id="67833-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="67833-134">特定のディレクトリに含まれるのは1つの `.csproj` ファイルのみであるため、ディレクトリだけを指定して、入力を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="67833-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="67833-135">このソリューションは、Visual Studio 2019、Visual Studio Code、または任意のエディターで開くことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="67833-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="67833-136">コード例をクリーンアップする</span><span class="sxs-lookup"><span data-stu-id="67833-136">Clean up the example code</span></span>

<span data-ttu-id="67833-137">これで、このブックで既に確認されている gRPC テンプレートを使用して、サンプルサービスを作成できました。</span><span class="sxs-lookup"><span data-stu-id="67833-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="67833-138">これは、株価取引のコンテキストでは役に立たないので、最初のプロジェクトの内容を編集します。</span><span class="sxs-lookup"><span data-stu-id="67833-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="67833-139">プロトコルファイルの名前を変更して編集する</span><span class="sxs-lookup"><span data-stu-id="67833-139">Rename and edit the proto file</span></span>

<span data-ttu-id="67833-140">`Protos/greet.proto` ファイルの名前を `Protos/portfolios.proto`に変更し、エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="67833-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="67833-141">`package` 行の後のすべてを削除します。</span><span class="sxs-lookup"><span data-stu-id="67833-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="67833-142">次に、`option csharp_namespace`、`package` と `service` の名前を変更し、既定の `SayHello` サービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="67833-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="67833-143">コードは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="67833-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="67833-144">テンプレートでは、既定では `Protos` 名前空間の部分は追加されませんが、これを追加すると、gRPC によって生成されたクラスと独自のクラスをコード内で明確に区別しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="67833-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="67833-145">Visual Studio などの統合開発環境 (IDE) で `greet.proto` ファイルの名前を変更すると、このファイルへの参照が `.csproj` ファイルで自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="67833-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="67833-146">ただし、Visual Studio Code などの他のエディターでは、この参照は自動的に更新されないため、プロジェクトファイルを手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67833-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="67833-147">GRPC ビルドターゲットには、`Protobuf` item 要素があります。この要素を使用して、コンパイルする `.proto` ファイルを指定できます。また、どの形式のコード生成が必要か (つまり、"Server" または "Client") があります。</span><span class="sxs-lookup"><span data-stu-id="67833-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="67833-148">`GreeterService` クラスの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="67833-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="67833-149">`GreeterService` クラスは `Services` フォルダーにあり、`Greeter.GreeterBase`から継承されます。</span><span class="sxs-lookup"><span data-stu-id="67833-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="67833-150">名前を `PortfolioService`に変更し、基本クラスを `Portfolios.PortfoliosBase`に変更します。</span><span class="sxs-lookup"><span data-stu-id="67833-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="67833-151">`override` メソッドを削除します。</span><span class="sxs-lookup"><span data-stu-id="67833-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="67833-152">`Startup` クラスの `Configure` メソッドに `GreeterService` クラスへの参照がありました。</span><span class="sxs-lookup"><span data-stu-id="67833-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="67833-153">リファクタリングを使用してクラスの名前を変更した場合は、この参照が自動的に更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67833-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="67833-154">ただし、使用していない場合は、手動で編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67833-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="67833-155">次のセクションでは、この新しいサービスに機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="67833-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="67833-156">[前へ](migrate-wcf-to-grpc.md)
>[次へ](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="67833-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
