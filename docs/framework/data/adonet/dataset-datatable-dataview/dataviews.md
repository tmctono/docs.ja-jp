---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 1b202af052c05ed9dc671fa20c9c366f280ec5c7
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774166"
---
# <a name="dataviews"></a><span data-ttu-id="fb9df-102">DataView</span><span class="sxs-lookup"><span data-stu-id="fb9df-102">DataViews</span></span>
<span data-ttu-id="fb9df-103"><xref:System.Data.DataView> では、<xref:System.Data.DataTable> に格納されているデータのさまざまなビューを作成できます。この機能は、データ連結アプリケーションで頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb9df-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="fb9df-104">**DataView**を使用すると、異なる並べ替え順序を持つテーブルのデータを公開したり、行の状態またはフィルター式に基づいてデータをフィルター処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fb9df-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>

 <span data-ttu-id="fb9df-105">**DataView**は、基になる**DataTable**のデータの動的ビューを提供します。コンテンツ、順序、およびメンバーシップには、発生した変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="fb9df-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="fb9df-106">この動作は、特定のフィルターまたは並べ替え順序に基づいてテーブルから <xref:System.Data.DataRow> 配列を返す**DataTable**の**Select**メソッドとは異なります。このコンテンツには、基になるテーブルに対する変更が反映されますが、そのメンバーシップと順序が反映されます。静的のままです。</span><span class="sxs-lookup"><span data-stu-id="fb9df-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: this content reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="fb9df-107">**DataView**の動的機能は、データバインディングアプリケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="fb9df-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>

 <span data-ttu-id="fb9df-108">**DataView**を使用すると、データベースビューと同じように、データの1つのセットを動的に表示できます。このビューでは、さまざまな並べ替えとフィルター処理の基準を適用できます。</span><span class="sxs-lookup"><span data-stu-id="fb9df-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="fb9df-109">ただし、データベースビューとは異なり、 **DataView**はテーブルとして扱うことができず、結合テーブルのビューを提供することもできません。</span><span class="sxs-lookup"><span data-stu-id="fb9df-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="fb9df-110">また、ソーステーブルに存在する列を除外したり、ソーステーブルに存在しない列 (計算列など) を追加したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fb9df-110">You also cannot exclude columns that exist in the source table or append columns that do not exist in the source table, such as computational columns.</span></span>

 <span data-ttu-id="fb9df-111">@No__t_0 を使用すると、**データセット**内のすべてのテーブルのビュー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="fb9df-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="fb9df-112">**DataViewManager**を使用すると、各テーブルの既定の表示設定を簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="fb9df-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="fb9df-113">コントロールを**データセット**の複数のテーブルにバインドする場合は、 **DataViewManager**へのバインドが最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="fb9df-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="fb9df-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fb9df-114">In This Section</span></span>
 <span data-ttu-id="fb9df-115">[DataView の作成](creating-a-dataview.md)**DataTable**の**DataView**を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-115">[Creating a DataView](creating-a-dataview.md) Describes how to create a **DataView** for a **DataTable**.</span></span>

 <span data-ttu-id="fb9df-116">[データの並べ替えとフィルター処理](sorting-and-filtering-data.md)特定のフィルター条件を満たすデータ行のサブセットを返す**DataView**のプロパティを設定する方法、または特定の並べ替え順序でデータを返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-116">[Sorting and Filtering Data](sorting-and-filtering-data.md) Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>

 <span data-ttu-id="fb9df-117">[Datarow と datarowview](datarows-and-datarowviews.md)**DataView**によって公開されるデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-117">[DataRows and DataRowViews](datarows-and-datarowviews.md) Describes how to access the data exposed by the **DataView**.</span></span>

 <span data-ttu-id="fb9df-118">[検索 (行](finding-rows.md)を)**DataView**内の特定の行を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-118">[Finding Rows](finding-rows.md) Describes how to find a particular row in a **DataView**.</span></span>

 <span data-ttu-id="fb9df-119">[Childviews とリレーション](childviews-and-relations.md)**DataView**を使用して親子関係からデータのビューを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-119">[ChildViews and Relations](childviews-and-relations.md) Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>

 <span data-ttu-id="fb9df-120">[DataViews の変更](modifying-dataviews.md)更新を有効または無効にするなど、 **DataView**を使用して基になる**DataTable**のデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-120">[Modifying DataViews](modifying-dataviews.md) Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>

 <span data-ttu-id="fb9df-121">[DataView イベントの処理](handling-dataview-events.md)**DataView**の内容または順序が更新されるときに、 **ListChanged**イベントを使用して通知を受け取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-121">[Handling DataView Events](handling-dataview-events.md) Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>

 <span data-ttu-id="fb9df-122">[DataViews の管理](managing-dataviews.md)**DataViewManager**を使用して、**データセット**内の各テーブルの**DataView**設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-122">[Managing DataViews](managing-dataviews.md) Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>

## <a name="related-sections"></a><span data-ttu-id="fb9df-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb9df-123">Related Sections</span></span>
 <span data-ttu-id="fb9df-124">[ASP.NET Web アプリケーション](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))ASP.NET アプリケーション、Web フォーム、および Web サービスを作成するための概要と詳細な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-124">[ASP.NET Web Applications](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100)) Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>

 <span data-ttu-id="fb9df-125">[Windows アプリケーション](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))Windows フォームとコンソールアプリケーションの操作に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-125">[Windows Applications](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100)) Provides detailed information about working with Windows Forms and console applications.</span></span>

 <span data-ttu-id="fb9df-126">[データセット、datatable、および DataViews](index.md)**DataSet**オブジェクトと、それを使用してアプリケーションデータを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-126">[DataSets, DataTables, and DataViews](index.md) Describes the **DataSet** object and how you can use it to manage application data.</span></span>

 <span data-ttu-id="fb9df-127">[Datatable](datatables.md)**DataTable**オブジェクトと、それを単独で、または**データセット**の一部として管理するために使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-127">[DataTables](datatables.md) Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>

 <span data-ttu-id="fb9df-128">[ADO.NET](../index.md)ADO.NET のアーキテクチャとコンポーネントについて説明します。また、ADO.NET を使用して既存のデータソースにアクセスし、アプリケーションデータを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb9df-128">[ADO.NET](../index.md) Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb9df-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb9df-129">See also</span></span>

- [<span data-ttu-id="fb9df-130">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="fb9df-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
