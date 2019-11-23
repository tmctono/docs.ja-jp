---
title: WCF 開発者向けの RPC-gRPC の種類
description: WCF でサポートされているリモートプロシージャコールの種類と gRPC で対応するリモートプロシージャコールのレビュー
ms.date: 09/02/2019
ms.openlocfilehash: 64375236da17c0aedbafe1cb441e72a144203358
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967269"
---
# <a name="types-of-rpc"></a><span data-ttu-id="5afc3-103">RPC の種類</span><span class="sxs-lookup"><span data-stu-id="5afc3-103">Types of RPC</span></span>

<span data-ttu-id="5afc3-104">Windows Communication Foundation (WCF) 開発者は、次の種類のリモートプロシージャコール (RPC) を扱うために使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="5afc3-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of Remote Procedure Call (RPC):</span></span>

- <span data-ttu-id="5afc3-105">要求/応答</span><span class="sxs-lookup"><span data-stu-id="5afc3-105">Request/Reply</span></span>
- <span data-ttu-id="5afc3-106">通信</span><span class="sxs-lookup"><span data-stu-id="5afc3-106">Duplex:</span></span>
  - <span data-ttu-id="5afc3-107">セッションを含む一方向の二重</span><span class="sxs-lookup"><span data-stu-id="5afc3-107">One-way duplex with session</span></span>
  - <span data-ttu-id="5afc3-108">セッションを使用した全二重</span><span class="sxs-lookup"><span data-stu-id="5afc3-108">Full duplex with session</span></span>
- <span data-ttu-id="5afc3-109">一方向</span><span class="sxs-lookup"><span data-stu-id="5afc3-109">One-way</span></span>

<span data-ttu-id="5afc3-110">これらの RPC の種類は、既存の gRPC の概念に自然にマップすることができます。この章では、これらの各領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts and this chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="5afc3-111">同様の例については、 [5 章](migrate-wcf-to-grpc.md)でさらに詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-111">Similar examples will be explored in much greater depth in [Chapter 5](migrate-wcf-to-grpc.md).</span></span>

| <span data-ttu-id="5afc3-112">WCF</span><span class="sxs-lookup"><span data-stu-id="5afc3-112">WCF</span></span> | <span data-ttu-id="5afc3-113">gRPC</span><span class="sxs-lookup"><span data-stu-id="5afc3-113">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="5afc3-114">通常の要求/応答</span><span class="sxs-lookup"><span data-stu-id="5afc3-114">Regular request/reply</span></span> | <span data-ttu-id="5afc3-115">単項</span><span class="sxs-lookup"><span data-stu-id="5afc3-115">Unary</span></span> |
| <span data-ttu-id="5afc3-116">クライアントコールバックインターフェイスを使用したセッションを使用した双方向サービス</span><span class="sxs-lookup"><span data-stu-id="5afc3-116">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="5afc3-117">サーバーストリーミング</span><span class="sxs-lookup"><span data-stu-id="5afc3-117">Server streaming</span></span> |
| <span data-ttu-id="5afc3-118">セッションを使用した全二重サービス</span><span class="sxs-lookup"><span data-stu-id="5afc3-118">Full duplex service with session</span></span> | <span data-ttu-id="5afc3-119">双方向ストリーミング</span><span class="sxs-lookup"><span data-stu-id="5afc3-119">Bidirectional streaming</span></span> |
| <span data-ttu-id="5afc3-120">一方向の操作</span><span class="sxs-lookup"><span data-stu-id="5afc3-120">One-way operations</span></span> | <span data-ttu-id="5afc3-121">クライアントストリーミング</span><span class="sxs-lookup"><span data-stu-id="5afc3-121">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="5afc3-122">要求/応答</span><span class="sxs-lookup"><span data-stu-id="5afc3-122">Request/reply</span></span>

<span data-ttu-id="5afc3-123">少量のデータを取得して返す単純な要求/応答メソッドの場合は、最も単純な gRPC パターンである単項 RPC を使用します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-123">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

<span data-ttu-id="5afc3-124">ご覧のように、gRPC の単項 RPC サービスメソッドを実装することは、WCF 操作の実装とよく似ています。ただし、gRPC では、インターフェイスを実装する代わりに基底クラスのメソッドをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="5afc3-124">As you can see, implementing a gRPC unary RPC service method is very similar to implementing a WCF operation, except that with gRPC you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="5afc3-125">サーバーでは、gRPC の基本メソッドは常に <xref:System.Threading.Tasks.Task%601>を返しますが、クライアントはサービスを呼び出すための非同期メソッドとブロッキングメソッドの両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-125">Note that on the server, gRPC base methods always return a <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="5afc3-126">WCF 双方向、クライアントへの一方向</span><span class="sxs-lookup"><span data-stu-id="5afc3-126">WCF duplex, one-way to client</span></span>

<span data-ttu-id="5afc3-127">WCF アプリケーション (特定のバインドを使用) では、クライアントとサーバーの間に永続的な接続を作成できます。また、<xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> プロパティで指定された*コールバックインターフェイス*を使用して、接続が閉じられるまで、サーバーはクライアントにデータを非同期に送信できます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-127">WCF applications (with certain bindings) can create a persistent connection between client and server, and the server can asynchronously send data to the client until the connection is closed, using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="5afc3-128">gRPC サービスは、メッセージストリームと同様の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-128">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="5afc3-129">実装という点で、ストリームは WCF 双方向サービスに*厳密*にはマップされませんが、同じ結果が得られる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5afc3-129">Streams don't map *exactly* to WCF duplex services in terms of implementation, but the same results can be achieved.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="5afc3-130">gRPC ストリーミング</span><span class="sxs-lookup"><span data-stu-id="5afc3-130">gRPC streaming</span></span>

<span data-ttu-id="5afc3-131">gRPC では、クライアントからサーバー、およびサーバーからクライアントへの永続的なストリームの作成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5afc3-131">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="5afc3-132">両方の種類のストリームが同時にアクティブになる場合があります。これを双方向ストリーミングと呼びます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-132">Both types of stream may be active concurrently; this is called bidirectional streaming.</span></span> <span data-ttu-id="5afc3-133">ストリームは、任意の非同期メッセージング、時間の経過と共に使用できます。また、1つの要求または応答で生成および送信するには大きすぎる大規模なデータセットを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-133">Streams can be used for arbitrary, asynchronous messaging over time, or for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="5afc3-134">次の例は、サーバーストリーミング RPC を示しています。</span><span class="sxs-lookup"><span data-stu-id="5afc3-134">The following example shows a server streaming RPC.</span></span>

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

<span data-ttu-id="5afc3-135">このサーバーストリームは、次のコードに示すように、クライアントアプリケーションから使用できます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-135">This server stream could be consumed from a client application as shown in the following code:</span></span>

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> <span data-ttu-id="5afc3-136">サーバーストリーミング Rpc は、サブスクリプション形式のサービスに役立ちます。また、データセット全体をメモリ内に構築するのが非効率であるか不可能である場合は、非常に大きなデータセットを送信するためにも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-136">Server streaming RPCs are useful for subscription-style services, and also for sending very large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="5afc3-137">ただし、ストリーミング応答は、1つのメッセージ内の `repeated` フィールドを送信する場合ほど高速ではありません。そのため、ルールストリーミングは小さいデータセットには使用できません。</span><span class="sxs-lookup"><span data-stu-id="5afc3-137">However, streaming responses isn't as fast as sending `repeated` fields in a single message, so as a rule streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-to-wcf"></a><span data-ttu-id="5afc3-138">WCF との違い</span><span class="sxs-lookup"><span data-stu-id="5afc3-138">Differences to WCF</span></span>

<span data-ttu-id="5afc3-139">WCF 双方向サービスでは、複数のメソッドを持つことができるクライアントコールバックインターフェイスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-139">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="5afc3-140">GRPC サーバーストリーミングサービスは、1つのストリームでのみメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-140">A gRPC server streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="5afc3-141">複数のメソッドが必要な場合は、[任意のフィールドまたはフィールドの](protobuf-any-oneof.md)いずれかを含むメッセージ型を使用して、異なるメッセージを送信し、それらを処理するためのコードをクライアントに記述します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-141">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="5afc3-142">WCF では、セッションを使用した[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)クラスは、接続が閉じられるまで保持され、セッション内で複数のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-142">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed, and multiple methods may be called within the session.</span></span> <span data-ttu-id="5afc3-143">GRPC では、実装メソッドによって返される `Task` は、接続が閉じられるまで完了しません。</span><span class="sxs-lookup"><span data-stu-id="5afc3-143">In gRPC, the `Task` returned by the implementation method shouldn't complete until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="5afc3-144">WCF の一方向操作と gRPC クライアントストリーミング</span><span class="sxs-lookup"><span data-stu-id="5afc3-144">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="5afc3-145">WCF は、トランスポート固有の確認を返す一方向操作 (`[OperationContract(IsOneWay = true)]`) を提供します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-145">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="5afc3-146">gRPC サービスメソッドは、空の場合でも常に応答を返し、クライアントは常にその応答を待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5afc3-146">gRPC service methods always return a response, even if it's empty, and the client should always await that response.</span></span> <span data-ttu-id="5afc3-147">GRPC の "火災と忘れる" スタイルのメッセージングでは、クライアントストリーミングサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-147">For "fire-and-forget" style messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="5afc3-148">thing_log. proto</span><span class="sxs-lookup"><span data-stu-id="5afc3-148">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="5afc3-149">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="5afc3-149">ThingLogService.cs</span></span>

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a><span data-ttu-id="5afc3-150">のログクライアントの例</span><span class="sxs-lookup"><span data-stu-id="5afc3-150">ThingLog client example</span></span>

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

<span data-ttu-id="5afc3-151">ここでも、前の例で示したように、クライアントストリーミングの Rpc を使用して、サーバーに非常に大きなデータセットを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-151">Again, client streaming RPCs can be used for fire-and-forget messaging as shown in the previous example, but also for sending very large datasets to the server.</span></span> <span data-ttu-id="5afc3-152">パフォーマンスに関する同じ警告が適用されます。小規模なデータセットの場合は、通常のメッセージで `repeated` フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="5afc3-152">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="5afc3-153">WCF の全二重サービス</span><span class="sxs-lookup"><span data-stu-id="5afc3-153">WCF full duplex services</span></span>

<span data-ttu-id="5afc3-154">WCF 双方向バインドでは、サービスインターフェイスとクライアントコールバックインターフェイスの両方に対して複数の一方向操作がサポートされているため、クライアントとサーバー間の継続的なメッセージ交換が可能になります。</span><span class="sxs-lookup"><span data-stu-id="5afc3-154">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface, allowing ongoing conversations between client and server.</span></span> <span data-ttu-id="5afc3-155">gRPC では、双方向ストリーミング Rpc と同様のものがサポートされていますが、両方のパラメーターが `stream` 修飾子でマークされています。</span><span class="sxs-lookup"><span data-stu-id="5afc3-155">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="5afc3-156">チャット. プロトコル</span><span class="sxs-lookup"><span data-stu-id="5afc3-156">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="5afc3-157">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="5afc3-157">ChatterService.cs</span></span>

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

<span data-ttu-id="5afc3-158">前の例では、実装メソッドが要求ストリーム (`IAsyncStreamReader<MessageRequest>`) と応答ストリーム (`IServerStreamWriter<MessageResponse>`) の両方を受信し、接続が閉じられるまでメッセージの読み取りと書き込みを行うことができることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5afc3-158">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`), and can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="5afc3-159">Chatter クライアント</span><span class="sxs-lookup"><span data-stu-id="5afc3-159">Chatter client</span></span>

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
><span data-ttu-id="5afc3-160">[前へ](wcf-bindings.md)
>[次へ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="5afc3-160">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
