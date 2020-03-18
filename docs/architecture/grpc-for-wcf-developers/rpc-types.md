---
title: RPC の種類 - WCF 開発者向け gRPC
description: WCF でサポートされているリモート プロシージャコールの種類と、gRPC での対応するリモート プロシージャ コールの種類のレビュー
ms.date: 09/02/2019
ms.openlocfilehash: b9d4ce7cae693ed7904229483cbccfe3b299b640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401785"
---
# <a name="types-of-rpc"></a><span data-ttu-id="2566b-103">RPC の種類</span><span class="sxs-lookup"><span data-stu-id="2566b-103">Types of RPC</span></span>

<span data-ttu-id="2566b-104">Windows 通信基盤 (WCF) 開発者として、次の種類のリモート プロシージャ コール (RPC) を扱うことに慣れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2566b-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="2566b-105">リクエスト/返信</span><span class="sxs-lookup"><span data-stu-id="2566b-105">Request/reply</span></span>
- <span data-ttu-id="2566b-106">二重：</span><span class="sxs-lookup"><span data-stu-id="2566b-106">Duplex:</span></span>
  - <span data-ttu-id="2566b-107">セッションを使用した一方向の二重化</span><span class="sxs-lookup"><span data-stu-id="2566b-107">One-way duplex with session</span></span>
  - <span data-ttu-id="2566b-108">全二重 (セッションを使用)</span><span class="sxs-lookup"><span data-stu-id="2566b-108">Full duplex with session</span></span>
- <span data-ttu-id="2566b-109">一方向</span><span class="sxs-lookup"><span data-stu-id="2566b-109">One-way</span></span>

<span data-ttu-id="2566b-110">これらの RPC 型は、既存の gRPC の概念にかなり自然に対応できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="2566b-111">この章では、これらの各領域を順番に説明します。</span><span class="sxs-lookup"><span data-stu-id="2566b-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="2566b-112">[第5章](migrate-wcf-to-grpc.md)では、同様の例をより詳しく見ていきます。</span><span class="sxs-lookup"><span data-stu-id="2566b-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="2566b-113">WCF</span><span class="sxs-lookup"><span data-stu-id="2566b-113">WCF</span></span> | <span data-ttu-id="2566b-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="2566b-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="2566b-115">通常の要求/応答</span><span class="sxs-lookup"><span data-stu-id="2566b-115">Regular request/reply</span></span> | <span data-ttu-id="2566b-116">単項演算子</span><span class="sxs-lookup"><span data-stu-id="2566b-116">Unary</span></span> |
| <span data-ttu-id="2566b-117">クライアント コールバック インターフェイスを使用したセッションを使用した双方向サービス</span><span class="sxs-lookup"><span data-stu-id="2566b-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="2566b-118">サーバー ストリーミング</span><span class="sxs-lookup"><span data-stu-id="2566b-118">Server streaming</span></span> |
| <span data-ttu-id="2566b-119">セッションを使用した全二重サービス</span><span class="sxs-lookup"><span data-stu-id="2566b-119">Full duplex service with session</span></span> | <span data-ttu-id="2566b-120">双方向ストリーミング</span><span class="sxs-lookup"><span data-stu-id="2566b-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="2566b-121">一方向操作</span><span class="sxs-lookup"><span data-stu-id="2566b-121">One-way operations</span></span> | <span data-ttu-id="2566b-122">クライアント ストリーミング</span><span class="sxs-lookup"><span data-stu-id="2566b-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="2566b-123">リクエスト/返信</span><span class="sxs-lookup"><span data-stu-id="2566b-123">Request/reply</span></span>

<span data-ttu-id="2566b-124">少量のデータを取得して返す単純な要求/応答メソッドの場合は、最も単純な gRPC パターンである単項 RPC を使用します。</span><span class="sxs-lookup"><span data-stu-id="2566b-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="2566b-125">ご覧のとおり、gRPC 単項 RPC サービス メソッドの実装は、WCF 操作の実装と同様です。</span><span class="sxs-lookup"><span data-stu-id="2566b-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="2566b-126">違いは、gRPC では、インターフェイスを実装する代わりに基本クラスのメソッドをオーバーライドする点です。</span><span class="sxs-lookup"><span data-stu-id="2566b-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="2566b-127">サーバーでは、gRPC 基本メソッドは常<xref:System.Threading.Tasks.Task%601>に 戻りますが、クライアントはサービスを呼び出すために非同期メソッドとブロッキングメソッドの両方を提供します。</span><span class="sxs-lookup"><span data-stu-id="2566b-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="2566b-128">WCF 二重方式(クライアントへの 1 つの方法)</span><span class="sxs-lookup"><span data-stu-id="2566b-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="2566b-129">WCF アプリケーション (特定のバインディング) は、クライアントとサーバー間の永続的な接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="2566b-130">サーバーは、プロパティで指定された*コールバック インターフェイス*を使用して、接続が閉じられるまで、クライアントに非同期的<xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>にデータを送信できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="2566b-131">gRPC サービスは、メッセージ ストリームと同様の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="2566b-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="2566b-132">ストリームは、実装の面で WCF 双方向サービスに*正確*にマップされませんが、同じ結果を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="2566b-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="2566b-133">gRPC ストリーミング</span><span class="sxs-lookup"><span data-stu-id="2566b-133">gRPC streaming</span></span>

<span data-ttu-id="2566b-134">gRPC は、クライアントからサーバーへ、およびサーバーからクライアントへの永続ストリームの作成をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2566b-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="2566b-135">両方の種類のストリームを同時にアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="2566b-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="2566b-136">この機能は双方向ストリーミングと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2566b-136">This ability is called bidirectional streaming.</span></span>

<span data-ttu-id="2566b-137">ストリームは、時間の経過と同時に任意の非同期メッセージングに使用できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="2566b-138">また、1 つの要求または応答で生成および送信するには大きすぎる大きなデータセットを渡すために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2566b-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="2566b-139">次の例は、サーバー ストリーミング RPC を示しています。</span><span class="sxs-lookup"><span data-stu-id="2566b-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="2566b-140">このサーバー ストリームは、次のコードに示すように、クライアント アプリケーションから使用できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="2566b-141">サーバー ストリーミング RPC は、サブスクリプション スタイルのサービスに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2566b-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="2566b-142">また、メモリ内でデータセット全体を構築することが非効率的または不可能な場合に、大規模なデータセットを送信する場合にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2566b-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="2566b-143">ただし、ストリーミング応答は、単一のメッセージでフィールドを`repeated`送信するほど高速ではありません。</span><span class="sxs-lookup"><span data-stu-id="2566b-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="2566b-144">原則として、小規模なデータセットにストリーミングを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="2566b-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="2566b-145">WCF との違い</span><span class="sxs-lookup"><span data-stu-id="2566b-145">Differences from WCF</span></span>

<span data-ttu-id="2566b-146">WCF 双方向サービスは、複数のメソッドを持つことができるクライアント コールバック インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2566b-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="2566b-147">gRPC サーバー ストリーミング サービスは、単一のストリームを介してメッセージを送信することしかできません。</span><span class="sxs-lookup"><span data-stu-id="2566b-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="2566b-148">複数のメソッドが必要な場合は[、Any フィールドまたはいずれかのフィールド](protobuf-any-oneof.md)でメッセージの種類を使用して異なるメッセージを送信し、クライアントでメッセージを処理するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="2566b-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="2566b-149">WCF では、セッションを持つ[ServiceContract](xref:System.ServiceModel.ServiceContractAttribute)クラスは、接続が閉じられるまで存続します。</span><span class="sxs-lookup"><span data-stu-id="2566b-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="2566b-150">セッション内で複数のメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2566b-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="2566b-151">gRPC では、`Task`実装メソッドが返すが、接続が閉じられるまで終了しないはずです。</span><span class="sxs-lookup"><span data-stu-id="2566b-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="2566b-152">WCF の一方向操作と gRPC クライアント ストリーミング</span><span class="sxs-lookup"><span data-stu-id="2566b-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="2566b-153">WCF には、トランスポート固有の確認を`[OperationContract(IsOneWay = true)]`返す一方向の操作 (でマーク) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="2566b-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="2566b-154">gRPC サービスメソッドは、空であっても常に応答を返します。</span><span class="sxs-lookup"><span data-stu-id="2566b-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="2566b-155">クライアントは常にその応答を待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="2566b-155">The client should always await that response.</span></span> <span data-ttu-id="2566b-156">gRPC でのメッセージングの "ファイアアンドフォーゲット" スタイルでは、クライアント ストリーミング サービスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="2566b-157">thing_log.プロト</span><span class="sxs-lookup"><span data-stu-id="2566b-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="2566b-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="2566b-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="2566b-159">ThingLog クライアントの例</span><span class="sxs-lookup"><span data-stu-id="2566b-159">ThingLog client example</span></span>

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

<span data-ttu-id="2566b-160">前の例に示すように、クライアント ストリーミング RPC を使用して、ファイア アンド フォーゲット メッセージングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2566b-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="2566b-161">また、非常に大きなデータセットをサーバーに送信するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="2566b-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="2566b-162">パフォーマンスに関する警告は、小さいデータセットの場合は`repeated`、通常のメッセージでフィールドを使用するという警告が適用されます。</span><span class="sxs-lookup"><span data-stu-id="2566b-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="2566b-163">WCF 全二重サービス</span><span class="sxs-lookup"><span data-stu-id="2566b-163">WCF full-duplex services</span></span>

<span data-ttu-id="2566b-164">WCF 双方向バインディングは、サービス インターフェイスとクライアント コールバック インターフェイスの両方で複数の一方向操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2566b-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="2566b-165">このサポートにより、クライアントとサーバー間の継続的な会話が可能になります。</span><span class="sxs-lookup"><span data-stu-id="2566b-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="2566b-166">gRPC は双方向ストリーミング RPC と同様のものをサポートしており、両方のパラメータに修飾子`stream`が付いています。</span><span class="sxs-lookup"><span data-stu-id="2566b-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="2566b-167">チャット.プロト</span><span class="sxs-lookup"><span data-stu-id="2566b-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="2566b-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="2566b-168">ChatterService.cs</span></span>

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

<span data-ttu-id="2566b-169">前の例では、実装メソッドが要求ストリーム ( ) と応答ストリーム`IAsyncStreamReader<MessageRequest>`( )`IServerStreamWriter<MessageResponse>`の両方を受け取ることがわかります。</span><span class="sxs-lookup"><span data-stu-id="2566b-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="2566b-170">このメソッドは、接続が閉じられるまでメッセージの読み取りと書き込みを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2566b-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="2566b-171">チャタクライアント</span><span class="sxs-lookup"><span data-stu-id="2566b-171">Chatter client</span></span>

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
><span data-ttu-id="2566b-172">[前次](wcf-bindings.md)
>[Next](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="2566b-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
