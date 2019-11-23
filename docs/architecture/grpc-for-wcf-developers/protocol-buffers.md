---
title: プロトコルバッファー-WCF 開発者向け gRPC
description: GRPC ネットワークに使用されるプロトコルバッファーワイヤ形式の概要。
ms.date: 09/09/2019
ms.openlocfilehash: dbe8cb43475cfeec19051daf68452ef86269372f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967287"
---
# <a name="protocol-buffers"></a><span data-ttu-id="8a4ba-103">プロトコルバッファー</span><span class="sxs-lookup"><span data-stu-id="8a4ba-103">Protocol buffers</span></span>

<span data-ttu-id="8a4ba-104">gRPC サービスは、WCF のデータコントラクトと同様に、データを*プロトコルバッファー (Protobuf) メッセージ*として送受信します。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="8a4ba-105">Protobuf は、XML や JSON などの人間が判読できる形式のオーバーヘッドを発生させることなく、マシン用の構造化データを読み書きするための効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="8a4ba-106">この章では、Protobuf のしくみと、独自の Protobuf メッセージの定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="8a4ba-107">Protobuf のしくみ</span><span class="sxs-lookup"><span data-stu-id="8a4ba-107">How Protobuf works</span></span>

<span data-ttu-id="8a4ba-108">WCF のデータコントラクトを含むほとんどの .NET オブジェクトのシリアル化手法は、リフレクションを使用して実行時にオブジェクト構造を分析することで機能します。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="8a4ba-109">これに対し、ほとんどの Protobuf ライブラリでは、`.proto` ファイルで専用言語 (*プロトコルバッファー言語*) を使用して、構造を事前に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="8a4ba-110">このファイルは、.NET、Java、C/C++、JavaScript など、サポートされているプラットフォームのいずれかのコードを生成するために、コンパイラによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="8a4ba-111">Protobuf コンパイラ (`protoc`) は Google によって管理されますが、代替の実装は使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="8a4ba-112">生成されたコードは効率的で、データの高速なシリアル化と逆シリアル化のために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="8a4ba-113">Protobuf wire 形式自体はバイナリエンコードです。これは、メッセージを表すために使用されるバイト数を最小限に抑えるために、いくつかの巧妙な手法を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="8a4ba-114">Protobuf を使用するためにバイナリエンコード形式の知識は必要ありませんが、関心がある場合は[、プロトコルバッファーの web サイト](https://developers.google.com/protocol-buffers/docs/encoding)で詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8a4ba-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8a4ba-115">[前へ](why-grpc.md)
>[次へ](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="8a4ba-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
