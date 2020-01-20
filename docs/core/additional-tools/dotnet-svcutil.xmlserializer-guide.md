---
title: dotnet-svcutil.xmlserializer の使用
description: .NET Core プロジェクト用にシリアル化アセンブリを事前に生成する `dotnet-svcutil.xmlserializer` NuGet パッケージの使用方法について説明します。
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344900"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="a9620-103">.NET Core で dotnet-svcutil.xmlserializer を使用する</span><span class="sxs-lookup"><span data-stu-id="a9620-103">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

<span data-ttu-id="a9620-104">`dotnet-svcutil.xmlserializer` NuGet パッケージは、.NET Core プロジェクト用にシリアル化アセンブリを事前に生成することができます。</span><span class="sxs-lookup"><span data-stu-id="a9620-104">The `dotnet-svcutil.xmlserializer` NuGet package can pre-generate a serialization assembly for .NET Core projects.</span></span> <span data-ttu-id="a9620-105">これは、クライアント アプリケーション内の型で、WCF サービス コントラクトによって使われ XmlSerializer によってシリアル化できるものに対して、C# のシリアル化コードを事前に生成します。</span><span class="sxs-lookup"><span data-stu-id="a9620-105">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the XmlSerializer.</span></span> <span data-ttu-id="a9620-106">これにより、それらの型のオブジェクトをシリアル化または逆シリアル化するときに XML シリアル化の起動時のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="a9620-106">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9620-107">必須コンポーネント</span><span class="sxs-lookup"><span data-stu-id="a9620-107">Prerequisites</span></span>

* <span data-ttu-id="a9620-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) 以降</span><span class="sxs-lookup"><span data-stu-id="a9620-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later</span></span>
* <span data-ttu-id="a9620-109">任意のコード エディター</span><span class="sxs-lookup"><span data-stu-id="a9620-109">Your favorite code editor</span></span>

<span data-ttu-id="a9620-110">コマンド `dotnet --info` を使用して、既にインストールされている .NET Core SDK およびランタイムのバージョンを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="a9620-110">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

## <a name="getting-started"></a><span data-ttu-id="a9620-111">作業の開始</span><span class="sxs-lookup"><span data-stu-id="a9620-111">Getting started</span></span>

<span data-ttu-id="a9620-112">.NET Core コンソール アプリケーションで `dotnet-svcutil.xmlserializer` を使用するには:</span><span class="sxs-lookup"><span data-stu-id="a9620-112">To use `dotnet-svcutil.xmlserializer` in a .NET Core console application:</span></span>

1. <span data-ttu-id="a9620-113">.NET Framework で既定のテンプレート 'WCF Service Application' を使用して、'MyWCFService' という名前の WCF サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9620-113">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span> <span data-ttu-id="a9620-114">次のようなサービス メソッドに `[XmlSerializerFormat]` 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9620-114">Add `[XmlSerializerFormat]` attribute on the service method like the following:</span></span>

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. <span data-ttu-id="a9620-115">.NET Core 2.1 以降のバージョンを対象とする WCF クライアント アプリケーションとして .NET Core コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9620-115">Create a .NET Core console application as WCF client application that targets at .NET Core 2.1 or later versions.</span></span> <span data-ttu-id="a9620-116">たとえば、次のコマンドを使用して、'MyWCFClient' という名前のアプリを作成します。</span><span class="sxs-lookup"><span data-stu-id="a9620-116">For example, create an app named 'MyWCFClient' with the following command:</span></span>

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    <span data-ttu-id="a9620-117">プロジェクトが .NET Core 2.1 以降を対象としていることを確認するには、プロジェクト ファイル内の `TargetFramework` XML 要素を調べます。</span><span class="sxs-lookup"><span data-stu-id="a9620-117">To ensure your project is targeting .NET Core 2.1 or later, inspect the `TargetFramework` XML element in your project file:</span></span>

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. <span data-ttu-id="a9620-118">次のコマンドを実行して、`System.ServiceModel.Http` へのパッケージ参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9620-118">Add a package reference to `System.ServiceModel.Http` by running the following command:</span></span>

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. <span data-ttu-id="a9620-119">WCF クライアント コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a9620-119">Add the WCF Client code:</span></span>

    ```csharp
    using System.ServiceModel;

        class Program
        {
            static void Main(string[] args)
            {
                var myBinding = new BasicHttpBinding();
                var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
                var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
                IService1 client = myChannelFactory.CreateChannel();
                string s = client.GetData(1);
                ((ICommunicationObject)client).Close();
            }
        }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

5. <span data-ttu-id="a9620-120">次のコマンドを実行して `dotnet-svcutil.xmlserializer` パッケージへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="a9620-120">Add a reference to the `dotnet-svcutil.xmlserializer` package by running the following command:</span></span>
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    <span data-ttu-id="a9620-121">コマンドを実行すると、次のようなエントリがプロジェクト ファイルに追加されます。</span><span class="sxs-lookup"><span data-stu-id="a9620-121">Running the command should add an entry to your project file similar to this:</span></span>
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="a9620-122">`dotnet build` を実行してアプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="a9620-122">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="a9620-123">すべて正常に終了すると、出力フォルダーに *MyWCFClient.XmlSerializers.dll* という名前のアセンブリが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a9620-123">If everything succeeds, an assembly named *MyWCFClient.XmlSerializers.dll* is generated in the output folder.</span></span> <span data-ttu-id="a9620-124">ツールがアセンブリの生成に失敗した場合は、ビルド出力に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a9620-124">If the tool failed to generate the assembly, you'll see warnings in the build output.</span></span>

7. <span data-ttu-id="a9620-125">ブラウザーで `http://localhost:2561/Service1.svc` を実行するなどして、WCF サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a9620-125">Start the WCF service by, for example, running `http://localhost:2561/Service1.svc` in the browser.</span></span> <span data-ttu-id="a9620-126">次にクライアント アプリケーションを起動します。実行時に、事前に生成されたシリアライザーが自動的に読み込まれ、使用されます。</span><span class="sxs-lookup"><span data-stu-id="a9620-126">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
