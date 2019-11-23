---
title: 運用環境の gRPC-WCF 開発者向け gRPC
description: 運用環境での gRPC アプリケーションの実行 ASP.NET Core
ms.date: 09/02/2019
ms.openlocfilehash: f30252b9937353b8670f509a245694f89512ba30
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967803"
---
# <a name="grpc-in-production"></a><span data-ttu-id="1a121-103">運用環境の gRPC</span><span class="sxs-lookup"><span data-stu-id="1a121-103">gRPC in production</span></span>

<span data-ttu-id="1a121-104">GRPC サービスを含む ASP.NET Core 3.0 アプリケーションは、Docker や Kubernetes などの最新のプラットフォームを使用して、Windows、Linux、およびコンテナーで実行できます。</span><span class="sxs-lookup"><span data-stu-id="1a121-104">ASP.NET Core 3.0 applications, including gRPC services, can be run on Windows, Linux, and in containers using modern platforms like Docker and Kubernetes.</span></span> <span data-ttu-id="1a121-105">この章では、運用環境で gRPC サービスを実行するためのさまざまなオプションについて説明します。また、監視とログのオプションを調べて、システムを最適に運用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="1a121-105">This chapter will explore the various options for running your gRPC services in production, and look at monitoring and logging options to ensure the optimal operation of systems.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1a121-106">[前へ](encryption.md)
>[次へ](self-hosted.md)</span><span class="sxs-lookup"><span data-stu-id="1a121-106">[Previous](encryption.md)
[Next](self-hosted.md)</span></span>
