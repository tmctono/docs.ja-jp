---
title: クラウドネイティブアプリケーションのスケーリング
description: クラウドネイティブアプリケーションを Azure Kubernetes Service と Azure Functions に拡張して、コスト効率に優れた方法でユーザーの要求を満たすことができます。
ms.date: 05/13/2020
ms.openlocfilehash: d425976eed248461a9c2e4fe03596f9f6dfd2eba
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613734"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="3bf8c-103">クラウドネイティブアプリケーションのスケーリング</span><span class="sxs-lookup"><span data-stu-id="3bf8c-103">Scaling cloud-native applications</span></span>

<span data-ttu-id="3bf8c-104">クラウドホスティング環境に移行することによって売りされる最大の利点の1つは、スケーラビリティです。</span><span class="sxs-lookup"><span data-stu-id="3bf8c-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="3bf8c-105">スケーラビリティ、またはアプリケーションがユーザーごとにパフォーマンスを損なうことなく追加のユーザー負荷を受け入れる機能。</span><span class="sxs-lookup"><span data-stu-id="3bf8c-105">Scalability, or the ability for an application to accept additional user load without compromising performance for each user.</span></span> <span data-ttu-id="3bf8c-106">多くの場合、アプリケーションを小さな部分に分割して、それぞれに必要なリソースを指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3bf8c-106">It's most often achieved by breaking up an application into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="3bf8c-107">クラウドベンダーは、世界中のどこでも、いつでも大規模なスケーラビリティを実現します。</span><span class="sxs-lookup"><span data-stu-id="3bf8c-107">Cloud vendors enable massive scalability anytime and anywhere in the world.</span></span>

 <span data-ttu-id="3bf8c-108">この章では、クラウドネイティブアプリケーションをユーザーのニーズに合わせて拡張できるようにするテクノロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3bf8c-108">In this chapter, we discuss technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="3bf8c-109">これらのテクノロジには以下のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3bf8c-109">These technologies include:</span></span>

- <span data-ttu-id="3bf8c-110">Containers</span><span class="sxs-lookup"><span data-stu-id="3bf8c-110">Containers</span></span>
- <span data-ttu-id="3bf8c-111">オーケストレーター</span><span class="sxs-lookup"><span data-stu-id="3bf8c-111">Orchestrators</span></span>
- <span data-ttu-id="3bf8c-112">サーバーレス コンピューティング</span><span class="sxs-lookup"><span data-stu-id="3bf8c-112">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3bf8c-113">[前へ](centralized-configuration.md)
>[次へ](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="3bf8c-113">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
