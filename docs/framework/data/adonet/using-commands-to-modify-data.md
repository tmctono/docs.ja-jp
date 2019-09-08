---
title: コマンドを使用したデータ変更
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780567"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="89c18-102">コマンドを使用したデータ変更</span><span class="sxs-lookup"><span data-stu-id="89c18-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="89c18-103">.NET Framework データ プロバイダーを使用すると、ストアド プロシージャまたはデータ定義言語のステートメント (たとえば、CREATE TABLE、ALTER COLUMN など) を実行して、データベースやカタログに対するスキーマ操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="89c18-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="89c18-104">これらのコマンドはクエリと同じように行を返さないので、 **Command**オブジェクトはそれらを処理する**ExecuteNonQuery**を提供します。</span><span class="sxs-lookup"><span data-stu-id="89c18-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="89c18-105">**ExecuteNonQuery**を使用してスキーマを変更するだけでなく、このメソッドを使用して、データを変更するが INSERT、UPDATE、DELETE などの行を返さない SQL ステートメントを処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="89c18-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="89c18-106">**ExecuteNonQuery**メソッドでは行が返されませんが、**コマンド**オブジェクトの**parameters**コレクションを使用して、入力パラメーターと出力パラメーターおよび戻り値を渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="89c18-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="89c18-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="89c18-107">In This Section</span></span>  
 [<span data-ttu-id="89c18-108">データ ソースのデータの更新</span><span class="sxs-lookup"><span data-stu-id="89c18-108">Updating Data in a Data Source</span></span>](updating-data-in-a-data-source.md)  
 <span data-ttu-id="89c18-109">データベース内のデータを変更するコマンドまたはストアド プロシージャを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89c18-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="89c18-110">カタログ操作の実行</span><span class="sxs-lookup"><span data-stu-id="89c18-110">Performing Catalog Operations</span></span>](performing-catalog-operations.md)  
 <span data-ttu-id="89c18-111">データベース スキーマを変更するコマンドを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89c18-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c18-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="89c18-112">See also</span></span>

- [<span data-ttu-id="89c18-113">ADO.NET でのデータの取得および変更</span><span class="sxs-lookup"><span data-stu-id="89c18-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="89c18-114">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="89c18-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="89c18-115">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="89c18-115">ADO.NET Overview</span></span>](ado-net-overview.md)
