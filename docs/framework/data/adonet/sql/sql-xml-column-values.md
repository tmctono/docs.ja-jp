---
title: SQL XML 列値
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d97ce4da-f09c-4d1e-85b7-a0ccedd7246a
ms.openlocfilehash: 29e9ac5b95b62ef2a4467bf41484c3740d550abd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964949"
---
# <a name="sql-xml-column-values"></a><span data-ttu-id="c7a31-102">SQL XML 列値</span><span class="sxs-lookup"><span data-stu-id="c7a31-102">SQL XML Column Values</span></span>
<span data-ttu-id="c7a31-103">SQL Server は`xml`データ型をサポートし、開発者は<xref:System.Data.SqlClient.SqlCommand>クラスの標準動作を使用して、この型を含む結果セットを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-103">SQL Server supports the `xml` data type, and developers can retrieve result sets including this type using standard behavior of the <xref:System.Data.SqlClient.SqlCommand> class.</span></span> <span data-ttu-id="c7a31-104">`xml` 列は、その他の列と同じようにして (<xref:System.Data.SqlClient.SqlDataReader> などに) 取得することができますが、その列の内容を XML として使用する場合は、<xref:System.Xml.XmlReader> を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-104">An `xml` column can be retrieved just as any column is retrieved (into a <xref:System.Data.SqlClient.SqlDataReader>, for example) but if you want to work with the content of the column as XML, you must use an <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7a31-105">例</span><span class="sxs-lookup"><span data-stu-id="c7a31-105">Example</span></span>  
 <span data-ttu-id="c7a31-106">次のコンソールアプリケーションでは、 `xml` **AdventureWorks**データベースの<xref:System.Data.SqlClient.SqlDataReader> **Sales. Store**テーブルからインスタンスに、列を含む2つの行を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-106">The following console application selects two rows, each containing an `xml` column, from the **Sales.Store** table in the **AdventureWorks** database to a <xref:System.Data.SqlClient.SqlDataReader> instance.</span></span> <span data-ttu-id="c7a31-107">それぞれの行について、`xml` 列の値は、<xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> の <xref:System.Data.SqlClient.SqlDataReader> メソッドを使用して読み取ります。</span><span class="sxs-lookup"><span data-stu-id="c7a31-107">For each row, the value of the `xml` column is read using the <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> method of <xref:System.Data.SqlClient.SqlDataReader>.</span></span> <span data-ttu-id="c7a31-108">値は、<xref:System.Xml.XmlReader> に格納されます。</span><span class="sxs-lookup"><span data-stu-id="c7a31-108">The value is stored in an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="c7a31-109">内容を <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> 変数に設定する場合は、<xref:System.Data.IDataRecord.GetValue%2A> メソッドではなく <xref:System.Data.SqlTypes.SqlXml> を使用する必要があることに注意してください。<xref:System.Data.IDataRecord.GetValue%2A> は、`xml` 列の値を文字列として返します。</span><span class="sxs-lookup"><span data-stu-id="c7a31-109">Note that you must use <xref:System.Data.SqlClient.SqlDataReader.GetSqlXml%2A> rather than the <xref:System.Data.IDataRecord.GetValue%2A> method if you want to set the contents to a <xref:System.Data.SqlTypes.SqlXml> variable; <xref:System.Data.IDataRecord.GetValue%2A> returns the value of the `xml` column as a string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7a31-110">SQL Server をインストールした場合、既定では、 **AdventureWorks**サンプルデータベースはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="c7a31-110">The **AdventureWorks** sample database is not installed by default when you install SQL Server.</span></span> <span data-ttu-id="c7a31-111">SQL Server Setup を実行してインストールします。</span><span class="sxs-lookup"><span data-stu-id="c7a31-111">You can install it by running SQL Server Setup.</span></span>  
  
 [!code-csharp[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.GetXmlDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.GetXmlDataReader/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c7a31-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7a31-112">See also</span></span>

- <xref:System.Data.SqlTypes.SqlXml>
- [<span data-ttu-id="c7a31-113">SQL Server における XML データ</span><span class="sxs-lookup"><span data-stu-id="c7a31-113">XML Data in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/xml-data-in-sql-server.md)
- [<span data-ttu-id="c7a31-114">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="c7a31-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
