---
title: SQL Server の共通言語ランタイム統合
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: d9fe0f03c88584607c6bc38fcbcff3f9424fd40c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183027"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="f996b-102">SQL Server の共通言語ランタイム統合</span><span class="sxs-lookup"><span data-stu-id="f996b-102">SQL Server Common Language Runtime Integration</span></span>

<span data-ttu-id="f996b-103">SQL Server 2005 で、Microsoft Windows 用の .NET Framework の共通言語ランタイム (CLR) コンポーネントの統合が導入されました。</span><span class="sxs-lookup"><span data-stu-id="f996b-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="f996b-104">つまり、Microsoft Visual Basic .NET や Microsoft Visual C# を含む任意の .NET Framework 言語を使用して、ストアド プロシージャ、トリガー、ユーザー定義型、ユーザー定義関数、ユーザー定義集計、およびストリーミング テーブル値関数を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f996b-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="f996b-105">マネージド コードが Microsoft SQL Server 環境とデータをやり取りできるように、<xref:Microsoft.SqlServer.Server> 名前空間には新しいアプリケーション プログラミング インターフェイス (API) のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f996b-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="f996b-106">このセクションでは、SQL Server の共通言語ランタイム (CLR) 統合および SQL Server のインプロセス固有の ADO.NET の拡張に固有の機能や動作ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="f996b-107">このセクションは、SQL Server の CLR 統合を利用したプログラミングを始めるのに十分な情報を提供することを目的としており、包括的な情報の提供は目的としていません。</span><span class="sxs-lookup"><span data-stu-id="f996b-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="f996b-108">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f996b-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="f996b-109">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="f996b-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="f996b-110">CLR (共通言語ランタイム) 統合のプログラミング概念</span><span class="sxs-lookup"><span data-stu-id="f996b-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="f996b-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f996b-111">In This Section</span></span>  

 [<span data-ttu-id="f996b-112">SQL Server の CLR 統合の概要</span><span class="sxs-lookup"><span data-stu-id="f996b-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="f996b-113">SQL Server の CLR 統合の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="f996b-114">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="f996b-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f996b-115">CLR ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="f996b-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="f996b-116">テーブル値関数、スカラー関数、ユーザー定義集計関数など、さまざまな種類の CLR 関数の実装方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="f996b-117">CLR ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="f996b-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="f996b-118">CLR のユーザー定義型を実装して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="f996b-119">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="f996b-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f996b-120">CLR ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="f996b-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="f996b-121">CLR のストアド プロシージャを実装して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="f996b-122">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="f996b-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f996b-123">CLR トリガー</span><span class="sxs-lookup"><span data-stu-id="f996b-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="f996b-124">CLR のトリガーを実装して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="f996b-125">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="f996b-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="f996b-126">コンテキスト接続</span><span class="sxs-lookup"><span data-stu-id="f996b-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="f996b-127">コンテキスト接続について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="f996b-128">SQL Server のインプロセス固有の ADO.NET の動作</span><span class="sxs-lookup"><span data-stu-id="f996b-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="f996b-129">SQL Server のインプロセス固有の ADO.NET の拡張およびコンテキスト接続について説明します。</span><span class="sxs-lookup"><span data-stu-id="f996b-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="f996b-130">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="f996b-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f996b-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="f996b-131">See also</span></span>

- [<span data-ttu-id="f996b-132">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f996b-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="f996b-133">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f996b-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
