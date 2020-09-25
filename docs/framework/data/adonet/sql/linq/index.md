---
title: LINQ to SQL
description: LINQ to SQL は .NET Framework のコンポーネントであり、リレーショナル データをオブジェクトとして管理するためのランタイム インフラストラクチャを提供します。
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 961e0713de714d0e75417f93e84e0ab748fd9a42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158319"
---
# <a name="linq-to-sql"></a><span data-ttu-id="919a0-103">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="919a0-103">LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="919a0-104">は .NET Framework バージョン 3.5 のコンポーネントであり、リレーショナル データをオブジェクトとして管理するためのランタイム インフラストラクチャを提供します。</span><span class="sxs-lookup"><span data-stu-id="919a0-104">is a component of .NET Framework version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="919a0-105">リレーショナル データは 2 次元テーブル (*リレーション*または*フラット ファイル*) のコレクションで表され、共通の列がテーブルを相互に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="919a0-105">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="919a0-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を効果的に使用するには、リレーショナル データベースの基本原則を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="919a0-106">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="919a0-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、リレーショナル データベースのデータ モデルが、開発者のプログラミング言語で表されるオブジェクト モデルに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="919a0-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="919a0-108">アプリケーションが実行されると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、オブジェクト モデルの統合言語クエリを SQL に変換し、それをデータベースに送信して実行します。</span><span class="sxs-lookup"><span data-stu-id="919a0-108">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="919a0-109">データベースから結果が返されると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] はそれをプログラミング言語で操作できるオブジェクトに変換し直します。</span><span class="sxs-lookup"><span data-stu-id="919a0-109">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="919a0-110">Visual Studio を使用する開発者は、通常、オブジェクト リレーショナル デザイナーを使用します。これには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の機能の多くを実装するためのユーザー インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="919a0-110">Developers using Visual Studio typically use the Object Relational Designer, which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="919a0-111">このリリースの [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に含まれているドキュメントでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションを構築するのに必要な基本的なビルド ブロック、プロセス、および手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="919a0-111">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="919a0-112">特定の問題について Microsoft Docs を検索したり、[LINQ フォーラム](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)に参加して、複雑なトピックについて専門家と検討したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="919a0-112">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="919a0-113">最後に、「[LINQ to SQL: リレーショナル データ用 .NET 統合言語クエリ](/previous-versions/dotnet/articles/bb425822(v=msdn.10))」ホワイト ペーパーには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] テクノロジの詳細と、Visual Basic および C# のコード例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="919a0-113">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="919a0-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="919a0-114">In This Section</span></span>  

 [<span data-ttu-id="919a0-115">はじめに</span><span class="sxs-lookup"><span data-stu-id="919a0-115">Getting Started</span></span>](getting-started.md)  
 <span data-ttu-id="919a0-116">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の簡単な概要と、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用して作業を始める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="919a0-116">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="919a0-117">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="919a0-117">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="919a0-118">マップ、クエリ、更新、デバッグ、および同様のタスクを行う手順を示します。</span><span class="sxs-lookup"><span data-stu-id="919a0-118">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="919a0-119">参照</span><span class="sxs-lookup"><span data-stu-id="919a0-119">Reference</span></span>](reference.md)  
 <span data-ttu-id="919a0-120">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のさまざまな側面に関するリファレンス情報を示します。</span><span class="sxs-lookup"><span data-stu-id="919a0-120">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="919a0-121">SQL-CLR 型マッピング、標準クエリ演算子変換などのトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="919a0-121">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="919a0-122">サンプル</span><span class="sxs-lookup"><span data-stu-id="919a0-122">Samples</span></span>](samples.md)  
 <span data-ttu-id="919a0-123">Visual Basic および C# のサンプルへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="919a0-123">Provides links to Visual Basic and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="919a0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="919a0-124">Related Sections</span></span>  

 <span data-ttu-id="919a0-125">[統合言語クエリ (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="919a0-125">[Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)</span></span>\
 <span data-ttu-id="919a0-126">C# での LINQ テクノロジの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="919a0-126">Provides overviews of LINQ technologies in C#.</span></span>

 [<span data-ttu-id="919a0-127">統合言語クエリ (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="919a0-127">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="919a0-128">Visual Basic での LINQ テクノロジの概要を提供します。</span><span class="sxs-lookup"><span data-stu-id="919a0-128">Provides overviews of LINQ technologies in Visual Basic.</span></span>
  
 [<span data-ttu-id="919a0-129">LINQ</span><span class="sxs-lookup"><span data-stu-id="919a0-129">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="919a0-130">Visual Basic ユーザー向けの LINQ テクノロジを提供します。</span><span class="sxs-lookup"><span data-stu-id="919a0-130">Describes LINQ technologies for Visual Basic users.</span></span>  
  
 [<span data-ttu-id="919a0-131">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="919a0-131">LINQ and ADO.NET</span></span>](../../linq-and-ado-net.md)  
 <span data-ttu-id="919a0-132">ADO.NET ポータルへのリンク。</span><span class="sxs-lookup"><span data-stu-id="919a0-132">Links to the ADO.NET portal.</span></span>  
  
 <span data-ttu-id="919a0-133">[LINQ to SQL チュートリアル](/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="919a0-133">[LINQ to SQL Walkthroughs](/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span></span>  
 <span data-ttu-id="919a0-134">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のチュートリアルを一覧します。</span><span class="sxs-lookup"><span data-stu-id="919a0-134">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="919a0-135">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="919a0-135">Downloading Sample Databases</span></span>](downloading-sample-databases.md)  
 <span data-ttu-id="919a0-136">ドキュメントで使用されるサンプル データベースをダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="919a0-136">Describes how to download sample databases used in the documentation.</span></span>  
  
 <span data-ttu-id="919a0-137">[LinqDataSource Web サーバー コントロールの概要](/previous-versions/aspnet/bb547113(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="919a0-137">[LinqDataSource Web Server Control Overview](/previous-versions/aspnet/bb547113(v=vs.100))</span></span>  
 <span data-ttu-id="919a0-138"><xref:System.Web.UI.WebControls.LinqDataSource> コントロールにより ASP.NET データ ソース コントロールのアーキテクチャを通じて統合言語クエリ (LINQ) が Web 開発者に公開される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="919a0-138">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes Language-Integrated Query (LINQ) to Web developers through the ASP.NET data-source control architecture.</span></span>
