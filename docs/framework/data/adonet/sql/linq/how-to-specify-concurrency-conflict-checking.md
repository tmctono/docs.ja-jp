---
title: '方法: コンカレンシーの競合のチェックを指定する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: fd3db5eb5dc9b74d8ea33af56dd522cf2f3fecdb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781588"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="64d69-102">方法: コンカレンシーの競合のチェックを指定する</span><span class="sxs-lookup"><span data-stu-id="64d69-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="64d69-103"><xref:System.Data.Linq.DataContext.SubmitChanges%2A> を呼び出すときにコンカレンシーの競合をチェックするデータベース列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="64d69-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="64d69-104">詳細については、「[方法 :同時実行の競合](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)をテストするメンバーを指定します。</span><span class="sxs-lookup"><span data-stu-id="64d69-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="64d69-105">例</span><span class="sxs-lookup"><span data-stu-id="64d69-105">Example</span></span>  
 <span data-ttu-id="64d69-106">次のコード例では、更新の確認時に `HomePage` メンバーを検査しないことを指定しています。</span><span class="sxs-lookup"><span data-stu-id="64d69-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="64d69-107">詳細については、「 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64d69-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="64d69-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="64d69-108">See also</span></span>

- [<span data-ttu-id="64d69-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="64d69-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="64d69-110">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="64d69-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
