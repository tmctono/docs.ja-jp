---
title: Azure 向けクラウド ネイティブ .NET アプリケーションの設計
description: Azure のコンテナー、マイクロサービス、サーバーレス機能を活用するクラウドネイティブなアプリケーションを構築するためのガイド。
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: ce9898366d0327dd619b36cdf1487229d9cda7f5
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182713"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="9d06f-103">Azure 向けクラウド ネイティブ .NET アプリケーションの設計</span><span class="sxs-lookup"><span data-stu-id="9d06f-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![カバーの画像](./media/cover.png)

<span data-ttu-id="9d06f-105">発行者</span><span class="sxs-lookup"><span data-stu-id="9d06f-105">PUBLISHED BY</span></span>

<span data-ttu-id="9d06f-106">Microsoft 開発部門、.NET および Visual Studio 製品チーム</span><span class="sxs-lookup"><span data-stu-id="9d06f-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="9d06f-107">A division of Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9d06f-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="9d06f-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9d06f-108">One Microsoft Way</span></span>

<span data-ttu-id="9d06f-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="9d06f-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="9d06f-110">Copyright © 2019 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9d06f-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="9d06f-111">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="9d06f-111">All rights reserved.</span></span> <span data-ttu-id="9d06f-112">本書のいかなる部分も、書面による発行者の許可なしに、いかなる形式または方法によっても、複製または伝送することを禁じます。</span><span class="sxs-lookup"><span data-stu-id="9d06f-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="9d06f-113">本書は "現状有姿" で提供され、著者の見解と意見を表しています。</span><span class="sxs-lookup"><span data-stu-id="9d06f-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="9d06f-114">URL および他の参照されているインターネットの Web サイトをはじめ、本書に記載されている見解、意見、および情報は、通知なく変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="9d06f-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="9d06f-115">ここに記載したいくつかの例は、説明のためだけに提供された架空のものです。</span><span class="sxs-lookup"><span data-stu-id="9d06f-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="9d06f-116">実在のものとの関連性または関係性は一切ありません。</span><span class="sxs-lookup"><span data-stu-id="9d06f-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="9d06f-117">[https://www.microsoft.com](https://www.microsoft.com ) の "商標" Web ページに記載されている Microsoft および商標は、Microsoft グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="9d06f-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="9d06f-118">Mac および macOS は Apple Inc. の商標です。</span><span class="sxs-lookup"><span data-stu-id="9d06f-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="9d06f-119">Docker のクジラのロゴは Docker, Inc. の登録商標です。許可を得て使用しています。</span><span class="sxs-lookup"><span data-stu-id="9d06f-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="9d06f-120">その他のすべてのマークおよびロゴは、該当する各社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="9d06f-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="9d06f-121">作成者:</span><span class="sxs-lookup"><span data-stu-id="9d06f-121">Author:</span></span>

> <span data-ttu-id="9d06f-122">**Steve "ardalis" Smith** - ソフトウェア アーキテクトおよびトレーナー - [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="9d06f-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="9d06f-123">**Rob Vettor** - Microsoft - プリンシパル クラウド システム アーキテクト/IP アーキテクト - [RobVettor.com](https://robvettor.com)</span><span class="sxs-lookup"><span data-stu-id="9d06f-123">**Rob Vettor** - Microsoft - Principal Cloud System Architect/IP Architect - [RobVettor.com](https://robvettor.com)</span></span>

<span data-ttu-id="9d06f-124">参加者とレビュー担当者:</span><span class="sxs-lookup"><span data-stu-id="9d06f-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="9d06f-125">**Cesar De la Torre**、Microsoft、.NET チーム、プリンシパル プログラム マネージャー</span><span class="sxs-lookup"><span data-stu-id="9d06f-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="9d06f-126">**Nish Anil**、Microsoft、.NET チーム、シニア プログラム マネージャー</span><span class="sxs-lookup"><span data-stu-id="9d06f-126">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>

<span data-ttu-id="9d06f-127">編集者:</span><span class="sxs-lookup"><span data-stu-id="9d06f-127">Editors:</span></span>

> <span data-ttu-id="9d06f-128">**Maira Wenzel**、Microsoft、.NET チーム、コンテンツ開発者</span><span class="sxs-lookup"><span data-stu-id="9d06f-128">**Maira Wenzel**, Sr. Content Developer, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="9d06f-129">対象読者</span><span class="sxs-lookup"><span data-stu-id="9d06f-129">Who should use this guide</span></span>

<span data-ttu-id="9d06f-130">本ガイドの対象読者は主に、クラウド向けに設計されたアプリケーションを構築する方法に関心がある開発者、開発リーダー、アーキテクトです。</span><span class="sxs-lookup"><span data-stu-id="9d06f-130">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="9d06f-131">2 番目の対象読者は、クラウドネイティブな手法でアプリケーションを構築するかどうかを決定する予定の技術部門の意思決定者です。</span><span class="sxs-lookup"><span data-stu-id="9d06f-131">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="9d06f-132">このガイドを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9d06f-132">How you can use this guide</span></span>

<span data-ttu-id="9d06f-133">本書ではまず、クラウド ネイティブを定義し、クラウドネイティブなプリンシパルとテクノロジで構築された参照アプリケーションを紹介します。</span><span class="sxs-lookup"><span data-stu-id="9d06f-133">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="9d06f-134">その最初の 2 章以降、本書の残りの部分は、ほとんどのクラウドネイティブ アプリケーションに共通するトピックに特化した章に分割されています。</span><span class="sxs-lookup"><span data-stu-id="9d06f-134">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="9d06f-135">任意の章までジャンプし、次に関するクラウドネイティブ手法について知ることができます。</span><span class="sxs-lookup"><span data-stu-id="9d06f-135">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="9d06f-136">データとデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="9d06f-136">Data and data access</span></span>
- <span data-ttu-id="9d06f-137">通信パターン</span><span class="sxs-lookup"><span data-stu-id="9d06f-137">Communication patterns</span></span>
- <span data-ttu-id="9d06f-138">スケーリングとスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="9d06f-138">Scaling and scalability</span></span>
- <span data-ttu-id="9d06f-139">アプリケーションの回復性</span><span class="sxs-lookup"><span data-stu-id="9d06f-139">Application resiliency</span></span>
- <span data-ttu-id="9d06f-140">監視と正常性</span><span class="sxs-lookup"><span data-stu-id="9d06f-140">Monitoring and health</span></span>
- <span data-ttu-id="9d06f-141">ID とセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9d06f-141">Identity and security</span></span>
- <span data-ttu-id="9d06f-142">DevOps</span><span class="sxs-lookup"><span data-stu-id="9d06f-142">DevOps</span></span>

<span data-ttu-id="9d06f-143">このガイドは PDF 形式とオンラインの両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="9d06f-143">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="9d06f-144">本書やそのオンライン版のリンクをチームに転送し、トピックの共通理解に役立ててください。</span><span class="sxs-lookup"><span data-stu-id="9d06f-144">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="9d06f-145">トピックのほとんどは、基礎的な原則、基礎的なパターン、トピックに関連する意思決定に関係する折り合いが同じように理解されることで効果を発揮します。</span><span class="sxs-lookup"><span data-stu-id="9d06f-145">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="9d06f-146">本書の目標は、アプリケーションのアーキテクチャ、開発、ホスティングについて、十分に情報が与えられた上で意思決定するために必要な情報をチームとそのリーダーに与えることです。</span><span class="sxs-lookup"><span data-stu-id="9d06f-146">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="9d06f-147">次へ</span><span class="sxs-lookup"><span data-stu-id="9d06f-147">Next</span></span>](introduction.md)
