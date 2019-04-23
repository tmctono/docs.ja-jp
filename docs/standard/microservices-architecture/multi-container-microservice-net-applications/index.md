---
title: 複数のコンテナーとマイクロサービス ベースの NET アプリケーションのデザインと開発
description: '.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | 複数のコンテナーとマイクロサービス ベースの NET アプリケーションをデザインおよび開発するための外部アーキテクチャを理解します。'
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/02/2018
ms.openlocfilehash: 3bbf746aa9c0b66a097b8c4df2964b5679342fd0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973629"
---
# <a name="designing-and-developing-multi-container-and-microservice-based-net-applications"></a><span data-ttu-id="8701e-103">複数のコンテナーとマイクロサービス ベースの NET アプリケーションのデザインと開発</span><span class="sxs-lookup"><span data-stu-id="8701e-103">Designing and Developing Multi-Container and Microservice-Based .NET Applications</span></span>

<span data-ttu-id="8701e-104">*コンテナー化されたマイクロサービス アプリケーションを開発しているということは、複数コンテナーのアプリケーションを構築しているということです。ただし、複数コンテナーのアプリケーションは、単純である可能性があり (3 層アプリケーションなど)、マイクロサービス アーキテクチャを使って構築されない場合があります。*</span><span class="sxs-lookup"><span data-stu-id="8701e-104">*Developing containerized microservice applications means you are building multi-container applications. However, a multi-container application could also be simpler—for example, a three-tier application—and might not be built using a microservice architecture.*</span></span>

<span data-ttu-id="8701e-105">以前に "マイクロサービス アーキテクチャを構築するときに Docker は必要か?" という疑問を提起しました。</span><span class="sxs-lookup"><span data-stu-id="8701e-105">Earlier we raised the question "Is Docker necessary when building a microservice architecture?"</span></span> <span data-ttu-id="8701e-106">その答えは、明らかに "いいえ" です。</span><span class="sxs-lookup"><span data-stu-id="8701e-106">The answer is a clear no.</span></span> <span data-ttu-id="8701e-107">Docker は拡張機能であり、大きな利点を提供できますが、コンテナーおよび Docker はマイクロサービスのハード要件ではありません。</span><span class="sxs-lookup"><span data-stu-id="8701e-107">Docker is an enabler and can provide significant benefits, but containers and Docker are not a hard requirement for microservices.</span></span> <span data-ttu-id="8701e-108">たとえば、簡単なプロセスまたは Docker コンテナーとして実行されているマイクロサービスをサポートする、Azure Service Fabric を使用している場合、Docker の有無にかかわらず、マイクロサービス ベースのアプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8701e-108">As an example, you could create a microservices-based application with or without Docker when using Azure Service Fabric, which supports microservices running as simple processes or as Docker containers.</span></span>

<span data-ttu-id="8701e-109">ただし、Docker コンテナーにも基づくマイクロサービス ベースのアプリケーションをデザインおよび開発する方法を知っている場合、その他の単純なアプリケーション モデルをデザインおよび開発することができます。</span><span class="sxs-lookup"><span data-stu-id="8701e-109">However, if you know how to design and develop a microservices-based application that is also based on Docker containers, you will be able to design and develop any other, simpler application model.</span></span> <span data-ttu-id="8701e-110">たとえば、複数コンテナーの手法も必要とする、3 層のアプリケーションをデザインする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8701e-110">For example, you might design a three-tier application that also requires a multi-container approach.</span></span> <span data-ttu-id="8701e-111">そのために、また、マイクロサービス アーキテクチャはコンテナーの世界で重要なトレンドであるため、このセクションでは、Docker コンテナーを使用するマイクロサービス アーキテクチャの実装に注目します。</span><span class="sxs-lookup"><span data-stu-id="8701e-111">Because of that, and because microservice architectures are an important trend within the container world, this section focuses on a microservice architecture implementation using Docker containers.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8701e-112">[前へ](../docker-application-development-process/docker-app-development-workflow.md)
>[次へ](microservice-application-design.md)</span><span class="sxs-lookup"><span data-stu-id="8701e-112">[Previous](../docker-application-development-process/docker-app-development-workflow.md)
[Next](microservice-application-design.md)</span></span>