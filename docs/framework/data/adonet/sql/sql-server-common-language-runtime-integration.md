---
title: SQL Server の共通言語ランタイム統合
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 77b40c6a1576b87d9bb4a7eb4b1ee3df8828b892
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780861"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="ca6f2-102">SQL Server の共通言語ランタイム統合</span><span class="sxs-lookup"><span data-stu-id="ca6f2-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="ca6f2-103">SQL Server 2005 で、Microsoft Windows 用の .NET Framework の共通言語ランタイム (CLR) コンポーネントの統合が導入されました。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="ca6f2-104">つまり、Microsoft Visual Basic .NET や Microsoft Visual C# を含む任意の .NET Framework 言語を使用して、ストアド プロシージャ、トリガー、ユーザー定義型、ユーザー定義関数、ユーザー定義集計、およびストリーミング テーブル値関数を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="ca6f2-105">マネージド コードが Microsoft SQL Server 環境とデータをやり取りできるように、<xref:Microsoft.SqlServer.Server> 名前空間には新しいアプリケーション プログラミング インターフェイス (API) のセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="ca6f2-106">このセクションでは、SQL Server の共通言語ランタイム (CLR) 統合および SQL Server のインプロセス固有の ADO.NET の拡張に固有の機能や動作ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="ca6f2-107">このセクションは、SQL Server の CLR 統合を利用したプログラミングを始めるのに十分な情報を提供することを目的としており、包括的な情報の提供は目的としていません。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="ca6f2-108">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="ca6f2-109">**SQL Server オンライン ブック**</span><span class="sxs-lookup"><span data-stu-id="ca6f2-109">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="ca6f2-110">共通言語ランタイム (CLR) 統合プログラミングの概念</span><span class="sxs-lookup"><span data-stu-id="ca6f2-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="ca6f2-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ca6f2-111">In This Section</span></span>  
 [<span data-ttu-id="ca6f2-112">SQL Server の CLR 統合の概要</span><span class="sxs-lookup"><span data-stu-id="ca6f2-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="ca6f2-113">SQL Server の CLR 統合の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="ca6f2-114">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ca6f2-115">CLR ユーザー定義関数</span><span class="sxs-lookup"><span data-stu-id="ca6f2-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="ca6f2-116">テーブル値関数、スカラー関数、ユーザー定義集計関数など、さまざまな種類の CLR 関数の実装方法と使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="ca6f2-117">CLR ユーザー定義型</span><span class="sxs-lookup"><span data-stu-id="ca6f2-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="ca6f2-118">CLR のユーザー定義型を実装して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="ca6f2-119">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ca6f2-120">CLR ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="ca6f2-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="ca6f2-121">CLR のストアド プロシージャを実装して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="ca6f2-122">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ca6f2-123">CLR トリガー</span><span class="sxs-lookup"><span data-stu-id="ca6f2-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="ca6f2-124">CLR のトリガーを実装して使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="ca6f2-125">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="ca6f2-126">コンテキスト接続</span><span class="sxs-lookup"><span data-stu-id="ca6f2-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="ca6f2-127">コンテキスト接続について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="ca6f2-128">SQL Server のインプロセス固有の ADO.NET の動作</span><span class="sxs-lookup"><span data-stu-id="ca6f2-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="ca6f2-129">SQL Server のインプロセス固有の ADO.NET の拡張およびコンテキスト接続について説明します。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="ca6f2-130">追加情報へのリンクもあります。</span><span class="sxs-lookup"><span data-stu-id="ca6f2-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6f2-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="ca6f2-131">See also</span></span>

- [<span data-ttu-id="ca6f2-132">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ca6f2-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="ca6f2-133">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="ca6f2-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
