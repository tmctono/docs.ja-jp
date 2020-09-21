---
title: アプリケーションの保護
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: af184f64b43c2d3dc39f8c0add08940d3b002c24
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550756"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="66412-102">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="66412-102">Securing ADO.NET applications</span></span>

<span data-ttu-id="66412-103">ユーザー入力の検証を怠るなど、コーディング時に陥りやすい基本的なミスを防ぐだけでは、安全な ADO.NET アプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="66412-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="66412-104">データにアクセスするアプリケーションには、機密データの取得、操作、破壊など、攻撃者に攻略される可能性がある障害点が多数あります。</span><span class="sxs-lookup"><span data-stu-id="66412-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="66412-105">そのため、アプリケーションの設計フェーズで行う脅威のモデリングのプロセスから、アプリケーションの最終的な配置と継続的な保守に至るまで、セキュリティのすべての側面を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="66412-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
<span data-ttu-id="66412-106">.NET Framework には、データベース アプリケーションのセキュリティを確保し、管理するのに有用なクラス、サービス、およびツールが多数用意されています。</span><span class="sxs-lookup"><span data-stu-id="66412-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="66412-107">共通言語ランタイム (CLR) によって、コードを実行するためのタイプ セーフな環境が実現され、それと同時に、コード アクセス セキュリティ (CAS) によって、マネージド コードのアクセス許可はより制限されています。</span><span class="sxs-lookup"><span data-stu-id="66412-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="66412-108">攻撃者によってもたらされる可能性のある損害は、安全なデータ アクセスのためのコーディング方法に従うことによって最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="66412-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
<span data-ttu-id="66412-109">データベースなどのアンマネージ リソースを扱う場合、安全なコードを作成したとしても、自ら招いたセキュリティ ホールを防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="66412-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="66412-110">SQL Server を含め、ほとんどのサーバー データベースには、正しく実装することによってセキュリティを強化できる独自のセキュリティ システムがあります。</span><span class="sxs-lookup"><span data-stu-id="66412-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="66412-111">しかし、データ ソースがいかに堅牢なセキュリティ システムを備えていたとしても、それが適切に構成されていなければ攻撃を防ぐことはできません。</span><span class="sxs-lookup"><span data-stu-id="66412-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="66412-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="66412-112">In this section</span></span>

 [<span data-ttu-id="66412-113">セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="66412-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="66412-114">安全な ADO.NET アプリケーションを設計するための推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="66412-115">安全なデータ アクセス</span><span class="sxs-lookup"><span data-stu-id="66412-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="66412-116">セキュリティで保護されたデータ ソースのデータを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="66412-117">安全なクライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="66412-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="66412-118">クライアント アプリケーションのセキュリティに関する考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="66412-119">コード アクセス セキュリティと ADO.NET</span><span class="sxs-lookup"><span data-stu-id="66412-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="66412-120">CAS を使用して ADO.NET コードを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="66412-121">部分信頼の使用方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="66412-122">プライバシーとデータ セキュリティ</span><span class="sxs-lookup"><span data-stu-id="66412-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="66412-123">ADO.NET アプリケーションの暗号化オプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="66412-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="66412-124">Related sections</span></span>

 [<span data-ttu-id="66412-125">DataSet と DataTable のセキュリティ ガイダンス</span><span class="sxs-lookup"><span data-stu-id="66412-125">DataSet and DataTable security guidance</span></span>](dataset-datatable-dataview/security-guidance.md)  
 <span data-ttu-id="66412-126"><xref:System.Data.DataSet> と <xref:System.Data.DataTable> に関するセキュリティ ガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="66412-126">Provides security guidance for <xref:System.Data.DataSet> and <xref:System.Data.DataTable>.</span></span>

 [<span data-ttu-id="66412-127">SQL Server のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="66412-127">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="66412-128">開発者の観点から SQL Server のセキュリティ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-128">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="66412-129">セキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="66412-129">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="66412-130">Entity Framework アプリケーションのセキュリティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-130">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="66412-131">セキュリティ</span><span class="sxs-lookup"><span data-stu-id="66412-131">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="66412-132">.NET のセキュリティをあらゆる観点から説明した記事へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="66412-132">Contains links to articles describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="66412-133">[セキュリティ ツール](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="66412-133">[Security Tools](/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="66412-134">セキュリティ保護およびセキュリティ ポリシーの管理に使用する .NET Framework ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66412-134">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="66412-135">[セキュリティで保護されたアプリケーションを作成するためのリソース](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="66412-135">[Resources for Creating Secure Applications](/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="66412-136">安全なアプリケーションを作成するための記事へのリンク集です。</span><span class="sxs-lookup"><span data-stu-id="66412-136">Provides links to articles for creating secure applications.</span></span>  
  
 [<span data-ttu-id="66412-137">セキュリティ参考文献</span><span class="sxs-lookup"><span data-stu-id="66412-137">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="66412-138">オンラインまたは出版物として提供されている外部リソースへのリンク集です。</span><span class="sxs-lookup"><span data-stu-id="66412-138">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66412-139">関連項目</span><span class="sxs-lookup"><span data-stu-id="66412-139">See also</span></span>

- [<span data-ttu-id="66412-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="66412-140">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="66412-141">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="66412-141">ADO.NET Overview</span></span>](ado-net-overview.md)
