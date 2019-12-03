---
title: GRPC クライアントライブラリの作成-WCF 開発者向け gRPC
description: GRPC サービス用の共有クライアントライブラリ/パッケージについて説明します。
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711456"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="2527f-103">GRPC クライアントライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="2527f-103">Create gRPC client libraries</span></span>

<span data-ttu-id="2527f-104">GRPC アプリケーション用のクライアントライブラリを配布する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2527f-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="2527f-105">組織内に `.proto` ファイルの共有ライブラリを作成することができます。また、他のチームはこれらのファイルを使用して、独自のプロジェクトでクライアントコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="2527f-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="2527f-106">ただし、プライベート NuGet リポジトリがあり、他の多くのチームが .NET Core を使用している場合は、サービスプロジェクトの一部としてクライアント NuGet パッケージを作成して発行することができます。</span><span class="sxs-lookup"><span data-stu-id="2527f-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="2527f-107">これは、サービスの共有と昇格に適した方法です。</span><span class="sxs-lookup"><span data-stu-id="2527f-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="2527f-108">クライアントライブラリを配布する利点の1つは、生成された gRPC および Protobuf クラスを、便利な "便利な" メソッドとプロパティを使用して拡張できることです。</span><span class="sxs-lookup"><span data-stu-id="2527f-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="2527f-109">クライアントコードでは、サーバーと同様に、すべてのクラスが `partial`として宣言されているため、生成されたコードを編集しなくても、それらを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="2527f-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="2527f-110">これは、コンストラクター、メソッド、および計算されるプロパティを基本的な型に簡単に追加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2527f-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="2527f-111">カスタムコードを使用して、重要な機能を提供しないでください。</span><span class="sxs-lookup"><span data-stu-id="2527f-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="2527f-112">共有ライブラリを使用する .NET チームにこの重要な機能を制限するのではなく、Python や Java などの他の言語やプラットフォームを使用するチームに提供する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2527f-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="2527f-113">可能な限り多くのチームが gRPC サービスにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2527f-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="2527f-114">これを行う最善の方法は、開発者が独自のクライアントを生成できるように `.proto` ファイルを共有することです。</span><span class="sxs-lookup"><span data-stu-id="2527f-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="2527f-115">これは、さまざまなチームがさまざまなプログラミング言語やフレームワークを頻繁に使用している場合や、API に外部からアクセスできる場合に、マルチプラットフォーム環境で特に当てはまります。</span><span class="sxs-lookup"><span data-stu-id="2527f-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="2527f-116">便利な拡張機能</span><span class="sxs-lookup"><span data-stu-id="2527f-116">Useful extensions</span></span>

<span data-ttu-id="2527f-117">.NET には、オブジェクトのストリームを処理するために一般的に使用されるインターフェイスとして、<xref:System.Collections.Generic.IEnumerable%601> と <xref:System.IObservable%601>の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="2527f-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="2527f-118">.NET Core 3.0 およびC# 8.0 以降では、ストリームを非同期処理するための <xref:System.Collections.Generic.IAsyncEnumerable%601> インターフェイスと、インターフェイスを使用するための `await foreach` 構文があります。</span><span class="sxs-lookup"><span data-stu-id="2527f-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="2527f-119">このセクションでは、これらのインターフェイスを gRPC ストリームに適用する再利用可能なコードを示します。</span><span class="sxs-lookup"><span data-stu-id="2527f-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="2527f-120">.NET Core gRPC クライアントライブラリには、`IAsyncEnumerable<T>` インターフェイスを作成する `IAsyncStreamReader<T>` の `ReadAllAsync` 拡張メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="2527f-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="2527f-121">事後対応型プログラミングを使用する開発者にとっては、`IObservable<T>` インターフェイスを作成するための同等の拡張メソッドが、次のセクションの例のようになります。</span><span class="sxs-lookup"><span data-stu-id="2527f-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="2527f-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="2527f-122">IObservable</span></span>

<span data-ttu-id="2527f-123">`IObservable<T>` インターフェイスは、`IEnumerable<T>`の "リアクティブな" 逆関数です。</span><span class="sxs-lookup"><span data-stu-id="2527f-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="2527f-124">ストリームから項目をプルするのではなく、事後対応型のアプローチによって、ストリームをサブスクライバーにプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="2527f-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="2527f-125">これは gRPC ストリームとよく似ており、`IAsyncStreamReader<T>` インターフェイスの `IObservable<T>` インターフェイスをラップするのは簡単です。</span><span class="sxs-lookup"><span data-stu-id="2527f-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="2527f-126">このコードは `IAsyncEnumerable<T>` コードよりも長くなってC#います。には observable を操作するためのサポートが組み込まれていないためです。</span><span class="sxs-lookup"><span data-stu-id="2527f-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="2527f-127">実装クラスは手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2527f-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="2527f-128">ただし、これはジェネリッククラスであるため、1つの実装がすべての型で動作します。</span><span class="sxs-lookup"><span data-stu-id="2527f-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="2527f-129">この監視可能な実装により、`Subscribe` メソッドを1回だけ呼び出すことができます。これは、複数のサブスクライバーがストリームから読み取ろうとすると混乱が生じるためです。</span><span class="sxs-lookup"><span data-stu-id="2527f-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="2527f-130">Observable の `Replay` などの演算子が[あります。](https://www.nuget.org/packages/System.Reactive.Linq)これにより、この実装で使用できるのバッファリングと反復可能な共有が可能になります。</span><span class="sxs-lookup"><span data-stu-id="2527f-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="2527f-131">`GrpcStreamSubscription` クラスは、`IAsyncStreamReader`の列挙体を処理します。</span><span class="sxs-lookup"><span data-stu-id="2527f-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="2527f-132">ここで必要なのは、ストリームリーダーから観測可能なを作成するための単純な拡張メソッドです。</span><span class="sxs-lookup"><span data-stu-id="2527f-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="2527f-133">要約</span><span class="sxs-lookup"><span data-stu-id="2527f-133">Summary</span></span>

<span data-ttu-id="2527f-134">`IAsyncEnumerable` モデルと `IObservable` モデルは、.NET でのデータの非同期ストリームを処理するための適切にサポートされ、適切に記述された方法です。</span><span class="sxs-lookup"><span data-stu-id="2527f-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="2527f-135">gRPC ストリームは、両方のパラダイムに適切にマップされ、.NET Core との密接な統合と、リアクティブおよび非同期のプログラミングスタイルを提供します。</span><span class="sxs-lookup"><span data-stu-id="2527f-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2527f-136">[前へ](streaming-versus-repeated.md)
>[次へ](security.md)</span><span class="sxs-lookup"><span data-stu-id="2527f-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
