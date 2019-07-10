---
title: プログラミング ガイド
ms.date: 03/30/2017
ms.assetid: ed1012d4-3ff2-4877-af27-93125c4180ea
ms.openlocfilehash: c63fbedc1cf7484943614c50e7dd7554a2ddea0e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742940"
---
# <a name="programming-guide"></a><span data-ttu-id="4bd05-102">プログラミング ガイド</span><span class="sxs-lookup"><span data-stu-id="4bd05-102">Programming Guide</span></span>
<span data-ttu-id="4bd05-103">ここでは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] のオブジェクト モデルを作成および使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-103">This section contains information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="4bd05-104">Visual Studio を使用している場合は、これらのタスクの多くを実行するオブジェクト リレーショナル デザイナーを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4bd05-104">If you are using Visual Studio, you can also use the Object Relational Designer to perform many of these same tasks.</span></span>  
  
 <span data-ttu-id="4bd05-105">特定の問題に関する Microsoft のドキュメントを検索することとに参加することができます、 [LINQ フォーラム](https://go.microsoft.com/fwlink/?LinkId=76488)専門家とより複雑なトピックを説明できます。</span><span class="sxs-lookup"><span data-stu-id="4bd05-105">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="4bd05-106">最後に、 [LINQ to SQL: リレーショナル データ用 .net 統合言語クエリ](https://go.microsoft.com/fwlink/?LinkId=93205)ホワイト ペーパーの詳細[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]テクノロジ、Visual Basic と c# のコード例を完了します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-106">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4bd05-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4bd05-107">In This Section</span></span>  
 [<span data-ttu-id="4bd05-108">オブジェクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="4bd05-108">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 <span data-ttu-id="4bd05-109">オブジェクト モデルを生成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-109">Describes how to generate an object model.</span></span>  
  
 [<span data-ttu-id="4bd05-110">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="4bd05-110">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)  
 <span data-ttu-id="4bd05-111">データベースへのコンジットとして <xref:System.Data.Linq.DataContext> オブジェクトを使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-111">Describes how to use a <xref:System.Data.Linq.DataContext> object as a conduit to the database.</span></span>  
  
 [<span data-ttu-id="4bd05-112">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="4bd05-112">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 <span data-ttu-id="4bd05-113">  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] でクエリを実行する方法を説明し、多数の例を示します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-113">Describes how to execute queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], and provides many examples.</span></span>  
  
 [<span data-ttu-id="4bd05-114">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="4bd05-114">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 <span data-ttu-id="4bd05-115">データベース内のデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-115">Describes how change data in the database.</span></span>  
  
 [<span data-ttu-id="4bd05-116">デバッグのサポート</span><span class="sxs-lookup"><span data-stu-id="4bd05-116">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)  
 <span data-ttu-id="4bd05-117">  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] プロジェクトのデバッグ機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-117">Describes the support available for debugging [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projects.</span></span>  
  
 [<span data-ttu-id="4bd05-118">背景情報</span><span class="sxs-lookup"><span data-stu-id="4bd05-118">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 <span data-ttu-id="4bd05-119">コンカレンシーの競合の解決、新しいデータベースの作成など、上級ユーザー向けの追加項目が記載されています。</span><span class="sxs-lookup"><span data-stu-id="4bd05-119">Includes additional items, such as concurrency conflict resolution, creating new databases, and more, for more advanced users.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="4bd05-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="4bd05-120">Related Sections</span></span>  
 [<span data-ttu-id="4bd05-121">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bd05-121">LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="4bd05-122">  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] テクノロジの説明および機能の解説が記載されているトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-122">Provides links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology and demonstrate features.</span></span>  
  
 [<span data-ttu-id="4bd05-123">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="4bd05-123">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 <span data-ttu-id="4bd05-124">ストアド プロシージャの使用手順のトピックへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-124">Includes links to topics that illustrate how to use stored procedures.</span></span>  
  
 [<span data-ttu-id="4bd05-125">LINQ の概要 (C#)</span><span class="sxs-lookup"><span data-stu-id="4bd05-125">Introduction to LINQ (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="4bd05-126">SQL を使用する LINQ について学習を開始するのに役立つリソースを提供します。C#します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-126">Provides resources to help you begin to learn about LINQ to SQL using C#.</span></span>

 [<span data-ttu-id="4bd05-127">LINQ の概要 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bd05-127">Introduction to LINQ (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)  
 <span data-ttu-id="4bd05-128">LINQ to SQL は Visual Basic を使用して学習を開始するのに役立つリソースを提供します。</span><span class="sxs-lookup"><span data-stu-id="4bd05-128">Provides resources to help you begin to learn about LINQ to SQL using Visual Basic.</span></span>
