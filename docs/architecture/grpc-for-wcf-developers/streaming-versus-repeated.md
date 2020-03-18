---
title: ストリーミング サービスと繰り返しフィールド - WCF 開発者向け gRPC
description: gRPC を使用してデータのコレクションを渡す方法として、繰り返しフィールドをストリーミング サービスと比較します。
ms.date: 09/02/2019
ms.openlocfilehash: 542ebc393f9c9c1ad717d02d01fab33d85c18917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147751"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a><span data-ttu-id="375d4-103">gRPC ストリーミングサービスと繰り返しフィールド</span><span class="sxs-lookup"><span data-stu-id="375d4-103">gRPC streaming services vs. repeated fields</span></span>

<span data-ttu-id="375d4-104">gRPC サービスは、データセットまたはオブジェクトのリストを返す 2 つの方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="375d4-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="375d4-105">プロトコル バッファ メッセージ仕様では、`repeated`別のメッセージ内のメッセージのリストまたは配列を宣言するキーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="375d4-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="375d4-106">gRPC サービス仕様では、`stream`このキーワードを使用して、長時間実行される永続接続を宣言します。</span><span class="sxs-lookup"><span data-stu-id="375d4-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection.</span></span> <span data-ttu-id="375d4-107">この接続を介して、複数のメッセージが送信され、個別に処理できます。</span><span class="sxs-lookup"><span data-stu-id="375d4-107">Over that connection, multiple messages are sent, and can be processed, individually.</span></span>

<span data-ttu-id="375d4-108">また、通知`stream`やログ メッセージなどの長時間実行されるテンポラル データにこの機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="375d4-108">You can also use the `stream` feature for long-running temporal data such as notifications or log messages.</span></span> <span data-ttu-id="375d4-109">しかし、この章では、単一のデータセットを返す際の使用について検討します。</span><span class="sxs-lookup"><span data-stu-id="375d4-109">But this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="375d4-110">どちらを使用するかは、次のような要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="375d4-110">Which you should use depends on factors such as:</span></span>

- <span data-ttu-id="375d4-111">データセットの全体的なサイズ。</span><span class="sxs-lookup"><span data-stu-id="375d4-111">The overall size of the dataset.</span></span>
- <span data-ttu-id="375d4-112">クライアント側またはサーバー側でデータセットを作成するのにかかった時間。</span><span class="sxs-lookup"><span data-stu-id="375d4-112">The time it took to create the dataset at either the client or server end.</span></span>
- <span data-ttu-id="375d4-113">データセットのコンシューマーが、最初の項目が使用可能になるとすぐにデータセットの処理を開始できるのか、または有用な操作を行うために完全なデータセットが必要か。</span><span class="sxs-lookup"><span data-stu-id="375d4-113">Whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="375d4-114">フィールドを使用`repeated`する場合</span><span class="sxs-lookup"><span data-stu-id="375d4-114">When to use `repeated` fields</span></span>

<span data-ttu-id="375d4-115">サイズが制限され、短時間で全体を生成できるデータセット (たとえば 1 秒以下) の場合は、通常の`repeated`Protobuf メッセージのフィールドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="375d4-115">For any dataset that's constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="375d4-116">たとえば、e コマース システムでは、注文内のアイテムのリストを作成するのも、大きなサイズにならないことが多いと考えられます。</span><span class="sxs-lookup"><span data-stu-id="375d4-116">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="375d4-117">フィールドを含む単一`repeated`のメッセージを返す方が、使用`stream`するよりも 1 桁の速度が速く、ネットワークオーバーヘッドが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="375d4-117">Returning a single message with a `repeated` field is an order of magnitude faster than using `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="375d4-118">クライアントが処理を開始する前にすべてのデータを必要とし、データセットがメモリ内で構築できるほど小さい場合は、`repeated`フィールドの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="375d4-118">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field.</span></span> <span data-ttu-id="375d4-119">サーバー上のメモリ内のデータセットの作成が遅い場合でも、この点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="375d4-119">Consider it even if the creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="375d4-120">メソッドを使用`stream`する場合</span><span class="sxs-lookup"><span data-stu-id="375d4-120">When to use `stream` methods</span></span>

<span data-ttu-id="375d4-121">データセット内のメッセージ オブジェクトが非常に大きい可能性がある場合は、ストリーミング要求または応答を使用して転送することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="375d4-121">When the message objects in your datasets are potentially very large, it's best for you transfer them by using streaming requests or responses.</span></span> <span data-ttu-id="375d4-122">メモリ内に大きなオブジェクトを構築し、ネットワークに書き込み、リソースを解放する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="375d4-122">It's more efficient to construct a large object in memory, write it to the network, and then free up the resources.</span></span> <span data-ttu-id="375d4-123">この方法を使用すると、サービスのスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="375d4-123">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="375d4-124">同様に、制約のないサイズのデータセットをストリームに送信して、構成中にメモリ不足が発生しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="375d4-124">Similarly, you should send datasets of unconstrained size over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="375d4-125">コンシューマーが各項目を個別に処理できるデータセットの場合、進行状況をユーザーに示すことができる場合は、ストリームの使用を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="375d4-125">For datasets where the consumer can separately process each item, you should consider using a stream if it means that progress can be indicated to the user.</span></span> <span data-ttu-id="375d4-126">ストリームを使用すると、アプリケーションの応答性を向上させることができますが、アプリケーションの全体的なパフォーマンスとのバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="375d4-126">Using a stream can improve the responsiveness of an application, but you should balance it against the overall performance of the application.</span></span>

<span data-ttu-id="375d4-127">ストリームが役立つもう 1 つのシナリオは、メッセージが複数のサービスで処理されている場合です。</span><span class="sxs-lookup"><span data-stu-id="375d4-127">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="375d4-128">チェーン内の各サービスがストリームを返す場合、ターミナル サービス (つまり、チェーンの最後のサービス) がメッセージを返し始めることができます。</span><span class="sxs-lookup"><span data-stu-id="375d4-128">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages.</span></span> <span data-ttu-id="375d4-129">これらのメッセージは処理され、チェーンに沿って元のリクエスターに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="375d4-129">These messages can be processed and passed back along the chain to the original requestor.</span></span> <span data-ttu-id="375d4-130">リクエスタは、ストリームを返すか、結果を単一の応答メッセージに集約できます。</span><span class="sxs-lookup"><span data-stu-id="375d4-130">The requestor can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="375d4-131">このアプローチは、MapReduce のようなパターンに適しています。</span><span class="sxs-lookup"><span data-stu-id="375d4-131">This approach lends itself well to patterns like MapReduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="375d4-132">[前次](migrate-duplex-services.md)
>[Next](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="375d4-132">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
