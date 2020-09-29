---
title: SqlClient による LocalDB のサポート
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203424"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="524b5-102">SqlClient による LocalDB のサポート</span><span class="sxs-lookup"><span data-stu-id="524b5-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="524b5-103">SQL Server コード名 Denali 以降、SQL Server の簡易バージョンである LocalDB を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="524b5-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="524b5-104">ここでは、LocalDB データベースに接続する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="524b5-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="524b5-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="524b5-105">Remarks</span></span>  

 <span data-ttu-id="524b5-106">LocalDB のインストール方法や LocalDB インスタンスの構成方法など、LocalDB の詳細については、SQL Server オンライン ブックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="524b5-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="524b5-107">LocalDB で実行できる操作の概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="524b5-107">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="524b5-108">sqllocaldb.exe または app.config ファイルを使用して LocalDB インスタンスを作成および開始する。</span><span class="sxs-lookup"><span data-stu-id="524b5-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="524b5-109">sqlcmd.exe を使用して LocalDB インスタンスにデータベースを追加および変更する。</span><span class="sxs-lookup"><span data-stu-id="524b5-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="524b5-110">たとえば、 `sqlcmd -S (localdb)\myinst`のようにします。</span><span class="sxs-lookup"><span data-stu-id="524b5-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="524b5-111">`AttachDBFilename` 接続文字列キーワードを使用して LocalDB インスタンスにデータベースを追加する。</span><span class="sxs-lookup"><span data-stu-id="524b5-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="524b5-112">`AttachDBFilename`を使用していて、 `Database` 接続文字列キーワードでデータベースの名前を指定しない場合、アプリケーションを閉じると、データベースは LocalDB インスタンスから削除されます。</span><span class="sxs-lookup"><span data-stu-id="524b5-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="524b5-113">接続文字列に LocalDB インスタンスを指定する。</span><span class="sxs-lookup"><span data-stu-id="524b5-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="524b5-114">たとえば、インスタンス名が `myInstance`の場合、接続文字列には次の行が含まれます。</span><span class="sxs-lookup"><span data-stu-id="524b5-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="524b5-115">`User Instance=True` は LocalDB データベースに接続するときに使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="524b5-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="524b5-116">LocalDB は [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="524b5-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="524b5-117">sqlcmd.exe を使用し、LocalDB インスタンスのデータを変更する場合、SQL Server 2012 の sqlcmd が表になります。これは SQL Server 2012 Feature Pack からも入手できます。</span><span class="sxs-lookup"><span data-stu-id="524b5-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="524b5-118">名前付きインスタンスをプログラムによって作成する</span><span class="sxs-lookup"><span data-stu-id="524b5-118">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="524b5-119">アプリケーションは、次のように名前付きインスタンスを作成してデータベースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="524b5-119">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="524b5-120">app.config ファイルに作成するための LocalDB インスタンスを次のように指定する。</span><span class="sxs-lookup"><span data-stu-id="524b5-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="524b5-121">インスタンスのバージョン番号は LocalDB インストールのバージョン番号と同じである必要があります。</span><span class="sxs-lookup"><span data-stu-id="524b5-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
- <span data-ttu-id="524b5-122">`server` 接続文字列キーワードを使用してインスタンス名を指定する。</span><span class="sxs-lookup"><span data-stu-id="524b5-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="524b5-123">`server` 接続文字列キーワードで指定されたインスタンス名は app.config ファイルで指定された名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="524b5-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="524b5-124">.MDF ファイルを指定するには、 `AttachDBFilename` 接続文字列キーワードを使用する。</span><span class="sxs-lookup"><span data-stu-id="524b5-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524b5-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="524b5-125">See also</span></span>

- [<span data-ttu-id="524b5-126">SQL Server の機能と ADO.NET</span><span class="sxs-lookup"><span data-stu-id="524b5-126">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="524b5-127">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="524b5-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
