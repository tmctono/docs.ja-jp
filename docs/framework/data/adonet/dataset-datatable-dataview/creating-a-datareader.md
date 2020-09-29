---
title: DataReader の作成
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 3af6ae3a8f4ecc3ec34c186ce55c1c77c27514a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202332"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="8507a-102">DataReader の作成</span><span class="sxs-lookup"><span data-stu-id="8507a-102">Creating a DataReader</span></span>

<span data-ttu-id="8507a-103"><xref:System.Data.DataTable> クラスおよび <xref:System.Data.DataSet> クラスには、<xref:System.Data.DataTable.CreateDataReader%2A> の内容または <xref:System.Data.DataTable> オブジェクトの <xref:System.Data.DataSet> コレクションの内容を、読み取り専用で前方参照専用の 1 つ以上の結果セットとして返す <xref:System.Data.DataSet.Tables%2A> メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="8507a-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8507a-104">例</span><span class="sxs-lookup"><span data-stu-id="8507a-104">Example</span></span>  

 <span data-ttu-id="8507a-105"><xref:System.Data.DataTable> インスタンスを作成するコンソール アプリケーションの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8507a-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="8507a-106">その後、データが格納された <xref:System.Data.DataTable> を、<xref:System.Data.DataTable.CreateDataReader%2A> メソッドを呼び出すプロシージャに渡し、そこで <xref:System.Data.DataTableReader> 内に格納された結果の反復処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="8507a-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="8507a-107">この例では、次の出力がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8507a-107">The example displays the following output in the console window:</span></span>  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="8507a-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="8507a-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="8507a-109">DataTableReaders</span><span class="sxs-lookup"><span data-stu-id="8507a-109">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="8507a-110">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="8507a-110">ADO.NET Overview</span></span>](../ado-net-overview.md)
