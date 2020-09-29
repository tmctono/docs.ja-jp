---
title: '方法: 関連データをフィルター処理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: e12bab55b03fac3383b98b8ee1c56ab1954ff978
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173459"
---
# <a name="how-to-filter-related-data"></a><span data-ttu-id="8e108-102">方法: 関連データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="8e108-102">How to: Filter Related Data</span></span>

<span data-ttu-id="8e108-103">取得したデータの量を制限するサブクエリを指定するには、<xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8e108-103">Use the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method to specify sub-queries to limit the amount of retrieved data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e108-104">例</span><span class="sxs-lookup"><span data-stu-id="8e108-104">Example</span></span>  

 <span data-ttu-id="8e108-105">次の例の <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> メソッドは、取得した `Orders` を、その日に出荷されていないものに限定します。</span><span class="sxs-lookup"><span data-stu-id="8e108-105">In the following example, the <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> method limits the `Orders` retrieved to those that have not been shipped today.</span></span> <span data-ttu-id="8e108-106">この処理を行わないと、サブセットのみが必要な場合でも、すべての `Orders` が取得されることになります。</span><span class="sxs-lookup"><span data-stu-id="8e108-106">Without this approach, all `Orders` would have been retrieved even though only a subset is desired.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8e108-107">関連項目</span><span class="sxs-lookup"><span data-stu-id="8e108-107">See also</span></span>

- [<span data-ttu-id="8e108-108">データベースに対するクエリの実行</span><span class="sxs-lookup"><span data-stu-id="8e108-108">Querying the Database</span></span>](querying-the-database.md)
