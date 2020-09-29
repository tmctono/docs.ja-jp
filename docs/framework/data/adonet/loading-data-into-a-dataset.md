---
title: DataSet へのデータの読み込み
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166717"
---
# <a name="loading-data-into-a-dataset"></a>DataSet へのデータの読み込み

LINQ to DataSet で <xref:System.Data.DataSet> オブジェクトに対するクエリを実行するには、まずデータセットにデータを読み込んでおく必要があります。 <xref:System.Data.DataSet> には、複数の方法でデータを読み込むことができます。 たとえば、[!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] を使用してデータベースのクエリを実行し、その結果を <xref:System.Data.DataSet> に読み込むことができます。 詳細については、「[LINQ to SQL](./sql/linq/index.md)」を参照してください。  
  
 データを <xref:System.Data.DataSet> に読み込む一般的な方法としては、他にも <xref:System.Data.Common.DataAdapter> クラスを使用してデータベースからデータを取得する方法もあります。 このことを次の例で説明します。  
  
## <a name="example"></a>例  

 この例では、<xref:System.Data.Common.DataAdapter> を使用して、2002 年度の売上情報を照会するクエリを AdventureWorks データベースに対して実行し、その結果を <xref:System.Data.DataSet> に読み込んでいます。 <xref:System.Data.DataSet> を設定した後、LINQ to DataSet を使用して、そのデータセットに対するクエリを作成できます。 この例の `FillDataSet` メソッドは、「[LINQ to DataSet の例](linq-to-dataset-examples.md)」のクエリ例で使用されています。 詳しくは、「[DataSet のクエリ](querying-datasets-linq-to-dataset.md)」をご覧ください。  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>関連項目

- [LINQ to DataSet の概要](linq-to-dataset-overview.md)
- [DataSet のクエリ](querying-datasets-linq-to-dataset.md)
- [LINQ to DataSet の例](linq-to-dataset-examples.md)
