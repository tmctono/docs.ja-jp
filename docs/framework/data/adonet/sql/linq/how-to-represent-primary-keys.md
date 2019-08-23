---
title: '方法: 主キーを表す'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 28c62798f965edfcffe1a156213c2481a8193b49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943527"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="dae4c-102">方法: 主キーを表す</span><span class="sxs-lookup"><span data-stu-id="dae4c-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="dae4c-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 属性のプロパティを使用して、データベース列の主キーを表すプロパティまたはフィールドを<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>指定します。 <xref:System.Data.Linq.Mapping.ColumnAttribute></span><span class="sxs-lookup"><span data-stu-id="dae4c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="dae4c-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dae4c-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="dae4c-105">では、計算列は主キーとしてサポートされません。</span><span class="sxs-lookup"><span data-stu-id="dae4c-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="dae4c-106">プロパティまたはフィールドを主キーとして指定するには</span><span class="sxs-lookup"><span data-stu-id="dae4c-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="dae4c-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="dae4c-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="dae4c-108">値として `true` を指定します。</span><span class="sxs-lookup"><span data-stu-id="dae4c-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae4c-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="dae4c-109">See also</span></span>

- [<span data-ttu-id="dae4c-110">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="dae4c-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="dae4c-111">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="dae4c-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
