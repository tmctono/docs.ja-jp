---
title: プロトコル バッファー - WCF 開発者向けの gRPC
description: gRPC ネットワーキングに使用されるプロトコル バッファの配線形式の概要。
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147933"
---
# <a name="protocol-buffers"></a><span data-ttu-id="5fd25-103">プロトコル バッファ</span><span class="sxs-lookup"><span data-stu-id="5fd25-103">Protocol buffers</span></span>

<span data-ttu-id="5fd25-104">gRPC サービスは、プロトコル*バッファー (Protobuf) メッセージ*としてデータを送受信する Windows 通信基盤 (WCF) のデータ コントラクトと同様です。</span><span class="sxs-lookup"><span data-stu-id="5fd25-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="5fd25-105">Protobuf は、XML や JSON などの人間が読み取り可能な形式で発生するオーバーヘッドを伴わずに、コンピューターが読み書きできるように構造化データを効率的にシリアル化する方法です。</span><span class="sxs-lookup"><span data-stu-id="5fd25-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="5fd25-106">この章では、Protobuf のしくみと、独自の Protobuf メッセージを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5fd25-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="5fd25-107">プロトブーフの仕組み</span><span class="sxs-lookup"><span data-stu-id="5fd25-107">How Protobuf works</span></span>

<span data-ttu-id="5fd25-108">WCF のデータ コントラクトを含むほとんどの .NET オブジェクトシリアル化手法は、実行時にオブジェクト構造を分析するリフレクションを使用して動作します。</span><span class="sxs-lookup"><span data-stu-id="5fd25-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="5fd25-109">一方、Protobuf ライブラリの多くは、ファイル内の専用言語 ( プロトコル*バッファ言語*) を`.proto`使用して、事前に構造を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd25-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="5fd25-110">コンパイラは、このファイルを使用して、サポートされているプラットフォームのコードを生成します。</span><span class="sxs-lookup"><span data-stu-id="5fd25-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="5fd25-111">サポートされるプラットフォームには、.NET、Java、C/C++、JavaScriptなどがあります。</span><span class="sxs-lookup"><span data-stu-id="5fd25-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span>

<span data-ttu-id="5fd25-112">Protobuf コンパイラは`protoc`、別の実装が利用可能ですが、Google によって保守されています。</span><span class="sxs-lookup"><span data-stu-id="5fd25-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="5fd25-113">生成されたコードは効率的で、データの高速なシリアル化と逆シリアル化に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="5fd25-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="5fd25-114">Protobuf ワイヤー形式はバイナリエンコーディングです。</span><span class="sxs-lookup"><span data-stu-id="5fd25-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="5fd25-115">メッセージを表すために使用されるバイト数を最小限に抑えるために、巧妙なトリックを使用します。</span><span class="sxs-lookup"><span data-stu-id="5fd25-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="5fd25-116">バイナリエンコーディング形式の知識は、Protobufを使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5fd25-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="5fd25-117">しかし、興味がある場合は、[プロトコルバッファのウェブサイト](https://developers.google.com/protocol-buffers/docs/encoding)で詳細を学ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="5fd25-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5fd25-118">[前次](why-grpc.md)
>[Next](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="5fd25-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
