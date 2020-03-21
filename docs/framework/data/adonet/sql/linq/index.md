---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: b0660312f540a69911905edd08541ed70cf39bb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174317"
---
# <a name="linq-to-sql"></a><span data-ttu-id="f65ec-102">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f65ec-102">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="f65ec-103">は、リレーショナル データをオブジェクトとして管理するためのランタイム インフラストラクチャを提供する .NET Framework Version 3.5 のコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="f65ec-103">is a component of .NET Framework version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f65ec-104">リレーショナル データは 2 次元テーブル (*リレーション*または*フラット ファイル*) のコレクションで表され、共通の列がテーブルを相互に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="f65ec-104">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="f65ec-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を効果的に使用するには、リレーショナル データベースの基本原則を理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f65ec-105">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="f65ec-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] では、リレーショナル データベースのデータ モデルが、開発者のプログラミング言語で表されるオブジェクト モデルに対応付けられています。</span><span class="sxs-lookup"><span data-stu-id="f65ec-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="f65ec-107">アプリケーションが実行されると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] は、オブジェクト モデルの統合言語クエリを SQL に変換し、それをデータベースに送信して実行します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-107">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="f65ec-108">データベースから結果が返されると、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] はそれをプログラミング言語で操作できるオブジェクトに変換し直します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-108">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="f65ec-109">Visual Studio を使用する開発者は通常、オブジェクト リレーショナル デザイナーを使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-109">Developers using Visual Studio typically use the Object Relational Designer, which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="f65ec-110">このリリースの [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] に含まれているドキュメントでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] アプリケーションを構築するのに必要な基本的なビルド ブロック、プロセス、および手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-110">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="f65ec-111">また、Microsoft Docs で特定の問題を検索したり、さらに複雑なトピックについて専門家と詳しく議論できる[LINQ フォーラム](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)に参加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f65ec-111">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="f65ec-112">最後に、 [LINQ to SQL: .NET リレーショナル データの統合クエリ](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10))の詳細に[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]関する技術を Visual Basic と C# のコード例を含みます。</span><span class="sxs-lookup"><span data-stu-id="f65ec-112">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://docs.microsoft.com/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f65ec-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f65ec-113">In This Section</span></span>  
 [<span data-ttu-id="f65ec-114">はじめに</span><span class="sxs-lookup"><span data-stu-id="f65ec-114">Getting Started</span></span>](getting-started.md)  
 <span data-ttu-id="f65ec-115">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の簡単な概要と、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用して作業を始める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-115">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="f65ec-116">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="f65ec-116">Programming Guide</span></span>](programming-guide.md)  
 <span data-ttu-id="f65ec-117">マップ、クエリ、更新、デバッグ、および同様のタスクを行う手順を示します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-117">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="f65ec-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="f65ec-118">Reference</span></span>](reference.md)  
 <span data-ttu-id="f65ec-119">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のさまざまな側面に関するリファレンス情報を示します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-119">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="f65ec-120">SQL-CLR 型マッピング、標準クエリ演算子変換などのトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f65ec-120">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="f65ec-121">サンプル</span><span class="sxs-lookup"><span data-stu-id="f65ec-121">Samples</span></span>](samples.md)  
 <span data-ttu-id="f65ec-122">Visual Basic および C# のサンプルへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-122">Provides links to Visual Basic and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f65ec-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="f65ec-123">Related Sections</span></span>  
 <span data-ttu-id="f65ec-124">[言語統合クエリ (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="f65ec-124">[Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)</span></span>\
 <span data-ttu-id="f65ec-125">C# での LINQ テクノロジの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-125">Provides overviews of LINQ technologies in C#.</span></span>

 [<span data-ttu-id="f65ec-126">統合言語クエリ (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f65ec-126">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="f65ec-127">VISUAL Basic での LINQ テクノロジの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-127">Provides overviews of LINQ technologies in Visual Basic.</span></span>
  
 [<span data-ttu-id="f65ec-128">LINQ</span><span class="sxs-lookup"><span data-stu-id="f65ec-128">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="f65ec-129">Visual Basic ユーザー向けの LINQ テクノロジについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-129">Describes LINQ technologies for Visual Basic users.</span></span>  
  
 [<span data-ttu-id="f65ec-130">LINQ と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f65ec-130">LINQ and ADO.NET</span></span>](../../linq-and-ado-net.md)  
 <span data-ttu-id="f65ec-131">ADO.NET ポータルへのリンク。</span><span class="sxs-lookup"><span data-stu-id="f65ec-131">Links to the ADO.NET portal.</span></span>  
  
 <span data-ttu-id="f65ec-132">[LINQ to SQL チュートリアル](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f65ec-132">[LINQ to SQL Walkthroughs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span></span>  
 <span data-ttu-id="f65ec-133">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のチュートリアルを一覧します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-133">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="f65ec-134">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="f65ec-134">Downloading Sample Databases</span></span>](downloading-sample-databases.md)  
 <span data-ttu-id="f65ec-135">ドキュメントで使用されるサンプル データベースをダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-135">Describes how to download sample databases used in the documentation.</span></span>  
  
 <span data-ttu-id="f65ec-136">[Web サーバー コントロールの概要](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f65ec-136">[LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span></span>  
 <span data-ttu-id="f65ec-137">ASP.NETデータ ソース<xref:System.Web.UI.WebControls.LinqDataSource>コントロール アーキテクチャを通じて、Web 開発者に対してコントロールが統合言語クエリ (LINQ) を公開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f65ec-137">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes Language-Integrated Query (LINQ) to Web developers through the ASP.NET data-source control architecture.</span></span>
