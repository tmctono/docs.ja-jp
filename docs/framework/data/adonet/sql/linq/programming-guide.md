---
title: プログラミング ガイド
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: 50c4370e23faf8400eb23f1e8c0cc74cd4dce80e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203567"
---
# <a name="programming-guide"></a><span data-ttu-id="c192b-102">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="c192b-102">Programming Guide</span></span>

<span data-ttu-id="c192b-103">ここでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のオブジェクト モデルを作成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c192b-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="c192b-104">Visual Studio を使用している場合は、オブジェクト リレーショナル デザイナーを使用して、これらの同じタスクの多くを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c192b-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="c192b-105">特定の問題について Microsoft Docs を検索したり、[LINQ フォーラム](https://social.msdn.microsoft.com/forums/home?forum=linqtosql)に参加して、複雑なトピックについて専門家と検討したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c192b-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://social.msdn.microsoft.com/forums/home?forum=linqtosql), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="c192b-106">最後に、「[LINQ to SQL: リレーショナル データ用 .NET 統合言語クエリ](/previous-versions/dotnet/articles/bb425822(v=msdn.10))」ホワイト ペーパーには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] テクノロジの詳細と、Visual Basic および C# のコード例が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c192b-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](/previous-versions/dotnet/articles/bb425822(v=msdn.10)) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c192b-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c192b-107">In This Section</span></span>  

 [<span data-ttu-id="c192b-108">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="c192b-108">Creating the Object Model</span></span>](creating-the-object-model.md)  
 <span data-ttu-id="c192b-109">オブジェクト モデルを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c192b-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="c192b-110">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="c192b-110">Communicating with the Database</span></span>](communicating-with-the-database.md)  
 <span data-ttu-id="c192b-111">データベースへのコンジットとして <xref:System.Data.Linq.DataContext> オブジェクトを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c192b-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="c192b-112">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="c192b-112">Querying the Database</span></span>](querying-the-database.md)  
 <span data-ttu-id="c192b-113">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でクエリを実行する方法を説明し、多数の例を示します。</span><span class="sxs-lookup"><span data-stu-id="c192b-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="c192b-114">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="c192b-114">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)  
 <span data-ttu-id="c192b-115">データベース内のデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c192b-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="c192b-116">デバッグのサポート</span><span class="sxs-lookup"><span data-stu-id="c192b-116">Debugging Support</span></span>](debugging-support.md)  
 <span data-ttu-id="c192b-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトのデバッグ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="c192b-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="c192b-118">背景情報</span><span class="sxs-lookup"><span data-stu-id="c192b-118">Background Information</span></span>](background-information.md)  
 <span data-ttu-id="c192b-119">コンカレンシーの競合の解決、新しいデータベースの作成など、上級ユーザー向けの追加項目が記載されています。</span><span class="sxs-lookup"><span data-stu-id="c192b-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c192b-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="c192b-120">Related Sections</span></span>  

 [<span data-ttu-id="c192b-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c192b-121">LINQ to SQL</span></span>](index.md)  
 <span data-ttu-id="c192b-122">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] テクノロジの説明および機能の解説が記載されているトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c192b-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="c192b-123">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="c192b-123">Stored Procedures</span></span>](stored-procedures.md)  
 <span data-ttu-id="c192b-124">ストアド プロシージャの使用手順のトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="c192b-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="c192b-125">LINQ の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="c192b-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="c192b-126">C# を使用して LINQ to SQL に関する学習を始めるときに役立つリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="c192b-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="c192b-127">LINQ の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c192b-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="c192b-128">Visual Basic を使用して LINQ to SQL に関する学習を始めるときに役立つリソースを示します。</span><span class="sxs-lookup"><span data-stu-id="c192b-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
