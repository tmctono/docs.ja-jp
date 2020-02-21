---
title: プロトコルバッファー-WCF 開発者向け gRPC
description: GRPC ネットワークに使用されるプロトコルバッファーワイヤ形式の概要。
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503456"
---
# <a name="protocol-buffers"></a><span data-ttu-id="7694d-103">プロトコルバッファー</span><span class="sxs-lookup"><span data-stu-id="7694d-103">Protocol buffers</span></span>

<span data-ttu-id="7694d-104">gRPC サービスは、Windows Communication Foundation (WCF) のデータコントラクトと同様に、データを*プロトコルバッファー (Protobuf) メッセージ*として送受信します。</span><span class="sxs-lookup"><span data-stu-id="7694d-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="7694d-105">Protobuf は、XML や JSON などの人間が判読できる形式のオーバーヘッドを発生させることなく、マシン用の構造化データを読み書きするための効率的な方法です。</span><span class="sxs-lookup"><span data-stu-id="7694d-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="7694d-106">この章では、Protobuf のしくみと、独自の Protobuf メッセージの定義方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7694d-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="7694d-107">Protobuf のしくみ</span><span class="sxs-lookup"><span data-stu-id="7694d-107">How Protobuf works</span></span>

<span data-ttu-id="7694d-108">WCF のデータコントラクトを含むほとんどの .NET オブジェクトのシリアル化手法は、リフレクションを使用して実行時にオブジェクト構造を分析することで機能します。</span><span class="sxs-lookup"><span data-stu-id="7694d-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="7694d-109">これに対し、ほとんどの Protobuf ライブラリでは、`.proto` ファイルで専用言語 (*プロトコルバッファー言語*) を使用して、構造を事前に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7694d-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="7694d-110">コンパイラは、このファイルを使用して、サポートされている任意のプラットフォームのコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="7694d-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="7694d-111">サポートされているプラットフォームには、C++.Net、Java、C/、JavaScript などがあります。</span><span class="sxs-lookup"><span data-stu-id="7694d-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span> 

<span data-ttu-id="7694d-112">Protobuf コンパイラ (`protoc`) は Google によって管理されますが、代替の実装は使用できます。</span><span class="sxs-lookup"><span data-stu-id="7694d-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="7694d-113">生成されたコードは効率的で、データの高速なシリアル化と逆シリアル化のために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="7694d-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="7694d-114">Protobuf ワイヤ形式は、バイナリエンコードです。</span><span class="sxs-lookup"><span data-stu-id="7694d-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="7694d-115">メッセージを表すために使用されるバイト数を最小限に抑えるために、いくつかの巧妙なテクニックを使用します。</span><span class="sxs-lookup"><span data-stu-id="7694d-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="7694d-116">Protobuf を使用するために、バイナリエンコード形式の知識は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="7694d-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="7694d-117">ただし、詳細については、「[プロトコルバッファー」 web サイト](https://developers.google.com/protocol-buffers/docs/encoding)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7694d-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7694d-118">[前へ](why-grpc.md)
>[次へ](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="7694d-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
