---
title: .NET でのセキュリティ
description: .NET でのセキュリティについて説明します。 主要なセキュリティの概念、ロールベースのセキュリティ、暗号化モデル、および安全なコーディングのガイドラインについて説明するリンクに従ってください。
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
ms.openlocfilehash: 21511b580a4f922d2aef04cc79f5d551f0406b45
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767820"
---
# <a name="security-in-net"></a><span data-ttu-id="7f731-104">.NET でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="7f731-104">Security in .NET</span></span>

<span data-ttu-id="7f731-105">共通言語ランタイムと .NET には、開発者が安全なコードを簡単に記述し、保護されたリソースにアクセスできるように、システム管理者がコードに付与されたアクセス許可をカスタマイズできるようにする、便利なクラスとサービスが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f731-105">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="7f731-106">さらに、ランタイムと .NET には、暗号化とロールベースのセキュリティの使用を容易にする便利なクラスとサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f731-106">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7f731-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7f731-107">In this section</span></span>

- [<span data-ttu-id="7f731-108">セキュリティの基本概念</span><span class="sxs-lookup"><span data-stu-id="7f731-108">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="7f731-109">共通言語ランタイムのセキュリティ機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="7f731-109">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="7f731-110">このセクションは開発者およびシステム管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7f731-110">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="7f731-111">ロール ベースのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="7f731-111">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="7f731-112">コード内でロール ベースのセキュリティと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f731-112">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="7f731-113">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7f731-113">This section is of interest to developers.</span></span>

- [<span data-ttu-id="7f731-114">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="7f731-114">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="7f731-115">.NET で提供される暗号化サービスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f731-115">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="7f731-116">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7f731-116">This section is of interest to developers.</span></span>

- [<span data-ttu-id="7f731-117">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="7f731-117">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="7f731-118">Reliable .NET アプリケーションを作成するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7f731-118">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="7f731-119">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="7f731-119">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7f731-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f731-120">Related sections</span></span>

[<span data-ttu-id="7f731-121">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="7f731-121">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="7f731-122">アプリケーションの作成、構成、デバッグ、セキュリティ、配置、および動的プログラミング、相互運用性、拡張性、メモリ管理、スレッド処理に関する情報を含む、アプリケーション開発用の主要な技術領域とタスクのすべてについての手引書です。</span><span class="sxs-lookup"><span data-stu-id="7f731-122">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
