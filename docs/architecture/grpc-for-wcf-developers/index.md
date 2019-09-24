---
title: WCF 開発者向け ASP.NET Core gRPC - WCF 開発者向け gRPC
description: 記述予定
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 7d02d7914aed39613b4a41da55515df80abddfe8
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182749"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="9077b-103">WCF 開発者向け ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="9077b-103">ASP.NET Core gRPC for WCF Developers</span></span>

![カバーの画像](./media/cover.png)

<span data-ttu-id="9077b-105">発行者</span><span class="sxs-lookup"><span data-stu-id="9077b-105">PUBLISHED BY</span></span>

<span data-ttu-id="9077b-106">Microsoft 開発部門、.NET および Visual Studio 製品チーム</span><span class="sxs-lookup"><span data-stu-id="9077b-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="9077b-107">A division of Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9077b-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="9077b-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="9077b-108">One Microsoft Way</span></span>

<span data-ttu-id="9077b-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="9077b-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="9077b-110">Copyright © 2019 by Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="9077b-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="9077b-111">All rights reserved.</span><span class="sxs-lookup"><span data-stu-id="9077b-111">All rights reserved.</span></span> <span data-ttu-id="9077b-112">本書のいかなる部分も、書面による発行者の許可なしに、いかなる形式または方法によっても、複製または伝送することを禁じます。</span><span class="sxs-lookup"><span data-stu-id="9077b-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="9077b-113">本書は "現状有姿" で提供され、著者の見解と意見を表しています。</span><span class="sxs-lookup"><span data-stu-id="9077b-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="9077b-114">URL および他の参照されているインターネットの Web サイトをはじめ、本書に記載されている見解、意見、および情報は、通知なく変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="9077b-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="9077b-115">ここに記載したいくつかの例は、説明のためだけに提供された架空のものです。</span><span class="sxs-lookup"><span data-stu-id="9077b-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="9077b-116">実在のものとの関連性または関係性は一切ありません。</span><span class="sxs-lookup"><span data-stu-id="9077b-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="9077b-117">[https://www.microsoft.com](https://www.microsoft.com ) の "商標" Web ページに記載されている Microsoft および商標は、Microsoft グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="9077b-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="9077b-118">Docker のクジラのロゴは Docker, Inc. の登録商標です。許可を得て使用しています。</span><span class="sxs-lookup"><span data-stu-id="9077b-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="9077b-119">その他のすべてのマークおよびロゴは、該当する各社が所有しています。</span><span class="sxs-lookup"><span data-stu-id="9077b-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="9077b-120">作成者:</span><span class="sxs-lookup"><span data-stu-id="9077b-120">Author:</span></span>

> <span data-ttu-id="9077b-121">**Mark Rendle** - 技術部門最高責任者 - [Visual ReCode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="9077b-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="9077b-122">**Miranda Steiner** - 技術文書作成者</span><span class="sxs-lookup"><span data-stu-id="9077b-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="9077b-123">編集者:</span><span class="sxs-lookup"><span data-stu-id="9077b-123">Editors:</span></span>

> <span data-ttu-id="9077b-124">**Maira Wenzel** - シニア コンテンツ開発者 - Microsoft</span><span class="sxs-lookup"><span data-stu-id="9077b-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="9077b-125">はじめに</span><span class="sxs-lookup"><span data-stu-id="9077b-125">Introduction</span></span>

<span data-ttu-id="9077b-126">TODO</span><span class="sxs-lookup"><span data-stu-id="9077b-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="9077b-127">目的</span><span class="sxs-lookup"><span data-stu-id="9077b-127">Purpose</span></span>

<span data-ttu-id="9077b-128">TODO</span><span class="sxs-lookup"><span data-stu-id="9077b-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="9077b-129">対象読者</span><span class="sxs-lookup"><span data-stu-id="9077b-129">Who should use this guide</span></span>

<span data-ttu-id="9077b-130">**これを更新する**</span><span class="sxs-lookup"><span data-stu-id="9077b-130">**UPDATE THIS**</span></span>

<span data-ttu-id="9077b-131">本ガイドの対象読者は、gRPC サービスを利用して .NET 4 以前の WCF ソリューションを ASP.NET Core 3.0 に移行することに関心がある WCF 開発者、開発リーダー、アーキテクトです。</span><span class="sxs-lookup"><span data-stu-id="9077b-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="9077b-132">このガイドを使用する方法</span><span class="sxs-lookup"><span data-stu-id="9077b-132">How you can use this guide</span></span>

<span data-ttu-id="9077b-133">**これを更新する**</span><span class="sxs-lookup"><span data-stu-id="9077b-133">**UPDATE THIS**</span></span>

<span data-ttu-id="9077b-134">本書では ASP.NET Core 3.0 で gRPC サービスを構築する方法を簡単に説明しています。特に、同類のプラットフォームとして WCF を参照しています。</span><span class="sxs-lookup"><span data-stu-id="9077b-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="9077b-135">gRPC の原則について説明しており、各概念をそれに相当する WCF の機能に関連付けています。また、既存の WCF アプリケーションを gRPC に移行する方法を紹介しています。</span><span class="sxs-lookup"><span data-stu-id="9077b-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="9077b-136">WCF の経験があり、新しいサービスを構築する目的で gRPC の知識を求めている開発者にとっても役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9077b-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="9077b-137">サンプル アプリケーションは独自のプロジェクトのためのテンプレートまたは参照として利用できます。本書やそのサンプルのコードは自由にコピーしたり、再利用したりしてかまいません。</span><span class="sxs-lookup"><span data-stu-id="9077b-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="9077b-138">これらの考慮事項と営業案件の共通理解を確保するために、チームにこのガイドを自由に転送してください。</span><span class="sxs-lookup"><span data-stu-id="9077b-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="9077b-139">用語の共通セットと基本原則を理解して全員が作業すると、アーキテクチャのパターンと実践方法を一貫して適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9077b-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="9077b-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="9077b-140">References</span></span>

- <span data-ttu-id="9077b-141">**gRPC Web サイト**</span><span class="sxs-lookup"><span data-stu-id="9077b-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="9077b-142">**サーバー アプリ用 .NET Core と .NET Framework の選択**</span><span class="sxs-lookup"><span data-stu-id="9077b-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="9077b-143">次へ</span><span class="sxs-lookup"><span data-stu-id="9077b-143">Next</span></span>](introduction.md)
