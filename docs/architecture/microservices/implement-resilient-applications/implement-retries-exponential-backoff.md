---
title: エクスポネンシャル バックオフを含む再試行を実装する
description: エクスポネンシャル バックオフを含む再試行を実装する方法について説明します。
ms.date: 10/16/2018
ms.openlocfilehash: 1b948e399495eeb12016006442ac08d2b04f2e69
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2019
ms.locfileid: "68674539"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="80255-103">エクスポネンシャル バックオフを含む再試行を実装する</span><span class="sxs-lookup"><span data-stu-id="80255-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="80255-104">[*エクスポネンシャル バックオフを含む再試行*](/azure/architecture/patterns/retry)は、最大再試行回数に達するまで、指数関数的に増加する待機時間で操作を再試行する手法です ([エクスポネンシャル バックオフ](https://en.wikipedia.org/wiki/Exponential_backoff))。</span><span class="sxs-lookup"><span data-stu-id="80255-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="80255-105">この手法を利用すると、何らかの理由でクラウド リソースが数秒以上断続的に使用できなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80255-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="80255-106">たとえば、オーケストレーターは、負荷分散のためにコンテナーをクラスター内の別ノードに移動している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80255-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="80255-107">その間は、一部の要求が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="80255-107">During that time, some requests might fail.</span></span> <span data-ttu-id="80255-108">また、SQL Azure のようなデータベースで、負荷分散のためにデータベースを別のサーバーに移動しているときに、データベースを数秒間使用できなくなる例もあります。</span><span class="sxs-lookup"><span data-stu-id="80255-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="80255-109">エクスポネンシャル バックオフを使用する再試行ロジックを実装するには、さまざまなアプローチがあります。</span><span class="sxs-lookup"><span data-stu-id="80255-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="80255-110">[前へ](partial-failure-strategies.md)
>[次へ](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="80255-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
