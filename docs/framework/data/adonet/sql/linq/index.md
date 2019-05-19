---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 4a44bd3f55cf6c21bb785ff70bca80e2c003cd18
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878260"
---
# <a name="linq-to-sql"></a><span data-ttu-id="02901-102">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="02901-102">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="02901-103">.NET Framework version 3.5 オブジェクトとしてのリレーショナル データを管理するためのランタイム インフラストラクチャを提供するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="02901-103">is a component of .NET Framework version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02901-104">リレーショナル データは 2 次元テーブル (*リレーション*または*フラット ファイル*) のコレクションで表され、共通の列がテーブルを相互に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="02901-104">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="02901-105">
  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を効果的に使用するには、リレーショナル データベースの基本原則を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="02901-105">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="02901-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、リレーショナル データベースのデータ モデルが、開発者のプログラミング言語で表されるオブジェクト モデルに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="02901-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="02901-107">アプリケーションが実行されると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、オブジェクト モデルの統合言語クエリを SQL に変換し、それをデータベースに送信して実行します。</span><span class="sxs-lookup"><span data-stu-id="02901-107">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="02901-108">データベースから結果が返されると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] はそれをプログラミング言語で操作できるオブジェクトに変換し直します。</span><span class="sxs-lookup"><span data-stu-id="02901-108">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="02901-109">通常 Visual Studio を使用している開発者が使用して、[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]の機能の多くを実装するためのユーザー インターフェイスを提供する[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="02901-109">Developers using Visual Studio typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="02901-110">このリリースの [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に含まれているドキュメントでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションを構築するのに必要な基本的なビルド ブロック、プロセス、および手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02901-110">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="02901-111">特定の問題に関する Microsoft のドキュメントを検索することとに参加することができます、 [LINQ フォーラム](https://go.microsoft.com/fwlink/?LinkId=76488)専門家とより複雑なトピックを説明できます。</span><span class="sxs-lookup"><span data-stu-id="02901-111">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="02901-112">最後に、 [LINQ to SQL: リレーショナル データ用 .net 統合言語クエリ](https://go.microsoft.com/fwlink/?LinkId=93205)ホワイト ペーパーの詳細[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]テクノロジ、Visual Basic と c# のコード例を完了します。</span><span class="sxs-lookup"><span data-stu-id="02901-112">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02901-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="02901-113">In This Section</span></span>  
 [<span data-ttu-id="02901-114">はじめに</span><span class="sxs-lookup"><span data-stu-id="02901-114">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 <span data-ttu-id="02901-115">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の簡単な概要と、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用して作業を始める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="02901-115">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="02901-116">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="02901-116">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="02901-117">マップ、クエリ、更新、デバッグ、および同様のタスクを行う手順を示します。</span><span class="sxs-lookup"><span data-stu-id="02901-117">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="02901-118">参照</span><span class="sxs-lookup"><span data-stu-id="02901-118">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 <span data-ttu-id="02901-119">
  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のさまざまな側面に関するリファレンス情報を示します。</span><span class="sxs-lookup"><span data-stu-id="02901-119">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="02901-120">SQL-CLR 型マッピング、標準クエリ演算子変換などのトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="02901-120">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="02901-121">サンプル</span><span class="sxs-lookup"><span data-stu-id="02901-121">Samples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 <span data-ttu-id="02901-122">Visual Basic および c# のサンプルへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="02901-122">Provides links to Visual Basic and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="02901-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="02901-123">Related Sections</span></span>  
 <span data-ttu-id="02901-124">[統合言語クエリ (LINQ)C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="02901-124">[Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\\</span></span>
 <span data-ttu-id="02901-125">LINQ テクノロジの概要について説明しますC#します。</span><span class="sxs-lookup"><span data-stu-id="02901-125">Provides overviews of LINQ technologies in C#.</span></span>
 
 [<span data-ttu-id="02901-126">統合言語クエリ (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="02901-126">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="02901-127">Visual Basic での LINQ テクノロジの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="02901-127">Provides overviews of LINQ technologies in Visual Basic.</span></span>
  
 [<span data-ttu-id="02901-128">LINQ</span><span class="sxs-lookup"><span data-stu-id="02901-128">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="02901-129">説明[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]Visual Basic ユーザー向けのテクノロジです。</span><span class="sxs-lookup"><span data-stu-id="02901-129">Describes [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technologies for Visual Basic users.</span></span>  
  
 [<span data-ttu-id="02901-130">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="02901-130">LINQ and ADO.NET</span></span>](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 <span data-ttu-id="02901-131">ADO.NET ポータルへのリンク。</span><span class="sxs-lookup"><span data-stu-id="02901-131">Links to the ADO.NET portal.</span></span>  
  
 <span data-ttu-id="02901-132">[LINQ to SQL チュートリアル](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="02901-132">[LINQ to SQL Walkthroughs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span></span>  
 <span data-ttu-id="02901-133">
  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のチュートリアルを一覧します。</span><span class="sxs-lookup"><span data-stu-id="02901-133">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="02901-134">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="02901-134">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 <span data-ttu-id="02901-135">ドキュメントで使用されるサンプル データベースをダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02901-135">Describes how to download sample databases used in the documentation.</span></span>  
  
 <span data-ttu-id="02901-136">[LinqDataSource Web サーバー コントロールの概要](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="02901-136">[LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span></span>  
 <span data-ttu-id="02901-137">について説明しますが、どのように<xref:System.Web.UI.WebControls.LinqDataSource>公開を制御[!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)]ASP.NET データ ソース コントロールのアーキテクチャを通じて Web 開発者にします。</span><span class="sxs-lookup"><span data-stu-id="02901-137">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] to Web developers through the ASP.NET data-source control architecture.</span></span>
