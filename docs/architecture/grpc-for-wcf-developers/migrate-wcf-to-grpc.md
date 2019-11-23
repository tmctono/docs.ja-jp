---
title: Wcf 開発者向けの gRPC-gRPC への WCF ソリューションの移行
description: GRPC で異なる種類の WCF サービスを同等のものに移行する方法について説明します。
ms.date: 09/02/2019
ms.openlocfilehash: 33823d20e1593323a03da12981c5a4534c4d491a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971770"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="1b040-103">WCF ソリューションを gRPC に移行する</span><span class="sxs-lookup"><span data-stu-id="1b040-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="1b040-104">この章では、ASP.NET Core 3.0 gRPC プロジェクトを操作する方法と、異なる種類の WCF サービスを同等の gRPC に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1b040-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="1b040-105">ASP.NET Core 3.0 gRPC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="1b040-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="1b040-106">GRPC 単項 RPC への単純な要求/応答操作。</span><span class="sxs-lookup"><span data-stu-id="1b040-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="1b040-107">GRPC クライアントストリーミング RPC への一方向操作。</span><span class="sxs-lookup"><span data-stu-id="1b040-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="1b040-108">GRPC 双方向ストリーミング RPC への全二重サービス。</span><span class="sxs-lookup"><span data-stu-id="1b040-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="1b040-109">また、ストリーミングサービスの使用と、データセットを返すための繰り返しフィールドと、章の最後にクライアントライブラリを使用する方法の比較もあります。</span><span class="sxs-lookup"><span data-stu-id="1b040-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="1b040-110">サンプル WCF アプリケーションは、依存関係の挿入のために*Autofac*というオープンソースのコントロールの反転 (IoC) コンテナーライブラリを使用して、一連の stock 取引サービスの最小スタブです。</span><span class="sxs-lookup"><span data-stu-id="1b040-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="1b040-111">これには、WCF サービスの種類ごとに1つずつ、3つのサービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1b040-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="1b040-112">これらのサービスについては、以降のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="1b040-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="1b040-113">ソリューションは、GitHub の[dotnet/grpc-wcf-開発者](https://github.com/dotnet-architecture/grpc-for-wcf-developers)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="1b040-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="1b040-114">サービスは、偽のデータを使用して外部の依存関係を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="1b040-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="1b040-115">サンプルには、各サービスの WCF および gRPC 実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1b040-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1b040-116">[前へ](ws-protocols.md)
>[次へ](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="1b040-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
