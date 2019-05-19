---
title: ASP.NET での LINQ to SQL N 層
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 85ead36d1d927084c11dca1bd73a192b16e4ab7b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880762"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="4b908-102">ASP.NET での LINQ to SQL N 層</span><span class="sxs-lookup"><span data-stu-id="4b908-102">LINQ to SQL N-Tier with ASP.NET</span></span>
<span data-ttu-id="4b908-103">使用する ASP.NET アプリケーションで[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]を使用する、 <xref:System.Web.UI.WebControls.LinqDataSource> Web サーバー コントロール。</span><span class="sxs-lookup"><span data-stu-id="4b908-103">In ASP.NET applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="4b908-104">このコントロールは、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]に対するクエリ実行、ブラウザーへのデータ送信、データの取得、データベースを更新する [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> へのデータ送信など、必要なほとんどのロジックを扱います。</span><span class="sxs-lookup"><span data-stu-id="4b908-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="4b908-105">マークアップでこのコントロールを構成するだけで、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] とブラウザーの間のすべてのデータ転送をコントロールが処理するようになります。</span><span class="sxs-lookup"><span data-stu-id="4b908-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="4b908-106">コントロールは、プレゼンテーション層との対話を処理するため、および[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]ハンドルのデータ層、ASP.NET 多層アプリケーションでは、メインのフォーカスとの通信は、カスタム ビジネス ロジックを記述します。</span><span class="sxs-lookup"><span data-stu-id="4b908-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in ASP.NET multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="4b908-107">詳細については`LINQDataSource`を参照してください[LinqDataSource Web サーバー コントロールの概要](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="4b908-107">For more information about `LINQDataSource`, see [LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b908-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b908-108">See also</span></span>

- [<span data-ttu-id="4b908-109">LINQ to SQL を使用する n 層アプリケーションとリモート アプリケーション</span><span class="sxs-lookup"><span data-stu-id="4b908-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
