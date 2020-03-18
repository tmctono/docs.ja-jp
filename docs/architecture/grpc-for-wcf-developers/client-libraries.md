---
title: gRPC クライアント ライブラリを作成する - gRPC WCF 開発者向け
description: gRPC サービス用の共有クライアントライブラリ/パッケージの説明
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401773"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="f2b00-103">gRPC クライアント ライブラリの作成</span><span class="sxs-lookup"><span data-stu-id="f2b00-103">Create gRPC client libraries</span></span>

<span data-ttu-id="f2b00-104">gRPC アプリケーション用のクライアントライブラリを配布する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="f2b00-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="f2b00-105">組織内のファイルの共有ライブラリを`.proto`作成でき、他のチームは、それらのファイルを使用して、独自のプロジェクトでクライアント コードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="f2b00-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="f2b00-106">ただし、プライベートな NuGet リポジトリがあり、他の多くのチームが .NET Core を使用している場合は、クライアントの NuGet パッケージを作成してサービス プロジェクトの一部として発行できます。</span><span class="sxs-lookup"><span data-stu-id="f2b00-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="f2b00-107">これは、サービスを共有し、促進するための良い方法です。</span><span class="sxs-lookup"><span data-stu-id="f2b00-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="f2b00-108">クライアント ライブラリを配布する利点の 1 つは、便利な "便利な" メソッドとプロパティを使用して、生成された gRPC クラスと Protobuf クラスを強化できることです。</span><span class="sxs-lookup"><span data-stu-id="f2b00-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="f2b00-109">クライアント コードでは、サーバーと同様に、すべてのクラスが として`partial`宣言されるため、生成されたコードを編集せずに拡張できます。</span><span class="sxs-lookup"><span data-stu-id="f2b00-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="f2b00-110">つまり、基本型にコンストラクター、メソッド、および計算プロパティを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="f2b00-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="f2b00-111">カスタム コードを使用して、重要な機能を提供しないでください。</span><span class="sxs-lookup"><span data-stu-id="f2b00-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="f2b00-112">共有ライブラリを使用する .NET チームに対してこの重要な機能を制限したり、Python や Java などの他の言語やプラットフォームを使用するチームに提供したりすることは望ましくない。</span><span class="sxs-lookup"><span data-stu-id="f2b00-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="f2b00-113">できるだけ多くのチームが gRPC サービスにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2b00-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="f2b00-114">これを行う最善の方法は、開発者`.proto`が独自のクライアントを生成できるようにファイルを共有することです。</span><span class="sxs-lookup"><span data-stu-id="f2b00-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="f2b00-115">これは、異なるチームが異なるプログラミング言語やフレームワークを頻繁に使用するマルチプラットフォーム環境や、API が外部からアクセス可能な場合に特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="f2b00-116">便利な拡張機能</span><span class="sxs-lookup"><span data-stu-id="f2b00-116">Useful extensions</span></span>

<span data-ttu-id="f2b00-117">NET には、オブジェクトのストリームを処理するためによく使用されるインターフェイスが<xref:System.Collections.Generic.IEnumerable%601>2<xref:System.IObservable%601>つあります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="f2b00-118">NET Core 3.0 および C# 8.0 以降、<xref:System.Collections.Generic.IAsyncEnumerable%601>ストリームを非同期に処理するためのインターフェイスと、`await foreach`インターフェイスを使用するための構文があります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="f2b00-119">このセクションでは、これらのインターフェイスを gRPC ストリームに適用するための再利用可能なコードを示します。</span><span class="sxs-lookup"><span data-stu-id="f2b00-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="f2b00-120">NET Core gRPC クライアント ライブラリには、`ReadAllAsync``IAsyncStreamReader<T>``IAsyncEnumerable<T>`インターフェイスを作成するための拡張メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="f2b00-121">リアクティブ プログラミングを使用する開発者の場合、インターフェイスを作成するための`IObservable<T>`同等の拡張メソッドは、次のセクションの例のようになります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="f2b00-122">Iobservable</span><span class="sxs-lookup"><span data-stu-id="f2b00-122">IObservable</span></span>

<span data-ttu-id="f2b00-123">インターフェイス`IObservable<T>`は の "反応" 逆です`IEnumerable<T>`。</span><span class="sxs-lookup"><span data-stu-id="f2b00-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="f2b00-124">ストリームから項目をプルするのではなく、リアクティブな方法で、ストリームがサブスクライバーに項目をプッシュできます。</span><span class="sxs-lookup"><span data-stu-id="f2b00-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="f2b00-125">これは gRPC ストリームと非常によく似ており、`IObservable<T>`インターフェイスを囲むのは簡単です`IAsyncStreamReader<T>`。</span><span class="sxs-lookup"><span data-stu-id="f2b00-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="f2b00-126">C# には、監視`IAsyncEnumerable<T>`可能な処理に対する組み込みのサポートがないため、このコードはコードよりも長くなります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="f2b00-127">実装クラスを手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="f2b00-128">しかし、これはジェネリッククラスなので、すべての型で単一の実装が機能します。</span><span class="sxs-lookup"><span data-stu-id="f2b00-128">It's a generic class, though, so a single implementation works across all types.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> <span data-ttu-id="f2b00-129">この観察可能な実装では`Subscribe`、ストリームから読み取ろうとする複数のサブスクライバを持つと混乱が生じるため、メソッドを 1 回だけ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f2b00-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="f2b00-130">`Replay` [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq)など、この実装で使用できる監視可能なバッファリングと反復可能な共有を可能にする演算子があります。</span><span class="sxs-lookup"><span data-stu-id="f2b00-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="f2b00-131">クラス`GrpcStreamSubscription`は、 の列挙体`IAsyncStreamReader`を処理します。</span><span class="sxs-lookup"><span data-stu-id="f2b00-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

<span data-ttu-id="f2b00-132">ここで必要なのは、ストリーム リーダーから監視可能なオブジェクトを作成するための単純な拡張メソッドです。</span><span class="sxs-lookup"><span data-stu-id="f2b00-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a><span data-ttu-id="f2b00-133">まとめ</span><span class="sxs-lookup"><span data-stu-id="f2b00-133">Summary</span></span>

<span data-ttu-id="f2b00-134">`IAsyncEnumerable`および`IObservable`モデルは、よくサポートされ、よく文書化された方法で、.NET の非同期データ ストリームを処理します。</span><span class="sxs-lookup"><span data-stu-id="f2b00-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="f2b00-135">gRPC ストリームは両方のパラダイムに適切に対応し、.NET Core との密接な統合と、反応型および非同期プログラミング スタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="f2b00-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f2b00-136">[前次](streaming-versus-repeated.md)
>[Next](security.md)</span><span class="sxs-lookup"><span data-stu-id="f2b00-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
