---
title: カタログ操作の実行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: 0291b6684092ec15fc672c39c909caf7781194e3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783259"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="3ff67-102">カタログ操作の実行</span><span class="sxs-lookup"><span data-stu-id="3ff67-102">Performing Catalog Operations</span></span>
<span data-ttu-id="3ff67-103">データベースまたはカタログを変更するコマンドを実行するには (CREATE TABLE ステートメントや CREATE PROCEDURE ステートメントなど)、適切な SQL ステートメントと**接続**オブジェクトを使用して**command**オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ff67-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="3ff67-104">**Command オブジェクトの** **ExecuteNonQuery**メソッドを使用してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3ff67-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="3ff67-105">Microsoft SQL Server データベースにストアド プロシージャを作成するコード サンプルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3ff67-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +   
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +   
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +   
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ff67-106">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ff67-106">See also</span></span>

- [<span data-ttu-id="3ff67-107">コマンドを使用したデータ変更</span><span class="sxs-lookup"><span data-stu-id="3ff67-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="3ff67-108">コマンドおよびパラメーター</span><span class="sxs-lookup"><span data-stu-id="3ff67-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="3ff67-109">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="3ff67-109">ADO.NET Overview</span></span>](ado-net-overview.md)
