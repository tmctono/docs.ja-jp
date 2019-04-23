---
title: '方法: ADO.NET コマンドおよび DataContext 間の接続を再利用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 47e1e45cfe693e3569c343f1058ce2d610af96dd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163151"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="9b256-102">方法: ADO.NET コマンドおよび DataContext 間の接続を再利用する</span><span class="sxs-lookup"><span data-stu-id="9b256-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="9b256-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]の一部である、[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]ファミリのテクノロジによって提供されるサービスに基づいています[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]、間の接続を再利用することができます、[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]コマンドと<xref:System.Data.Linq.DataContext>します。</span><span class="sxs-lookup"><span data-stu-id="9b256-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies and is based on services provided by [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], you can reuse a connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b256-104">例</span><span class="sxs-lookup"><span data-stu-id="9b256-104">Example</span></span>  
 <span data-ttu-id="9b256-105">[!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] コマンドおよび <xref:System.Data.Linq.DataContext> 間の同じ接続を再利用する方法を次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="9b256-105">The following example shows how to reuse the same connection between an [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="9b256-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="9b256-106">See also</span></span>

- [<span data-ttu-id="9b256-107">背景情報</span><span class="sxs-lookup"><span data-stu-id="9b256-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="9b256-108">ADO.NET および LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9b256-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="9b256-109">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="9b256-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
