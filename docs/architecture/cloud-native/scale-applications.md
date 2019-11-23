---
title: クラウドネイティブアプリケーションのスケーリング
description: クラウドネイティブアプリケーションを Azure Kubernetes Service と Azure Functions に拡張して、コスト効率に優れた方法でユーザーの要求を満たすことができます。
ms.date: 09/23/2019
ms.openlocfilehash: 5f4aac5804c5498c331787083c943a6ea1b69748
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841031"
---
# <a name="scaling-cloud-native-applications"></a><span data-ttu-id="acfe2-103">クラウドネイティブアプリケーションのスケーリング</span><span class="sxs-lookup"><span data-stu-id="acfe2-103">Scaling cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="acfe2-104">クラウドホスティング環境に移行することによって売りされる最大の利点の1つは、スケーラビリティです。</span><span class="sxs-lookup"><span data-stu-id="acfe2-104">One of the most-often touted advantages of moving to a cloud hosting environment is scalability.</span></span> <span data-ttu-id="acfe2-105">スケーラビリティ、またはアプリケーションが各ユーザーのパフォーマンスを大幅に低下させることなく追加のユーザー負荷を受け入れることが最も多いのは、アプリケーションを小さな部分に分割し、それぞれに必要なリソースをそれぞれ指定できるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="acfe2-105">Scalability, or the ability for an application to accept additional user load without unduly degrading performance for each user, is most often achieved by breaking up applications into small pieces that can each be given whatever resources they require.</span></span> <span data-ttu-id="acfe2-106">この章では、クラウドネイティブアプリケーションをユーザーのニーズに合わせて拡張できるようにするテクノロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="acfe2-106">In this chapter, we introduce the technologies that enable cloud-native applications to scale to meet user demand.</span></span> <span data-ttu-id="acfe2-107">次のようなテクノロジがあります。</span><span class="sxs-lookup"><span data-stu-id="acfe2-107">These technologies include:</span></span>

- <span data-ttu-id="acfe2-108">コンテナー</span><span class="sxs-lookup"><span data-stu-id="acfe2-108">Containers</span></span>
- <span data-ttu-id="acfe2-109">オーケストレーター</span><span class="sxs-lookup"><span data-stu-id="acfe2-109">Orchestrators</span></span>
- <span data-ttu-id="acfe2-110">サーバーレスコンピューティング</span><span class="sxs-lookup"><span data-stu-id="acfe2-110">Serverless computing</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="acfe2-111">[前へ](centralized-configuration.md)
>[次へ](leverage-containers-orchestrators.md)</span><span class="sxs-lookup"><span data-stu-id="acfe2-111">[Previous](centralized-configuration.md)
[Next](leverage-containers-orchestrators.md)</span></span>
