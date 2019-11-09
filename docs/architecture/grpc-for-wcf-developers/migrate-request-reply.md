---
title: Wcf 開発者向けの gRPC-gRPC への WCF 要求/応答サービスの移行
description: 単純な要求/応答サービスを WCF から gRPC に移行する方法について説明します。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 12e042e8e7e3683cc4da1fedce2482e7199b04a7
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841505"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="9c83c-103">WCF 要求/応答サービスを gRPC 単項 RPC に移行する</span><span class="sxs-lookup"><span data-stu-id="9c83c-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="9c83c-104">このセクションでは、WCF の基本的な要求/応答サービスを ASP.NET Core gRPC の単項 RPC サービスに移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="9c83c-105">これらのサービスは、Windows Communication Foundation (WCF) と gRPC の両方で最も単純なサービスの種類であるため、開始するのが優れた場所です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="9c83c-106">サービスを移行した後、.NET クライアントアプリケーションからサービスを使用するために、同じ `.proto` ファイルからクライアントライブラリを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="9c83c-107">WCF ソリューション</span><span class="sxs-lookup"><span data-stu-id="9c83c-107">The WCF solution</span></span>

<span data-ttu-id="9c83c-108">[PortfoliosSample ソリューション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys)には、単一のポートフォリオをダウンロードするための単純な要求/応答ポートフォリオサービス、または特定の商人のすべてのポートフォリオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple Request-Reply Portfolio service to download a single portfolio, or all portfolios for a given Trader.</span></span> <span data-ttu-id="9c83c-109">このサービスは、インターフェイス `IPortfolioService` `ServiceContract` 属性で定義されています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

```csharp
[ServiceContract]
public interface IPortfolioService
{
    [OperationContract]
    Task<Portfolio> Get(Guid traderId, int portfolioId);

    [OperationContract]
    Task<List<Portfolio>> GetAll(Guid traderId);
}
```

<span data-ttu-id="9c83c-110">`Portfolio` モデルは、`PortfolioItem` オブジェクトC#の一覧など、 [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)でマークされた単純なクラスです。</span><span class="sxs-lookup"><span data-stu-id="9c83c-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute), including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="9c83c-111">これらのモデルは、`TraderSys.PortfolioData` プロジェクトで、データアクセスの抽象化を表すリポジトリクラスと共に定義されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-111">These models are defined in the `TraderSys.PortfolioData` project, along with a repository class representing a data access abstraction.</span></span>

```csharp
[DataContract]
public class Portfolio
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public Guid TraderId { get; set; }

    [DataMember]
    public List<PortfolioItem> Items { get; set; }
}

[DataContract]
public class PortfolioItem
{
    [DataMember]
    public int Id { get; set; }

    [DataMember]
    public int ShareId { get; set; }

    [DataMember]
    public int Holding { get; set; }

    [DataMember]
    public decimal Cost { get; set; }
}
```

<span data-ttu-id="9c83c-112">`ServiceContract` 実装では、`DataContract` 型のインスタンスを返す依存関係の挿入によって提供されるリポジトリクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types.</span></span>

```csharp
public class PortfolioService : IPortfolioService
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }

    public async Task<Portfolio> Get(Guid traderId, int portfolioId)
    {
        return await _repository.GetAsync(traderId, portfolioId);
    }

    public async Task<List<Portfolio>> GetAll(Guid traderId)
    {
        return await _repository.GetAllAsync(traderId);
    }
}
```

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="9c83c-113">ポートフォリオのプロトコルファイル</span><span class="sxs-lookup"><span data-stu-id="9c83c-113">The portfolios.proto file</span></span>

<span data-ttu-id="9c83c-114">前のセクションの手順に従っている場合は、次のような `portfolios.proto` ファイルを含む gRPC プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="9c83c-115">最初の手順では、`DataContract` クラスを同等の Protobuf に移行します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontracts-to-grpc-messages"></a><span data-ttu-id="9c83c-116">DataContracts を gRPC メッセージに変換する</span><span class="sxs-lookup"><span data-stu-id="9c83c-116">Convert the DataContracts to gRPC messages</span></span>

<span data-ttu-id="9c83c-117">`Portfolio` クラスが依存しているため、`PortfolioItem` クラスは最初に Protobuf メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-117">The `PortfolioItem` class will be converted to a Protobuf message first, as the `Portfolio` class depends on it.</span></span> <span data-ttu-id="9c83c-118">クラスは非常に単純で、3つのプロパティは gRPC データ型に直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-118">The class is very simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="9c83c-119">購入時に共有に対して支払われた価格を表す `Cost` プロパティは `decimal` のフィールドであり、gRPC は `float` または `double` をサポートしています。これは、通貨には適していません。</span><span class="sxs-lookup"><span data-stu-id="9c83c-119">The `Cost` property, representing the price paid for the shares at purchase, is a `decimal` field, and gRPC only supports `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="9c83c-120">共有価格は少なくとも1セントで異なるため、コストはセントの `int32` として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-120">Since share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="9c83c-121">`.proto` ファイルのフィールド名には `camelCase` を使用することを忘れないでください。C#コードジェネレーターは、それらを `PascalCase` に変換します。他の言語のユーザーは、さまざまなコーディング基準を使用することに感謝します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-121">Remember to use `camelCase` for field names in your `.proto` file; the C# code generator will convert them to `PascalCase` for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="9c83c-122">`Portfolio` クラスは少し複雑です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-122">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="9c83c-123">WCF コードでは、開発者は `TraderId` プロパティに `Guid` を使用し、`List<PortfolioItem>`を格納しています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-123">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="9c83c-124">ファーストクラスの `UUID` 型を持たない Protobuf では、`traderId` フィールドに `string` を使用し、独自のコードで解析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-124">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="9c83c-125">項目の一覧を表示するには、フィールドで `repeated` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-125">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="9c83c-126">これで、データメッセージが作成されました。サービス RPC エンドポイントを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-126">Now we have our data messages, we can declare the service RPC endpoints.</span></span>

## <a name="convert-the-servicecontract-to-a-grpc-service"></a><span data-ttu-id="9c83c-127">ServiceContract を gRPC サービスに変換する</span><span class="sxs-lookup"><span data-stu-id="9c83c-127">Convert the ServiceContract to a gRPC service</span></span>

<span data-ttu-id="9c83c-128">WCF `Get` メソッドは、`Guid traderId` と `int portfolioId`の2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-128">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="9c83c-129">gRPC サービスメソッドは、1つのパラメーターのみを受け取ることができるため、2つの値を保持するためにメッセージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-129">gRPC service methods can only take a single parameter, so a message must be created to hold the two values.</span></span> <span data-ttu-id="9c83c-130">これらの要求オブジェクトには、メソッドとサフィックス `Request`と同じ名前を付けるのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-130">It's common practice to name these request objects with the same name as the method and the suffix `Request`.</span></span> <span data-ttu-id="9c83c-131">ここでも、`string` は `Guid`ではなく `traderId` フィールドに使用されています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-131">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="9c83c-132">サービスは `Portfolio` メッセージを直接返すこともできましたが、今後は旧バージョンとの互換性に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-132">The service could just return a `Portfolio` message directly, but again, this could impact backward compatibility in the future.</span></span> <span data-ttu-id="9c83c-133">サービスのメソッドごとに個別の `Request` と `Response` メッセージを定義することをお勧めします。その多くが同じであっても、1つの `Portfolio` フィールドを持つ `GetResponse` メッセージを宣言します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-133">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now, so declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="9c83c-134">次の例は、`GetRequest` メッセージを使用した gRPC サービスメソッドの宣言を示しています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-134">The following example shows the declaration of the gRPC service method using the `GetRequest` message:</span></span>

```protobuf
message GetRequest {
    string trader_id = 1;
    int32 portfolio_id = 2;
}

message GetResponse {
    Portfolio portfolio = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (GetResponse);
}
```

<span data-ttu-id="9c83c-135">WCF `GetAll` メソッドは、1つのパラメーター `traderId`のみを受け取ります。そのため、パラメーターの型として `string` を指定することもできますが、gRPC には定義されたメッセージ型が必要です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-135">The WCF `GetAll` method only takes a single parameter, `traderId`, so it might seem that one could specify `string` as the parameter type, but gRPC requires a defined message type.</span></span> <span data-ttu-id="9c83c-136">この要件は、今後の旧バージョンとの互換性のために、すべての入力と出力にカスタムメッセージを使用する方法を適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-136">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="9c83c-137">また、WCF メソッドは `List<Portfolio>`も返しましたが、単純なパラメーター型を許可しないのと同じ理由で、gRPC は戻り値の型として `repeated Portfolio` を許可しません。</span><span class="sxs-lookup"><span data-stu-id="9c83c-137">The WCF method also returned a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="9c83c-138">代わりに、`GetAllResponse` の種類を作成してリストをラップします。</span><span class="sxs-lookup"><span data-stu-id="9c83c-138">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="9c83c-139">`PortfolioList` メッセージまたは類似したメッセージを作成して、複数のサービスメソッドで使用することも考えられますが、このようなことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="9c83c-139">You may be tempted to create a `PortfolioList` message or similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="9c83c-140">今後、サービスのさまざまなメソッドがどのように進化するかを知ることはできません。そのため、メッセージを明確にして明確に分離することができます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-140">It's impossible to know how the various methods on a service may evolve in the future, so keep their messages specific and cleanly separated.</span></span>

```protobuf
message GetAllRequest {
    string trader_id = 1;
}

message PortfolioList {
    repeated Portfolio portfolios = 1;
}

service Portfolios {
    rpc Get(GetRequest) returns (Portfolio);
    rpc GetAll(GetAllRequest) returns (GetAllResponse);
}
```

<span data-ttu-id="9c83c-141">これらの変更を使用してプロジェクトを保存すると、gRPC ビルドターゲットがバックグラウンドで実行され、すべての Protobuf メッセージ型と、サービスを実装するために継承できる基本クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-141">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class you can inherit to implement the service.</span></span>

<span data-ttu-id="9c83c-142">`Services/GreeterService.cs` クラスを開き、コード例を削除します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-142">Open up the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="9c83c-143">これで、ポートフォリオサービスの実装を追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9c83c-143">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="9c83c-144">生成された基底クラスは `Protos` 名前空間にあり、入れ子になったクラスとして生成されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-144">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="9c83c-145">gRPC は、`.proto` ファイルにサービスと同じ名前の静的クラスを作成した後、その静的クラス内で `Base` サフィックスを持つ基底クラスを作成するため、基本型の完全な識別子は `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`ます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-145">gRPC creates a static class with the same name as the service in the `.proto` file, and then a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="9c83c-146">基本クラスは、サービスを実装するためにオーバーライドできる `Get` および `GetAll` の `virtual` メソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-146">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="9c83c-147">メソッドは、`abstract` ではなく `virtual` ので、実装していない場合は、通常C#のコードで `NotImplementedException` をスローするのと同じように、サービスは明示的な grpc `Unimplemented` 状態コードを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-147">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="9c83c-148">ASP.NET Core 内のすべての gRPC 単項サービスメソッドの署名が一貫しています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-148">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="9c83c-149">2つのパラメーターがあります。1つ目は `.proto` ファイルで宣言されたメッセージ型、2つ目は ASP.NET Core の `HttpContext` と同様に機能する `ServerCallContext` です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-149">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="9c83c-150">実際には、基になる `HttpContext`を取得するために使用できる `ServerCallContext` クラスに `GetHttpContext` という拡張メソッドがありますが、頻繁に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c83c-150">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="9c83c-151">この章の後半の `ServerCallContext` と、認証について説明している章を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c83c-151">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="9c83c-152">メソッドの戻り値の型は `Task<T>` であり、`T` は応答メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-152">The method's return type is a `Task<T>` where `T` is the response message type.</span></span> <span data-ttu-id="9c83c-153">すべての gRPC サービスメソッドは非同期です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-153">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="9c83c-154">PortfolioData ライブラリを .NET Core に移行する</span><span class="sxs-lookup"><span data-stu-id="9c83c-154">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="9c83c-155">この時点で、プロジェクトには、WCF ソリューションの `TraderSys.PortfolioData` クラスライブラリに含まれるポートフォリオリポジトリとモデルが必要です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-155">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="9c83c-156">新しいクラスライブラリを作成する最も簡単な方法は、Visual Studio の **[新しいプロジェクト]** ダイアログを*クラスライブラリ (.NET Standard)* テンプレートと共に使用するか、コマンドラインで .NET Core CLI を使用して、`TraderSys.sln` ファイルが格納されているディレクトリから次のコマンドを実行することです。</span><span class="sxs-lookup"><span data-stu-id="9c83c-156">The easiest way to bring them across is to create a new class library using either the Visual Studio **New project** dialog with the *Class Library (.NET Standard)* template, or from the command line using the .NET Core CLI, running the following commands from the directory containing the `TraderSys.sln` file.</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="9c83c-157">ライブラリを作成してソリューションに追加したら、生成された `Class1.cs` ファイルを削除し、WCF ソリューションのライブラリのファイルを新しいクラスライブラリのフォルダーにコピーして、フォルダー構造を維持します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-157">Once the library has been created and added to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure.</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="9c83c-158">SDK スタイルの .NET プロジェクトでは、任意の `.cs` ファイルがそのディレクトリに自動的に含まれます。そのため、プロジェクトに明示的に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9c83c-158">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so there's no need to explicitly add them to the project.</span></span> <span data-ttu-id="9c83c-159">残りの手順は、`DataContract` と `DataMember` 属性を `Portfolio` クラスと `PortfolioItem` クラスから削除することです。これにC#より、これらは単純な古いクラスになります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-159">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes.</span></span>

```csharp
public class Portfolio
{
    public int Id { get; set; }
    public Guid TraderId { get; set; }
    public List<PortfolioItem> Items { get; set; }
}

public class PortfolioItem
{
    public int Id { get; set; }
    public int ShareId { get; set; }
    public int Holding { get; set; }
    public decimal Cost { get; set; }
}
```

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="9c83c-160">ASP.NET Core 依存関係の挿入の使用</span><span class="sxs-lookup"><span data-stu-id="9c83c-160">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="9c83c-161">これで、このライブラリへの参照を gRPC アプリケーションプロジェクトに追加し、gRPC サービス実装で依存関係の挿入を使用して `PortfolioRepository` クラスを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9c83c-161">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="9c83c-162">WCF アプリケーションでは、依存関係の注入は Autofac IoC コンテナーによって提供されていました。</span><span class="sxs-lookup"><span data-stu-id="9c83c-162">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="9c83c-163">ASP.NET Core には依存関係の挿入が組み込まれています。リポジトリは、`Startup` クラスの `ConfigureServices` メソッドに登録できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-163">ASP.NET Core has dependency injection baked in; the repository can be registered in the `ConfigureServices` method in the `Startup` class.</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Register the repository class as a scoped service (instance per request)
        services.AddScoped<IPortfolioRepository, PortfolioRepository>();

        services.AddGrpc();
    }

    // ...
}
```

<span data-ttu-id="9c83c-164">`IPortfolioRepository` の実装は、次のように `PortfolioService` クラスのコンストラクターパラメーターとして指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="9c83c-164">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

```csharp
public class PortfolioService : Protos.Portfolios.PortfoliosBase
{
    private readonly IPortfolioRepository _repository;

    public PortfolioService(IPortfolioRepository repository)
    {
        _repository = repository;
    }
}
```

## <a name="implement-the-grpc-service"></a><span data-ttu-id="9c83c-165">GRPC サービスを実装する</span><span class="sxs-lookup"><span data-stu-id="9c83c-165">Implement the gRPC service</span></span>

<span data-ttu-id="9c83c-166">メッセージとサービスを `portfolios.proto` ファイルで宣言したので、gRPC によって生成された `Portfolios.PortfoliosBase` クラスを継承する `PortfolioService` クラスにサービスメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-166">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="9c83c-167">メソッドは、基本クラスの `virtual` として宣言されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-167">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="9c83c-168">オーバーライドしないと、既定で gRPC "未実装" 状態コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-168">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="9c83c-169">まず、`Get` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-169">Start by implementing the `Get` method.</span></span> <span data-ttu-id="9c83c-170">既定のオーバーライドは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-170">The default override looks like the following example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="9c83c-171">最初の問題は、`request.TraderId` が文字列であり、サービスに `Guid`が必要であることです。</span><span class="sxs-lookup"><span data-stu-id="9c83c-171">The first issue is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="9c83c-172">文字列に必要な書式が `UUID`であっても、呼び出し元が無効な値を送信し、適切に応答する可能性をコードで処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-172">Even though the expected format for the string is a `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="9c83c-173">サービスは、`RpcException`をスローすることによってエラーで応答し、標準の `InvalidArgument` ステータスコードを使用して問題を表現できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-173">The service can respond with errors by throwing an `RpcException`, and use the standard `InvalidArgument` status code to express the problem.</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    return base.Get(request, context);
}
```

<span data-ttu-id="9c83c-174">`traderId`に適切な `Guid` 値があれば、リポジトリを使用してポートフォリオを取得し、それをクライアントに返すことができます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-174">Once there's a proper `Guid` value for `traderId`, the repository can be used to retrieve the Portfolio and return it to the client.</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="9c83c-175">内部モデルを gRPC メッセージにマップする</span><span class="sxs-lookup"><span data-stu-id="9c83c-175">Map internal models to gRPC messages</span></span>

<span data-ttu-id="9c83c-176">リポジトリが独自の POCO モデル `Portfolio`を返すため、前のコードは実際には機能しませんが、gRPC は独自の Protobuf メッセージ `Portfolio`*を必要と*します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-176">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs *its* own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="9c83c-177">Entity Framework 型からデータ転送型へのマッピングと同様に、最適な解決策は、2つの間の変換を提供することです。</span><span class="sxs-lookup"><span data-stu-id="9c83c-177">Much like mapping Entity Framework types to data transfer types, the best solution is to provide conversion between the two.</span></span> <span data-ttu-id="9c83c-178">このコードを配置するための適切な場所は、Protobuf によって生成されるクラスにあります。これは、拡張できるように `partial` クラスとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-178">A good place to put the code for this is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended.</span></span>

```csharp
namespace TraderSys.Portfolios.Protos
{
    public partial class PortfolioItem
    {
        public static PortfolioItem FromRepositoryModel(PortfolioData.Models.PortfolioItem source)
        {
            if (source is null) return null;

            return new PortfolioItem
            {
                Id = source.Id,
                ShareId = source.ShareId,
                Holding = source.Holding,
                CostCents = (int)(source.Cost * 100)
            };
        }
    }

    public partial class Portfolio
    {
        public static Portfolio FromRepositoryModel(PortfolioData.Models.Portfolio source)
        {
            if (source is null) return null;

            var target = new Portfolio
            {
                Id = source.Id,
                TraderId = source.TraderId.ToString(),
            };

            target.Items.AddRange(source.Items.Select(PortfolioItem.FromRepositoryModel));

            return target;
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="9c83c-179">[Automapper](https://automapper.org/)のようなライブラリを使用して、内部モデルクラスから Protobuf 型への変換を処理できます。ただし、`string`/`Guid` や `decimal`/`double` やリストマッピングなどの下位レベルの型変換を構成する場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-179">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="9c83c-180">変換コードを配置すると、`Get` メソッドの実装を完了できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-180">With the conversion code in place, the `Get` method implementation can be completed.</span></span>

```csharp
public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolio = await _repository.GetAsync(traderId, request.PortfolioId);

    return new GetResponse
    {
        Portfolio = Portfolio.FromRepositoryModel(portfolio)
    };
}

```

<span data-ttu-id="9c83c-181">`GetAll` メソッドの実装も似ています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-181">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="9c83c-182">Protobuf メッセージの `repeated` フィールドは `RepeatedField<T>`型の `readonly` プロパティとして生成されるため、次の例のように、`AddRange` メソッドを使用して項目を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-182">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them using the `AddRange` method, like in the following example:</span></span>

```csharp
public override async Task<GetAllResponse> GetAll(GetAllRequest request, ServerCallContext context)
{
    if (!Guid.TryParse(request.TraderId, out var traderId))
    {
        throw new RpcException(new Status(StatusCode.InvalidArgument, "traderId must be a UUID"));
    }

    var portfolios = await _repository.GetAllAsync(traderId);

    var response = new GetAllResponse();
    response.Portfolios.AddRange(portfolios.Select(Portfolio.FromRepositoryModel));

    return response;
}
```

<span data-ttu-id="9c83c-183">WCF 要求-応答サービスを gRPC に正常に移行したところで、`.proto` ファイルからクライアントを作成する方法を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="9c83c-183">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="9c83c-184">クライアントコードの生成</span><span class="sxs-lookup"><span data-stu-id="9c83c-184">Generate client code</span></span>

<span data-ttu-id="9c83c-185">クライアントを格納するために、同じソリューションに .NET Standard クラスライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-185">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="9c83c-186">これは、主にクライアントコードを作成する例ですが、NuGet を使用してこのようなライブラリをパッケージ化し、他の .NET チームが使用できるように内部リポジトリに配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-186">This is primarily an example of creating client code, but you could package such a library using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="9c83c-187">`TraderSys.Portfolios.Client` という名前の新しい .NET Standard クラスライブラリをソリューションに追加し、`Class1.cs` ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-187">Go ahead and add a new .NET Standard Class Library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="9c83c-188">[Grpc .Net クライアント](https://www.nuget.org/packages/Grpc.Net.Client)の NuGet パッケージには、.net Core 3.0 (または .NET Standard 2.1 に準拠した別のランタイム) が必要です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-188">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="9c83c-189">以前のバージョンの .NET Framework と .NET Core は、 [Grpc. Core](https://www.nuget.org/packages/Grpc.Core) NuGet パッケージによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9c83c-189">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="9c83c-190">Visual Studio 2019 では、以前のバージョンの Visual Studio で WCF プロジェクトにサービス参照を追加するのと同様の方法で、gRPC サービスへの参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-190">In Visual Studio 2019, you can add references to gRPC services similar to the way you'd add Service References to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="9c83c-191">サービス参照と接続済みサービスは、すべて同じ UI で管理されます。これは、ソリューションエクスプローラーで `TraderSys.Portfolios.Client` プロジェクトの **[依存関係]** ノードを右クリックし、 **[接続済みサービスの追加]** を選択してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-191">Service References and Connected Services are all managed under the same UI now, which you can access by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="9c83c-192">表示されたツールウィンドウで、 **[サービス参照]** セクションを選択し、 **[新しい grpc サービス参照の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c83c-192">In the tool window that appears, select the **Service References** section and click **Add new gRPC service reference**.</span></span>

![Visual Studio 2019 の接続済みサービス UI](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="9c83c-194">`TraderSys.Portfolios` プロジェクトの `portfolios.proto` ファイルを参照し、**クライアント**として**生成されるクラスの種類**をそのまま使用して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c83c-194">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave the **type of class to be generated** as **Client**, and click **OK**.</span></span>

![Visual Studio 2019 の [新しい gRPC サービス参照の追加] ダイアログ](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="9c83c-196">このダイアログには、URL フィールドも表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9c83c-196">Notice that this dialog also provides a URL field.</span></span> <span data-ttu-id="9c83c-197">組織が `.proto` ファイルの web アクセス可能なディレクトリを保持している場合は、この URL アドレスを設定するだけでクライアントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-197">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="9c83c-198">Visual Studio の **[接続済みサービスの追加]** 機能を使用すると、`portfolios.proto` ファイルはコピーされるのではなく、リンクされた*ファイル*としてクラスライブラリプロジェクトに追加されるため、サービスプロジェクト内のファイルに対する変更は自動的にクライアントプロジェクトに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-198">When using the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the Class Library project as a *linked file*, rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="9c83c-199">`csproj` ファイルの `<Protobuf>` 要素は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-199">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="9c83c-200">Visual Studio を使用していない場合、またはコマンドラインから作業する場合は、 **dotnet-grpc**グローバルツールを使用して、.Net grpc プロジェクト内の Protobuf 参照を管理できます。</span><span class="sxs-lookup"><span data-stu-id="9c83c-200">If you are not using Visual Studio or prefer to work from the command line, you can use the **dotnet-grpc** global tool to manage Protobuf references within a .NET gRPC project.</span></span> <span data-ttu-id="9c83c-201">[詳細については、 **dotnet-grpc**のドキュメントを参照して](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc)ください。</span><span class="sxs-lookup"><span data-stu-id="9c83c-201">[Refer to the **dotnet-grpc** documentation for more information](https://docs.microsoft.com/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="9c83c-202">クライアントアプリケーションからのポートフォリオサービスの使用</span><span class="sxs-lookup"><span data-stu-id="9c83c-202">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="9c83c-203">次のコードは、生成されたクライアントをコンソールアプリケーションで使用する簡単な例です。</span><span class="sxs-lookup"><span data-stu-id="9c83c-203">The following code is a brief example of using the generated client in a console application.</span></span> <span data-ttu-id="9c83c-204">GRPC クライアントコードのより詳細な探索については、この章の最後にあります。</span><span class="sxs-lookup"><span data-stu-id="9c83c-204">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

```csharp
public class Program
{
    public async Task Main(string[] args)
    {
        GetResponse response;

        using (var channel = GrpcChannel.ForAddress("https://localhost:5001"))
        {
            var client = new Protos.Portfolios.PortfoliosClient(channel);

            response = await client.GetAsync(new GetRequest
            {
                TraderId = args[0],
                PortfolioId = int.Parse(args[1])
            });
        }

        foreach (var item in response.Portfolio.Items)
        {
            Console.WriteLine($"Holding {item.Holding} of Share ID {item.ShareId}.");
        }
    }
}
```

<span data-ttu-id="9c83c-205">ここでは、基本的な WCF アプリケーションを ASP.NET Core gRPC サービスに移行し、.NET アプリケーションからサービスを使用するクライアントを作成しました。</span><span class="sxs-lookup"><span data-stu-id="9c83c-205">Now, you've migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="9c83c-206">次のセクションでは、より複雑な "二重" サービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9c83c-206">The next section will cover the more involved "duplex" services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="9c83c-207">[前へ](create-project.md)
>[次へ](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="9c83c-207">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
