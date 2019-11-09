---
title: Wcf 開発者向けの gRPC-gRPC への WCF ソリューションの移行
description: GRPC で異なる種類の WCF サービスを同等のものに移行する方法について説明します。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 65c30b777d9981cb3291b846f698f2a69b4498fc
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841499"
---
# <a name="migrate-a-wcf-solution-to-grpc"></a><span data-ttu-id="8eb1a-103">WCF ソリューションを gRPC に移行する</span><span class="sxs-lookup"><span data-stu-id="8eb1a-103">Migrate a WCF solution to gRPC</span></span>

<span data-ttu-id="8eb1a-104">この章では、ASP.NET Core 3.0 gRPC プロジェクトを操作する方法と、異なる種類の WCF サービスを同等の gRPC に移行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-104">This chapter will look at how to work with ASP.NET Core 3.0 gRPC projects and demonstrate migrating different types of WCF service to the gRPC equivalent:</span></span>

- <span data-ttu-id="8eb1a-105">ASP.NET Core 3.0 gRPC プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-105">Create an ASP.NET Core 3.0 gRPC project.</span></span>
- <span data-ttu-id="8eb1a-106">GRPC 単項 RPC への単純な要求/応答操作。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-106">Simple Request-Reply operations to gRPC unary RPC.</span></span>
- <span data-ttu-id="8eb1a-107">GRPC クライアントストリーミング RPC への一方向操作。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-107">One-way operations to gRPC client streaming RPC.</span></span>
- <span data-ttu-id="8eb1a-108">GRPC 双方向ストリーミング RPC への全二重サービス。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-108">Full Duplex services to gRPC bidirectional streaming RPC.</span></span>

<span data-ttu-id="8eb1a-109">また、ストリーミングサービスの使用と、データセットを返すための繰り返しフィールドと、章の最後にクライアントライブラリを使用する方法の比較もあります。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-109">There's also a comparison of using streaming services versus repeated fields for returning data sets, and the use of client libraries at the end of the chapter.</span></span>

<span data-ttu-id="8eb1a-110">サンプル WCF アプリケーションは、依存関係の挿入のために*Autofac*というオープンソースのコントロールの反転 (IoC) コンテナーライブラリを使用して、一連の stock 取引サービスの最小スタブです。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-110">The sample WCF application is a minimal stub of a set of stock trading services, using the open-source Inversion of Control (IoC) container library called *Autofac* for dependency injection.</span></span> <span data-ttu-id="8eb1a-111">これには、WCF サービスの種類ごとに1つずつ、3つのサービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-111">It includes three services, one for each WCF service type.</span></span> <span data-ttu-id="8eb1a-112">これらのサービスについては、以降のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-112">The services will be discussed in more detail in the following sections.</span></span> <span data-ttu-id="8eb1a-113">ソリューションは、GitHub の[dotnet/grpc-wcf-開発者](https://github.com/dotnet-architecture/grpc-for-wcf-developers)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-113">The solutions can be downloaded from [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers) on GitHub.</span></span> <span data-ttu-id="8eb1a-114">サービスは、偽のデータを使用して外部の依存関係を最小限に抑えます。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-114">The services use fake data to minimize external dependencies.</span></span>

<span data-ttu-id="8eb1a-115">サンプルには、各サービスの WCF および gRPC 実装が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8eb1a-115">The samples include the WCF and gRPC implementations of each service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8eb1a-116">[前へ](ws-protocols.md)
>[次へ](create-project.md)</span><span class="sxs-lookup"><span data-stu-id="8eb1a-116">[Previous](ws-protocols.md)
[Next](create-project.md)</span></span>
