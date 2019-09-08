---
title: '方法: クラス メンバーとして列を表す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 515a8477b3a9c72934e0ad11d7b1bf599e8b16a2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793505"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="0f443-102">方法: クラス メンバーとして列を表す</span><span class="sxs-lookup"><span data-stu-id="0f443-102">How to: Represent Columns as Class Members</span></span>
<span data-ttu-id="0f443-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 属性を使用して、フィールドまたはプロパティをデータベース<xref:System.Data.Linq.Mapping.ColumnAttribute>列に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="0f443-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="0f443-104">フィールドまたはプロパティをデータベース列に対応付けるには</span><span class="sxs-lookup"><span data-stu-id="0f443-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="0f443-105">プロパティまたはフィールドの宣言に <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="0f443-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f443-106">例</span><span class="sxs-lookup"><span data-stu-id="0f443-106">Example</span></span>  
 <span data-ttu-id="0f443-107">次の例では、`CustomerID` クラス内の `Customer` フィールドを `CustomerID` データベース テーブル内の `Customers` 列に対応付けます。</span><span class="sxs-lookup"><span data-stu-id="0f443-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="0f443-108">名前が推論できる場合は、<xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> プロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0f443-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="0f443-109">名前を指定しない場合は、プロパティまたはフィールドと同じ名前であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="0f443-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f443-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="0f443-110">See also</span></span>

- [<span data-ttu-id="0f443-111">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="0f443-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="0f443-112">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="0f443-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
