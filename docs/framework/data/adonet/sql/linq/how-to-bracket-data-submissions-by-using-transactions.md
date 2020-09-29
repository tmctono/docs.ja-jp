---
title: '方法: データ送信をトランザクションで囲む'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161361"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>方法: データ送信をトランザクションで囲む

データベースへの送信を <xref:System.Transactions.TransactionScope> で囲むことができます。 詳しくは、「[トランザクションのサポート](transaction-support.md)」をご覧ください。  
  
## <a name="example"></a>例  

 次のコードでは、データベース送信を <xref:System.Transactions.TransactionScope> で囲みます。  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>関連項目

- [サンプル データベースのダウンロード](downloading-sample-databases.md)
- [データの変更と変更の送信](making-and-submitting-data-changes.md)
- [トランザクションのサポート](transaction-support.md)
