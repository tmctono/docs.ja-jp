---
title: '方法: クラスとしてテーブルを表す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 1169def4e0180b1d14103d4a968ff3ed56f63d0c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781765"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="66a9d-102">方法: クラスとしてテーブルを表す</span><span class="sxs-lookup"><span data-stu-id="66a9d-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="66a9d-103">クラスを[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]データベーステーブルに関連付けられたエンティティクラスとして指定するには、 <xref:System.Data.Linq.Mapping.TableAttribute>属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="66a9d-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="66a9d-104">データベース テーブルにクラスを対応付けるには</span><span class="sxs-lookup"><span data-stu-id="66a9d-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="66a9d-105">クラス宣言に <xref:System.Data.Linq.Mapping.TableAttribute> 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="66a9d-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66a9d-106">例</span><span class="sxs-lookup"><span data-stu-id="66a9d-106">Example</span></span>  
 <span data-ttu-id="66a9d-107">次のコードでは、`Customer` データベース テーブルに関連付けられたエンティティ クラスとして、`Customers` クラスを確立します。</span><span class="sxs-lookup"><span data-stu-id="66a9d-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="66a9d-108">名前が推論できる場合は、<xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> プロパティを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="66a9d-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="66a9d-109">名前を指定しない場合は、プロパティまたはフィールドと同じ名前であると見なされます。</span><span class="sxs-lookup"><span data-stu-id="66a9d-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a9d-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="66a9d-110">See also</span></span>

- [<span data-ttu-id="66a9d-111">LINQ to SQL オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="66a9d-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="66a9d-112">方法: コードエディターを使用してエンティティクラスをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="66a9d-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
