---
title: DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202319"
---
# <a name="datatablereaders"></a>DataTableReader

<xref:System.Data.DataTableReader> は、<xref:System.Data.DataTable> または <xref:System.Data.DataSet> の内容を、読み取り専用かつ前方参照専用の 1 つ以上の結果セットとして表します。  
  
 **DataTable** から **DataTableReader** を作成すると、結果の **DataTableReader** オブジェクトには、その作成元である **DataTable** と同一データ (ただし、Deleted とマークされた行は除く) を持つ結果セットが 1 つ設定されます。 各列は、元の **DataTable** と同じ順序で格納されます。  
  
 <xref:System.Data.DataSet.CreateDataReader%2A> の呼び出しによって作成された **DataTableReader** には、複数の結果セットが含まれる場合があります。 結果は、**DataSet** オブジェクトの <xref:System.Data.DataSet.Tables%2A> コレクション内の **DataTable** と同じ順序になります。  
  
## <a name="in-this-section"></a>このセクションの内容  

 [DataReader の作成](creating-a-datareader.md)  
 **DataTableReader** オブジェクトの作成方法について説明します。  
  
 [DataTable の移動](navigating-datatables.md)  
 **Read** メソッドを使用して、**DataTableReader** の内容を取得する方法について説明します。  
  
## <a name="see-also"></a>関連項目

- [ADO.NET でのデータの取得および変更](../retrieving-and-modifying-data.md)
- [ADO.NET の概要](../ado-net-overview.md)
