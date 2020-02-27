---
title: Wcf 開発者向けの gRPC-gRPC への WCF 要求/応答サービスの移行
description: 単純な要求/応答サービスを WCF から gRPC に移行する方法について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 018aa94a15cdcb1e0f559afb7b3a88cd4f915398
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628554"
---
# <a name="migrate-a-wcf-request-reply-service-to-a-grpc-unary-rpc"></a><span data-ttu-id="0cdfe-103">WCF 要求/応答サービスを gRPC 単項 RPC に移行する</span><span class="sxs-lookup"><span data-stu-id="0cdfe-103">Migrate a WCF request-reply service to a gRPC unary RPC</span></span>

<span data-ttu-id="0cdfe-104">このセクションでは、WCF の基本的な要求/応答サービスを ASP.NET Core gRPC の単項 RPC サービスに移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-104">This section covers how to migrate a basic request-reply service in WCF to a unary RPC service in ASP.NET Core gRPC.</span></span> <span data-ttu-id="0cdfe-105">これらのサービスは、Windows Communication Foundation (WCF) と gRPC の両方で最も単純なサービスの種類であるため、開始するのが優れた場所です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-105">These services are the simplest service types in both Windows Communication Foundation (WCF) and gRPC, so it's an excellent place to start.</span></span> <span data-ttu-id="0cdfe-106">サービスを移行した後、.NET クライアントアプリケーションからサービスを使用するために、同じ `.proto` ファイルからクライアントライブラリを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-106">After migrating the service, you'll learn how to generate a client library from the same `.proto` file to consume the service from a .NET client application.</span></span>

## <a name="the-wcf-solution"></a><span data-ttu-id="0cdfe-107">WCF ソリューション</span><span class="sxs-lookup"><span data-stu-id="0cdfe-107">The WCF solution</span></span>

<span data-ttu-id="0cdfe-108">[PortfoliosSample ソリューション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys)には、単一のポートフォリオまたは特定の商人のすべてのポートフォリオをダウンロードする単純な要求/応答ポートフォリオサービスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-108">The [PortfoliosSample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/PortfoliosSample/wcf/TraderSys) includes a simple request-reply Portfolio service to download either a single portfolio or all portfolios for a given trader.</span></span> <span data-ttu-id="0cdfe-109">このサービスは、インターフェイス `IPortfolioService` `ServiceContract` 属性で定義されています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-109">The service is defined in the interface `IPortfolioService` with a `ServiceContract` attribute:</span></span>

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

<span data-ttu-id="0cdfe-110">`Portfolio` モデルは、 [DataContract](xref:System.Runtime.Serialization.DataContractAttribute)でC#マークされた単純なクラスで、`PortfolioItem` オブジェクトの一覧を含みます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-110">The `Portfolio` model is a simple C# class marked with [DataContract](xref:System.Runtime.Serialization.DataContractAttribute) and including a list of `PortfolioItem` objects.</span></span> <span data-ttu-id="0cdfe-111">これらのモデルは、`TraderSys.PortfolioData` プロジェクトで、データアクセスの抽象化を表すリポジトリクラスと共に定義されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-111">These models are defined in the `TraderSys.PortfolioData` project along with a repository class that represents a data access abstraction.</span></span>

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

<span data-ttu-id="0cdfe-112">`ServiceContract` の実装では、`DataContract` 型のインスタンスを返す依存関係の挿入によって提供されるリポジトリクラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-112">The `ServiceContract` implementation uses a repository class provided via dependency injection that returns instances of the `DataContract` types:</span></span>

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

## <a name="the-portfoliosproto-file"></a><span data-ttu-id="0cdfe-113">ポートフォリオのプロトコルファイル</span><span class="sxs-lookup"><span data-stu-id="0cdfe-113">The portfolios.proto file</span></span>

<span data-ttu-id="0cdfe-114">前のセクションの手順に従っている場合は、次のような `portfolios.proto` ファイルを含む gRPC プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-114">If you followed the instructions in the previous section, you should have a gRPC project with a `portfolios.proto` file that looks like this:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

<span data-ttu-id="0cdfe-115">最初の手順では、`DataContract` クラスを同等の Protobuf に移行します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-115">The first step is to migrate the `DataContract` classes to their Protobuf equivalents.</span></span>

## <a name="convert-the-datacontract-classes-to-grpc-messages"></a><span data-ttu-id="0cdfe-116">DataContract クラスを gRPC メッセージに変換します</span><span class="sxs-lookup"><span data-stu-id="0cdfe-116">Convert the DataContract classes to gRPC messages</span></span>

<span data-ttu-id="0cdfe-117">`Portfolio` クラスが依存しているため、`PortfolioItem` クラスは最初に Protobuf メッセージに変換されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-117">The `PortfolioItem` class will be converted to a Protobuf message first, because the `Portfolio` class depends on it.</span></span> <span data-ttu-id="0cdfe-118">クラスは単純で、3つのプロパティは gRPC データ型に直接マップされます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-118">The class is simple, and three of the properties map directly to gRPC data types.</span></span> <span data-ttu-id="0cdfe-119">購入時に共有に対して支払われた価格を表す `Cost` プロパティは `decimal` のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-119">The `Cost` property, which represents the price paid for the shares at purchase, is a `decimal` field.</span></span> <span data-ttu-id="0cdfe-120">gRPC は、`float` または `double` のみをサポートしています。これは、通貨には適していません。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-120">gRPC supports only `float` or `double` for real numbers, which aren't suitable for currency.</span></span> <span data-ttu-id="0cdfe-121">共有価格は最低1セントであるため、コストはセントの `int32` として表すことができます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-121">Because share prices vary by a minimum of one cent, the cost can be expressed as an `int32` of cents.</span></span>

> [!NOTE]
> <span data-ttu-id="0cdfe-122">`.proto` ファイル内のフィールド名には、必ずキャメルケースを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-122">Remember to use camelCase for field names in your `.proto` file.</span></span> <span data-ttu-id="0cdfe-123">C#コードジェネレーターはこれらをユーザーに対してパスワード変換します。他の言語のユーザーは、異なるコーディング基準を使用することに感謝します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-123">The C# code generator will convert them to PascalCase for you, and users of other languages will thank you for respecting their different coding standards.</span></span>

```protobuf
message PortfolioItem {
    int32 id = 1;
    int32 share_id = 2;
    int32 holding = 3;
    int32 cost_cents = 4;
}
```

<span data-ttu-id="0cdfe-124">`Portfolio` クラスは少し複雑です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-124">The `Portfolio` class is a little more complicated.</span></span> <span data-ttu-id="0cdfe-125">WCF コードでは、開発者は `TraderId` プロパティに `Guid` を使用し、`List<PortfolioItem>`を格納しています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-125">In the WCF code, the developer used a `Guid` for the `TraderId` property, and contains a `List<PortfolioItem>`.</span></span> <span data-ttu-id="0cdfe-126">ファーストクラスの `UUID` 型を持たない Protobuf では、`traderId` フィールドに `string` を使用し、独自のコードで解析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-126">In Protobuf, which doesn't have a first-class `UUID` type, you should use a `string` for the `traderId` field and parse it in your own code.</span></span> <span data-ttu-id="0cdfe-127">項目の一覧を表示するには、フィールドで `repeated` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-127">For the list of items, use the `repeated` keyword on the field.</span></span>

```protobuf
message Portfolio {
    int32 id = 1;
    string trader_id = 2;
    repeated PortfolioItem items = 3;
}
```

<span data-ttu-id="0cdfe-128">データメッセージを取得したので、サービス RPC エンドポイントを宣言できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-128">Now that you have the data messages, you can declare the service RPC endpoints.</span></span>

## <a name="convert-servicecontract-to-a-grpc-service"></a><span data-ttu-id="0cdfe-129">ServiceContract を gRPC サービスに変換する</span><span class="sxs-lookup"><span data-stu-id="0cdfe-129">Convert ServiceContract to a gRPC service</span></span>

<span data-ttu-id="0cdfe-130">WCF `Get` メソッドは、`Guid traderId` と `int portfolioId`の2つのパラメーターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-130">The WCF `Get` method takes two parameters: `Guid traderId` and `int portfolioId`.</span></span> <span data-ttu-id="0cdfe-131">gRPC サービスメソッドは、1つのパラメーターのみを受け取ることができるため、2つの値を格納するメッセージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-131">gRPC service methods can take only a single parameter, so you need to create a message to hold the two values.</span></span> <span data-ttu-id="0cdfe-132">これらの要求オブジェクトには、メソッドと同じ名前を付け、その後にサフィックス `Request`を付けるのが一般的です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-132">It's common practice to name these request objects with the same name as the method followed by the suffix `Request`.</span></span> <span data-ttu-id="0cdfe-133">ここでも、`string` は `Guid`ではなく `traderId` フィールドに使用されています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-133">Again, `string` is being used for the `traderId` field instead of `Guid`.</span></span>

<span data-ttu-id="0cdfe-134">サービスは `Portfolio` メッセージを直接返すこともできましたが、今後は旧バージョンとの互換性に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-134">The service could just return a `Portfolio` message directly, but again, this could affect backward compatibility in the future.</span></span> <span data-ttu-id="0cdfe-135">サービスのメソッドごとに個別の `Request` と `Response` メッセージを定義することをお勧めします。これは、その多くが同じであっても同じです。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-135">It's a good practice to define separate `Request` and `Response` messages for every method in a service, even if many of them are the same right now.</span></span> <span data-ttu-id="0cdfe-136">そのため、1つの `Portfolio` フィールドで `GetResponse` メッセージを宣言します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-136">So declare a `GetResponse` message with a single `Portfolio` field.</span></span>

<span data-ttu-id="0cdfe-137">次の例では、`GetRequest` メッセージを使用した gRPC サービスメソッドの宣言を示します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-137">This example shows the declaration of the gRPC service method with the `GetRequest` message:</span></span>

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

<span data-ttu-id="0cdfe-138">WCF `GetAll` メソッドは、1つのパラメーター (`traderId`) のみを受け取るので、パラメーターの型として `string` を指定できるように思われるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-138">The WCF `GetAll` method takes only a single parameter, `traderId`, so it might seem that you could specify `string` as the parameter type.</span></span> <span data-ttu-id="0cdfe-139">ただし、gRPC には定義済みのメッセージ型が必要です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-139">But gRPC requires a defined message type.</span></span> <span data-ttu-id="0cdfe-140">この要件は、今後の旧バージョンとの互換性のために、すべての入力と出力にカスタムメッセージを使用する方法を適用するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-140">This requirement helps to enforce the practice of using custom messages for all inputs and outputs, for future backward compatibility.</span></span>

<span data-ttu-id="0cdfe-141">また、WCF メソッドは `List<Portfolio>`も返しますが、単純なパラメーター型を許可しないのと同じ理由で、gRPC は戻り値の型として `repeated Portfolio` を許可しません。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-141">The WCF method also returns a `List<Portfolio>`, but for the same reason it doesn't allow simple parameter types, gRPC won't allow `repeated Portfolio` as a return type.</span></span> <span data-ttu-id="0cdfe-142">代わりに、`GetAllResponse` の種類を作成してリストをラップします。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-142">Instead, create a `GetAllResponse` type to wrap the list.</span></span>

> [!WARNING]
> <span data-ttu-id="0cdfe-143">`PortfolioList` メッセージを作成したり、類似したものを使用して複数のサービス方法で使用したりすることがありますが、このようなことは避けてください。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-143">You might be tempted to create a `PortfolioList` message or something similar and use it across multiple service methods, but you should resist this temptation.</span></span> <span data-ttu-id="0cdfe-144">サービスのさまざまなメソッドがどのように進化しているかを知ることはできません。そのため、メッセージを明確にして明確に分離することができます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-144">It's impossible to know how the various methods on a service will evolve, so keep their messages specific and cleanly separated.</span></span>

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

<span data-ttu-id="0cdfe-145">これらの変更を使用してプロジェクトを保存すると、gRPC ビルドターゲットがバックグラウンドで実行され、すべての Protobuf メッセージ型と、サービスを実装するために継承できる基本クラスが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-145">If you save your project with these changes, the gRPC build target will run in the background and generate all the Protobuf message types and a base class that you can inherit to implement the service.</span></span>

<span data-ttu-id="0cdfe-146">`Services/GreeterService.cs` クラスを開き、コード例を削除します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-146">Open the `Services/GreeterService.cs` class and delete the example code.</span></span> <span data-ttu-id="0cdfe-147">これで、ポートフォリオサービスの実装を追加できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-147">Now you can add the Portfolio service implementation.</span></span> <span data-ttu-id="0cdfe-148">生成された基底クラスは `Protos` 名前空間にあり、入れ子になったクラスとして生成されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-148">The generated base class will be in the `Protos` namespace and is generated as a nested class.</span></span> <span data-ttu-id="0cdfe-149">gRPC は、`.proto` ファイルにサービスと同じ名前の静的クラスを作成し、その静的クラス内に `Base` サフィックスを持つ基底クラスを作成します。そのため、基本型の完全な識別子は `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`ます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-149">gRPC creates a static class with the same name as the service in the `.proto` file and a base class with the suffix `Base` inside that static class, so the full identifier for the base type is `TraderSys.Portfolios.Protos.Portfolios.PortfoliosBase`.</span></span>

```csharp
namespace TraderSys.Portfolios.Services
{
    public class PortfolioService : Protos.Portfolios.PortfoliosBase
    {
    }
}
```

<span data-ttu-id="0cdfe-150">基本クラスは、サービスを実装するためにオーバーライドできる `Get` および `GetAll` の `virtual` メソッドを宣言します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-150">The base class declares `virtual` methods for `Get` and `GetAll` that can be overridden to implement the service.</span></span> <span data-ttu-id="0cdfe-151">メソッドは、`abstract` ではなく `virtual` ので、実装していない場合は、通常C#のコードで `NotImplementedException` をスローするのと同じように、サービスは明示的な grpc `Unimplemented` 状態コードを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-151">The methods are `virtual` rather than `abstract` so that if you don't implement them, the service can return an explicit gRPC `Unimplemented` status code, much like you might throw a `NotImplementedException` in regular C# code.</span></span>

<span data-ttu-id="0cdfe-152">ASP.NET Core 内のすべての gRPC 単項サービスメソッドの署名が一貫しています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-152">The signature for all gRPC unary service methods in ASP.NET Core is consistent.</span></span> <span data-ttu-id="0cdfe-153">2つのパラメーターがあります。1つ目は `.proto` ファイルで宣言されたメッセージ型、2つ目は ASP.NET Core の `HttpContext` と同様に機能する `ServerCallContext` です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-153">There are two parameters: the first is the message type declared in the `.proto` file, and the second is a `ServerCallContext` that works similarly to the `HttpContext` from ASP.NET Core.</span></span> <span data-ttu-id="0cdfe-154">実際には、基になる `HttpContext`を取得するために使用できる `ServerCallContext` クラスに `GetHttpContext` という拡張メソッドがありますが、頻繁に使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-154">In fact, there's an extension method called `GetHttpContext` on the `ServerCallContext` class that you can use to get the underlying `HttpContext`, although you shouldn't need to use it often.</span></span> <span data-ttu-id="0cdfe-155">この章の後半の `ServerCallContext` と、認証について説明している章を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-155">We'll take a look at `ServerCallContext` later in this chapter, and also in the chapter that discusses authentication.</span></span>

<span data-ttu-id="0cdfe-156">メソッドの戻り値の型は `Task<T>`であり、`T` は応答メッセージの種類です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-156">The method's return type is a `Task<T>`, where `T` is the response message type.</span></span> <span data-ttu-id="0cdfe-157">すべての gRPC サービスメソッドは非同期です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-157">All gRPC service methods are asynchronous.</span></span>

## <a name="migrate-the-portfoliodata-library-to-net-core"></a><span data-ttu-id="0cdfe-158">PortfolioData ライブラリを .NET Core に移行する</span><span class="sxs-lookup"><span data-stu-id="0cdfe-158">Migrate the PortfolioData library to .NET Core</span></span>

<span data-ttu-id="0cdfe-159">この時点で、プロジェクトには、WCF ソリューションの `TraderSys.PortfolioData` クラスライブラリに含まれるポートフォリオリポジトリとモデルが必要です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-159">At this point, the project needs the Portfolio repository and models contained in the `TraderSys.PortfolioData` class library in the WCF solution.</span></span> <span data-ttu-id="0cdfe-160">新しいクラスライブラリを作成する最も簡単な方法は、Visual Studio の **[新しいプロジェクト]** ダイアログボックスでクラスライブラリ (.NET Standard) テンプレートを使用するか、コマンドラインで .NET Core CLI を使用して、`TraderSys.sln` ファイルが格納されているディレクトリから次のコマンドを実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-160">The easiest way to bring them across is to create a new class library by using either the Visual Studio **New project** dialog box with the Class Library (.NET Standard) template, or from the command line by using the .NET Core CLI, running these commands from the directory that contains the `TraderSys.sln` file:</span></span>

```dotnetcli
dotnet new classlib -o src/TraderSys.PortfolioData
dotnet sln add src/TraderSys.PortfolioData
```

<span data-ttu-id="0cdfe-161">ライブラリを作成してソリューションに追加したら、生成された `Class1.cs` ファイルを削除し、WCF ソリューションのライブラリのファイルを新しいクラスライブラリのフォルダーにコピーして、フォルダー構造を保持します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-161">After you've created the library and added it to the solution, delete the generated `Class1.cs` file and copy the files from the WCF solution's library into the new class library's folder, keeping the folder structure:</span></span>

```
Models
  Portfolio.cs
  PortfolioItem.cs
IPortfolioRepository.cs
PortfolioRepository.cs
```

<span data-ttu-id="0cdfe-162">SDK スタイルの .NET プロジェクトでは、任意の `.cs` ファイルが独自のディレクトリに自動的に含まれるため、プロジェクトに明示的に追加する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-162">SDK-style .NET projects automatically include any `.cs` files in or under their own directory, so you don't need to explicitly add them to the project.</span></span> <span data-ttu-id="0cdfe-163">残りの手順は、`DataContract` と `DataMember` 属性を `Portfolio` クラスと `PortfolioItem` クラスから削除することです。これにC#より、これらは単純な古いクラスになります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-163">The only step remaining is to remove the `DataContract` and `DataMember` attributes from the `Portfolio` and `PortfolioItem` classes so they're plain old C# classes:</span></span>

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

## <a name="use-aspnet-core-dependency-injection"></a><span data-ttu-id="0cdfe-164">ASP.NET Core 依存関係の挿入の使用</span><span class="sxs-lookup"><span data-stu-id="0cdfe-164">Use ASP.NET Core dependency injection</span></span>

<span data-ttu-id="0cdfe-165">これで、このライブラリへの参照を gRPC アプリケーションプロジェクトに追加し、gRPC サービス実装で依存関係の挿入を使用して `PortfolioRepository` クラスを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-165">Now you can add a reference to this library to the gRPC application project and consume the `PortfolioRepository` class by using dependency injection in the gRPC service implementation.</span></span> <span data-ttu-id="0cdfe-166">WCF アプリケーションでは、依存関係の注入は Autofac IoC コンテナーによって提供されていました。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-166">In the WCF application, dependency injection was provided by the Autofac IoC container.</span></span> <span data-ttu-id="0cdfe-167">ASP.NET Core には依存関係の注入が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-167">ASP.NET Core has dependency injection baked in.</span></span> <span data-ttu-id="0cdfe-168">`Startup` クラスの `ConfigureServices` メソッドにリポジトリを登録できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-168">You can register the repository in the `ConfigureServices` method in the `Startup` class:</span></span>

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

<span data-ttu-id="0cdfe-169">`IPortfolioRepository` の実装は、次のように `PortfolioService` クラスのコンストラクターパラメーターとして指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-169">The `IPortfolioRepository` implementation can now be specified as a constructor parameter in the `PortfolioService` class, as follows:</span></span>

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

## <a name="implement-the-grpc-service"></a><span data-ttu-id="0cdfe-170">GRPC サービスを実装する</span><span class="sxs-lookup"><span data-stu-id="0cdfe-170">Implement the gRPC service</span></span>

<span data-ttu-id="0cdfe-171">メッセージとサービスを `portfolios.proto` ファイルで宣言したので、gRPC によって生成された `Portfolios.PortfoliosBase` クラスを継承する `PortfolioService` クラスにサービスメソッドを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-171">Now that you've declared your messages and your service in the `portfolios.proto` file, you have to implement the service methods in the `PortfolioService` class that inherits from the gRPC-generated `Portfolios.PortfoliosBase` class.</span></span> <span data-ttu-id="0cdfe-172">メソッドは、基本クラスの `virtual` として宣言されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-172">The methods are declared as `virtual` in the base class.</span></span> <span data-ttu-id="0cdfe-173">オーバーライドしないと、既定で gRPC "未実装" 状態コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-173">If you don't override them, they'll return a gRPC "Not Implemented" status code by default.</span></span>

<span data-ttu-id="0cdfe-174">まず、`Get` メソッドを実装します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-174">Start by implementing the `Get` method.</span></span> <span data-ttu-id="0cdfe-175">既定のオーバーライドは、次の例のようになります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-175">The default override looks like this example:</span></span>

```csharp
public override Task<GetResponse> Get(GetRequest request, ServerCallContext context)
{
    return base.Get(request, context);
}
```

<span data-ttu-id="0cdfe-176">最初の問題は、`request.TraderId` が文字列であり、サービスに `Guid`が必要であることです。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-176">The first problem is that `request.TraderId` is a string, and the service requires a `Guid`.</span></span> <span data-ttu-id="0cdfe-177">文字列に対して予期される書式が `UUID`場合でも、呼び出し元が無効な値を送信し、適切に応答する可能性をコードで処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-177">Even though the expected format for the string is `UUID`, the code has to deal with the possibility that a caller has sent an invalid value and respond appropriately.</span></span> <span data-ttu-id="0cdfe-178">サービスは、`RpcException` をスローし、標準の `InvalidArgument` ステータスコードを使用して問題を表すことにより、エラーで応答できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-178">The service can respond with errors by throwing an `RpcException` and use the standard `InvalidArgument` status code to express the problem:</span></span>

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

<span data-ttu-id="0cdfe-179">`traderId`に適切な `Guid` 値が得られたら、リポジトリを使用してポートフォリオを取得し、それをクライアントに返すことができます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-179">After there's a proper `Guid` value for `traderId`, you can use the repository to retrieve the Portfolio and return it to the client:</span></span>

```csharp
    var response = new GetResponse
    {
        Portfolio = await _repository.GetAsync(request.TraderId, request.PortfolioId)
    };
```

### <a name="map-internal-models-to-grpc-messages"></a><span data-ttu-id="0cdfe-180">内部モデルを gRPC メッセージにマップする</span><span class="sxs-lookup"><span data-stu-id="0cdfe-180">Map internal models to gRPC messages</span></span>

<span data-ttu-id="0cdfe-181">リポジトリが独自の POCO モデル `Portfolio`を返すため、前のコードは実際には機能しませんが、gRPC は独自の Protobuf メッセージ `Portfolio`を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-181">The previous code doesn't actually work because the repository is returning its own POCO model `Portfolio`, but gRPC needs its own Protobuf message `Portfolio`.</span></span> <span data-ttu-id="0cdfe-182">Entity Framework の種類をデータ転送の種類にマップする場合は、2つの間の変換を提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-182">As when you map Entity Framework types to data transfer types, the best solution is to provide a conversion between the two.</span></span> <span data-ttu-id="0cdfe-183">この変換のためのコードを配置するための適切な場所は、Protobuf によって生成されるクラスにあります。これは、拡張できるように `partial` クラスとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-183">A good place to put the code for this conversion is in the Protobuf-generated class, which is declared as a `partial` class so it can be extended:</span></span>

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
> <span data-ttu-id="0cdfe-184">[Automapper](https://automapper.org/)のようなライブラリを使用して、内部モデルクラスから Protobuf 型への変換を処理できます。ただし、`string`/`Guid` や `decimal`/`double` やリストマッピングなどの下位レベルの型変換を構成する場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-184">You could use a library like [AutoMapper](https://automapper.org/) to handle this conversion from internal model classes to Protobuf types, as long as you configure the lower-level type conversions like `string`/`Guid` or `decimal`/`double` and the list mapping.</span></span>

<span data-ttu-id="0cdfe-185">これで、変換コードを配置したので、`Get` メソッドの実装を完了できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-185">Now that you have the conversion code in place, you can complete the `Get` method implementation:</span></span>

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

<span data-ttu-id="0cdfe-186">`GetAll` メソッドの実装も似ています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-186">The implementation of the `GetAll` method is similar.</span></span> <span data-ttu-id="0cdfe-187">Protobuf メッセージの `repeated` フィールドは `RepeatedField<T>`型の `readonly` プロパティとして生成されるため、次の例のように、`AddRange` メソッドを使用して項目を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-187">Note that the `repeated` fields on Protobuf messages are generated as `readonly` properties of type `RepeatedField<T>`, so you have to add items to them by using the `AddRange` method, like in this example:</span></span>

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

<span data-ttu-id="0cdfe-188">WCF 要求-応答サービスを gRPC に正常に移行したところで、`.proto` ファイルからクライアントを作成する方法を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-188">Having successfully migrated the WCF request-reply service to gRPC, let's look at creating a client for it from the `.proto` file.</span></span>

## <a name="generate-client-code"></a><span data-ttu-id="0cdfe-189">クライアントコードの生成</span><span class="sxs-lookup"><span data-stu-id="0cdfe-189">Generate client code</span></span>

<span data-ttu-id="0cdfe-190">クライアントを格納するために、同じソリューションに .NET Standard クラスライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-190">Create a .NET Standard class library in the same solution to contain the client.</span></span> <span data-ttu-id="0cdfe-191">これは、主にクライアントコードを作成する例ですが、NuGet を使用してこのようなライブラリをパッケージ化し、他の .NET チームが使用できるように内部リポジトリに配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-191">This is primarily an example of creating client code, but you could package such a library by using NuGet and distribute it on an internal repository for other .NET teams to consume.</span></span> <span data-ttu-id="0cdfe-192">`TraderSys.Portfolios.Client` という名前の新しい .NET Standard クラスライブラリをソリューションに追加し、`Class1.cs` ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-192">Go ahead and add a new .NET Standard class library called `TraderSys.Portfolios.Client` to the solution and delete the `Class1.cs` file.</span></span>

> [!CAUTION]
> <span data-ttu-id="0cdfe-193">[Grpc .Net クライアント](https://www.nuget.org/packages/Grpc.Net.Client)の NuGet パッケージには、.net Core 3.0 (または .NET Standard 2.1 に準拠した別のランタイム) が必要です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-193">The [Grpc.Net.Client](https://www.nuget.org/packages/Grpc.Net.Client) NuGet package requires .NET Core 3.0 (or another .NET Standard 2.1-compliant runtime).</span></span> <span data-ttu-id="0cdfe-194">以前のバージョンの .NET Framework と .NET Core は、 [Grpc. Core](https://www.nuget.org/packages/Grpc.Core) NuGet パッケージによってサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-194">Earlier versions of .NET Framework and .NET Core are supported by the [Grpc.Core](https://www.nuget.org/packages/Grpc.Core) NuGet package.</span></span>

<span data-ttu-id="0cdfe-195">Visual Studio 2019 では、以前のバージョンの Visual Studio で WCF プロジェクトにサービス参照を追加するのと同様の方法で、gRPC サービスへの参照を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-195">In Visual Studio 2019, you can add references to gRPC services in a way that's similar to how you'd add service references to WCF projects in earlier versions of Visual Studio.</span></span> <span data-ttu-id="0cdfe-196">サービス参照と接続済みサービスはすべて同じ UI で管理されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-196">Service references and connected services are all managed under the same UI now.</span></span> <span data-ttu-id="0cdfe-197">UI にアクセスするには、ソリューションエクスプローラーで `TraderSys.Portfolios.Client` プロジェクトの **[依存関係]** ノードを右クリックし、 **[接続済みサービスの追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-197">You can access the UI by right-clicking the **Dependencies** node in the `TraderSys.Portfolios.Client` project in Solution Explorer and selecting **Add Connected Service**.</span></span> <span data-ttu-id="0cdfe-198">表示されたツールウィンドウで、 **[サービス参照]** セクションを選択し、 **[新しい grpc サービス参照の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-198">In the tool window that appears, select the **Service References** section and then select **Add new gRPC service reference**:</span></span>

![Visual Studio 2019 の接続済みサービス UI](media/migrate-request-reply/add-connected-service.png)

<span data-ttu-id="0cdfe-200">`TraderSys.Portfolios` プロジェクトの `portfolios.proto` ファイルを参照し、 **[生成するクラスの種類を選択]** の下の **[クライアント]** のままにして、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-200">Browse to the `portfolios.proto` file in the `TraderSys.Portfolios` project, leave **Client** under **Select the type of class to be generated**, and then select **OK**:</span></span>

![Visual Studio 2019 の [新しい gRPC サービス参照の追加] ダイアログボックス](media/migrate-request-reply/add-new-grpc-service-reference.png)

> [!TIP]
> <span data-ttu-id="0cdfe-202">このダイアログボックスには、[URL] フィールドも表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-202">Notice that this dialog box also provides a URL field.</span></span> <span data-ttu-id="0cdfe-203">組織が `.proto` ファイルの web アクセス可能なディレクトリを保持している場合は、この URL アドレスを設定するだけでクライアントを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-203">If your organization maintains a web-accessible directory of `.proto` files, you can create clients just by setting this URL address.</span></span>

<span data-ttu-id="0cdfe-204">Visual Studio の **[接続済みサービスの追加]** 機能を使用すると、`portfolios.proto` ファイルはコピーされるのではなく、リンクされた*ファイル*としてクラスライブラリプロジェクトに追加されるため、サービスプロジェクトのファイルに対する変更は、クライアントプロジェクトで自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-204">When you use the Visual Studio **Add Connected Service** feature, the `portfolios.proto` file is added to the class library project as a *linked file* rather than copied, so changes to the file in the service project will automatically be applied in the client project.</span></span> <span data-ttu-id="0cdfe-205">`csproj` ファイルの `<Protobuf>` 要素は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-205">The `<Protobuf>` element in the `csproj` file looks like this:</span></span>

```xml
<Protobuf Include="..\TraderSys.Portfolios\Protos\portfolios.proto" GrpcServices="Client">
  <Link>Protos\portfolios.proto</Link>
</Protobuf>
```

> [!TIP]
> <span data-ttu-id="0cdfe-206">Visual Studio を使用していない場合、またはコマンドラインから作業する場合は、`dotnet-grpc` グローバルツールを使用して、.NET gRPC プロジェクトの Protobuf 参照を管理できます。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-206">If you're not using Visual Studio or prefer to work from the command line, you can use the `dotnet-grpc` global tool to manage Protobuf references in a .NET gRPC project.</span></span> <span data-ttu-id="0cdfe-207">詳細については、 [`dotnet-grpc` のドキュメント](/aspnet/core/grpc/dotnet-grpc)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-207">For more information, see the [`dotnet-grpc` documentation](/aspnet/core/grpc/dotnet-grpc).</span></span>

### <a name="use-the-portfolios-service-from-a-client-application"></a><span data-ttu-id="0cdfe-208">クライアントアプリケーションからのポートフォリオサービスの使用</span><span class="sxs-lookup"><span data-stu-id="0cdfe-208">Use the Portfolios service from a client application</span></span>

<span data-ttu-id="0cdfe-209">次のコードは、生成されたクライアントをコンソールアプリケーションで使用する方法の簡単な例です。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-209">The following code is a brief example of how to use the generated client in a console application.</span></span> <span data-ttu-id="0cdfe-210">GRPC クライアントコードのより詳細な探索については、この章の最後にあります。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-210">A more detailed exploration of the gRPC client code is at the end of this chapter.</span></span>

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

<span data-ttu-id="0cdfe-211">これで、基本的な WCF アプリケーションを ASP.NET Core gRPC サービスに移行し、.NET アプリケーションからサービスを使用するクライアントを作成しました。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-211">You've now migrated a basic WCF application to an ASP.NET Core gRPC service and created a client to consume the service from a .NET application.</span></span> <span data-ttu-id="0cdfe-212">次のセクションでは、より複雑な双方向サービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0cdfe-212">The next section will cover the more involved duplex services.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="0cdfe-213">[前へ](create-project.md)
>[次へ](migrate-duplex-services.md)</span><span class="sxs-lookup"><span data-stu-id="0cdfe-213">[Previous](create-project.md)
[Next](migrate-duplex-services.md)</span></span>
