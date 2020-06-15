---
title: データベースからの単一の値の取得
description: ADO.NET で単一の値を返す方法について説明します。 このコード例は、挿入されたレコードの ID 列の値を返します。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286703"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="2836e-104">データベースからの単一の値の取得</span><span class="sxs-lookup"><span data-stu-id="2836e-104">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="2836e-105">テーブルやデータ ストリームの形式ではなく、単に 1 つの値をデータベース情報として返すことが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2836e-105">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="2836e-106">たとえば、COUNT(\*)、SUM(Price)、AVG(Quantity) などの集計関数の結果を返す場合です。</span><span class="sxs-lookup"><span data-stu-id="2836e-106">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="2836e-107">**Command** オブジェクトでは、**ExecuteScalar** メソッドを使用して単一の値を返す機能が提供されています。</span><span class="sxs-lookup"><span data-stu-id="2836e-107">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="2836e-108">**ExecuteScalar** メソッドでは、結果セットの 1 行目の 1 列目の値がスカラー値として返されます。</span><span class="sxs-lookup"><span data-stu-id="2836e-108">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="2836e-109"><xref:System.Data.SqlClient.SqlCommand> を使用して新しい値をデータベースに挿入するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="2836e-109">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="2836e-110">挿入したレコードの ID 列の値を取得するために、<xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> メソッドが使用されています。</span><span class="sxs-lookup"><span data-stu-id="2836e-110">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2836e-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="2836e-111">See also</span></span>

- [<span data-ttu-id="2836e-112">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="2836e-112">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="2836e-113">コマンドの実行</span><span class="sxs-lookup"><span data-stu-id="2836e-113">Executing a Command</span></span>](executing-a-command.md)
- [<span data-ttu-id="2836e-114">DbConnection、DbCommand、および DbException</span><span class="sxs-lookup"><span data-stu-id="2836e-114">DbConnection, DbCommand and DbException</span></span>](dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="2836e-115">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="2836e-115">ADO.NET Overview</span></span>](ado-net-overview.md)
