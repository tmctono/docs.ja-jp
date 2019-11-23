---
title: GRPC-gRPC の WCF 開発者向けの概要
description: GRPC の開発に関する一連の原則について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: a92fe7ca2f8e17126025362fcc3c190024ebf7d3
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967761"
---
# <a name="grpc-overview"></a><span data-ttu-id="a63a4-103">gRPC の概要</span><span class="sxs-lookup"><span data-stu-id="a63a4-103">gRPC overview</span></span>

<span data-ttu-id="a63a4-104">この章では、最後の章で WCF と gRPC の両方の genesis を確認した後、gRPC の主な機能と WCF との比較について説明します。</span><span class="sxs-lookup"><span data-stu-id="a63a4-104">After looking at the genesis of both WCF and gRPC in the last chapter, this chapter will consider some of the key features of gRPC and how they compare to WCF.</span></span>

<span data-ttu-id="a63a4-105">ASP.NET Core 3.0 は、grpc をファーストクラスの市民としてネイティブにサポートする ASP.NET の最初のリリースであり、gRPC の公式の .NET 実装に貢献する Microsoft チームがいます。</span><span class="sxs-lookup"><span data-stu-id="a63a4-105">ASP.NET Core 3.0 is the first release of ASP.NET that natively supports gRPC as a first-class citizen, with Microsoft teams contributing to the official .NET implementation of gRPC.</span></span> <span data-ttu-id="a63a4-106">他のすべての主要なプログラミング言語とフレームワークと相互運用できる .NET を使用して分散アプリケーションを構築する場合は、この方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a63a4-106">It's recommended as the best approach for building distributed applications with .NET that can interoperate with all other major programming languages and frameworks.</span></span>

## <a name="key-principles"></a><span data-ttu-id="a63a4-107">主要原則</span><span class="sxs-lookup"><span data-stu-id="a63a4-107">Key principles</span></span>

<span data-ttu-id="a63a4-108">第1章で説明したように、Google は、Stubby、その内部、汎用 RPC インフラストラクチャを置き換えるために、HTTP/2 の導入を使用する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="a63a4-108">As discussed in chapter 1, Google wanted to use the introduction of HTTP/2 to replace Stubby, its internal, general purpose RPC infrastructure.</span></span> <span data-ttu-id="a63a4-109">Stubby に基づく gRPC は、標準化を利用し、モバイルコンピューティング、クラウド、およびモノのインターネットへの適用性を拡張できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a63a4-109">gRPC, based on Stubby, now could take advantage of standardization and would extend its applicability to mobile computing, the cloud, and the Internet of Things.</span></span>

<span data-ttu-id="a63a4-110">これを実現するために、[クラウドネイティブコンピューティングファンデーション (CNCF)](https://www.cncf.io/)は grpc を管理する一連の原則を確立しました。</span><span class="sxs-lookup"><span data-stu-id="a63a4-110">To achieve this, the [Cloud Native Computing Foundation (CNCF)](https://www.cncf.io/) established a set of principles that would govern gRPC.</span></span> <span data-ttu-id="a63a4-111">次の一覧は最も関連性の高いものを示しています。主にアクセシビリティと使いやすさを最大限に活用することに関係しています。</span><span class="sxs-lookup"><span data-stu-id="a63a4-111">The following list shows the most relevant ones, which are mainly concerned with maximizing accessibility and usability:</span></span>

- <span data-ttu-id="a63a4-112">**Free と open** –すべての成果物は、開発者が grpc の採用を制限しない、ライセンス付きのオープンソースである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a63a4-112">**Free and open** – all artifacts should be open source with licensing that doesn't constrain developers from adopting gRPC.</span></span>
- <span data-ttu-id="a63a4-113">**カバレッジとシンプル**さ– grpc は、すべての一般的なプラットフォームで利用可能であり、任意のプラットフォームで構築するのに十分である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a63a4-113">**Coverage and simplicity** – gRPC should be available across every popular platform and simple enough to build on any platform.</span></span>
- <span data-ttu-id="a63a4-114">**相互運用性と接続性**-広く使用可能なネットワーク標準を使用して、帯域幅や待ち時間に関係なく、grpc を任意のネットワークで使用することができます。</span><span class="sxs-lookup"><span data-stu-id="a63a4-114">**Interoperability and reach** – it should be possible to use gRPC on any network, regardless of bandwidth or latency, using widely available network standards.</span></span>
- <span data-ttu-id="a63a4-115">**一般的な目的と**パフォーマンスの向上–パフォーマンスを低下させずに、可能な限り幅広いユースケースでフレームワークを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a63a4-115">**General purpose and performant** – the framework should be usable by as broad a range of use-cases as possible without compromising performance.</span></span>
- <span data-ttu-id="a63a4-116">**ストリーミング**–プロトコルは、大規模なデータセットまたは非同期メッセージングのストリーミングセマンティクスを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a63a4-116">**Streaming** – the protocol should provide streaming semantics for large data-sets or asynchronous messaging.</span></span>
- <span data-ttu-id="a63a4-117">**メタデータ交換**–プロトコルを使用すると、認証トークンなどの非ビジネスデータを実際のビジネスデータとは別に処理できます。</span><span class="sxs-lookup"><span data-stu-id="a63a4-117">**Metadata exchange** – the protocol allow non-business data, such as authentication tokens, to be handled separately from actual business data.</span></span>
- <span data-ttu-id="a63a4-118">標準化された**状態コード**–エラー処理の決定を明確にするために、エラーコードの変動を減らす必要があります。さらに充実したエラー処理が必要な場合は、メタデータ交換内でこれを管理するためのメカニズムを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a63a4-118">**Standardized status codes** – the variability of error codes should be reduced to make error handling decisions clearer and, where additional richer error handling is required, a mechanism should be provided for managing this within the metadata exchange.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a63a4-119">[前へ](introduction.md)
>[次へ](approach.md)</span><span class="sxs-lookup"><span data-stu-id="a63a4-119">[Previous](introduction.md)
[Next](approach.md)</span></span>
