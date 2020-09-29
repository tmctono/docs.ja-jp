---
title: '方法: 列をデータベース生成列として表す'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 914fdcb78efbaaddf08330e32e1d7f7c4e62436e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166314"
---
# <a name="how-to-represent-columns-as-database-generated"></a>方法: 列をデータベース生成列として表す

データベース生成列を表すフィールドまたはプロパティを指定するには、<xref:System.Data.Linq.Mapping.ColumnAttribute> 属性の [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> プロパティを使用します。  
  
 コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>」を参照してください。  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>データベース生成列を表すフィールドまたはプロパティを指定するには  
  
1. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。  
  
2. プロパティ値を `true` に設定します。  
  
## <a name="see-also"></a>関連項目

- [LINQ to SQL オブジェクト モデル](the-linq-to-sql-object-model.md)
- [方法: コード エディターを使用してエンティティ クラスをカスタマイズする](how-to-customize-entity-classes-by-using-the-code-editor.md)
