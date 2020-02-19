---
title: コンテキスト接続
ms.date: 03/30/2017
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.openlocfilehash: e237bb53c699fd4bf051876a378c31b73a038502
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451812"
---
# <a name="the-context-connection"></a><span data-ttu-id="d908f-102">コンテキスト接続</span><span class="sxs-lookup"><span data-stu-id="d908f-102">The Context Connection</span></span>
<span data-ttu-id="d908f-103">内部データへのアクセスに関する問題は、ごく一般的なものです。</span><span class="sxs-lookup"><span data-stu-id="d908f-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="d908f-104">内部データにアクセスすることは、CLR (共通言語ランタイム) ストアド プロシージャや関数を実行しているサーバーへのアクセスを考えることです。</span><span class="sxs-lookup"><span data-stu-id="d908f-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="d908f-105">これを実現する 1 つの選択肢として、<xref:System.Data.SqlClient.SqlConnection> を使用して接続を作成し、ローカル サーバーを指す接続文字列を指定して、接続を開く方法があります。</span><span class="sxs-lookup"><span data-stu-id="d908f-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="d908f-106">これには、ログインのための資格情報を指定することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="d908f-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="d908f-107">接続が、ストアド プロシージャや関数とは別のデータベース セッションにある場合、`SET` オプションが異なっている場合、別のトランザクションに存在している場合、一時テーブルを認識しない場合なども考えられます。</span><span class="sxs-lookup"><span data-stu-id="d908f-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="d908f-108">マネージド ストアド プロシージャや関数のコードが SQL Server プロセスで実行されているということは、だれかがそのサーバーに接続して、マネージド コードを呼び出す SQL ステートメントを実行したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="d908f-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="d908f-109">このような場合、その接続のコンテキストで、その接続のトランザクションや `SET` オプションと共存する形で、ストアド プロシージャまたは関数を実行することを考えます。</span><span class="sxs-lookup"><span data-stu-id="d908f-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="d908f-110">これを "コンテキスト接続" と呼びます。</span><span class="sxs-lookup"><span data-stu-id="d908f-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="d908f-111">コンテキスト接続を使用すると、コードを最初に呼び出したのと同じコンテキストで Transact-SQL ステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d908f-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="d908f-112">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d908f-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="d908f-113">**SQL Server のドキュメント**</span><span class="sxs-lookup"><span data-stu-id="d908f-113">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="d908f-114">コンテキスト接続</span><span class="sxs-lookup"><span data-stu-id="d908f-114">The Context Connection</span></span>](/sql/relational-databases/clr-integration/data-access/context-connection)  
  
## <a name="see-also"></a><span data-ttu-id="d908f-115">参照</span><span class="sxs-lookup"><span data-stu-id="d908f-115">See also</span></span>

- [<span data-ttu-id="d908f-116">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="d908f-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
