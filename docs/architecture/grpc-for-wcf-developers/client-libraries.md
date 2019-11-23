---
title: GRPC クライアントライブラリの作成-WCF 開発者向け gRPC
description: GRPC サービス用の共有クライアントライブラリ/パッケージについて説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 2135fe8b24a2311a31cb2bed191d290b1112bc66
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967884"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="dd492-103">GRPC クライアントライブラリを作成する</span><span class="sxs-lookup"><span data-stu-id="dd492-103">Create gRPC client libraries</span></span>

<span data-ttu-id="dd492-104">GRPC アプリケーション用のクライアントライブラリを配布する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dd492-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="dd492-105">組織内に `.proto` ファイルの共有ライブラリを作成することができます。また、他のチームはこれらのファイルを使用して、独自のプロジェクトでクライアントコードを生成できます。</span><span class="sxs-lookup"><span data-stu-id="dd492-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="dd492-106">ただし、プライベート NuGet リポジトリがあり、他の多くのチームが .NET Core を使用している場合は、サービスプロジェクトの一部としてクライアント NuGet パッケージを作成して発行すると、サービスを共有して昇格させることができます。</span><span class="sxs-lookup"><span data-stu-id="dd492-106">But if you have a private NuGet repository and many other teams are using .NET Core, creating and publishing client NuGet packages as part of your service project may be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="dd492-107">クライアントライブラリを配布する利点の1つは、生成された gRPC および Protobuf クラスを、便利な "便利な" メソッドとプロパティを使用して拡張できることです。</span><span class="sxs-lookup"><span data-stu-id="dd492-107">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="dd492-108">クライアントコードでは、サーバーと同様に、すべてのクラスが `partial` として宣言されているため、生成されたコードを編集せずに、すべてのクラスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="dd492-108">In the client code, as in the server, all the classes are declared as `partial` so you can extend them without editing the generated code.</span></span> <span data-ttu-id="dd492-109">これは、コンストラクター、メソッド、計算されたプロパティなどを基本型に簡単に追加できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dd492-109">This means it's easy to add constructors, methods, calculated properties, and more to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="dd492-110">重要な機能を提供するためにカスタムコードを使用し**ない**でください。これは、機能が、他の言語や Python や Java などのプラットフォームを使用しているチームではなく、共有ライブラリを使用して .net チームに限定されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="dd492-110">You should **not** use custom code to provide essential functionality, as this would mean that functionality would be restricted to .NET teams using the shared library, and not to teams using other languages or platforms such as Python or Java.</span></span>

<span data-ttu-id="dd492-111">複数のチームが頻繁に異なるプログラミング言語とフレームワークを使用している場合、または API に外部からアクセスできる場合は、`.proto` ファイルを共有するだけで、開発者が独自のクライアントを生成できるようになります。これは、可能な限り多くのチームが gRPC サービスにアクセスできるようにするための最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="dd492-111">In a multi-platform environment where different teams frequently use different programming languages and frameworks, or where your API is externally accessible, simply sharing `.proto` files so developers can generate their own clients is the best way to ensure as many teams as possible can access your gRPC service.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="dd492-112">便利な拡張機能</span><span class="sxs-lookup"><span data-stu-id="dd492-112">Useful extensions</span></span>

<span data-ttu-id="dd492-113">.NET には、オブジェクトのストリームを処理するために一般的に使用されるインターフェイスとして、<xref:System.Collections.Generic.IEnumerable%601> と <xref:System.IObservable%601>の2つがあります。</span><span class="sxs-lookup"><span data-stu-id="dd492-113">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="dd492-114">.NET Core 3.0 およびC# 8.0 以降では、ストリームを非同期処理するための <xref:System.Collections.Generic.IAsyncEnumerable%601> インターフェイスと、インターフェイスを使用するための `await foreach` 構文があります。</span><span class="sxs-lookup"><span data-stu-id="dd492-114">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="dd492-115">このセクションでは、これらのインターフェイスを gRPC ストリームに適用する再利用可能なコードを示します。</span><span class="sxs-lookup"><span data-stu-id="dd492-115">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="dd492-116">.NET Core gRPC クライアントライブラリには、`IAsyncEnumerable<T>`を作成する `IAsyncStreamReader<T>` の `ReadAllAsync` 拡張メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="dd492-116">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>`.</span></span> <span data-ttu-id="dd492-117">事後対応型プログラミングを使用している開発者にとっては、`IObservable<T>` を作成するための同等の拡張メソッドは、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dd492-117">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` might look like this.</span></span>

### <a name="iobservable"></a><span data-ttu-id="dd492-118">IObservable</span><span class="sxs-lookup"><span data-stu-id="dd492-118">IObservable</span></span>

<span data-ttu-id="dd492-119">`IObservable<T>` インターフェイスは、`IEnumerable<T>`の "リアクティブな" 逆関数です。</span><span class="sxs-lookup"><span data-stu-id="dd492-119">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="dd492-120">ストリームから項目をプルするのではなく、事後対応型のアプローチによって、ストリームをサブスクライバーにプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="dd492-120">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="dd492-121">これは gRPC ストリームとよく似ており、`IAsyncStreamReader<T>`の `IObservable<T>` を簡単にラップできます。</span><span class="sxs-lookup"><span data-stu-id="dd492-121">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` around an `IAsyncStreamReader<T>`.</span></span>

<span data-ttu-id="dd492-122">このコードは `IAsyncEnumerable<T>` コードC#よりも長くなっています。では observable を操作するためのサポートが組み込まれていないため、実装クラスを手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd492-122">This code is longer than the `IAsyncEnumerable<T>` code because C# doesn't have built-in support for working with observables, so the implementation class has to be created manually.</span></span> <span data-ttu-id="dd492-123">ただし、これはジェネリッククラスです。そのため、1つの実装がすべての型で動作します。</span><span class="sxs-lookup"><span data-stu-id="dd492-123">It's a generic class, though, so a single implementation will work across all types.</span></span>

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
> <span data-ttu-id="dd492-124">この観測可能な実装では、`Subscribe` メソッドを1回だけ呼び出すことができます。これは、複数のサブスクライバーがストリームからの読み取りを試みた場合に混乱が生じるためです。</span><span class="sxs-lookup"><span data-stu-id="dd492-124">This observable implementation only allows the `Subscribe` method to be called once, as having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="dd492-125">Observable のバッファリングと反復可能な共有を有効にする、のよう `Replay` な演算子が[あります。](https://www.nuget.org/packages/System.Reactive.Linq)これは、この実装で使用できます。</span><span class="sxs-lookup"><span data-stu-id="dd492-125">There are operators such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq) that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="dd492-126">`GrpcStreamSubscription` クラスは、`IAsyncStreamReader`の列挙体を処理します。</span><span class="sxs-lookup"><span data-stu-id="dd492-126">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`.</span></span>

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

<span data-ttu-id="dd492-127">ここで必要なのは、ストリームリーダーから観測可能なを作成するための単純な拡張メソッドです。</span><span class="sxs-lookup"><span data-stu-id="dd492-127">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="dd492-128">概要</span><span class="sxs-lookup"><span data-stu-id="dd492-128">Summary</span></span>

<span data-ttu-id="dd492-129">`IAsyncEnumerable` モデルと `IObservable` モデルは、.NET でのデータの非同期ストリームを処理するための適切にサポートされ、適切に記述された方法です。</span><span class="sxs-lookup"><span data-stu-id="dd492-129">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="dd492-130">gRPC ストリームは、最新の .NET Core フレームワークとリアクティブ/非同期プログラミングスタイルとの密接な統合を実現するために、両方のパラダイムに適しています。</span><span class="sxs-lookup"><span data-stu-id="dd492-130">gRPC streams map well to both paradigms, offering close integration with the modern .NET Core framework and reactive/asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="dd492-131">[前へ](streaming-versus-repeated.md)
>[次へ](security.md)</span><span class="sxs-lookup"><span data-stu-id="dd492-131">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
