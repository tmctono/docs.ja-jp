---
title: Azure 向けクラウド ネイティブ .NET アプリケーションの設計
description: Azure のコンテナー、マイクロサービス、サーバーレス機能を活用するクラウドネイティブなアプリケーションを構築するためのガイド。
author: ardalis
ms.date: 05/13/2020
ms.openlocfilehash: 172097b4915deb2d6f0b06441d7c4ca389bbca25
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051507"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="bcf7b-103">Azure 向けクラウド ネイティブ .NET アプリケーションの設計</span><span class="sxs-lookup"><span data-stu-id="bcf7b-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![カバーの画像](./media/cover.png)

<span data-ttu-id="bcf7b-105">**EDITION v.1.0**</span><span class="sxs-lookup"><span data-stu-id="bcf7b-105">**EDITION v.1.0**</span></span>

<span data-ttu-id="bcf7b-106">発行者</span><span class="sxs-lookup"><span data-stu-id="bcf7b-106">PUBLISHED BY</span></span>

<span data-ttu-id="bcf7b-107">Microsoft 開発部門、.NET および Visual Studio 製品チーム</span><span class="sxs-lookup"><span data-stu-id="bcf7b-107">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="bcf7b-108">A division of Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bcf7b-108">A division of Microsoft Corporation</span></span>

<span data-ttu-id="bcf7b-109">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="bcf7b-109">One Microsoft Way</span></span>

<span data-ttu-id="bcf7b-110">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="bcf7b-110">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="bcf7b-111">Copyright &copy; 2020 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="bcf7b-111">Copyright &copy; 2020 by Microsoft Corporation</span></span>

<span data-ttu-id="bcf7b-112">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="bcf7b-112">All rights reserved.</span></span> <span data-ttu-id="bcf7b-113">本書のいかなる部分も、書面による発行者の許可なしに、いかなる形式または方法によっても、複製または伝送することを禁じます。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-113">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="bcf7b-114">本書は "現状有姿" で提供され、著者の見解と意見を表しています。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-114">This book is provided "as-is" and expresses the author's views and opinions.</span></span> <span data-ttu-id="bcf7b-115">URL および他の参照されているインターネットの Web サイトをはじめ、本書に記載されている見解、意見、および情報は、通知なく変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-115">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="bcf7b-116">ここに記載したいくつかの例は、説明のためだけに提供された架空のものです。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-116">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="bcf7b-117">実在のものとの関連性または関係性は一切ありません。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-117">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="bcf7b-118"><https://www.microsoft.com> の "商標" Web ページに記載されている Microsoft および商標は、Microsoft グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-118">Microsoft and the trademarks listed at <https://www.microsoft.com> on the "Trademarks" webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="bcf7b-119">Mac および macOS は Apple Inc. の商標です。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-119">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="bcf7b-120">Docker のクジラのロゴは Docker, Inc. の登録商標です。許可を得て使用しています。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-120">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="bcf7b-121">その他のすべてのマークおよびロゴは、該当する各社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-121">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="bcf7b-122">作成者:</span><span class="sxs-lookup"><span data-stu-id="bcf7b-122">Authors:</span></span>

> <span data-ttu-id="bcf7b-123">**Rob Vettor**、Microsoft、プリンシパル クラウド システム アーキテクト/IP アーキテクト - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/)</span><span class="sxs-lookup"><span data-stu-id="bcf7b-123">**Rob Vettor**, Principal Cloud System Architect/IP Architect - [thinkingincloudnative.com](https://thinkingincloudnative.com/about/), Microsoft</span></span>
>
> <span data-ttu-id="bcf7b-124">**Steve "ardalis" Smith**、ソフトウェア アーキテクトおよびトレーナー - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="bcf7b-124">**Steve "ardalis" Smith**, Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>

<span data-ttu-id="bcf7b-125">参加者とレビュー担当者:</span><span class="sxs-lookup"><span data-stu-id="bcf7b-125">Participants and Reviewers:</span></span>

> <span data-ttu-id="bcf7b-126">**Cesar De la Torre**、Microsoft、.NET チーム、プリンシパル プログラム マネージャー</span><span class="sxs-lookup"><span data-stu-id="bcf7b-126">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="bcf7b-127">**Nish Anil**、Microsoft、.NET チーム、シニア プログラム マネージャー</span><span class="sxs-lookup"><span data-stu-id="bcf7b-127">**Nish Anil**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="bcf7b-128">**Jeremy Likness**、Microsoft、.NET チーム、シニア プログラム マネージャー</span><span class="sxs-lookup"><span data-stu-id="bcf7b-128">**Jeremy Likness**, Senior Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="bcf7b-129">**Cecil Phillip**、Microsoft、上級クラウド アドボケイト</span><span class="sxs-lookup"><span data-stu-id="bcf7b-129">**Cecil Phillip**, Senior Cloud Advocate, Microsoft</span></span>

<span data-ttu-id="bcf7b-130">編集者:</span><span class="sxs-lookup"><span data-stu-id="bcf7b-130">Editors:</span></span>

> <span data-ttu-id="bcf7b-131">**Maira Wenzel**、Microsoft、.NET チーム、シニア プログラム マネージャー</span><span class="sxs-lookup"><span data-stu-id="bcf7b-131">**Maira Wenzel**, Program Manager, .NET team, Microsoft</span></span>

## <a name="version"></a><span data-ttu-id="bcf7b-132">バージョン</span><span class="sxs-lookup"><span data-stu-id="bcf7b-132">Version</span></span>

<span data-ttu-id="bcf7b-133">このガイドは、 **.NET Core 3.1** バージョンと、.NET Core 3.1 のリリースと同時期に更新された関連するその他の多数の同じ “相次ぐ” テクノロジ (つまり、Azure やサードパーティ製のテクノロジ) を説明するように記述されています。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-133">This guide has been written to cover **.NET Core 3.1** version along with many additional updates related to the same “wave” of technologies (that is, Azure and additional third-party technologies) coinciding in time with the .NET Core 3.1 release.</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="bcf7b-134">対象読者</span><span class="sxs-lookup"><span data-stu-id="bcf7b-134">Who should use this guide</span></span>

<span data-ttu-id="bcf7b-135">本ガイドの対象読者は主に、クラウド向けに設計されたアプリケーションを構築する方法に関心がある開発者、開発リーダー、アーキテクトです。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-135">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="bcf7b-136">2 番目の対象読者は、クラウドネイティブな手法でアプリケーションを構築するかどうかを決定する予定の技術部門の意思決定者です。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-136">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="bcf7b-137">このガイドを使用する方法</span><span class="sxs-lookup"><span data-stu-id="bcf7b-137">How you can use this guide</span></span>

<span data-ttu-id="bcf7b-138">本書ではまず、クラウド ネイティブを定義し、クラウドネイティブなプリンシパルとテクノロジで構築された参照アプリケーションを紹介します。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-138">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="bcf7b-139">その最初の 2 章以降、本書の残りの部分は、ほとんどのクラウドネイティブ アプリケーションに共通するトピックに特化した章に分割されています。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-139">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="bcf7b-140">任意の章までジャンプし、次に関するクラウドネイティブ手法について知ることができます。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-140">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="bcf7b-141">データとデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="bcf7b-141">Data and data access</span></span>
- <span data-ttu-id="bcf7b-142">通信パターン</span><span class="sxs-lookup"><span data-stu-id="bcf7b-142">Communication patterns</span></span>
- <span data-ttu-id="bcf7b-143">スケーリングとスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="bcf7b-143">Scaling and scalability</span></span>
- <span data-ttu-id="bcf7b-144">アプリケーションの回復性</span><span class="sxs-lookup"><span data-stu-id="bcf7b-144">Application resiliency</span></span>
- <span data-ttu-id="bcf7b-145">監視と正常性</span><span class="sxs-lookup"><span data-stu-id="bcf7b-145">Monitoring and health</span></span>
- <span data-ttu-id="bcf7b-146">ID とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="bcf7b-146">Identity and security</span></span>
- <span data-ttu-id="bcf7b-147">DevOps</span><span class="sxs-lookup"><span data-stu-id="bcf7b-147">DevOps</span></span>

<span data-ttu-id="bcf7b-148">このガイドは [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) 形式とオンラインの両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-148">This guide is available both in [PDF](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf) form and online.</span></span> <span data-ttu-id="bcf7b-149">本書やそのオンライン版のリンクをチームに転送し、トピックの共通理解に役立ててください。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-149">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="bcf7b-150">トピックのほとんどは、基礎的な原則、基礎的なパターン、トピックに関連する意思決定に関係する折り合いが同じように理解されることで効果を発揮します。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-150">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="bcf7b-151">本書の目標は、アプリケーションのアーキテクチャ、開発、ホスティングについて、十分に情報が与えられた上で意思決定するために必要な情報をチームとそのリーダーに与えることです。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-151">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

## <a name="send-your-feedback"></a><span data-ttu-id="bcf7b-152">フィードバックの送信</span><span class="sxs-lookup"><span data-stu-id="bcf7b-152">Send your feedback</span></span>

<span data-ttu-id="bcf7b-153">本書と関連サンプルは継続的に更新されるので、お客様のフィードバックを歓迎しています。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-153">This book and related samples are constantly evolving, so your feedback is welcomed!</span></span> <span data-ttu-id="bcf7b-154">本書を改善する方法についてコメントがある場合、[GitHub の問題](https://github.com/dotnet/docs/issues)に関して作成されたあらゆるページの下部にあるフィードバック セクションをご利用ください。</span><span class="sxs-lookup"><span data-stu-id="bcf7b-154">If you have comments about how this book can be improved, use the feedback section at the bottom of any page built on [GitHub issues](https://github.com/dotnet/docs/issues).</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="bcf7b-155">次へ</span><span class="sxs-lookup"><span data-stu-id="bcf7b-155">Next</span></span>](introduction.md)
