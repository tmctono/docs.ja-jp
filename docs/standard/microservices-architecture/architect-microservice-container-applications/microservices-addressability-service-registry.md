---
title: マイクロサービスのアドレス指定能力およびサービス レジストリ
description: マイクロサービス アーキテクチャ内のコンテナー イメージ レジストリの役割を理解します。
ms.date: 09/20/2018
ms.openlocfilehash: d72ba399f3da730f0e57c44c5ec01c1cc9f5fc05
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690462"
---
# <a name="microservices-addressability-and-the-service-registry"></a><span data-ttu-id="8345e-103">マイクロサービスのアドレス指定能力およびサービス レジストリ</span><span class="sxs-lookup"><span data-stu-id="8345e-103">Microservices addressability and the service registry</span></span>

<span data-ttu-id="8345e-104">各マイクロサービスには、その場所を解決するために使用する一意の名前 (URL) が付けられています。</span><span class="sxs-lookup"><span data-stu-id="8345e-104">Each microservice has a unique name (URL) that's used to resolve its location.</span></span> <span data-ttu-id="8345e-105">ご利用のマイクロサービスは、その実行場所にかかわらず、アドレス指定可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8345e-105">Your microservice needs to be addressable wherever it's running.</span></span> <span data-ttu-id="8345e-106">特定のマイクロサービスをどのコンピューターで実行するかについて考える必要がある場合、事態はすぐに悪化する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8345e-106">If you have to think about which computer is running a particular microservice, things can go bad quickly.</span></span> <span data-ttu-id="8345e-107">DNS が URL を特定のコンピューターに解決するのと同様に、マイクロサービスの現在の場所が探索できるようにマイクロサービスには一意の名前が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8345e-107">In the same way that DNS resolves a URL to a particular computer, your microservice needs to have a unique name so that its current location is discoverable.</span></span> <span data-ttu-id="8345e-108">マイクロサービスには、実行されているインフラストラクチャからマイクロサービスを独立させるためのアドレス指定可能な名前が必要です。</span><span class="sxs-lookup"><span data-stu-id="8345e-108">Microservices need addressable names that make them independent from the infrastructure that they're running on.</span></span> <span data-ttu-id="8345e-109">このことは、[サービス レジストリ](https://microservices.io/patterns/service-registry.html)が必要であるために、サービスの展開方法とサービスの検出方法との間には相互作用があることを意味しています。</span><span class="sxs-lookup"><span data-stu-id="8345e-109">This implies that there's an interaction between how your service is deployed and how it's discovered, because there needs to be a [service registry](https://microservices.io/patterns/service-registry.html).</span></span> <span data-ttu-id="8345e-110">同様に、コンピューターで障害が発生した場合、レジストリ サービスは、サービスが現在実行されている場所を示すことができなければなりません。</span><span class="sxs-lookup"><span data-stu-id="8345e-110">In the same vein, when a computer fails, the registry service must be able to indicate where the service is now running.</span></span>

<span data-ttu-id="8345e-111">[サービス レジストリ パターン](https://microservices.io/patterns/service-registry.html)は、サービス検出の重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="8345e-111">The [service registry pattern](https://microservices.io/patterns/service-registry.html) is a key part of service discovery.</span></span> <span data-ttu-id="8345e-112">レジストリは、サービス インスタンスのネットワークの場所を含むデータベースです。</span><span class="sxs-lookup"><span data-stu-id="8345e-112">The registry is a database containing the network locations of service instances.</span></span> <span data-ttu-id="8345e-113">サービス レジストリは、可用性が高く、最新の状態である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8345e-113">A service registry needs to be highly available and up-to-date.</span></span> <span data-ttu-id="8345e-114">クライアントは、サービス レジストリから取得したネットワークの場所をキャッシュすることが可能です。</span><span class="sxs-lookup"><span data-stu-id="8345e-114">Clients could cache network locations obtained from the service registry.</span></span> <span data-ttu-id="8345e-115">ただし、その情報は最終的には期限切れになり、クライアントはサービス インスタンスを検出できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8345e-115">However, that information eventually goes out of date and clients can no longer discover service instances.</span></span> <span data-ttu-id="8345e-116">したがって、サービス レジストリは、レプリケーション プロトコルを使用して整合性を維持するサーバーのクラスターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8345e-116">Consequently, a service registry consists of a cluster of servers that use a replication protocol to maintain consistency.</span></span>

<span data-ttu-id="8345e-117">一部のマイクロサービスの展開環境 (クラスターと呼ばれ、後のセクションで説明します) には、サービス検出が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="8345e-117">In some microservice deployment environments (called clusters, to be covered in a later section), service discovery is built-in.</span></span> <span data-ttu-id="8345e-118">たとえば、Kubernetes (AKS) 環境での Azure Container Service では、サービス インスタンスの登録と登録解除を処理できます。</span><span class="sxs-lookup"><span data-stu-id="8345e-118">For example, an Azure Container Service with Kubernetes (AKS) environment can handle service instance registration and deregistration.</span></span> <span data-ttu-id="8345e-119">また、これはサーバー側の検出ルーターの役割を果たす各クラスター ホスト上でプロキシも実行します。</span><span class="sxs-lookup"><span data-stu-id="8345e-119">It also runs a proxy on each cluster host that plays the role of server-side discovery router.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8345e-120">その他の技術情報</span><span class="sxs-lookup"><span data-stu-id="8345e-120">Additional resources</span></span>

- <span data-ttu-id="8345e-121">**Chris Richardson。パターン: サービス レジストリ** </span><span class="sxs-lookup"><span data-stu-id="8345e-121">**Chris Richardson. Pattern: Service registry** </span></span>\
  <https://microservices.io/patterns/service-registry.html>

- <span data-ttu-id="8345e-122">**Auth0。サービス レジストリ** </span><span class="sxs-lookup"><span data-stu-id="8345e-122">**Auth0. The Service Registry** </span></span>\
  <https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/>

- <span data-ttu-id="8345e-123">**Gabriel Schenker。サービス探索** </span><span class="sxs-lookup"><span data-stu-id="8345e-123">**Gabriel Schenker. Service discovery** </span></span>\
  <https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/>

>[!div class="step-by-step"]
><span data-ttu-id="8345e-124">[前へ](maintain-microservice-apis.md)
>[次へ](microservice-based-composite-ui-shape-layout.md)</span><span class="sxs-lookup"><span data-stu-id="8345e-124">[Previous](maintain-microservice-apis.md)
[Next](microservice-based-composite-ui-shape-layout.md)</span></span>
