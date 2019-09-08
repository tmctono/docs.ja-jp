---
title: '方法: データ送信をトランザクションで囲む'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 6a4c5ba7c4938b48fe489e43ff4a3ff806bd8916
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793805"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="a06a2-102">方法: データ送信をトランザクションで囲む</span><span class="sxs-lookup"><span data-stu-id="a06a2-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="a06a2-103">データベースへの送信を <xref:System.Transactions.TransactionScope> で囲むことができます。</span><span class="sxs-lookup"><span data-stu-id="a06a2-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="a06a2-104">詳細については、「[トランザクションのサポート](transaction-support.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a06a2-104">For more information, see [Transaction Support](transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a06a2-105">例</span><span class="sxs-lookup"><span data-stu-id="a06a2-105">Example</span></span>  
 <span data-ttu-id="a06a2-106">次のコードでは、データベース送信を <xref:System.Transactions.TransactionScope> で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a06a2-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a06a2-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="a06a2-107">See also</span></span>

- [<span data-ttu-id="a06a2-108">サンプル データベースのダウンロード</span><span class="sxs-lookup"><span data-stu-id="a06a2-108">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="a06a2-109">データの変更と変更の送信</span><span class="sxs-lookup"><span data-stu-id="a06a2-109">Making and Submitting Data Changes</span></span>](making-and-submitting-data-changes.md)
- [<span data-ttu-id="a06a2-110">トランザクションのサポート</span><span class="sxs-lookup"><span data-stu-id="a06a2-110">Transaction Support</span></span>](transaction-support.md)
