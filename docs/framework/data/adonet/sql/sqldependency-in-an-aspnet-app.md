---
title: ASP.NET アプリケーションでの SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: f3e28adc2cf7c24cee9ee344eb78404f01b79793
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780717"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="f70a9-102">ASP.NET アプリケーションでの SqlDependency</span><span class="sxs-lookup"><span data-stu-id="f70a9-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="f70a9-103">ここでは、ASP.NET の <xref:System.Data.SqlClient.SqlDependency> オブジェクトを使用して、<xref:System.Web.Caching.SqlCacheDependency> を間接的に使用する方法の例を示します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="f70a9-104"><xref:System.Web.Caching.SqlCacheDependency> オブジェクトでは <xref:System.Data.SqlClient.SqlDependency> を使用して通知をリッスンし、キャッシュを適切に更新します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f70a9-105">このサンプル コードを実行するには、「[クエリ通知の有効化](enabling-query-notifications.md)」のスクリプトを実行してクエリ通知を有効にしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="f70a9-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="f70a9-106">サンプル アプリケーションについて</span><span class="sxs-lookup"><span data-stu-id="f70a9-106">About the Sample Application</span></span>  
 <span data-ttu-id="f70a9-107">このサンプル アプリケーションでは、1 つの ASP.NET Web ページを使用して、SQL Server データベースである **AdventureWorks** に格納されている製品情報を <xref:System.Web.UI.WebControls.GridView> コントロールに表示します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="f70a9-108">ページが読み込まれる際に、コードによって <xref:System.Web.UI.WebControls.Label> コントロールに現在の時刻が書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="f70a9-109">次に、<xref:System.Web.Caching.SqlCacheDependency> オブジェクトが定義され、最大 3 分間キャッシュ データが格納されるように <xref:System.Web.Caching.Cache> オブジェクトのプロパティが設定されます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="f70a9-110">その後、データベースに接続され、データが取得されます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="f70a9-111">ページが読み込まれ、アプリケーションが実行されると、ASP.NET によって、データがキャッシュから取得されます。これは、ページ上の時刻が変更されないことで確認できます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="f70a9-112">監視しているデータが変化すると、ASP.NET によりキャッシュが無効化され、`GridView` コントロールに最新データが再入力されることで、`Label` コントロールに表示される時刻が更新されます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="f70a9-113">サンプル アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="f70a9-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="f70a9-114">サンプル アプリケーションを作成して実行するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f70a9-114">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="f70a9-115">新しい ASP.NET Web サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-115">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="f70a9-116"><xref:System.Web.UI.WebControls.Label> および <xref:System.Web.UI.WebControls.GridView> コントロールを Default.aspx ページに追加します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="f70a9-117">ページのクラス モジュールを開き、次のディレクティブを追加します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="f70a9-118">次のコードをページの `Page_Load` イベントに追加します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="f70a9-119">`GetConnectionString` および `GetSQL` という 2 つのヘルパー メソッドを追加します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="f70a9-120">定義される接続文字列は、統合セキュリティを利用します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="f70a9-121">使用しているアカウントが、必要とされるデータベースへのアクセス許可を持っており、サンプル データベースの **AdventureWorks** で通知が有効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f70a9-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="f70a9-122">アプリケーションのテスト</span><span class="sxs-lookup"><span data-stu-id="f70a9-122">Testing the Application</span></span>  
 <span data-ttu-id="f70a9-123">このアプリケーションは Web フォームに表示されるデータをキャッシングし、操作が行われなければ 3 分ごとにデータを更新します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="f70a9-124">データベースに変更があれば、キャッシュは直ちに更新されます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="f70a9-125">Visual Studio からアプリケーションを実行すると、ブラウザーにページが読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="f70a9-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="f70a9-126">表示されるキャッシュ更新時刻は、最後にキャッシュが更新された時刻を示します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="f70a9-127">3 分間の待機後、ページを更新すると、ポストバック イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="f70a9-128">ページに表示される時刻が変更されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f70a9-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="f70a9-129">3 分経過する前にページを更新した場合、ページに表示される時刻は変わりません。</span><span class="sxs-lookup"><span data-stu-id="f70a9-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="f70a9-130">次に、Transact-SQL の UPDATE コマンドを使用して、データベースのデータを更新し、ページを更新します。</span><span class="sxs-lookup"><span data-stu-id="f70a9-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="f70a9-131">表示される時刻を見ると、データベースの新しいデータを使ってキャッシュが更新されたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="f70a9-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="f70a9-132">キャッシュは更新されますが、ページに表示される時刻はポストバック イベントが発生するまで変更されないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="f70a9-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70a9-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="f70a9-133">See also</span></span>

- [<span data-ttu-id="f70a9-134">SQL Server のクエリ通知</span><span class="sxs-lookup"><span data-stu-id="f70a9-134">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="f70a9-135">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="f70a9-135">ADO.NET Overview</span></span>](../ado-net-overview.md)
