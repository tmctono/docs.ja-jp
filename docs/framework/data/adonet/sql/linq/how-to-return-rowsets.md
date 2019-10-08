---
title: '方法: 行セットを返す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b853a6f2175009cbcbc01c14a6732b98e37e1a7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003061"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="22e5f-102">方法: 行セットを返す</span><span class="sxs-lookup"><span data-stu-id="22e5f-102">How to: Return Rowsets</span></span>
<span data-ttu-id="22e5f-103">この例では、データベースから行セットを返し、入力パラメーターを使用して結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="22e5f-104">行セットを返すストアドプロシージャを実行する場合は、ストアドプロシージャからの戻り値を格納する*result*クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="22e5f-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="22e5f-105">詳細については、「 [LINQ to SQL ソースコードの分析](analyzing-linq-to-sql-source-code.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e5f-105">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="22e5f-106">例</span><span class="sxs-lookup"><span data-stu-id="22e5f-106">Example</span></span>  
 <span data-ttu-id="22e5f-107">次の例は、顧客の行を返し、入力パラメーターを使用して、顧客が在住する市が "London" である行のみを返すストアド プロシージャを示しています。</span><span class="sxs-lookup"><span data-stu-id="22e5f-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="22e5f-108">例では、列挙可能な `CustomersByCityResult` クラスを想定しています。</span><span class="sxs-lookup"><span data-stu-id="22e5f-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```sql  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="22e5f-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="22e5f-109">See also</span></span>

- [<span data-ttu-id="22e5f-110">ストアド プロシージャ</span><span class="sxs-lookup"><span data-stu-id="22e5f-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="22e5f-111">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="22e5f-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
