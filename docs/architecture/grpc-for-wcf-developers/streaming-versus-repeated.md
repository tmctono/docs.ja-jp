---
title: ストリーミングサービスと繰り返しフィールド-WCF 開発者向け gRPC
description: GRPC を使用してデータのコレクションを渡す方法として、繰り返しフィールドをストリーミングサービスに比較します。
ms.date: 09/02/2019
ms.openlocfilehash: 0e717df57ba2bb52d63a063072d8a45bf0f7e395
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503369"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a><span data-ttu-id="3d42d-103">gRPC streaming services と繰り返されるフィールド</span><span class="sxs-lookup"><span data-stu-id="3d42d-103">gRPC streaming services vs. repeated fields</span></span>

<span data-ttu-id="3d42d-104">gRPC サービスには、データセットを返すための2つの方法、またはオブジェクトの一覧が用意されています。</span><span class="sxs-lookup"><span data-stu-id="3d42d-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="3d42d-105">プロトコルバッファーメッセージの指定では、別のメッセージ内のメッセージのリストまたは配列を宣言するために `repeated` キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="3d42d-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="3d42d-106">GRPC サービス仕様では、`stream` キーワードを使用して、長時間実行される永続的な接続を宣言します。</span><span class="sxs-lookup"><span data-stu-id="3d42d-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection.</span></span> <span data-ttu-id="3d42d-107">この接続では、複数のメッセージが送信され、個別に処理できます。</span><span class="sxs-lookup"><span data-stu-id="3d42d-107">Over that connection, multiple messages are sent, and can be processed, individually.</span></span> 

<span data-ttu-id="3d42d-108">`stream` 機能を使用して、通知やログメッセージなどの長時間実行されるテンポラルデータを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="3d42d-108">You can also use the `stream` feature for long-running temporal data such as notifications or log messages.</span></span> <span data-ttu-id="3d42d-109">ただし、この章では、1つのデータセットを返すための使用方法を検討します。</span><span class="sxs-lookup"><span data-stu-id="3d42d-109">But this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="3d42d-110">使用する必要がある要素は、次のような要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="3d42d-110">Which you should use depends on factors such as:</span></span>

- <span data-ttu-id="3d42d-111">データセットの全体的なサイズ。</span><span class="sxs-lookup"><span data-stu-id="3d42d-111">The overall size of the dataset.</span></span>
- <span data-ttu-id="3d42d-112">クライアント側またはサーバー側でデータセットを作成するために要した時間。</span><span class="sxs-lookup"><span data-stu-id="3d42d-112">The time it took to create the dataset at either the client or server end.</span></span>
- <span data-ttu-id="3d42d-113">最初のアイテムが使用可能になるとすぐにデータセットのコンシューマーがアクションを開始できるかどうか、またはすべてのデータセットを使用して有用な処理を行う必要があるかどうか。</span><span class="sxs-lookup"><span data-stu-id="3d42d-113">Whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="3d42d-114">`repeated` フィールドを使用する場合</span><span class="sxs-lookup"><span data-stu-id="3d42d-114">When to use `repeated` fields</span></span>

<span data-ttu-id="3d42d-115">サイズが制限され、短時間で完全に生成できるデータセットの場合 (1 秒未満の場合など) は、通常の Protobuf メッセージで `repeated` フィールドを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d42d-115">For any dataset that's constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="3d42d-116">たとえば、e コマースシステムでは、注文内の項目のリストを作成するのは簡単であり、リストが非常に大きくなるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="3d42d-116">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="3d42d-117">`repeated` フィールドを持つ1つのメッセージを返すのは、`stream` を使用する場合よりもはるかに高速であり、ネットワークオーバーヘッドが少なくなります。</span><span class="sxs-lookup"><span data-stu-id="3d42d-117">Returning a single message with a `repeated` field is an order of magnitude faster than using `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="3d42d-118">クライアントが処理を開始する前にすべてのデータを必要とし、データセットがメモリ内に構築するのに十分な大きさである場合は、`repeated` フィールドの使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="3d42d-118">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field.</span></span> <span data-ttu-id="3d42d-119">サーバー上のメモリ内のデータセットの作成速度が遅い場合でも、この点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3d42d-119">Consider it even if the creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="3d42d-120">`stream` メソッドを使用する場合</span><span class="sxs-lookup"><span data-stu-id="3d42d-120">When to use `stream` methods</span></span>

<span data-ttu-id="3d42d-121">データセット内のメッセージオブジェクトが非常に大きい可能性がある場合は、ストリーミング要求または応答を使用して転送することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d42d-121">When the message objects in your datasets are potentially very large, it's best for you transfer them by using streaming requests or responses.</span></span> <span data-ttu-id="3d42d-122">メモリ内に大きなオブジェクトを構築し、それをネットワークに書き込んでから、リソースを解放する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="3d42d-122">It's more efficient to construct a large object in memory, write it to the network, and then free up the resources.</span></span> <span data-ttu-id="3d42d-123">このアプローチにより、サービスのスケーラビリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="3d42d-123">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="3d42d-124">同様に、メモリが不足するのを防ぐために、無制限のサイズのデータセットをストリームに送信することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3d42d-124">Similarly, you should send datasets of unconstrained size over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="3d42d-125">コンシューマーが各項目を個別に処理できるデータセットの場合、進行状況をユーザーに示すことができる場合は、ストリームの使用を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d42d-125">For datasets where the consumer can separately process each item, you should consider using a stream if it means that progress can be indicated to the user.</span></span> <span data-ttu-id="3d42d-126">ストリームを使用すると、アプリケーションの応答性を向上させることができますが、アプリケーションの全体的なパフォーマンスとのバランスを取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d42d-126">Using a stream can improve the responsiveness of an application, but you should balance it against the overall performance of the application.</span></span>

<span data-ttu-id="3d42d-127">また、ストリームが役に立つ可能性があるもう1つのシナリオは、メッセージが複数のサービスにわたって処理される場所です。</span><span class="sxs-lookup"><span data-stu-id="3d42d-127">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="3d42d-128">チェーン内の各サービスが1つのストリームを返す場合は、ターミナルサービス (つまり、チェーン内の最後のサービス) がメッセージの返却を開始できます。</span><span class="sxs-lookup"><span data-stu-id="3d42d-128">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages.</span></span> <span data-ttu-id="3d42d-129">これらのメッセージは処理され、元の要求元にチェーンに従って戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="3d42d-129">These messages can be processed and passed back along the chain to the original requestor.</span></span> <span data-ttu-id="3d42d-130">要求元は、ストリームを返すか、結果を1つの応答メッセージに集約することができます。</span><span class="sxs-lookup"><span data-stu-id="3d42d-130">The requestor can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="3d42d-131">このアプローチは、MapReduce のようなパターンに適しています。</span><span class="sxs-lookup"><span data-stu-id="3d42d-131">This approach lends itself well to patterns like MapReduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3d42d-132">[前へ](migrate-duplex-services.md)
>[次へ](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="3d42d-132">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
