---
title: '方法: 関連データをフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218226"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="2c5b0-102">方法: 関連データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="2c5b0-102">How to: Filter Related Data</span></span>
<span data-ttu-id="2c5b0-103">取得したデータの量を制限するサブクエリを指定するには、<xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2c5b0-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c5b0-104">例</span><span class="sxs-lookup"><span data-stu-id="2c5b0-104">Example</span></span>  
 <span data-ttu-id="2c5b0-105">次の例の <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> メソッドは、取得した `Orders` を、その日に出荷されていないものに限定します。</span><span class="sxs-lookup"><span data-stu-id="2c5b0-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="2c5b0-106">この処理を行わないと、サブセットのみが必要な場合でも、すべての `Orders` が取得されることになります。</span><span class="sxs-lookup"><span data-stu-id="2c5b0-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2c5b0-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c5b0-107">See also</span></span>

- [<span data-ttu-id="2c5b0-108">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="2c5b0-108">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
