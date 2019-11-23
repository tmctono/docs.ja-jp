---
title: Wcf 開発者向けの gRPC-gRPC への WCF 双方向サービスの移行
description: さまざまな形式の WCF 双方向サービスを gRPC streaming services に移行する方法について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: e2248df20e5c2d8f96055d42ba684749251154bd
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971879"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="f3c64-103">WCF 双方向サービスを gRPC に移行する</span><span class="sxs-lookup"><span data-stu-id="f3c64-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="f3c64-104">基本的な概念を説明したので、このセクションではより複雑な*ストリーミング*grpc サービスについて見ていきます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-104">Now that the basic concepts are in place, this section will look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="f3c64-105">Windows Communication Foundation (WCF) で双方向サービスを使用するには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f3c64-106">一部のサービスはクライアントによって開始され、サーバーからデータをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="f3c64-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="f3c64-107">その他の全二重サービスには、WCF ドキュメントの従来の "電卓" の例のような、より継続的な双方向通信が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-107">Other full-duplex services might involve more ongoing two-way communication like the classic "Calculator" example from the WCF documentation.</span></span> <span data-ttu-id="f3c64-108">この章では、2つの WCF "Stock ティッカー" 実装を実行し、gRPC に移行します。1つはサーバーストリーミング RPC を使用し、もう1つは双方向ストリーミング RPC を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-108">This chapter will take two possible WCF "Stock Ticker" implementations and migrate them to gRPC: one using a server streaming RPC, and the other one using a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="f3c64-109">サーバーストリーミング RPC</span><span class="sxs-lookup"><span data-stu-id="f3c64-109">Server streaming RPC</span></span>

<span data-ttu-id="f3c64-110">*SimpleStockPriceTicker*の[サンプル SIMPLESTOCKTICKER WCF ソリューション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker)では、クライアントが株価記号の一覧を使用して接続を開始し、サーバーが*コールバックインターフェイス*を使用して更新プログラムが使用可能になったときに送信する双方向サービスがあります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, there's a duplex service where the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="f3c64-111">クライアントは、サーバーからの呼び出しに応答するために、そのインターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="f3c64-112">WCF ソリューション</span><span class="sxs-lookup"><span data-stu-id="f3c64-112">The WCF solution</span></span>

<span data-ttu-id="f3c64-113">WCF ソリューションは、.NET Framework 4.x コンソールアプリケーションで自己ホスト型 NetTCP サーバーとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-113">The WCF solution is implemented as a self-hosted NetTCP server in a .NET Framework 4.x console application.</span></span>

#### <a name="the-servicecontract"></a><span data-ttu-id="f3c64-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="f3c64-114">The ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="f3c64-115">サービスには、戻り値の型のない1つのメソッドがあります。これは、リアルタイムでクライアントにデータを送信するためにコールバックインターフェイス `ISimpleStockTickerCallback` を使用するためです。</span><span class="sxs-lookup"><span data-stu-id="f3c64-115">The service has a single method with no return type, because it will be using the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="f3c64-116">コールバックインターフェイス</span><span class="sxs-lookup"><span data-stu-id="f3c64-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="f3c64-117">これらのインターフェイスの実装は、フェイク外部依存関係と共に、テストデータを提供するために、ソリューションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3c64-117">The implementations of these interfaces can be found in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="f3c64-118">gRPC ストリーミング</span><span class="sxs-lookup"><span data-stu-id="f3c64-118">gRPC streaming</span></span>

<span data-ttu-id="f3c64-119">GRPC はリアルタイムデータを処理する方法が異なります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-119">The gRPC way of handling real-time data is different.</span></span> <span data-ttu-id="f3c64-120">クライアントからサーバーへの呼び出しでは、永続ストリームを作成できます。このストリームは、非同期的に受信されるメッセージを監視できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-120">A call from client to server can create a persistent stream, which can be monitored for messages arriving asynchronously.</span></span> <span data-ttu-id="f3c64-121">違いにかかわらず、ストリームは、このデータを処理するためのより直観的な方法であり、LINQ、リアクティブストリーム、関数型プログラミングなどに重点を置いた最新のプログラミングにおいてさらに関連性があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming with the emphasis on LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="f3c64-122">サービス定義には2つのメッセージが必要です。1つは要求用で、もう1つはストリーム用です。</span><span class="sxs-lookup"><span data-stu-id="f3c64-122">The service definition needs two messages: one for the request, and one for the stream.</span></span> <span data-ttu-id="f3c64-123">サービスは、`return` 宣言で `stream` キーワードを使用して、`StockTickerUpdate` メッセージのストリームを返します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-123">The service returns a stream of the `StockTickerUpdate` message using the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="f3c64-124">更新に `Timestamp` を追加して、価格が変更された正確な時間を示すことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3c64-124">It's recommended that you add a `Timestamp` to the update to show the exact time the price changed.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="f3c64-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="f3c64-125">simple_stock_ticker.proto</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-the-simplestockticker"></a><span data-ttu-id="f3c64-126">SimpleStockTicker を実装する</span><span class="sxs-lookup"><span data-stu-id="f3c64-126">Implement the SimpleStockTicker</span></span>

<span data-ttu-id="f3c64-127">`TraderSys.StockMarket` クラスライブラリからターゲットソリューションの新しい .NET Standard クラスライブラリに3つのクラスをコピーして、WCF プロジェクトの偽の `StockPriceSubscriber` を再利用します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="f3c64-128">ベストプラクティスに従うには、`Factory` の種類を追加してインスタンスを作成し、`IStockPriceSubscriberFactory` を ASP.NET Core の依存関係挿入サービスに登録します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-128">To better follow best practices, add a `Factory` type to create instances of it and register the `IStockPriceSubscriberFactory` with ASP.NET Core's dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="f3c64-129">ファクトリ実装</span><span class="sxs-lookup"><span data-stu-id="f3c64-129">The factory implementation</span></span>

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="registering-the-factory"></a><span data-ttu-id="f3c64-130">ファクトリを登録しています</span><span class="sxs-lookup"><span data-stu-id="f3c64-130">Registering the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="f3c64-131">これで、このクラスを使用して gRPC StockTicker サービスを実装できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f3c64-131">Now, this class can be used to implement the gRPC StockTicker service.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="f3c64-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="f3c64-132">StockTickerService.cs</span></span>

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors due to broken connection etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

<span data-ttu-id="f3c64-133">ご覧のように、`.proto` ファイルの宣言では、メソッドによって `StockTickerUpdate` メッセージのストリームが "返される" ことが示されますが、実際にはバニラ `Task`が返されます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-133">As you can see, although the declaration in the `.proto` file says the method "returns" a stream of `StockTickerUpdate` messages, in fact it returns a vanilla `Task`.</span></span> <span data-ttu-id="f3c64-134">ストリームの作成ジョブは、生成されたコードと、`IServerStreamWriter<StockTickerUpdate>` 応答ストリームを提供する gRPC ランタイムライブラリによって処理され、すぐに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="f3c64-135">接続が開いている間にサービスクラスのインスタンスが保持されている WCF 双方向サービスとは異なり、gRPC サービスは返されたタスクを使用してサービスを維持します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned Task to keep the service alive.</span></span> <span data-ttu-id="f3c64-136">接続が閉じられるまで、タスクは完了しません。</span><span class="sxs-lookup"><span data-stu-id="f3c64-136">The Task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="f3c64-137">サービスは、`ServerCallContext`の `CancellationToken` を使用して、クライアントが接続を閉じたことを通知できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="f3c64-138">単純な静的メソッド `AwaitCancellation`は、トークンが取り消されたときに完了するタスクを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-138">A simple static method, `AwaitCancellation`, is used to create a Task that completes when the token is canceled.</span></span>

<span data-ttu-id="f3c64-139">`Subscribe` メソッドで、`StockPriceSubscriber` を取得し、応答ストリームに書き込むイベントハンドラーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="f3c64-140">次に、接続が閉じられるのを待ってから、`subscriber` を直ちに破棄して、閉じたストリームにデータを書き込もうとしないようにします。</span><span class="sxs-lookup"><span data-stu-id="f3c64-140">Then wait for the connection to be closed, before immediately disposing the `subscriber` to prevent it trying to write data to the closed stream.</span></span>

<span data-ttu-id="f3c64-141">`WriteUpdateAsync` メソッドには、ストリームにメッセージを書き込むときに発生する可能性のあるエラーを処理するための `try`/`catch` ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when writing a message to the stream.</span></span> <span data-ttu-id="f3c64-142">これは、意図的に、またはどこかの障害が原因で、任意のミリ秒で中断される可能性があるネットワーク経由の永続的な接続での重要な考慮事項です。</span><span class="sxs-lookup"><span data-stu-id="f3c64-142">This is an important consideration in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="using-the-stocktickerservice-from-a-client-application"></a><span data-ttu-id="f3c64-143">クライアントアプリケーションからの Stockkerservice の使用</span><span class="sxs-lookup"><span data-stu-id="f3c64-143">Using the StockTickerService from a client application</span></span>

<span data-ttu-id="f3c64-144">前のセクションと同じ手順に従って、`.proto` ファイルから共有可能なクライアントクラスライブラリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="f3c64-145">このサンプルには、クライアントの使用方法を示す .NET Core 3.0 コンソールアプリケーションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="f3c64-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="f3c64-146">Program.cs の例</span><span class="sxs-lookup"><span data-stu-id="f3c64-146">Example Program.cs</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

<span data-ttu-id="f3c64-147">この場合、生成されたクライアントの `Subscribe` メソッドは非同期ではありません。</span><span class="sxs-lookup"><span data-stu-id="f3c64-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="f3c64-148">このストリームは、`MoveNext` メソッドが非同期であり、初めて呼び出されたときに、接続が有効になるまで完了しないため、すぐに作成および使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-148">The stream is created and usable right away, because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="f3c64-149">ストリームは、非同期 `DisplayAsync` メソッドに渡されます。その後、アプリケーションは、ユーザーがキーを押すまで待機し、`DisplayAsync` メソッドをキャンセルして、タスクが完了するのを待ってから終了します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-149">The stream is passed to an async `DisplayAsync` method; the application then waits for the user to press a key, then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="f3c64-150">このコードでは、新しいC# 8 "using 宣言" 構文を使用して、`Main` メソッドの終了時にストリームとチャネルを破棄します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-150">This code is using the new C# 8 "using declaration" syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="f3c64-151">これは小さな変更ですが、インデントや空の線を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-151">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="f3c64-152">ストリームを使用する</span><span class="sxs-lookup"><span data-stu-id="f3c64-152">Consume the stream</span></span>

<span data-ttu-id="f3c64-153">サーバーがクライアントでメソッドを直接呼び出すことができるようにするために使用される、WCF のコールバックインターフェイス。</span><span class="sxs-lookup"><span data-stu-id="f3c64-153">WCF used callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="f3c64-154">gRPC ストリームの動作は異なります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-154">gRPC streams work differently.</span></span> <span data-ttu-id="f3c64-155">クライアントは、返されたストリームに対して反復処理を行い、`IEnumerable`を返すローカルメソッドから返された場合と同様にメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-155">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="f3c64-156">`IAsyncStreamReader<T>` 型は、`IEnumerator<T>`のように機能します。これには、より多くのデータが存在する限り true を返す `MoveNext` メソッドと、最新の値を返す `Current` プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-156">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`: there's a `MoveNext` method that will return true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="f3c64-157">唯一の違いは、`MoveNext` メソッドは `bool`だけではなく `Task<bool>` を返すという点です。</span><span class="sxs-lookup"><span data-stu-id="f3c64-157">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="f3c64-158">`ReadAllAsync` 拡張メソッドは、新しい `await foreach` 構文で使用C#できる標準 8 `IAsyncEnumerable` でストリームをラップします。</span><span class="sxs-lookup"><span data-stu-id="f3c64-158">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> <span data-ttu-id="f3c64-159">この章の最後にある「[クライアントライブラリ](client-libraries.md#iobservable)」のセクションでは、事後対応型のプログラミングパターンを使用する開発者のために、拡張メソッドとクラスを追加して、`IObservable<T>` に `IAsyncStreamReader<T>` ラップする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-159">The section on [client libraries](client-libraries.md#iobservable) at the end of this chapter looks at how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>` for developers using reactive programming patterns.</span></span>

<span data-ttu-id="f3c64-160">ここでも、ネットワークエラーが発生する可能性があるので例外をキャッチするように注意してください。また、コードが <xref:System.Threading.CancellationToken> を使用してループを中断しているためにスローされる <xref:System.OperationCanceledException> があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-160">Again, be careful to catch exceptions here because of the possibility of network failure, as well as the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="f3c64-161">`RpcException` 型には、`StatusCode`を含む gRPC ランタイムエラーに関する有用な情報が多数含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3c64-161">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="f3c64-162">詳細については、[第4章の「*エラー処理*](error-handling.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c64-162">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="f3c64-163">双方向ストリーミング</span><span class="sxs-lookup"><span data-stu-id="f3c64-163">Bidirectional streaming</span></span>

<span data-ttu-id="f3c64-164">WCF の全二重サービスを使用すると、非同期のリアルタイムメッセージングを双方向で実現できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-164">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="f3c64-165">サーバーストリーミングの例では、クライアントが要求を開始し、更新のストリームを受信します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-165">In the server streaming example, the client starts a request, then receives a stream of updates.</span></span> <span data-ttu-id="f3c64-166">適切なバージョンのサービスを使用すると、クライアントは、停止して新しいサブスクリプションを作成することなく、一覧に対して株式の追加や削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-166">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="f3c64-167">この機能は、 [Fullstockticker サンプルソリューション](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker)に実装されています。</span><span class="sxs-lookup"><span data-stu-id="f3c64-167">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="f3c64-168">`IFullStockTickerService` インターフェイスには、次の3つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-168">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="f3c64-169">`Subscribe` 接続を開始します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-169">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="f3c64-170">`AddSymbol` は、ウォッチするストックシンボルを追加します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-170">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="f3c64-171">`RemoveSymbol` は、マークされた一覧からシンボルを削除します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-171">`RemoveSymbol` removes a symbol from the watched list.</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

<span data-ttu-id="f3c64-172">コールバックインターフェイスは同じままです。</span><span class="sxs-lookup"><span data-stu-id="f3c64-172">The callback interface remains the same.</span></span>

<span data-ttu-id="f3c64-173">このパターンを gRPC に実装するのは簡単ではありません。これは、1つはクライアントからサーバー、もう1つはサーバーからクライアントの2つのデータストリームが渡されるためです。</span><span class="sxs-lookup"><span data-stu-id="f3c64-173">Implementing this pattern in gRPC is less straightforward, because there are now two streams of data with messages being passed: one from client to server, and another from server to client.</span></span> <span data-ttu-id="f3c64-174">複数のメソッドを使用して追加と削除の操作を実装することはできませんが、1つのストリームに複数の種類のメッセージを渡すことはできます。これについては、[第3章](protobuf-any-oneof.md)で説明した `Any` 型または `oneof` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-174">It isn't possible to use multiple methods to implement the Add and Remove operation, but more than one type of message can be passed on a single stream, using either the `Any` type or `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="f3c64-175">許容される特定の型のセットがある場合は、`oneof` の方が適しています。</span><span class="sxs-lookup"><span data-stu-id="f3c64-175">For a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="f3c64-176">`AddSymbolRequest` または `RemoveSymbolRequest`のいずれかを保持できる `ActionMessage` を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-176">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`.</span></span>

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

<span data-ttu-id="f3c64-177">`ActionMessage` メッセージのストリームを取得する双方向ストリーミングサービスを宣言します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-177">Declare a bi-directional streaming service that takes a stream of `ActionMessage` messages.</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="f3c64-178">このサービスの実装は、前の例と似ていますが、`Subscribe` メソッドの最初のパラメーターが `IAsyncStreamReader<ActionMessage>`になりました。これを使用して、`Add` と `Remove` の要求を処理できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-178">The implementation for this service is similar to the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests.</span></span>

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors due to broken connection etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

<span data-ttu-id="f3c64-179">GRPC が生成した `ActionMessage` クラスは、`Add` プロパティと `Remove` プロパティのどちらか1つだけを設定でき、`null` どの種類のメッセージが使用されているかを見つけるための有効な方法ですが、より良い方法があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-179">The `ActionMessage` class that gRPC has generated for us guarantees that only one of the `Add` and `Remove` properties can be set, and finding which one isn't `null` is a valid way of finding which type of message is used, but there's a better way.</span></span> <span data-ttu-id="f3c64-180">また、コード生成によって `ActionMessage` クラスに `enum ActionOneOfCase` が作成されました。これは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-180">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="f3c64-181">`ActionMessage` オブジェクトのプロパティ `ActionCase` を `switch` ステートメントと共に使用して、どのフィールドが設定されているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-181">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set.</span></span>

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> <span data-ttu-id="f3c64-182">`switch` ステートメントには、不明な `ActionOneOfCase` 値が検出された場合に警告をログに記録する `default` ケースがあります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-182">The `switch` statement has a `default` case that logs a warning if an unknown `ActionOneOfCase` value is encountered.</span></span> <span data-ttu-id="f3c64-183">これは、クライアントがより新しいバージョンの `.proto` ファイルを使用していて、さらにアクションが追加されていることを示す場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="f3c64-183">This could be useful in indicating that a client is using a later version of the `.proto` file which has added more actions.</span></span> <span data-ttu-id="f3c64-184">これは、既知のフィールドで `null` をテストするよりも `switch` を使用する方がよい理由の1つです。</span><span class="sxs-lookup"><span data-stu-id="f3c64-184">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="f3c64-185">クライアントアプリケーションからの FullStockTickerService の使用</span><span class="sxs-lookup"><span data-stu-id="f3c64-185">Use the FullStockTickerService from a client application</span></span>

<span data-ttu-id="f3c64-186">このより複雑なクライアントの使用方法を示すための単純な .NET Core 3.0 WPF アプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-186">There's a simple .NET Core 3.0 WPF application to demonstrate use of this more complex client.</span></span> <span data-ttu-id="f3c64-187">完全なアプリケーションについては、 [GitHub を](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker)参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3c64-187">The full application can be found [on GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="f3c64-188">クライアントは `MainWindowViewModel` クラスで使用されます。このクラスは、依存関係の挿入から `FullStockTicker.FullStockTickerClient` 型のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-188">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection.</span></span>

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

<span data-ttu-id="f3c64-189">`client.Subscribe()` メソッドによって返されるオブジェクトは、gRPC ライブラリ型 `AsyncDuplexStreamingCall<TRequest, TResponse>`のインスタンスになりました。これにより、サーバーに要求を送信するための `RequestStream` と、応答を処理するための `ResponseStream` が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-189">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server, and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="f3c64-190">要求ストリームは、いくつかの WPF `ICommand` メソッドから、シンボルを追加および削除するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-190">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="f3c64-191">各操作について、`ActionMessage` オブジェクトの関連フィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="f3c64-191">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> <span data-ttu-id="f3c64-192">メッセージに `oneof` フィールドの値を設定すると、以前に設定されていたすべてのフィールドが自動的にクリアされます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-192">Setting a `oneof` field's value on a message automatically clears any fields that have been previously set.</span></span>

<span data-ttu-id="f3c64-193">応答のストリームは `async` メソッドで処理され、返された `Task` はウィンドウが閉じられたときに破棄されたままになります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-193">The stream of responses is handled in an `async` method, and the `Task` it returns is held to be disposed when the window is closed.</span></span>

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-clean-up"></a><span data-ttu-id="f3c64-194">クライアントのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="f3c64-194">Client clean-up</span></span>

<span data-ttu-id="f3c64-195">ウィンドウが閉じられ、`MainWindowViewModel` が破棄された場合 (`MainWindow`の `Closed` イベントから)、`AsyncDuplexStreamingCall` オブジェクトを適切に破棄することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3c64-195">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), it's recommended that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="f3c64-196">特に、サーバー上のストリームを適切に閉じるには、`RequestStream` の `CompleteAsync` メソッドを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3c64-196">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="f3c64-197">次の例は、サンプルビューモデルの `DisposeAsync` メソッドを示しています。</span><span class="sxs-lookup"><span data-stu-id="f3c64-197">The following example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

<span data-ttu-id="f3c64-198">要求ストリームを閉じると、サーバーは自身のリソースを適切なタイミングで破棄できます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-198">Closing request streams enables the server to dispose of its own resources in a timely manner.</span></span> <span data-ttu-id="f3c64-199">これにより、サービスの効率とスケーラビリティが向上し、例外が回避されます。</span><span class="sxs-lookup"><span data-stu-id="f3c64-199">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f3c64-200">[前へ](migrate-request-reply.md)
>[次へ](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="f3c64-200">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
