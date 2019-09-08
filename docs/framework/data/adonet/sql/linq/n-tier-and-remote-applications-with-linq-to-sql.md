---
title: LINQ to SQL を使用する n 層アプリケーションとリモート アプリケーション
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 94ca057da10c3570e85e17b5caec2d86154d8a3f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781406"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a><span data-ttu-id="769d6-102">LINQ to SQL を使用する n 層アプリケーションとリモート アプリケーション</span><span class="sxs-lookup"><span data-stu-id="769d6-102">N-Tier and Remote Applications with LINQ to SQL</span></span>
<span data-ttu-id="769d6-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用する n 層つまり多層アプリケーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="769d6-103">You can create n-tier or multitier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="769d6-104">通常、 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]データコンテキスト、エンティティクラス、およびクエリ構築ロジックは、データアクセス層 (DAL) として中間層に配置されます。</span><span class="sxs-lookup"><span data-stu-id="769d6-104">Typically, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] data context, entity classes, and query construction logic are located on the middle tier as the data access layer (DAL).</span></span> <span data-ttu-id="769d6-105">ビジネス ロジックと非永続的データは、エンティティとデータ コンテキストの部分クラスと部分メソッドの中に完全に実装できます。または、別個のクラスに実装することもできます。</span><span class="sxs-lookup"><span data-stu-id="769d6-105">Business logic and any non-persistent data can be implemented completely in partial classes and methods of entities and the data context, or it can be implemented in separate classes.</span></span>

 <span data-ttu-id="769d6-106">クライアントまたはプレゼンテーション層は、中間層のリモート インターフェイス上のメソッドを呼び出し、その層の DAL は、<xref:System.Data.Linq.DataContext> メソッドにマップされるクエリまたはストアド プロシージャを実行します。</span><span class="sxs-lookup"><span data-stu-id="769d6-106">The client or presentation layer calls methods on the middle-tier's remote interface, and the DAL on that tier will execute queries or stored procedures that are mapped to <xref:System.Data.Linq.DataContext> methods.</span></span> <span data-ttu-id="769d6-107">中間層は、通常、エンティティまたはプロキシ オブジェクトの XML 表現としてデータをクライアントに返します。</span><span class="sxs-lookup"><span data-stu-id="769d6-107">The middle tier returns the data to clients typically as XML representations of entities or proxy objects.</span></span>

 <span data-ttu-id="769d6-108">中間層では、データ コンテキストによってエンティティが作成され、データ コンテキストはエンティティの状態を追跡し、データベースからの遅延読み込み、および変更内容のデータベースへの送信を管理します。</span><span class="sxs-lookup"><span data-stu-id="769d6-108">On the middle tier, entities are created by the data context, which tracks their state, and manages deferred loading from and submission of changes to the database.</span></span> <span data-ttu-id="769d6-109">これらのエンティティは、`DataContext` にいわばアタッチされます。</span><span class="sxs-lookup"><span data-stu-id="769d6-109">These entities are "attached" to the `DataContext`.</span></span> <span data-ttu-id="769d6-110">ただし、シリアル化によってエンティティが別の層に送られた後は、エンティティがデタッチされます。つまり、その状態が `DataContext` によって追跡されなくなります。</span><span class="sxs-lookup"><span data-stu-id="769d6-110">However, after the entities are sent to another tier through serialization, they become detached, which means the `DataContext` is no longer tracking their state.</span></span> <span data-ttu-id="769d6-111">更新のためにクライアントによって戻されるエンティティは、[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] が変更内容をデータベースに送信する前に、データ コンテキストに再びアタッチされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="769d6-111">Entities that the client sends back for updates must be reattached to the data context before [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can submit the changes to the database.</span></span> <span data-ttu-id="769d6-112">オプティミスティック同時実行チェックのために元の値またはタイムスタンプが必要とされる場合、クライアントはこれらを中間層に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="769d6-112">The client is responsible for providing original values and/or timestamps back to the middle tier if those are required for optimistic concurrency checks.</span></span>

 <span data-ttu-id="769d6-113">ASP.NET アプリケーションでは、このような複雑な操作の大部分が <xref:System.Web.UI.WebControls.LinqDataSource> によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="769d6-113">In ASP.NET applications, the <xref:System.Web.UI.WebControls.LinqDataSource> manages most of this complexity.</span></span> <span data-ttu-id="769d6-114">詳細については、「 [LinqDataSource Web サーバーコントロールの概要](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769d6-114">For more information, see [LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="769d6-115">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="769d6-115">Additional Resources</span></span>
 <span data-ttu-id="769d6-116">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] を使用する n 層アプリケーションの実装方法について、詳しくは以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="769d6-116">For more information about how to implement n-tier applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], see the following topics:</span></span>

- [<span data-ttu-id="769d6-117">ASP.NET での LINQ to SQL N 層</span><span class="sxs-lookup"><span data-stu-id="769d6-117">LINQ to SQL N-Tier with ASP.NET</span></span>](linq-to-sql-n-tier-with-aspnet.md)

- [<span data-ttu-id="769d6-118">Web サービスを使用した LINQ to SQL N 層</span><span class="sxs-lookup"><span data-stu-id="769d6-118">LINQ to SQL N-Tier with Web Services</span></span>](linq-to-sql-n-tier-with-web-services.md) 

- [<span data-ttu-id="769d6-119">N 層ビジネス ロジックの実装</span><span class="sxs-lookup"><span data-stu-id="769d6-119">Implementing N-Tier Business Logic</span></span>](implementing-business-logic-linq-to-sql.md)

- [<span data-ttu-id="769d6-120">N 層アプリケーションでのデータ取得および CUD 操作 (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="769d6-120">Data Retrieval and CUD Operations in N-Tier Applications (LINQ to SQL)</span></span>](data-retrieval-and-cud-operations-in-n-tier-applications.md)

 <span data-ttu-id="769d6-121">ADO.NET データセットを使用する n 層アプリケーションの詳細については、「 [n 層アプリケーションでのデータセットの操作](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="769d6-121">For more information about n-tier applications that use ADO.NET DataSets, see [Work with datasets in n-tier applications](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).</span></span>

## <a name="see-also"></a><span data-ttu-id="769d6-122">関連項目</span><span class="sxs-lookup"><span data-stu-id="769d6-122">See also</span></span>

- [<span data-ttu-id="769d6-123">背景情報</span><span class="sxs-lookup"><span data-stu-id="769d6-123">Background Information</span></span>](background-information.md)
