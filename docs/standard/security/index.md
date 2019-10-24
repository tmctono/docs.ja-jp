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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c3c7eb20bb3368205dab4c7e03b6b80d09a2121
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775269"
---
# <a name="security-in-net"></a><span data-ttu-id="d238a-102">.NET でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d238a-102">Security in .NET</span></span>

<span data-ttu-id="d238a-103">共通言語ランタイムと .NET には、開発者が安全なコードを簡単に記述し、保護されたリソースにアクセスできるように、システム管理者がコードに付与されたアクセス許可をカスタマイズできるようにする、便利なクラスとサービスが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="d238a-103">The common language runtime and the .NET provide many useful classes and services that enable developers to easily write secure code and enable system administrators to customize the permissions granted to code so that it can access protected resources.</span></span> <span data-ttu-id="d238a-104">さらに、ランタイムと .NET には、暗号化とロールベースのセキュリティの使用を容易にする便利なクラスとサービスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d238a-104">In addition, the runtime and the .NET provide useful classes and services that facilitate the use of cryptography and role-based security.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d238a-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d238a-105">In this section</span></span>

- [<span data-ttu-id="d238a-106">セキュリティの基本概念</span><span class="sxs-lookup"><span data-stu-id="d238a-106">Key Security Concepts</span></span>](key-security-concepts.md)  
<span data-ttu-id="d238a-107">共通言語ランタイムのセキュリティ機能の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="d238a-107">Provides an overview of common language runtime security features.</span></span> <span data-ttu-id="d238a-108">このセクションは開発者およびシステム管理者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d238a-108">This section is of interest to developers and system administrators.</span></span>

- [<span data-ttu-id="d238a-109">ロール ベースのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="d238a-109">Role-Based Security</span></span>](role-based-security.md)  
<span data-ttu-id="d238a-110">コード内でロール ベースのセキュリティと対話する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d238a-110">Describes how to interact with role-based security in your code.</span></span> <span data-ttu-id="d238a-111">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d238a-111">This section is of interest to developers.</span></span>

- [<span data-ttu-id="d238a-112">暗号モデル</span><span class="sxs-lookup"><span data-stu-id="d238a-112">Cryptography Model</span></span>](cryptography-model.md)  
<span data-ttu-id="d238a-113">.NET で提供される暗号化サービスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="d238a-113">Provides an overview of cryptographic services provided by .NET.</span></span> <span data-ttu-id="d238a-114">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d238a-114">This section is of interest to developers.</span></span>

- [<span data-ttu-id="d238a-115">安全なコーディングのガイドライン</span><span class="sxs-lookup"><span data-stu-id="d238a-115">Secure Coding Guidelines</span></span>](secure-coding-guidelines.md)  
<span data-ttu-id="d238a-116">Reliable .NET アプリケーションを作成するためのベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d238a-116">Describes some of the best practices for creating reliable .NET applications.</span></span> <span data-ttu-id="d238a-117">このセクションは開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="d238a-117">This section is of interest to developers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="d238a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="d238a-118">Related sections</span></span>

[<span data-ttu-id="d238a-119">開発ガイド</span><span class="sxs-lookup"><span data-stu-id="d238a-119">Development Guide</span></span>](../../framework/development-guide.md)  
<span data-ttu-id="d238a-120">アプリケーションの作成、構成、デバッグ、セキュリティ、配置、および動的プログラミング、相互運用性、拡張性、メモリ管理、スレッド処理に関する情報を含む、アプリケーション開発用の主要な技術領域とタスクのすべてについての手引書です。</span><span class="sxs-lookup"><span data-stu-id="d238a-120">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>
