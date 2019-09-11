---
title: サンプル プロバイダーでの SQL 生成
ms.date: 03/30/2017
ms.assetid: e70f553d-4622-4627-928e-1aa2ee605d8e
ms.openlocfilehash: a59f1fecf85d63208c3388204c962b5838902ba7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854321"
---
# <a name="sql-generation-in-the-sample-provider"></a><span data-ttu-id="3daec-102">サンプル プロバイダーでの SQL 生成</span><span class="sxs-lookup"><span data-stu-id="3daec-102">SQL Generation in the Sample Provider</span></span>
<span data-ttu-id="3daec-103">[Entity Framework サンプルプロバイダー](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)は、Entity Framework をサポートする ADO.NET データプロバイダーの新しいコンポーネントを示しています。</span><span class="sxs-lookup"><span data-stu-id="3daec-103">The [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) demonstrates the new components of ADO.NET Data Providers that support the Entity Framework.</span></span>  <span data-ttu-id="3daec-104">これは、SQL Server 2005 データベースで動作し、System.Data.SqlClient ADO.NET 2.0 データ プロバイダーのラッパーとして実装されます。</span><span class="sxs-lookup"><span data-stu-id="3daec-104">It works with a SQL Server 2005 database and is implemented as a wrapper for the System.Data.SqlClient ADO.NET 2.0 Data Provider.</span></span>  
  
 <span data-ttu-id="3daec-105">サンプル プロバイダーの SQL 生成モジュール (DmlSqlGenerator.cs ファイルを除き、SQL Generation フォルダーにあります) では、入力として DbQueryCommandTree を使用し、単一の SQL SELECT ステートメントを生成します。</span><span class="sxs-lookup"><span data-stu-id="3daec-105">The SQL Generation module of the Sample Provider (located under the SQL Generation folder, except for the file DmlSqlGenerator.cs) takes an input DbQueryCommandTree and produces a single SQL SELECT statement.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3daec-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3daec-106">In This Section</span></span>  
 <span data-ttu-id="3daec-107">ここでは、次のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3daec-107">This section includes the following topics:</span></span>  
  
 [<span data-ttu-id="3daec-108">アーキテクチャとデザイン</span><span class="sxs-lookup"><span data-stu-id="3daec-108">Architecture and Design</span></span>](architecture-and-design.md)  
  
 [<span data-ttu-id="3daec-109">チュートリアル: SQL 生成</span><span class="sxs-lookup"><span data-stu-id="3daec-109">Walkthrough: SQL Generation</span></span>](walkthrough-sql-generation.md)  
  
## <a name="see-also"></a><span data-ttu-id="3daec-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="3daec-110">See also</span></span>

- [<span data-ttu-id="3daec-111">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="3daec-111">SQL Generation</span></span>](sql-generation.md)
