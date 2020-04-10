---
title: ASP.NET Core および Azure での最新の Web アプリケーションの設計
description: ASP.NET Core と Azure を使用したモノリシックな Web アプリケーションの構築に関するエンドツーエンドのガイダンスを提供するガイドです。
author: ardalis
ms.author: wiwagn
ms.date: 12/4/2019
ms.openlocfilehash: 18449ea02b7f9e89744a0f3088f80b7a51a807da
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2020
ms.locfileid: "80987895"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="6d4ff-103">ASP.NET Core および Azure での最新の Web アプリケーションの設計</span><span class="sxs-lookup"><span data-stu-id="6d4ff-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

![最新の Web アプリケーションの設計ガイドのブック カバー画像。](./media/index/web-application-guide-cover-image.png)

<span data-ttu-id="6d4ff-105">**エディション v3.1** - ASP.NET Core 3.1 に更新</span><span class="sxs-lookup"><span data-stu-id="6d4ff-105">**EDITION v3.1** - Updated to ASP.NET Core 3.1</span></span>

<span data-ttu-id="6d4ff-106">発行者</span><span class="sxs-lookup"><span data-stu-id="6d4ff-106">PUBLISHED BY</span></span>

<span data-ttu-id="6d4ff-107">Microsoft 開発部門、.NET および Visual Studio 製品チーム</span><span class="sxs-lookup"><span data-stu-id="6d4ff-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="6d4ff-108">A division of Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="6d4ff-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="6d4ff-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="6d4ff-109">One Microsoft Way</span></span>

<span data-ttu-id="6d4ff-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="6d4ff-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="6d4ff-111">Copyright © 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="6d4ff-111">Copyright © 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="6d4ff-112">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="6d4ff-112">All rights reserved.</span></span> <span data-ttu-id="6d4ff-113">本書のいかなる部分も、書面による発行者の許可なしに、いかなる形式または方法によっても、複製または伝送することを禁じます。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="6d4ff-114">本書は "現状有姿" で提供され、著者の見解と意見を表しています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="6d4ff-115">URL および他の参照されているインターネットの Web サイトをはじめ、本書に記載されている見解、意見、および情報は、通知なく変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-115">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="6d4ff-116">ここに記載したいくつかの例は、説明のためだけに提供された架空のものです。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="6d4ff-117">実在のものとの関連性または関係性は一切ありません。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="6d4ff-118">https://www.microsoft.com の "商標" Web ページに記載されている Microsoft および商標は、Microsoft グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-118">Microsoft and the trademarks listed at https://www.microsoft.com on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="6d4ff-119">Mac および macOS は Apple Inc. の商標です。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="6d4ff-120">Docker のクジラのロゴは Docker, Inc. の登録商標です。許可を得て使用しています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="6d4ff-121">その他のすべてのマークおよびロゴは、該当する各社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="6d4ff-122">作成者:</span><span class="sxs-lookup"><span data-stu-id="6d4ff-122">Author:</span></span>

> <span data-ttu-id="6d4ff-123">**Steve "ardalis" Smith** - ソフトウェア アーキテクトおよびトレーナー - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="6d4ff-123">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="6d4ff-124">編集者:</span><span class="sxs-lookup"><span data-stu-id="6d4ff-124">Editors:</span></span>

> <span data-ttu-id="6d4ff-125">**Maira Wenzel**</span><span class="sxs-lookup"><span data-stu-id="6d4ff-125">**Maira Wenzel**</span></span>

## <a name="introduction"></a><span data-ttu-id="6d4ff-126">はじめに</span><span class="sxs-lookup"><span data-stu-id="6d4ff-126">Introduction</span></span>

<span data-ttu-id="6d4ff-127">.NET Core と ASP.NET Core は、従来の .NET 開発よりも優れたいくつかの利点を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-127">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="6d4ff-128">次の一部またはすべてがアプリケーションの成功に重要な場合は、サーバー アプリケーションに .NET Core を使用してください。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-128">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

- <span data-ttu-id="6d4ff-129">クロス プラットフォーム サポート。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-129">Cross-platform support.</span></span>

- <span data-ttu-id="6d4ff-130">マイクロサービスの使用。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-130">Use of microservices.</span></span>

- <span data-ttu-id="6d4ff-131">Docker コンテナーの使用。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-131">Use of Docker containers.</span></span>

- <span data-ttu-id="6d4ff-132">高パフォーマンスとスケーラビリティの要件。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-132">High performance and scalability requirements.</span></span>

- <span data-ttu-id="6d4ff-133">同じサーバー上のアプリケーション別の .NET バージョンのサイド バイ サイドのバージョン管理。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-133">Side-by-side versioning of .NET versions by application on the same server.</span></span>

<span data-ttu-id="6d4ff-134">従来の .NET アプリケーションはこれらの要件の多くをサポートできますが、ASP.NET Core と .NET Core は、上記のシナリオに対する改善されたサポートを提供するように最適化されています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-134">Traditional .NET applications can and do support many of these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="6d4ff-135">ますます多くの組織が、Microsoft Azure などのサービスを使用してクラウドで Web アプリケーションをホストすることを選択しています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-135">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="6d4ff-136">アプリケーションまたは組織にとって次のことが重要な場合は、クラウドでのアプリケーションのホストを検討してください。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-136">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

- <span data-ttu-id="6d4ff-137">データ センターのコストに対する投資の削減 (ハードウェア、ソフトウェア、スペース、ユーティリティ、サーバー管理など)。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-137">Reduced investment in data center costs (hardware, software, space, utilities, server management, etc.)</span></span>

- <span data-ttu-id="6d4ff-138">柔軟な料金 (アイドル状態の容量ではなく、使用量に基づく支払い)。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-138">Flexible pricing (pay based on usage, not for idle capacity).</span></span>

- <span data-ttu-id="6d4ff-139">極限の信頼性。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-139">Extreme reliability.</span></span>

- <span data-ttu-id="6d4ff-140">強化されたアプリのモビリティ。アプリが展開されている場所と方法を簡単に変更できること。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-140">Improved app mobility; easily change where and how your app is deployed.</span></span>

- <span data-ttu-id="6d4ff-141">柔軟な容量。実際のニーズに基づいたスケール アップまたはスケール ダウン。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-141">Flexible capacity; scale up or down based on actual needs.</span></span>

<span data-ttu-id="6d4ff-142">Azure でホストされる ASP.NET Core での Web アプリケーションを構築すると、従来型の代替手段よりも優れた多くの競争上の優位性が得られます。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-142">Building web applications with ASP.NET Core, hosted in Azure, offers many competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="6d4ff-143">ASP.NET Core は、最新の Web アプリケーションの開発作業とクラウド ホスティングのシナリオ用に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-143">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="6d4ff-144">このガイドでは、これらの機能を最適に活用するために ASP.NET Core アプリケーションを設計する方法を学習します。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-144">In this guide, you'll learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="6d4ff-145">目的</span><span class="sxs-lookup"><span data-stu-id="6d4ff-145">Purpose</span></span>

<span data-ttu-id="6d4ff-146">このガイドでは、ASP.NET Core と Azure を使った "*モノリシック*" Web アプリケーションの構築に関するエンド ツー エンドのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-146">This guide provides end-to-end guidance on building *monolithic* web applications using ASP.NET Core and Azure.</span></span> <span data-ttu-id="6d4ff-147">このコンテキストにおける "モノリシック" とは、相互作用するサービスとアプリケーションのコレクションとしてではなく、単一のユニットとしてこれらのアプリケーションをデプロイするという意味です。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-147">In this context, "monolithic" refers to the fact that these applications are deployed as a single unit, not as a collection of interacting services and applications.</span></span>

<span data-ttu-id="6d4ff-148">このガイドは、エンタープライズ アプリケーションをホストするために Docker、マイクロサービス、およびコンテナーのデプロイに注目した、[" _.NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ_"](../microservices/index.md) を補完するものです。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-148">This guide is complementary to the ["_.NET Microservices. Architecture for Containerized .NET Applications_"](../microservices/index.md) which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

### <a name="net-microservices-architecture-for-containerized-net-applications"></a><span data-ttu-id="6d4ff-149">.NET マイクロサービス。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-149">.NET Microservices.</span></span> <span data-ttu-id="6d4ff-150">コンテナー化された .NET アプリケーションのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="6d4ff-150">Architecture for Containerized .NET Applications</span></span>

- <span data-ttu-id="6d4ff-151">**電子ブック**</span><span class="sxs-lookup"><span data-stu-id="6d4ff-151">**e-book**</span></span>  
  <https://aka.ms/MicroservicesEbook>
- <span data-ttu-id="6d4ff-152">**サンプル アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="6d4ff-152">**Sample Application**</span></span>  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="6d4ff-153">対象読者</span><span class="sxs-lookup"><span data-stu-id="6d4ff-153">Who should use this guide</span></span>

<span data-ttu-id="6d4ff-154">このガイドの対象ユーザーは、主にクラウドでの Microsoft テクノロジとサービスを使用した最新の Web アプリケーションの構築に関心がある開発者、開発担当者、およびアーキテクトです。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-154">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="6d4ff-155">2 番目の対象ユーザーは、ASP.NET や Azure を既に使い慣れていて、新規または既存のプロジェクトに対して ASP.NET Core にアップグレードすることに意味があるかどうかに関する情報を探している技術的な意思決定者です。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-155">A secondary audience is technical decision makers who are already familiar ASP.NET or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="6d4ff-156">このガイドを使用する方法</span><span class="sxs-lookup"><span data-stu-id="6d4ff-156">How you can use this guide</span></span>

<span data-ttu-id="6d4ff-157">このガイドは、最新の .NET テクノロジと Windows Azure を使用した Web アプリケーションの構築に焦点を当てた比較的小さなドキュメントに凝縮されています。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-157">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="6d4ff-158">そのため、このようなアプリケーションと、技術的な考慮事項を理解するための基盤を提供するものとして、全体を読むことができます。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-158">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="6d4ff-159">ガイドは、サンプル アプリケーションと共に、最初に参照するものとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-159">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="6d4ff-160">関連するサンプル アプリケーションをテンプレートとして使用するか、アプリケーションのコンポーネント部分を整理する方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-160">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="6d4ff-161">独自のアプリケーションでこれらの選択肢を比較検討する場合、ガイドの基本原則とアーキテクチャのカバレッジ、テクノロジのオプション、および決定時の考慮事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-161">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when you're weighing these choices for your own application.</span></span>

<span data-ttu-id="6d4ff-162">これらの考慮事項と営業案件の共通理解を確保するために、チームにこのガイドを自由に転送してください。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-162">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="6d4ff-163">用語の共通セットと基本原則を理解して全員が作業すると、アーキテクチャのパターンと実践方法を一貫して適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6d4ff-163">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="6d4ff-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="6d4ff-164">References</span></span>

- <span data-ttu-id="6d4ff-165">**サーバー アプリ用 .NET Core と .NET Framework の選択**</span><span class="sxs-lookup"><span data-stu-id="6d4ff-165">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  [https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server](../../standard/choosing-core-framework-server.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="6d4ff-166">次へ</span><span class="sxs-lookup"><span data-stu-id="6d4ff-166">Next</span></span>](modern-web-applications-characteristics.md)
