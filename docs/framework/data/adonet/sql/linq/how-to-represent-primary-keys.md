---
title: '方法: 主キーを表す'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: dcb8929c9cd9a7b88f19d760b70117a1092760f9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59295589"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="235ba-102">方法: 主キーを表す</span><span class="sxs-lookup"><span data-stu-id="235ba-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="235ba-103">使用して、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>プロパティを<xref:System.Data.Linq.Mapping.ColumnAttribute>をデータベース列に主キーを表すフィールドまたはプロパティを指定する属性。</span><span class="sxs-lookup"><span data-stu-id="235ba-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="235ba-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="235ba-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="235ba-105">では、計算列は主キーとしてサポートされません。</span><span class="sxs-lookup"><span data-stu-id="235ba-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="235ba-106">プロパティまたはフィールドを主キーとして指定するには</span><span class="sxs-lookup"><span data-stu-id="235ba-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="235ba-107"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="235ba-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="235ba-108">値として `true` を指定します。</span><span class="sxs-lookup"><span data-stu-id="235ba-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235ba-109">関連項目</span><span class="sxs-lookup"><span data-stu-id="235ba-109">See also</span></span>

- [<span data-ttu-id="235ba-110">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="235ba-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="235ba-111">方法: コード エディターを使用してエンティティ クラスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="235ba-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
