---
title: .NET Framework におけるセキュリティの変更点
ms.date: 03/30/2017
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f4cf91924e762495df6787a187e4295b69f2cd96
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045377"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="b0163-102">.NET Framework におけるセキュリティの変更点</span><span class="sxs-lookup"><span data-stu-id="b0163-102">Security Changes in the .NET Framework</span></span>

<span data-ttu-id="b0163-103">.NET Framework 4.5 でのセキュリティの最も重要な変更点は、厳密な名前付けです。</span><span class="sxs-lookup"><span data-stu-id="b0163-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span></span> <span data-ttu-id="b0163-104">これらの変更の詳細については、「 [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0163-104">See [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
<span data-ttu-id="b0163-105">.NET Framework は、マネージド アプリケーションに 2 階層のセキュリティ モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="b0163-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] <span data-ttu-id="b0163-106">アプリはリソースへのアクセスを制限する Windows セキュリティ コンテナーで実行されます。</span><span class="sxs-lookup"><span data-stu-id="b0163-106">apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="b0163-107">そのコンテナー内では、マネージド アプリケーションは完全に信頼された状態で実行します。</span><span class="sxs-lookup"><span data-stu-id="b0163-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="b0163-108">コード アクセス セキュリティの (CAS) の観点からは、権限を昇格するために開発者が実行できる操作はありません。</span><span class="sxs-lookup"><span data-stu-id="b0163-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="b0163-109">Windows で与えられる権限の詳細については、Windows デベロッパー センターの「 [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) 」 (アプリの機能宣言 (Windows ストア アプリ)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0163-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="b0163-110">[!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] アプリの作成については、「 [C# または Visual Basic を使った初めての Windows ストア アプリの作成](https://go.microsoft.com/fwlink/?LinkId=230461)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b0163-110">For information about creating a [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
