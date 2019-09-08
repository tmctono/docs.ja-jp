---
title: DataReader の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 79cb2ce7ffae81aeba9aaca557e37ba566a8370c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784768"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="dae5f-102">DataReader の作成</span><span class="sxs-lookup"><span data-stu-id="dae5f-102">Creating a DataReader</span></span>
<span data-ttu-id="dae5f-103"><xref:System.Data.DataTable> クラスおよび <xref:System.Data.DataSet> クラスには、<xref:System.Data.DataTable.CreateDataReader%2A> の内容または <xref:System.Data.DataTable> オブジェクトの <xref:System.Data.DataSet> コレクションの内容を、読み取り専用で前方参照専用の 1 つ以上の結果セットとして返す <xref:System.Data.DataSet.Tables%2A> メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="dae5f-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dae5f-104">例</span><span class="sxs-lookup"><span data-stu-id="dae5f-104">Example</span></span>  
 <span data-ttu-id="dae5f-105"><xref:System.Data.DataTable> インスタンスを作成するコンソール アプリケーションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dae5f-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="dae5f-106">この例では、入力<xref:System.Data.DataTable>されたを、 <xref:System.Data.DataTable.CreateDataReader%2A>メソッドを呼び出すプロシージャに渡します。このメソッドは<xref:System.Data.DataTableReader>、に含まれる結果を反復処理します。</span><span class="sxs-lookup"><span data-stu-id="dae5f-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="dae5f-107">この例では、次の出力がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dae5f-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="dae5f-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="dae5f-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="dae5f-109">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="dae5f-109">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="dae5f-110">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="dae5f-110">ADO.NET Overview</span></span>](../ado-net-overview.md)
