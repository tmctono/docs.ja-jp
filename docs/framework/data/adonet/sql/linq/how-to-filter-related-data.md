---
title: '方法: 関連データをフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: e8e63c139f38d6de46390925428e18682a65818d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793607"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="21aa2-102">方法: 関連データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="21aa2-102">How to: Filter Related Data</span></span>
<span data-ttu-id="21aa2-103">取得したデータの量を制限するサブクエリを指定するには、<xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="21aa2-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21aa2-104">例</span><span class="sxs-lookup"><span data-stu-id="21aa2-104">Example</span></span>  
 <span data-ttu-id="21aa2-105">次の例の <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> メソッドは、取得した `Orders` を、その日に出荷されていないものに限定します。</span><span class="sxs-lookup"><span data-stu-id="21aa2-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="21aa2-106">この処理を行わないと、サブセットのみが必要な場合でも、すべての `Orders` が取得されることになります。</span><span class="sxs-lookup"><span data-stu-id="21aa2-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="21aa2-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="21aa2-107">See also</span></span>

- [<span data-ttu-id="21aa2-108">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="21aa2-108">Querying the Database</span></span>](querying-the-database.md)
