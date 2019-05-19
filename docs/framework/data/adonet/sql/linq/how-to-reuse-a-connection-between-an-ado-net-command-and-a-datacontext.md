---
title: '方法: ADO.NET コマンドおよび DataContext 間の接続を再利用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
ms.openlocfilehash: 92b0d8cf2c4904fabc17241ef2c31175f0c87baf
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878537"
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a><span data-ttu-id="8658e-102">方法: ADO.NET コマンドおよび DataContext 間の接続を再利用する</span><span class="sxs-lookup"><span data-stu-id="8658e-102">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>
<span data-ttu-id="8658e-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ADO.NET ファミリのテクノロジの一部であるし、ADO.NET、ADO.NET コマンド間の接続を再利用できます提供されるサービスに基づいて、<xref:System.Data.Linq.DataContext>します。</span><span class="sxs-lookup"><span data-stu-id="8658e-103">Because [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] is a part of the ADO.NET family of technologies and is based on services provided by ADO.NET, you can reuse a connection between an ADO.NET command and a <xref:System.Data.Linq.DataContext>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8658e-104">例</span><span class="sxs-lookup"><span data-stu-id="8658e-104">Example</span></span>  
 <span data-ttu-id="8658e-105">次の例では、ADO.NET コマンドの間で同じ接続を再利用する方法を示していますと<xref:System.Data.Linq.DataContext>します。</span><span class="sxs-lookup"><span data-stu-id="8658e-105">The following example shows how to reuse the same connection between an ADO.NET command and the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8658e-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="8658e-106">See also</span></span>

- [<span data-ttu-id="8658e-107">背景情報</span><span class="sxs-lookup"><span data-stu-id="8658e-107">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [<span data-ttu-id="8658e-108">ADO.NET および LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8658e-108">ADO.NET and LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)
- [<span data-ttu-id="8658e-109">データベースとの通信</span><span class="sxs-lookup"><span data-stu-id="8658e-109">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
