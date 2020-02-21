---
title: WCF 開発者向けの RPC-gRPC の種類
description: WCF でサポートされているリモートプロシージャコールの種類と gRPC で対応するリモートプロシージャコールのレビュー
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503444"
---
# <a name="types-of-rpc"></a><span data-ttu-id="f8e5f-103">RPC の種類</span><span class="sxs-lookup"><span data-stu-id="f8e5f-103">Types of RPC</span></span>

<span data-ttu-id="f8e5f-104">Windows Communication Foundation (WCF) 開発者は、次の種類のリモートプロシージャコール (RPC) を扱うために使用されることがあります。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="f8e5f-105">要求/応答</span><span class="sxs-lookup"><span data-stu-id="f8e5f-105">Request/reply</span></span>
- <span data-ttu-id="f8e5f-106">通信</span><span class="sxs-lookup"><span data-stu-id="f8e5f-106">Duplex:</span></span>
  - <span data-ttu-id="f8e5f-107">セッションを含む一方向の二重</span><span class="sxs-lookup"><span data-stu-id="f8e5f-107">One-way duplex with session</span></span>
  - <span data-ttu-id="f8e5f-108">セッションを使用した全二重</span><span class="sxs-lookup"><span data-stu-id="f8e5f-108">Full duplex with session</span></span>
- <span data-ttu-id="f8e5f-109">一方向</span><span class="sxs-lookup"><span data-stu-id="f8e5f-109">One-way</span></span>

<span data-ttu-id="f8e5f-110">これらの RPC の種類は、既存の gRPC の概念に自然にマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="f8e5f-111">この章では、これらの各領域について見ていきます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="f8e5f-112">[第5章](migrate-wcf-to-grpc.md)では、同様の例について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="f8e5f-113">WCF</span><span class="sxs-lookup"><span data-stu-id="f8e5f-113">WCF</span></span> | <span data-ttu-id="f8e5f-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="f8e5f-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="f8e5f-115">通常の要求/応答</span><span class="sxs-lookup"><span data-stu-id="f8e5f-115">Regular request/reply</span></span> | <span data-ttu-id="f8e5f-116">単項演算子</span><span class="sxs-lookup"><span data-stu-id="f8e5f-116">Unary</span></span> |
| <span data-ttu-id="f8e5f-117">クライアントコールバックインターフェイスを使用したセッションを使用した双方向サービス</span><span class="sxs-lookup"><span data-stu-id="f8e5f-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="f8e5f-118">サーバーストリーミング</span><span class="sxs-lookup"><span data-stu-id="f8e5f-118">Server streaming</span></span> |
| <span data-ttu-id="f8e5f-119">セッションを使用した全二重サービス</span><span class="sxs-lookup"><span data-stu-id="f8e5f-119">Full duplex service with session</span></span> | <span data-ttu-id="f8e5f-120">双方向ストリーミング</span><span class="sxs-lookup"><span data-stu-id="f8e5f-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="f8e5f-121">一方向の操作</span><span class="sxs-lookup"><span data-stu-id="f8e5f-121">One-way operations</span></span> | <span data-ttu-id="f8e5f-122">クライアントストリーミング</span><span class="sxs-lookup"><span data-stu-id="f8e5f-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="f8e5f-123">要求/応答</span><span class="sxs-lookup"><span data-stu-id="f8e5f-123">Request/reply</span></span>

<span data-ttu-id="f8e5f-124">少量のデータを取得して返す単純な要求/応答メソッドの場合は、最も単純な gRPC パターンである単項 RPC を使用します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="f8e5f-125">ご覧のように、gRPC の単項 RPC サービスメソッドを実装することは、WCF 操作の実装に似ています。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="f8e5f-126">ただし、gRPC では、インターフェイスを実装するのではなく、基底クラスのメソッドをオーバーライドする点が異なります。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="f8e5f-127">サーバーでは、gRPC の基本メソッドは常に <xref:System.Threading.Tasks.Task%601>を返します。ただし、クライアントはサービスを呼び出すための非同期メソッドとブロッキングメソッドの両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="f8e5f-128">WCF デュプレックス (クライアントへの一方向)</span><span class="sxs-lookup"><span data-stu-id="f8e5f-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="f8e5f-129">WCF アプリケーション (特定のバインドを使用) では、クライアントとサーバーの間に永続的な接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="f8e5f-130">サーバーは、[<xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>] プロパティで指定された*コールバックインターフェイス*を使用して、接続が閉じられるまで、非同期にデータをクライアントに送信できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="f8e5f-131">gRPC サービスは、メッセージストリームと同様の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="f8e5f-132">実装という点で、ストリームは WCF 双方向サービスに*厳密*にはマップされませんが、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="f8e5f-133">gRPC ストリーミング</span><span class="sxs-lookup"><span data-stu-id="f8e5f-133">gRPC streaming</span></span>

<span data-ttu-id="f8e5f-134">gRPC では、クライアントからサーバー、およびサーバーからクライアントへの永続的なストリームの作成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="f8e5f-135">両方の種類のストリームを同時にアクティブにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="f8e5f-136">この機能は、双方向ストリーミングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-136">This ability is called bidirectional streaming.</span></span> 

<span data-ttu-id="f8e5f-137">時間の経過と共に、任意の非同期メッセージングにストリームを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="f8e5f-138">または、1つの要求または応答で生成および送信するには大きすぎる大規模なデータセットを渡すために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="f8e5f-139">次の例は、サーバーストリーミング RPC を示しています。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="f8e5f-140">このサーバーストリームは、次のコードに示すように、クライアントアプリケーションから使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="f8e5f-141">サーバーストリーミング Rpc は、サブスクリプション形式のサービスに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="f8e5f-142">また、データセット全体をメモリ内に構築するのが非効率であるか不可能である場合に、大規模なデータセットを送信する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="f8e5f-143">ただし、ストリーミング応答は、1つのメッセージで `repeated` フィールドを送信する場合ほど高速ではありません。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="f8e5f-144">ルールとして、小規模なデータセットには streaming を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="f8e5f-145">WCF との違い</span><span class="sxs-lookup"><span data-stu-id="f8e5f-145">Differences from WCF</span></span>

<span data-ttu-id="f8e5f-146">WCF 双方向サービスでは、複数のメソッドを持つことができるクライアントコールバックインターフェイスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="f8e5f-147">GRPC サーバーストリーミングサービスは、1つのストリームでのみメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="f8e5f-148">複数のメソッドが必要な場合は、[任意のフィールドまたはフィールドの](protobuf-any-oneof.md)いずれかを含むメッセージ型を使用して、異なるメッセージを送信し、それらを処理するためのコードをクライアントに記述します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="f8e5f-149">WCF では、セッションを使用した[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)クラスは、接続が閉じられるまで維持されます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="f8e5f-150">セッション内では、複数のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="f8e5f-151">GRPC では、実装メソッドが返す `Task` は、接続が閉じられるまで完了しません。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="f8e5f-152">WCF の一方向操作と gRPC クライアントストリーミング</span><span class="sxs-lookup"><span data-stu-id="f8e5f-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="f8e5f-153">WCF は、トランスポート固有の確認を返す一方向操作 (`[OperationContract(IsOneWay = true)]`) を提供します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="f8e5f-154">gRPC サービスメソッドは、空の場合でも、常に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="f8e5f-155">クライアントは、常にその応答を待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-155">The client should always await that response.</span></span> <span data-ttu-id="f8e5f-156">GRPC でのメッセージングの "火災と忘れる" スタイルについては、クライアントストリーミングサービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="f8e5f-157">thing_log. proto</span><span class="sxs-lookup"><span data-stu-id="f8e5f-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="f8e5f-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="f8e5f-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="f8e5f-159">のログクライアントの例</span><span class="sxs-lookup"><span data-stu-id="f8e5f-159">ThingLog client example</span></span>

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

<span data-ttu-id="f8e5f-160">前の例で示したように、火災および忘れるメッセージにクライアントストリーミング Rpc を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="f8e5f-161">また、非常に大規模なデータセットをサーバーに送信するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="f8e5f-162">パフォーマンスに関する同じ警告が適用されます。小規模なデータセットの場合は、通常のメッセージで `repeated` フィールドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="f8e5f-163">WCF の全二重サービス</span><span class="sxs-lookup"><span data-stu-id="f8e5f-163">WCF full-duplex services</span></span>

<span data-ttu-id="f8e5f-164">WCF 双方向バインドでは、サービスインターフェイスとクライアントコールバックインターフェイスの両方で、複数の一方向操作がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="f8e5f-165">このサポートにより、クライアントとサーバーの間で実行中のメッセージ交換が可能になります。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="f8e5f-166">gRPC では、双方向ストリーミング Rpc と同様のものがサポートされていますが、両方のパラメーターが `stream` 修飾子でマークされています。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="f8e5f-167">チャット. プロトコル</span><span class="sxs-lookup"><span data-stu-id="f8e5f-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="f8e5f-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="f8e5f-168">ChatterService.cs</span></span>

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

<span data-ttu-id="f8e5f-169">前の例では、実装メソッドが要求ストリーム (`IAsyncStreamReader<MessageRequest>`) と応答ストリーム (`IServerStreamWriter<MessageResponse>`) の両方を受け取ることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="f8e5f-170">メソッドは、接続が閉じられるまで、メッセージの読み取りと書き込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f8e5f-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="f8e5f-171">Chatter クライアント</span><span class="sxs-lookup"><span data-stu-id="f8e5f-171">Chatter client</span></span>

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
><span data-ttu-id="f8e5f-172">[前へ](wcf-bindings.md)
>[次へ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="f8e5f-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
