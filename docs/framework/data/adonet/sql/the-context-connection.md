---
title: コンテキスト接続
ms.date: 03/30/2017
ms.assetid: e443ca86-9243-4234-a822-ed10a53a9de0
ms.openlocfilehash: 83e9f4a9672d2703514c0a86ad8d41b968c255fd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343442"
---
# <a name="the-context-connection"></a><span data-ttu-id="d51d5-102">コンテキスト接続</span><span class="sxs-lookup"><span data-stu-id="d51d5-102">The Context Connection</span></span>
<span data-ttu-id="d51d5-103">内部データ アクセスの問題は、非常に一般的なシナリオです。</span><span class="sxs-lookup"><span data-stu-id="d51d5-103">The problem of internal data access is a fairly common scenario.</span></span> <span data-ttu-id="d51d5-104">つまり、共通言語ランタイム (CLR) ストアド プロシージャまたは関数を実行しているサーバーにアクセスする場合の問題です。</span><span class="sxs-lookup"><span data-stu-id="d51d5-104">That is, you wish to access the same server on which your common language runtime (CLR) stored procedure or function is executing.</span></span> <span data-ttu-id="d51d5-105">1 つの解決方法は、<xref:System.Data.SqlClient.SqlConnection> を使用して接続文字列を作成し、ローカル サーバーをポイントするように接続文字列で指定して、接続を開くことです。</span><span class="sxs-lookup"><span data-stu-id="d51d5-105">One option is to create a connection using <xref:System.Data.SqlClient.SqlConnection>, specify a connection string that points to the local server, and open the connection.</span></span> <span data-ttu-id="d51d5-106">これを行うには、ログインするための資格情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d51d5-106">This requires specifying credentials for logging in.</span></span> <span data-ttu-id="d51d5-107">接続がストアド プロシージャまたは関数とは別のデータベース セッションにある場合や、異なる `SET` オプションが指定されている場合があります。また、別のトランザクション内にある場合や、一時テーブルを参照していない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d51d5-107">The connection is in a different database session than the stored procedure or function, it may have different `SET` options, it is in a separate transaction, it does not see your temporary tables, and so on.</span></span> <span data-ttu-id="d51d5-108">マネージド ストアド プロシージャまたは関数コードが SQL Server プロセス内で実行されている場合、別のユーザーがサーバーに接続して、そのマネージド ストアド プロシージャまたは関数コードを起動する SQL ステートメントを実行していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="d51d5-108">If your managed stored procedure or function code is executing in the SQL Server process, it is because someone connected to that server and executed a SQL statement to invoke it.</span></span> <span data-ttu-id="d51d5-109">接続のコンテキスト内で、ストアド プロシージャまたは関数をトランザクションや `SET` オプションなどと共に実行する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d51d5-109">You probably want the stored procedure or function to execute in the context of that connection, along with its transaction, `SET` options, and so on.</span></span> <span data-ttu-id="d51d5-110">これは、コンテキスト接続と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d51d5-110">This is called the context connection.</span></span>  
  
 <span data-ttu-id="d51d5-111">コンテキスト接続を使用すると、コードが初めに起動されたコンテキスト内で Transact-SQL ステートメントを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="d51d5-111">The context connection lets you execute Transact-SQL statements in the same context that your code was invoked in the first place.</span></span> <span data-ttu-id="d51d5-112">詳細については、ご使用中の SQL Server のバージョンに対応するバージョンの SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d51d5-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="d51d5-113">**SQL Server オンライン ブック**</span><span class="sxs-lookup"><span data-stu-id="d51d5-113">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="d51d5-114">コンテキスト接続</span><span class="sxs-lookup"><span data-stu-id="d51d5-114">The Context Connection</span></span>](https://go.microsoft.com/fwlink/?LinkId=115395)  
  
## <a name="see-also"></a><span data-ttu-id="d51d5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="d51d5-115">See also</span></span>

- [<span data-ttu-id="d51d5-116">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="d51d5-116">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
