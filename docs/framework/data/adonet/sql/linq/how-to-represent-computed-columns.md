---
title: '方法: 計算列を表す'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: f624bb49773af2c0053851ac55727b6db8632131
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204121"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="77adf-102">方法: 計算列を表す</span><span class="sxs-lookup"><span data-stu-id="77adf-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="77adf-103">使用して、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>プロパティを<xref:System.Data.Linq.Mapping.ColumnAttribute>計算の結果で構成される列を表す属性です。</span><span class="sxs-lookup"><span data-stu-id="77adf-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="77adf-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77adf-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="77adf-105">主キーとしては、計算列をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="77adf-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="77adf-106">計算列を表すには</span><span class="sxs-lookup"><span data-stu-id="77adf-106">To represent a computed column</span></span>  
  
1.  <span data-ttu-id="77adf-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="77adf-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="77adf-108"><xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> プロパティに数式を表す文字列を代入します。</span><span class="sxs-lookup"><span data-stu-id="77adf-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77adf-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="77adf-109">See also</span></span>

- [<span data-ttu-id="77adf-110">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="77adf-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="77adf-111">方法: コード エディターを使用してエンティティ クラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="77adf-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
