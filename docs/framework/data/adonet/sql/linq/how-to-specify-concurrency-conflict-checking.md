---
title: '方法: コンカレンシーの競合のチェックを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: fd3db5eb5dc9b74d8ea33af56dd522cf2f3fecdb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781588"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="81504-102">方法: コンカレンシーの競合のチェックを指定する</span><span class="sxs-lookup"><span data-stu-id="81504-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="81504-103"><xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すときにコンカレンシーの競合をチェックするデータベース列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="81504-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="81504-104">詳細については、[コンカレンシーの競合を検査するメンバーを指定する](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81504-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="81504-105">例</span><span class="sxs-lookup"><span data-stu-id="81504-105">Example</span></span>  
 <span data-ttu-id="81504-106">次のコード例では、更新の確認時に `HomePage` メンバーを検査しないことを指定しています。</span><span class="sxs-lookup"><span data-stu-id="81504-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="81504-107">詳細については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81504-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="81504-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="81504-108">See also</span></span>

- [<span data-ttu-id="81504-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="81504-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="81504-110">方法: コード エディターを使用してエンティティ クラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="81504-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
