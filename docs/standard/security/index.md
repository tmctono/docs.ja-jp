---
title: .NET でのセキュリティ
ms.date: 06/04/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, security
- security [.NET], about security
- application development [.NET], security
- security [.NET Framework]
- security [.NET]
ms.assetid: 9a9621d7-8883-4a4f-a874-65e8e09e20a6
ms.openlocfilehash: 2e4c289d7049fb587cdc9a4928f98852483fde5f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705994"
---
# <a name="security-in-net"></a><span data-ttu-id="8fdaf-102">.NET でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8fdaf-102">Security in .NET</span></span>

<span data-ttu-id="8fdaf-103">共通言語ランタイムと .NET には、開発者が安全なコードを簡単に記述し、保護されたリソースにアクセスできるように、システム管理者がコードに付与されたアクセス許可をカスタマイズできるようにする、便利なクラスとサービスが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="8fdaf-104">さらに、ランタイムと .NET には、暗号化とロールベースのセキュリティの使用を容易にする便利なクラスとサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="8fdaf-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8fdaf-105">In this section</span></span>

- [<span data-ttu-id="8fdaf-106">セキュリティの基本概念</span><span class="sxs-lookup"><span data-stu-id="8fdaf-106">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="8fdaf-107">共通言語ランタイムのセキュリティ機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="8fdaf-108">このセクションは開発者およびシステム管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-108">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="8fdaf-109">ロール ベースのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="8fdaf-109">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="8fdaf-110">コード内でロール ベースのセキュリティと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="8fdaf-111">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-111">This section is of interest to developers.</span></span>

- [<span data-ttu-id="8fdaf-112">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="8fdaf-112">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="8fdaf-113">.NET で提供される暗号化サービスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="8fdaf-114">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-114">This section is of interest to developers.</span></span>

- [<span data-ttu-id="8fdaf-115">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="8fdaf-115">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="8fdaf-116">Reliable .NET アプリケーションを作成するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="8fdaf-117">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-117">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="8fdaf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fdaf-118">Related sections</span></span>

[<span data-ttu-id="8fdaf-119">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="8fdaf-119">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="8fdaf-120">アプリケーションの作成、構成、デバッグ、セキュリティ、配置、および動的プログラミング、相互運用性、拡張性、メモリ管理、スレッド処理に関する情報を含む、アプリケーション開発用の主要な技術領域とタスクのすべてについての手引書です。</span><span class="sxs-lookup"><span data-stu-id="8fdaf-120">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
