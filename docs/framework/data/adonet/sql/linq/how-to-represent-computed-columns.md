---
title: '方法: 計算列を表す'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 01c3442448285893ebb476ed11889e073065d4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943542"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="0e6f1-102">方法: 計算列を表す</span><span class="sxs-lookup"><span data-stu-id="0e6f1-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="0e6f1-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 属性のプロパティを使用して、計算結果が内容である<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>列を表します<xref:System.Data.Linq.Mapping.ColumnAttribute> 。</span><span class="sxs-lookup"><span data-stu-id="0e6f1-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="0e6f1-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0e6f1-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="0e6f1-105">では、計算列は主キーとしてサポートされません。</span><span class="sxs-lookup"><span data-stu-id="0e6f1-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="0e6f1-106">計算列を表すには</span><span class="sxs-lookup"><span data-stu-id="0e6f1-106">To represent a computed column</span></span>  
  
1. <span data-ttu-id="0e6f1-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="0e6f1-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="0e6f1-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> プロパティに数式を表す文字列を代入します。</span><span class="sxs-lookup"><span data-stu-id="0e6f1-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e6f1-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="0e6f1-109">See also</span></span>

- [<span data-ttu-id="0e6f1-110">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="0e6f1-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="0e6f1-111">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="0e6f1-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
