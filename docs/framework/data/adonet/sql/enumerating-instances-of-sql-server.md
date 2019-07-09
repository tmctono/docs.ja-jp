---
title: SQL Server のインスタンスの列挙 (ADO.NET)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: d6d76d677bcf7dfa7df632bde8de76401a46db05
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661886"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="f0776-102">SQL Server のインスタンスの列挙 (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="f0776-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="f0776-103">SQL Server には、現在のネットワーク内の SQL Server インスタンスを検索するアプリケーションが許可されます。</span><span class="sxs-lookup"><span data-stu-id="f0776-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="f0776-104"><xref:System.Data.Sql.SqlDataSourceEnumerator> クラスは、表示可能なすべてのサーバーに関する情報が含まれた <xref:System.Data.DataTable> を提供することで、アプリケーション開発者にこの情報を公開します。</span><span class="sxs-lookup"><span data-stu-id="f0776-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="f0776-105">これは、テーブルには、ユーザーが新しい接続を作成しようとしたときに指定された一覧と一致してで使用可能なすべてのサーバーを含むドロップダウン リストを展開するネットワークで使用できるサーバー インスタンスの一覧が含まれています返される、**接続。プロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f0776-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="f0776-106">結果には一部のインスタンスが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f0776-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0776-107">大半の Windows サービスと同様に、できるだけ少ない特権で SQL Browser サービスを実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0776-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="f0776-108">SQL Browser サービスの詳細および SQL Browser サービスの動作を管理する方法については、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f0776-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="f0776-109">列挙子インスタンスの取得</span><span class="sxs-lookup"><span data-stu-id="f0776-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="f0776-110">使用可能な SQL Server インスタンスに関する情報が含まれたテーブルを取得するには、まず、共有プロパティまたは静的プロパティである <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> プロパティを使用して列挙子を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0776-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="f0776-111">静的なインスタンスを取得したら、使用可能なサーバーに関する情報が含まれた <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> を返す <xref:System.Data.DataTable> メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="f0776-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="f0776-112">このメソッド呼び出しから返されるテーブルには、次の列が含まれています。これらすべての列に `string` 値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0776-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="f0776-113">Column</span><span class="sxs-lookup"><span data-stu-id="f0776-113">Column</span></span>|<span data-ttu-id="f0776-114">説明</span><span class="sxs-lookup"><span data-stu-id="f0776-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f0776-115">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="f0776-115">**ServerName**</span></span>|<span data-ttu-id="f0776-116">サーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="f0776-116">Name of the server.</span></span>|  
|<span data-ttu-id="f0776-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="f0776-117">**InstanceName**</span></span>|<span data-ttu-id="f0776-118">サーバー インスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="f0776-118">Name of the server instance.</span></span> <span data-ttu-id="f0776-119">サーバーが既定のインスタンスとして実行されている場合は空白になります。</span><span class="sxs-lookup"><span data-stu-id="f0776-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="f0776-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="f0776-120">**IsClustered**</span></span>|<span data-ttu-id="f0776-121">サーバーがクラスターの一部になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="f0776-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="f0776-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="f0776-122">**Version**</span></span>|<span data-ttu-id="f0776-123">サーバーのバージョン。</span><span class="sxs-lookup"><span data-stu-id="f0776-123">Version of the server.</span></span> <span data-ttu-id="f0776-124">例えば:</span><span class="sxs-lookup"><span data-stu-id="f0776-124">For example:</span></span><br /><br /> <span data-ttu-id="f0776-125">-9.00.x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="f0776-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="f0776-126">-   10.0.xx (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="f0776-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="f0776-127">-10.50.x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="f0776-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="f0776-128">-   11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="f0776-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="f0776-129">列挙の制約</span><span class="sxs-lookup"><span data-stu-id="f0776-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="f0776-130">使用可能なサーバーの一部が表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="f0776-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="f0776-131">サーバーの一覧は、タイムアウトやネットワーク トラフィックなどの要因によって異なることがあります。</span><span class="sxs-lookup"><span data-stu-id="f0776-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="f0776-132">そのため、2 回続けて呼び出しても、呼び出しごとにリストが異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f0776-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="f0776-133">同じネットワーク上のサーバーのみがリストに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0776-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="f0776-134">通常、ブロードキャスト パケットはルーターを経由しません。そのため、特定のサーバーがリストに表示されないことがありますが、その状態はいつ呼び出しを行っても変わりません。</span><span class="sxs-lookup"><span data-stu-id="f0776-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="f0776-135">一覧に含まれているサーバーは、`IsClustered` やバージョンなどの追加情報を持っている場合も、持っていない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="f0776-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="f0776-136">サーバーが持っている情報は、一覧が取得された方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="f0776-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="f0776-137">SQL Server ブラウザー サービスを介して一覧表示されるサーバーには、名前しか一覧表示しない Windows インフラストラクチャを介して検索されたサーバーより多くの詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0776-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0776-138">サーバー列挙は、完全に信頼された環境で実行している場合にのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="f0776-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="f0776-139">部分的に信頼された環境で実行されているアセンブリは、<xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) アクセス許可を持っている場合でも、サーバー列挙を使用できません。</span><span class="sxs-lookup"><span data-stu-id="f0776-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="f0776-140">SQL Server の情報を提供する、 <xref:System.Data.Sql.SqlDataSourceEnumerator> SQL Browser という名前の外部 Windows サービスを利用しています。</span><span class="sxs-lookup"><span data-stu-id="f0776-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="f0776-141">このサービスは既定で有効になりますが、管理者がこのサービスをオフにしたり無効にしたりすると、サーバー インスタンスがこのクラスから見えなくなります。</span><span class="sxs-lookup"><span data-stu-id="f0776-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f0776-142">例</span><span class="sxs-lookup"><span data-stu-id="f0776-142">Example</span></span>  
 <span data-ttu-id="f0776-143">次のコンソール アプリケーションは、表示可能なすべての SQL Server インスタンスに関する情報を取得し、コンソール ウィンドウにその情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="f0776-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
    foreach (System.Data.DataRow row in table.Rows)  
    {  
      foreach (System.Data.DataColumn col in table.Columns)  
      {  
        Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
      }  
      Console.WriteLine("============================");  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0776-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0776-144">See also</span></span>

- [<span data-ttu-id="f0776-145">SQL Server と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f0776-145">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="f0776-146">ADO.NET のマネージド プロバイダーと DataSet デベロッパー センター</span><span class="sxs-lookup"><span data-stu-id="f0776-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
