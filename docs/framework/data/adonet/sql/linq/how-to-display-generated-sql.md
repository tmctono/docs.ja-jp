---
title: '方法: 生成された SQL を表示する'
description: Log プロパティを使用して、クエリに対して生成された SQL コードを表示し、デバッグのために LINQ to SQL 機能の理解を深める方法について説明します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
ms.openlocfilehash: 81f6b9603cc7f8b7863f787272ce6a1af920fa75
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169493"
---
# <a name="how-to-display-generated-sql"></a><span data-ttu-id="af7b3-103">方法: 生成された SQL を表示する</span><span class="sxs-lookup"><span data-stu-id="af7b3-103">How to: Display Generated SQL</span></span>

<span data-ttu-id="af7b3-104"><xref:System.Data.Linq.DataContext.Log%2A> プロパティを使用して、クエリに対して生成された SQL コードを表示し、処理を変更できます。</span><span class="sxs-lookup"><span data-stu-id="af7b3-104">You can view the SQL code generated for queries and change processing by using the <xref:System.Data.Linq.DataContext.Log%2A> property.</span></span> <span data-ttu-id="af7b3-105">この方法は、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の機能を理解し、特定の問題をデバッグするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="af7b3-105">This approach can be useful for understanding [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] functionality and for debugging specific problems.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af7b3-106">例</span><span class="sxs-lookup"><span data-stu-id="af7b3-106">Example</span></span>  

 <span data-ttu-id="af7b3-107"><xref:System.Data.Linq.DataContext.Log%2A> プロパティを使用して、コードを実行する前にコンソール ウィンドウに SQL コードを表示するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="af7b3-107">The following example uses the <xref:System.Data.Linq.DataContext.Log%2A> property to display SQL code in the console window before the code is executed.</span></span>  <span data-ttu-id="af7b3-108">このプロパティは、query、insert、update、および delete の各コマンドで使用できます。</span><span class="sxs-lookup"><span data-stu-id="af7b3-108">You can use this property with query, insert, update, and delete commands.</span></span>  
  
 <span data-ttu-id="af7b3-109">コンソール ウィンドウの行は、後の Visual Basic コードまたは C# コードを実行すると表示される内容です。</span><span class="sxs-lookup"><span data-stu-id="af7b3-109">The lines from the console window are what you see when you execute the Visual Basic or C# code that follows.</span></span>  
  
```console  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```console  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="af7b3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="af7b3-110">See also</span></span>

- [<span data-ttu-id="af7b3-111">デバッグのサポート</span><span class="sxs-lookup"><span data-stu-id="af7b3-111">Debugging Support</span></span>](debugging-support.md)
