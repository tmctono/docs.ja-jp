---
title: Docker コンテナー用 .NET Core と .NET Framework の選択
description: '.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | Docker コンテナー用 .NET Core と .NET Framework の選択'
ms.date: 09/11/2018
ms.openlocfilehash: b01aaf25f4071e8e4a07905a12ec9dd0d89a738d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "70849277"
---
# <a name="choosing-between-net-core-and-net-framework-for-docker-containers"></a><span data-ttu-id="1f3b8-103">Docker コンテナー用 .NET Core と .NET Framework の選択</span><span class="sxs-lookup"><span data-stu-id="1f3b8-103">Choosing Between .NET Core and .NET Framework for Docker Containers</span></span>

<span data-ttu-id="1f3b8-104">.NET を使用してサーバー側のコンテナー化された Docker アプリケーションをビルドする場合に選択できるサポート対象のフレームワークには、[.NET Framework と .NET Core](https://dotnet.microsoft.com/download) の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="1f3b8-104">There are two supported frameworks for building server-side containerized Docker applications with .NET: [.NET Framework and .NET Core](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="1f3b8-105">それらは多数の .NET プラットフォームのコンポーネントを共有しているため、両者でコードを共有できます。</span><span class="sxs-lookup"><span data-stu-id="1f3b8-105">They share many .NET platform components, and you can share code across the two.</span></span> <span data-ttu-id="1f3b8-106">ただし、それらには基本的な違いがあり、どちらのフレームワークを使用するかは実行内容によって決まります。</span><span class="sxs-lookup"><span data-stu-id="1f3b8-106">However, there are fundamental differences between them, and which framework you use will depend on what you want to accomplish.</span></span> <span data-ttu-id="1f3b8-107">このセクションでは、それぞれのフレームワークを選択する場合のガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f3b8-107">This section provides guidance on when to choose each framework.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1f3b8-108">[前へ](../container-docker-introduction/docker-containers-images-registries.md)
>[次へ](general-guidance.md)</span><span class="sxs-lookup"><span data-stu-id="1f3b8-108">[Previous](../container-docker-introduction/docker-containers-images-registries.md)
[Next](general-guidance.md)</span></span>
