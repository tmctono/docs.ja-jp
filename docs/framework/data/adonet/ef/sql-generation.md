---
title: SQL 生成
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854360"
---
# <a name="sql-generation"></a><span data-ttu-id="eb77a-102">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="eb77a-102">SQL Generation</span></span>
<span data-ttu-id="eb77a-103">Entity Framework のプロバイダーを作成する場合は、Entity Framework コマンドツリーを、SQL Server や PL/SQL for Oracle など、特定のデータベースで認識できる SQL に変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb77a-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="eb77a-104">このセクションでは、Entity Framework プロバイダーの SQL 生成コンポーネント (SELECT クエリ用) を開発する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb77a-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="eb77a-105">Insert、update、および delete クエリの詳細については、「 [SQL 生成の変更](modification-sql-generation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb77a-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="eb77a-106">このセクションを理解するには、Entity Framework と ADO.NET プロバイダーモデルについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb77a-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="eb77a-107">また、コマンド ツリーと <xref:System.Data.Common.CommandTrees.DbExpression> について理解している必要もあります。</span><span class="sxs-lookup"><span data-stu-id="eb77a-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="eb77a-108">SQL 生成モジュールの役割</span><span class="sxs-lookup"><span data-stu-id="eb77a-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="eb77a-109">Entity Framework プロバイダーの SQL 生成モジュールは、指定されたクエリコマンドツリーを、SQL: 1999 に準拠したデータベースを対象とする1つの SQL SELECT ステートメントに変換します。</span><span class="sxs-lookup"><span data-stu-id="eb77a-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="eb77a-110">生成される SQL 内の入れ子になったクエリは、できるだけ少なくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb77a-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="eb77a-111">SQL 生成モジュールによって出力クエリ コマンド ツリーを簡素化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="eb77a-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="eb77a-112">この操作を行うには、結合をなくし、連続するフィルターノードを折りたたむなど Entity Framework します。</span><span class="sxs-lookup"><span data-stu-id="eb77a-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="eb77a-113"><xref:System.Data.Common.DbProviderServices> クラスは、SQL 生成レイヤーにアクセスしてコマンド ツリーを <xref:System.Data.Common.DbCommand> に変換するための開始点となります。</span><span class="sxs-lookup"><span data-stu-id="eb77a-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb77a-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="eb77a-114">In This Section</span></span>  
 [<span data-ttu-id="eb77a-115">コマンド ツリーの構造</span><span class="sxs-lookup"><span data-stu-id="eb77a-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="eb77a-116">コマンド ツリーからの SQL の生成: ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="eb77a-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="eb77a-117">サンプル プロバイダーでの SQL 生成</span><span class="sxs-lookup"><span data-stu-id="eb77a-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="eb77a-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb77a-118">See also</span></span>

- [<span data-ttu-id="eb77a-119">Entity Framework データ プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="eb77a-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
