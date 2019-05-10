---
title: SQL Server Compact および LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: a0cb45b31f7134264068297f54013f49b35f669d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651203"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="88fb6-102">SQL Server Compact および LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="88fb6-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="88fb6-103">SQL Server Compact は、Visual Studio にインストールされている既定のデータベースです。</span><span class="sxs-lookup"><span data-stu-id="88fb6-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="88fb6-104">詳細については、次を参照してください。[を使用して SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))します。</span><span class="sxs-lookup"><span data-stu-id="88fb6-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="88fb6-105">ここでは、使用量、構成、機能セット、およびスコープの主な相違点の概要について[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]をサポートします。</span><span class="sxs-lookup"><span data-stu-id="88fb6-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="88fb6-106">LINQ to SQL との関係における SQL Server Compact の特徴</span><span class="sxs-lookup"><span data-stu-id="88fb6-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="88fb6-107">既定では、SQL Server Compact のすべての Visual Studio エディションがインストールされている、そのため開発用コンピューターで使用するために使用可能な[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="88fb6-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="88fb6-108">SQL Server Compact を使用するアプリケーションの展開と[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]SQL Server アプリケーションとは異なります。</span><span class="sxs-lookup"><span data-stu-id="88fb6-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="88fb6-109">SQL Server Compact は .NET Framework の一部ではないため、アプリケーションにパッケージ化するか、Microsoft サイトから個別にダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88fb6-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="88fb6-110">これには、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="88fb6-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="88fb6-111">SQL Server Compact は DLL としてパッケージ化されており、データベース ファイル (.sdf 拡張子) に対して直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="88fb6-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="88fb6-112">SQL Server Compact は、クライアント アプリケーションと同じプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="88fb6-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="88fb6-113">SQL Server Compact との通信の効率性はそのため、SQL Server と通信するよりも高い。</span><span class="sxs-lookup"><span data-stu-id="88fb6-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="88fb6-114">その一方で、SQL Server Compact はコストを伴うマネージ コードとアンマネージ コード間の相互運用性が必要です。</span><span class="sxs-lookup"><span data-stu-id="88fb6-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="88fb6-115">SQL Server Compact DLL のサイズが小さです。</span><span class="sxs-lookup"><span data-stu-id="88fb6-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="88fb6-116">このため、アプリケーション全体のサイズが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="88fb6-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="88fb6-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ランタイムおよび SQLMetal コマンド ライン ツールが SQL Server Compact をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="88fb6-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="88fb6-118">[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] では、SQL Server Compact はサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="88fb6-118">The [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="88fb6-119">機能セット</span><span class="sxs-lookup"><span data-stu-id="88fb6-119">Feature Set</span></span>  
 <span data-ttu-id="88fb6-120">影響を与える次の方法で、SQL Server Compact の機能セットが SQL Server の機能セットよりはるかに簡単[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]アプリケーション。</span><span class="sxs-lookup"><span data-stu-id="88fb6-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="88fb6-121">SQL Server Compact は、ストアド プロシージャまたはビューをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="88fb6-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="88fb6-122">SQL Server Compact は、一部のデータ型と SQL 関数のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="88fb6-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="88fb6-123">SQL Server Compact は、一部の SQL コンストラクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="88fb6-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="88fb6-124">SQL Server Compact は、最小限のオプティマイザーを備えています。</span><span class="sxs-lookup"><span data-stu-id="88fb6-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="88fb6-125">一部のクエリがタイムアウトになる可能性があることができます。</span><span class="sxs-lookup"><span data-stu-id="88fb6-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="88fb6-126">SQL Server Compact は、部分信頼をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="88fb6-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88fb6-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="88fb6-127">See also</span></span>

- [<span data-ttu-id="88fb6-128">参照</span><span class="sxs-lookup"><span data-stu-id="88fb6-128">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
