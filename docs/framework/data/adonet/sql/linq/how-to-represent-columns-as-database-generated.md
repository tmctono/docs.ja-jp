---
title: '方法: 列をデータベース生成列として表す'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2803697c668a8e1dbbeb426ea41b64878f70c145
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307913"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="1c025-102">方法: 列をデータベース生成列として表す</span><span class="sxs-lookup"><span data-stu-id="1c025-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="1c025-103">使用して、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>プロパティを<xref:System.Data.Linq.Mapping.ColumnAttribute>データベース生成列を表すフィールドまたはプロパティを指定する属性。</span><span class="sxs-lookup"><span data-stu-id="1c025-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="1c025-104">コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c025-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="1c025-105">データベース生成列を表すフィールドまたはプロパティを指定するには</span><span class="sxs-lookup"><span data-stu-id="1c025-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="1c025-106"><xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="1c025-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="1c025-107">プロパティ値を `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="1c025-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c025-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="1c025-108">See also</span></span>

- [<span data-ttu-id="1c025-109">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="1c025-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="1c025-110">方法: コード エディターを使用してエンティティ クラスをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="1c025-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
