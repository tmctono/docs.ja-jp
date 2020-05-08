---
title: SQL 生成
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854360"
---
# <a name="sql-generation"></a><span data-ttu-id="4c2fb-102">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="4c2fb-102">SQL Generation</span></span>
<span data-ttu-id="4c2fb-103">Entity Framework 用のプロバイダーを作成する場合は、Entity Framework のコマンド ツリーを特定のデータベースで認識できる SQL (たとえば、SQL Server の場合は Transact-SQL、Oracle の場合は PL/SQL) に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="4c2fb-104">ここでは、Entity Framework プロバイダーのための SQL 生成コンポーネント (SELECT クエリ用) を開発する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="4c2fb-105">INSERT、UPDATE、および DELETE の各クエリについて詳しくは、「[変更 SQL 生成](modification-sql-generation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="4c2fb-106">このセクションの内容を理解するには、Entity Framework と ADO.NET プロバイダー モデルについての知識が必要です。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="4c2fb-107">また、コマンド ツリーと <xref:System.Data.Common.CommandTrees.DbExpression> について理解している必要もあります。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="4c2fb-108">SQL 生成モジュールの役割</span><span class="sxs-lookup"><span data-stu-id="4c2fb-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="4c2fb-109">Entity Framework プロバイダーの SQL 生成モジュールでは、指定したクエリ コマンド ツリーが、SQL:1999 準拠のデータベースを対象とする 1 つの SQL SELECT ステートメントに変換されます。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="4c2fb-110">生成される SQL 内の入れ子になったクエリは、できるだけ少なくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="4c2fb-111">SQL 生成モジュールによって出力クエリ コマンド ツリーを簡素化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="4c2fb-112">これは、結合の排除や連続するフィルター ノードの折りたたみなどにより、Entity Framework によって実行される処理です。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="4c2fb-113"><xref:System.Data.Common.DbProviderServices> クラスは、SQL 生成レイヤーにアクセスしてコマンド ツリーを <xref:System.Data.Common.DbCommand> に変換するための開始点となります。</span><span class="sxs-lookup"><span data-stu-id="4c2fb-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c2fb-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c2fb-114">In This Section</span></span>  
 [<span data-ttu-id="4c2fb-115">コマンド ツリーの構造</span><span class="sxs-lookup"><span data-stu-id="4c2fb-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="4c2fb-116">コマンド ツリーからの SQL の生成: ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="4c2fb-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="4c2fb-117">サンプル プロバイダーでの SQL 生成</span><span class="sxs-lookup"><span data-stu-id="4c2fb-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="4c2fb-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c2fb-118">See also</span></span>

- [<span data-ttu-id="4c2fb-119">Entity Framework データ プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="4c2fb-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
