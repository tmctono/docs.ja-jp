---
title: コンテナーと Docker の概要
description: Docker を使用することの主な利点を概説します。
ms.date: 02/15/2019
ms.openlocfilehash: 9ac08a64cd2465b4b88a266c1ec0925f37680bf9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "73738172"
---
# <a name="introduction-to-containers-and-docker"></a><span data-ttu-id="1d237-103">コンテナーと Docker の概要</span><span class="sxs-lookup"><span data-stu-id="1d237-103">Introduction to containers and Docker</span></span>

<span data-ttu-id="1d237-104">*コンテナリゼーションは、ソフトウェア開発のアプローチであり、アプリケーションまたはサービス、その依存関係、その構成 (デプロイ マニフェスト ファイルとして抽象化) がコンテナー イメージとしてパッケージ化されます。次に、コンテナー化アプリケーションをユニットとしてテストし、ホスト オペレーティング システム (OS) にコンテナー イメージ インスタンスとして展開することができます。*</span><span class="sxs-lookup"><span data-stu-id="1d237-104">*Containerization is an approach to software development in which an application or service, its dependencies, and its configuration (abstracted as deployment manifest files) are packaged together as a container image. You then can test the containerized application as a unit and deploy it as a container image instance to the host operating system (OS).*</span></span>

<span data-ttu-id="1d237-105">輸送用のコンテナーが、内部の貨物に関係なく商品を船舶、列車、またはトラックによって輸送できるのと同様に、ソフトウェア コンテナーは、別のコードと依存関係を含めることができるソフトウェア デプロイの標準的なユニットとして機能します。</span><span class="sxs-lookup"><span data-stu-id="1d237-105">Just as shipping containers allow goods to be transported by ship, train, or truck regardless of the cargo inside, software containers act as a standard unit of software deployment that can contain different code and dependencies.</span></span> <span data-ttu-id="1d237-106">ソフトウェアをこのようにコンテナー化することで、開発者や IT プロフェッショナルは、ほとんどまたはまったく変更せずに環境全体にソフトウェアを展開できます。</span><span class="sxs-lookup"><span data-stu-id="1d237-106">Containerizing software this way enables developers and IT professionals to deploy them across environments with little or no modification.</span></span>

<span data-ttu-id="1d237-107">コンテナーは、共有 OS 上で個々のアプリケーションも分離します。</span><span class="sxs-lookup"><span data-stu-id="1d237-107">Containers also isolate applications from each other on a shared OS.</span></span> <span data-ttu-id="1d237-108">コンテナー化アプリケーションは、さらに、OS (Linux または Windows) で実行されているコンテナー ホスト上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="1d237-108">Containerized applications run on top of a container host that in turn runs on the OS (Linux or Windows).</span></span> <span data-ttu-id="1d237-109">したがって、コンテナーは、仮想マシン (VM) のイメージよりも占有領域が大幅に小さくなります。</span><span class="sxs-lookup"><span data-stu-id="1d237-109">Containers therefore have a much smaller footprint than virtual machine (VM) images.</span></span>

<span data-ttu-id="1d237-110">各コンテナーは、図 1-1 に示すように、Web アプリケーションまたはサービスの全体を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="1d237-110">Each container can run a whole web application or a service, as shown in Figure 1-1.</span></span> <span data-ttu-id="1d237-111">この例では、Docker ホストはコンテナー ホストであり、App1、App2、Svc1、Svc2 はコンテナー化されたアプリケーションまたはサービスです。</span><span class="sxs-lookup"><span data-stu-id="1d237-111">In this example, Docker host is a container host, and App1, App2, Svc1, and Svc2 are containerized applications or services.</span></span>

![VM またはサーバーで実行されている 4 つのコンテナーを示す図。](./media/index/multiple-containers-single-host.png)

<span data-ttu-id="1d237-113">**(図 1-1)** 。</span><span class="sxs-lookup"><span data-stu-id="1d237-113">**Figure 1-1**.</span></span> <span data-ttu-id="1d237-114">コンテナー ホストで実行されている複数のコンテナー</span><span class="sxs-lookup"><span data-stu-id="1d237-114">Multiple containers running on a container host</span></span>

<span data-ttu-id="1d237-115">コンテナリゼーションから得られるもう 1 つの利点はスケーラビリティです。</span><span class="sxs-lookup"><span data-stu-id="1d237-115">Another benefit you can derive from containerization is scalability.</span></span> <span data-ttu-id="1d237-116">短期的なタスク用の新しいコンテナーを作成することでに簡単にスケール アウトできます。</span><span class="sxs-lookup"><span data-stu-id="1d237-116">You can scale out quickly by creating new containers for short-term tasks.</span></span> <span data-ttu-id="1d237-117">アプリケーションの観点から、イメージのインスタンス化 (コンテナーの作成) は、サービスまたは Web アプリのようなプロセスのインスタンス化に似ています。</span><span class="sxs-lookup"><span data-stu-id="1d237-117">From an application point of view, instantiating an image (creating a container) is similar to instantiating a process like a service or web app.</span></span> <span data-ttu-id="1d237-118">ただし、信頼性のために、同じイメージの複数のインスタンスを複数のホスト サーバーで実行するときには通常、各コンテナー (イメージのインスタンス) を異なるフォールト ドメイン内の別のホスト サーバーまたは VM で実行します。</span><span class="sxs-lookup"><span data-stu-id="1d237-118">For reliability, however, when you run multiple instances of the same image across multiple host servers, you typically want each container (image instance) to run in a different host server or VM in different fault domains.</span></span>

<span data-ttu-id="1d237-119">つまり、コンテナーには、アプリケーション ライフサイクル ワークフロー全体にわたり、分離、移植性、機敏性、スケーラビリティ、コントロールの利点があります。</span><span class="sxs-lookup"><span data-stu-id="1d237-119">In short, containers offer the benefits of isolation, portability, agility, scalability, and control across the entire application lifecycle workflow.</span></span> <span data-ttu-id="1d237-120">最も重要な利点は、開発と運用間で提供される環境の分離です。</span><span class="sxs-lookup"><span data-stu-id="1d237-120">The most important benefit is the environment isolation provided between Dev and Ops.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="1d237-121">次へ</span><span class="sxs-lookup"><span data-stu-id="1d237-121">Next</span></span>](what-is-docker.md)
