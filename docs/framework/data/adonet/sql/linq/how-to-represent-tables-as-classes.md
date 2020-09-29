---
title: '方法: クラスとしてテーブルを表す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166223"
---
# <a name="how-to-represent-tables-as-classes"></a>方法: クラスとしてテーブルを表す

データベース テーブルに関連付けられたエンティティ クラスとしてクラスを指定するには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> 属性を使用します。  
  
### <a name="to-map-a-class-to-a-database-table"></a>データベース テーブルにクラスを対応付けるには  
  
- クラス宣言に <xref:System.Data.Linq.Mapping.TableAttribute> 属性を追加します。  
  
## <a name="example"></a>例  

 次のコードでは、`Customer` データベース テーブルに関連付けられたエンティティ クラスとして、`Customers` クラスを確立します。  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 名前が推論できる場合は、<xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> プロパティを指定する必要はありません。 名前を指定しない場合は、プロパティまたはフィールドと同じ名前であると見なされます。  
  
## <a name="see-also"></a>関連項目

- [LINQ to SQL オブジェクト モデル](the-linq-to-sql-object-model.md)
- [方法: コード エディターを使用してエンティティ クラスをカスタマイズする](how-to-customize-entity-classes-by-using-the-code-editor.md)
