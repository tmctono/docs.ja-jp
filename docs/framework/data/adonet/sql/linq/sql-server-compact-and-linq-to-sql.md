---
title: SQL Server Compact および LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: b5a1a12018bd85cf313c1841e6b67ab2edf67b4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792540"
---
# <a name="sql-server-compact-and-linq-to-sql"></a><span data-ttu-id="312ef-102">SQL Server Compact および LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="312ef-102">SQL Server Compact and LINQ to SQL</span></span>
<span data-ttu-id="312ef-103">SQL Server Compact は、Visual Studio と共にインストールされる既定のデータベースです。</span><span class="sxs-lookup"><span data-stu-id="312ef-103">SQL Server Compact is the default database installed with Visual Studio.</span></span> <span data-ttu-id="312ef-104">詳細については、「 [SQL Server Compact の使用 (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="312ef-104">For more information, see [Using SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).</span></span>  
  
 <span data-ttu-id="312ef-105">このトピックでは、使用法、構成、機能セット、およびサポート範囲の[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]主な違いについて概説します。</span><span class="sxs-lookup"><span data-stu-id="312ef-105">This topic outlines the key differences in usage, configuration, feature sets, and scope of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] support.</span></span>  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a><span data-ttu-id="312ef-106">LINQ to SQL との関係における SQL Server Compact の特徴</span><span class="sxs-lookup"><span data-stu-id="312ef-106">Characteristics of SQL Server Compact in Relation to LINQ to SQL</span></span>  
 <span data-ttu-id="312ef-107">既定では、すべての Visual Studio エディションに対して SQL Server Compact がインストールされます。したがって、で[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]使用するために開発用コンピューターで使用できます。</span><span class="sxs-lookup"><span data-stu-id="312ef-107">By default, SQL Server Compact is installed for all Visual Studio editions, and is therefore available on the development computer for use with [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="312ef-108">ただし、SQL Server Compact を使用するアプリケーションの配置[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]は、SQL Server アプリケーションとは異なります。</span><span class="sxs-lookup"><span data-stu-id="312ef-108">But deployment of an application that uses SQL Server Compact and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differs from that for a SQL Server application.</span></span> <span data-ttu-id="312ef-109">SQL Server Compact は .NET Framework の一部ではないため、アプリケーションにパッケージ化するか、Microsoft サイトから個別にダウンロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="312ef-109">SQL Server Compact is not a part of the .NET Framework, and therefore must be packaged with the application or downloaded separately from the Microsoft site.</span></span>  
  
 <span data-ttu-id="312ef-110">これには、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="312ef-110">Note the following characteristics:</span></span>  
  
- <span data-ttu-id="312ef-111">SQL Server Compact は DLL としてパッケージ化されており、データベース ファイル (.sdf 拡張子) に対して直接使用できます。</span><span class="sxs-lookup"><span data-stu-id="312ef-111">SQL Server Compact is packaged as a DLL that can be used against database files (.sdf extension) directly.</span></span>  
  
- <span data-ttu-id="312ef-112">SQL Server Compact は、クライアントアプリケーションと同じプロセスで実行されます。</span><span class="sxs-lookup"><span data-stu-id="312ef-112">SQL Server Compact runs in the same process as the client application.</span></span> <span data-ttu-id="312ef-113">そのため、SQL Server Compact との通信効率が SQL Server との通信よりも大幅に高くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="312ef-113">The efficiency of communication with SQL Server Compact can therefore be significantly higher than communicating with SQL Server.</span></span> <span data-ttu-id="312ef-114">一方、SQL Server Compact では、マネージコードとアンマネージコードとの間の相互運用性が必要です。</span><span class="sxs-lookup"><span data-stu-id="312ef-114">On the other hand, SQL Server Compact does require interoperability between managed and unmanaged code with its attendant costs.</span></span>  
  
- <span data-ttu-id="312ef-115">SQL Server Compact DLL のサイズが小さくなっています。</span><span class="sxs-lookup"><span data-stu-id="312ef-115">The size of the SQL Server Compact DLL is small.</span></span> <span data-ttu-id="312ef-116">このため、アプリケーション全体のサイズが抑制されます。</span><span class="sxs-lookup"><span data-stu-id="312ef-116">This feature reduces the overall application size.</span></span>  
  
- <span data-ttu-id="312ef-117">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ランタイムおよび SQLMetal コマンド ライン ツールが SQL Server Compact をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="312ef-117">The [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime and the SQLMetal command-line tool support SQL Server Compact.</span></span>  
  
- <span data-ttu-id="312ef-118">オブジェクトリレーショナルデザイナーは SQL Server Compact をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="312ef-118">The Object Relational Designer does not support SQL Server Compact.</span></span>  
  
## <a name="feature-set"></a><span data-ttu-id="312ef-119">機能セット</span><span class="sxs-lookup"><span data-stu-id="312ef-119">Feature Set</span></span>  
 <span data-ttu-id="312ef-120">SQL Server Compact 機能セットは、アプリケーションに影響[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]する可能性のある次のような SQL Server の機能セットよりもはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="312ef-120">The SQL Server Compact feature set is much simpler than the feature set of SQL Server in the following ways that can affect [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications :</span></span>  
  
- <span data-ttu-id="312ef-121">SQL Server Compact は、ストアド プロシージャまたはビューをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="312ef-121">SQL Server Compact does not support stored procedures or views.</span></span>  
  
- <span data-ttu-id="312ef-122">SQL Server Compact は、一部のデータ型と SQL 関数のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="312ef-122">SQL Server Compact supports only a subset of data types and SQL functions.</span></span>  
  
- <span data-ttu-id="312ef-123">SQL Server Compact は、一部の SQL コンストラクトのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="312ef-123">SQL Server Compact supports only a subset of SQL constructs.</span></span>  
  
- <span data-ttu-id="312ef-124">SQL Server Compact は、最小限のオプティマイザーを備えています。</span><span class="sxs-lookup"><span data-stu-id="312ef-124">SQL Server Compact provides only a minimal optimizer.</span></span> <span data-ttu-id="312ef-125">一部のクエリがタイムアウトする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="312ef-125">It is possible that some queries might time out.</span></span>  
  
- <span data-ttu-id="312ef-126">SQL Server Compact は、部分信頼をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="312ef-126">SQL Server Compact does not support partial trust.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="312ef-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="312ef-127">See also</span></span>

- [<span data-ttu-id="312ef-128">参照</span><span class="sxs-lookup"><span data-stu-id="312ef-128">Reference</span></span>](reference.md)
