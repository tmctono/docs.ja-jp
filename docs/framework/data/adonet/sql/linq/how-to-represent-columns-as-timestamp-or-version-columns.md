---
title: '方法: 列をタイムスタンプ列またはバージョン列として表現する'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: cc8538ab7b2ecf5183cfb97995c04648493a369f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191750"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>方法: 列をタイムスタンプ列またはバージョン列として表現する

データベースのタイムスタンプまたはバージョン番号を保持するデータベース列を表すフィールドまたはプロパティを指定するには、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] の <xref:System.Data.Linq.Mapping.ColumnAttribute> 属性の <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> プロパティを使用します。  
  
 コード例については、「<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>」を参照してください。  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>タイムスタンプ列またはバージョン列を表すフィールドまたはプロパティを指定するには  
  
1. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> 属性に <xref:System.Data.Linq.Mapping.ColumnAttribute> プロパティを追加します。  
  
2. <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> プロパティ値を `true` に設定します。  
  
## <a name="see-also"></a>関連項目

- [LINQ to SQL オブジェクト モデル](the-linq-to-sql-object-model.md)
- [方法: コンカレンシーの競合を検査するメンバーを指定する](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [方法: コード エディターを使用してエンティティ クラスをカスタマイズする](how-to-customize-entity-classes-by-using-the-code-editor.md)
