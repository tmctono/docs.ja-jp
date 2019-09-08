---
title: '方法: ADO.NET コマンドおよび DataContext 間の接続を再利用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: f1ee7726042327eae88e69e9e6d062909c5bc74e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793293"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="e50c1-102">方法: ADO.NET コマンドおよび DataContext 間の接続を再利用する</span><span class="sxs-lookup"><span data-stu-id="e50c1-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="e50c1-103">は[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ADO.NET のテクノロジファミリの一部であり、ADO.NET によって提供されるサービスに基づいているため、ADO.NET コマンドとの<xref:System.Data.Linq.DataContext>間の接続を再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="e50c1-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e50c1-104">例</span><span class="sxs-lookup"><span data-stu-id="e50c1-104">Example</span></span>  
 <span data-ttu-id="e50c1-105">次の例は、ADO.NET コマンドとの<xref:System.Data.Linq.DataContext>間で同じ接続を再利用する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="e50c1-105">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e50c1-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="e50c1-106">See also</span></span>

- [<span data-ttu-id="e50c1-107">背景情報</span><span class="sxs-lookup"><span data-stu-id="e50c1-107">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="e50c1-108">ADO.NET および LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="e50c1-108">ADO.NET and LINQ to SQL</span></span>](ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="e50c1-109">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="e50c1-109">Communicating with the Database</span></span>](communicating-with-the-database.md)
