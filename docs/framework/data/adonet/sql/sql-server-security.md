---
title: SQL Server のセキュリティ
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: 5db14e681b5a9445c034be60993661a61a038e08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177307"
---
# <a name="sql-server-security"></a><span data-ttu-id="2bec5-102">SQL Server のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="2bec5-102">SQL Server Security</span></span>

<span data-ttu-id="2bec5-103">SQL Server は、安全なデータベース アプリケーションの作成を支援するさまざまな機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="2bec5-103">SQL Server has many features that support creating secure database applications.</span></span>  
  
 <span data-ttu-id="2bec5-104">データの盗難や破壊など、セキュリティに関する基本的な考慮事項は、使用している SQL Server のバージョンに関係なく当てはまります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-104">Common security considerations, such as data theft or vandalism, apply regardless of the version of SQL Server you are using.</span></span> <span data-ttu-id="2bec5-105">データの整合性も、セキュリティの問題と見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-105">Data integrity should also be considered as a security issue.</span></span> <span data-ttu-id="2bec5-106">データが保護されていない場合、アドホック データ操作が許可されていて、そのデータが誤って、または悪意を持って正しくない値に変更されたり、完全に削除されたりすると、そのデータは使い物にならなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-106">If data is not protected, it is possible that it could become worthless if ad hoc data manipulation is permitted and the data is inadvertently or maliciously modified with incorrect values or deleted entirely.</span></span> <span data-ttu-id="2bec5-107">また、機密情報を適切に保存するなど、遵守しなければならない法的要件が存在することもよくあります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-107">In addition, there are often legal requirements that must be adhered to, such as the correct storage of confidential information.</span></span> <span data-ttu-id="2bec5-108">特定の管轄区域に適用される法律によっては、特定の種類の個人データを保存することが完全に禁止されています。</span><span class="sxs-lookup"><span data-stu-id="2bec5-108">Storing some kinds of personal data is proscribed entirely, depending on the laws that apply in a particular jurisdiction.</span></span>  
  
 <span data-ttu-id="2bec5-109">SQL Server の各バージョンにはそれぞれ異なるセキュリティ機能があり、Windows と同様、新しいバージョンほど機能が強化されています。</span><span class="sxs-lookup"><span data-stu-id="2bec5-109">Each version of SQL Server has different security features, as does each version of Windows, with later versions having enhanced functionality over earlier ones.</span></span> <span data-ttu-id="2bec5-110">セキュリティ機能だけでは、データベース アプリケーションの安全性が保証されないことを理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="2bec5-110">It is important to understand that security features alone cannot guarantee a secure database application.</span></span> <span data-ttu-id="2bec5-111">データベース アプリケーションの要件、実行環境、デプロイ モデル、物理的な場所、およびユーザー数は、それぞれ独特です。</span><span class="sxs-lookup"><span data-stu-id="2bec5-111">Each database application is unique in its requirements, execution environment, deployment model, physical location, and user population.</span></span> <span data-ttu-id="2bec5-112">スコープ内のローカル アプリケーションの中には最小限のセキュリティしか必要としないものもありますが、その他のローカル アプリケーションや、インターネット上で展開されたアプリケーションについては、厳しいセキュリティ対策と継続的な監視と評価が必要な場合もあります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-112">Some applications that are local in scope may need only minimal security whereas other local applications or applications deployed over the Internet may require stringent security measures and ongoing monitoring and evaluation.</span></span>  
  
 <span data-ttu-id="2bec5-113">SQL Server データベース アプリケーションのセキュリティ要件は、事後的対策としてではなくデザイン時に考慮することが大切です。</span><span class="sxs-lookup"><span data-stu-id="2bec5-113">The security requirements of a SQL Server database application should be considered at design time, not as an afterthought.</span></span> <span data-ttu-id="2bec5-114">開発サイクルの早い段階で脅威を評価すれば、脆弱性が検出されたときの損害の可能性を軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="2bec5-114">Evaluating threats early in the development cycle gives you the opportunity to mitigate potential damage wherever a vulnerability is detected.</span></span>  
  
 <span data-ttu-id="2bec5-115">アプリケーションの初期設計が適切であっても、システムの進化に伴って新しい脅威が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-115">Even if the initial design of an application is sound, new threats may emerge as the system evolves.</span></span> <span data-ttu-id="2bec5-116">データベースに対して複数の防御線を張ることで、セキュリティ侵害による被害を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="2bec5-116">By creating multiple lines of defense around your database, you can minimize the damage inflicted by a security breach.</span></span> <span data-ttu-id="2bec5-117">まずは必要以上の権限を決して付与しないことです。これにより攻撃対象の領域が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="2bec5-117">Your first line of defense is to reduce the attack surface area by never to granting more permissions than are absolutely necessary.</span></span>  
  
 <span data-ttu-id="2bec5-118">このセクションの各トピックでは、開発者に関係のある SQL Server のセキュリティ機能を簡単に説明します。SQL Server オンライン ブックの関連項目へのリンクのほか、より掘り下げて解説したリソースへのリンクも示しています。</span><span class="sxs-lookup"><span data-stu-id="2bec5-118">The topics in this section briefly describe the security features in SQL Server that are relevant for developers, with links to relevant topics in SQL Server Books Online and other resources that provide more detailed coverage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2bec5-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2bec5-119">In This Section</span></span>  

 [<span data-ttu-id="2bec5-120">SQL Server セキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="2bec5-120">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)  
 <span data-ttu-id="2bec5-121">SQL Server のアーキテクチャおよびセキュリティ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bec5-121">Describes the architecture and security features of SQL Server.</span></span>  
  
 [<span data-ttu-id="2bec5-122">SQL Server におけるアプリケーション セキュリティのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2bec5-122">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="2bec5-123">ADO.NET および SQL Server アプリケーションに該当するさまざまなセキュリティ シナリオを取り上げます。</span><span class="sxs-lookup"><span data-stu-id="2bec5-123">Contains topics discussing various application security scenarios for ADO.NET and SQL Server applications.</span></span>  
  
 [<span data-ttu-id="2bec5-124">SQL Server Express のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="2bec5-124">SQL Server Express Security</span></span>](sql-server-express-security.md)  
 <span data-ttu-id="2bec5-125">SQL Server Express のセキュリティ上の考慮事項を説明します。</span><span class="sxs-lookup"><span data-stu-id="2bec5-125">Describes security considerations for SQL Server Express.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2bec5-126">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bec5-126">Related Sections</span></span>  

[<span data-ttu-id="2bec5-127">SQL Server データベース エンジンと Azure SQL Database のセキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="2bec5-127">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
<span data-ttu-id="2bec5-128">SQL Server と Azure SQL Database のセキュリティ上の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bec5-128">Describes security considerations for SQL Server and Azure SQL Database.</span></span>

[<span data-ttu-id="2bec5-129">SQL Server インストールにおけるセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="2bec5-129">Security Considerations for a SQL Server Installation</span></span>](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
<span data-ttu-id="2bec5-130">SQL Server をインストールする前に考慮すべきセキュリティの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2bec5-130">Describes security concerns to consider before installing SQL Server.</span></span>

## <a name="see-also"></a><span data-ttu-id="2bec5-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="2bec5-131">See also</span></span>

- [<span data-ttu-id="2bec5-132">ADO.NET アプリケーションのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="2bec5-132">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="2bec5-133">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="2bec5-133">SQL Server and ADO.NET</span></span>](index.md)
