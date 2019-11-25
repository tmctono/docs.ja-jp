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
ms.openlocfilehash: af2869e5ca3b41778c094b7a78a9493e74868811
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204506"
---
# <a name="security-changes-in-the-net-framework"></a><span data-ttu-id="24721-102">.NET Framework におけるセキュリティの変更点</span><span class="sxs-lookup"><span data-stu-id="24721-102">Security Changes in the .NET Framework</span></span>

<span data-ttu-id="24721-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span><span class="sxs-lookup"><span data-stu-id="24721-103">The most important change to security in the .NET Framework 4.5 is in strong naming.</span></span> <span data-ttu-id="24721-104">これらの変更の詳細については、「 [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24721-104">See [Enhanced Strong Naming](../../standard/assembly/enhanced-strong-naming.md) for a description of those changes.</span></span>  
  
<span data-ttu-id="24721-105">.NET Framework は、マネージド アプリケーションに 2 階層のセキュリティ モデルを提供します。</span><span class="sxs-lookup"><span data-stu-id="24721-105">The .NET Framework provides a two-tier security model for managed applications.</span></span> <span data-ttu-id="24721-106">Windows 8.x Store apps run in a Windows security container that limits access to resources.</span><span class="sxs-lookup"><span data-stu-id="24721-106">Windows 8.x Store apps run in a Windows security container that limits access to resources.</span></span> <span data-ttu-id="24721-107">そのコンテナー内では、マネージド アプリケーションは完全に信頼された状態で実行します。</span><span class="sxs-lookup"><span data-stu-id="24721-107">Within that container, managed applications run fully trusted.</span></span> <span data-ttu-id="24721-108">コード アクセス セキュリティの (CAS) の観点からは、権限を昇格するために開発者が実行できる操作はありません。</span><span class="sxs-lookup"><span data-stu-id="24721-108">From a code access security (CAS) perspective, there is nothing a developer can do to elevate privileges.</span></span> <span data-ttu-id="24721-109">Windows で与えられる権限の詳細については、Windows デベロッパー センターの「 [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) 」 (アプリの機能宣言 (Windows ストア アプリ)) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="24721-109">For information about the privileges granted by Windows, see [App capability declarations (Windows Store apps)](https://go.microsoft.com/fwlink/?LinkId=230436) in the Windows Dev Center.</span></span> <span data-ttu-id="24721-110">For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span><span class="sxs-lookup"><span data-stu-id="24721-110">For information about creating a Windows 8.x Store app, see [Create your first Windows Store app using C# or Visual Basic](https://go.microsoft.com/fwlink/?LinkId=230461).</span></span>
