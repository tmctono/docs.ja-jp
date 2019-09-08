---
title: DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: 8a06accb11631f2dce6b0d39587d7274223c0e68
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786344"
---
# <a name="dataviews"></a><span data-ttu-id="bbe8a-102">DataView</span><span class="sxs-lookup"><span data-stu-id="bbe8a-102">DataViews</span></span>
<span data-ttu-id="bbe8a-103"><xref:System.Data.DataView> では、<xref:System.Data.DataTable> に格納されているデータのさまざまなビューを作成できます。この機能は、データ連結アプリケーションで頻繁に使用されます。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-103">A <xref:System.Data.DataView> enables you to create different views of the data stored in a <xref:System.Data.DataTable>, a capability that is often used in data-binding applications.</span></span> <span data-ttu-id="bbe8a-104">**DataView**を使用すると、異なる並べ替え順序を持つテーブルのデータを公開したり、行の状態またはフィルター式に基づいてデータをフィルター処理したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-104">Using a **DataView**, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span>  
  
 <span data-ttu-id="bbe8a-105">**DataView**は、基になる**DataTable**のデータの動的ビューを提供します。コンテンツ、順序、およびメンバーシップには、発生した変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-105">A **DataView** provides a dynamic view of data in the underlying **DataTable**: the content, ordering, and membership reflect changes as they occur.</span></span> <span data-ttu-id="bbe8a-106">この動作は、特定のフィルターや並べ替え順序に基づいてテーブル<xref:System.Data.DataRow>から配列を返す DataTable の**Select**メソッドとは異なります。このコンテンツには、基になるテーブルに対する変更が反映されますが、そのメンバーシップと順序付けは静的なままです。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-106">This behavior differs from the **Select** method of the **DataTable**, which returns a <xref:System.Data.DataRow> array from a table based on a particular filter and/or sort order: this content reflects changes to the underlying table, but its membership and ordering remain static.</span></span> <span data-ttu-id="bbe8a-107">**DataView**の動的機能は、データバインディングアプリケーションに最適です。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-107">The dynamic capabilities of the **DataView** make it ideal for data-binding applications.</span></span>  
  
 <span data-ttu-id="bbe8a-108">**DataView**を使用すると、データベースビューと同じように、データの1つのセットを動的に表示できます。このビューでは、さまざまな並べ替えとフィルター処理の基準を適用できます。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-108">A **DataView** provides you with a dynamic view of a single set of data, much like a database view, to which you can apply different sorting and filtering criteria.</span></span> <span data-ttu-id="bbe8a-109">ただし、データベースビューとは異なり、 **DataView**はテーブルとして扱うことができず、結合テーブルのビューを提供することもできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-109">Unlike a database view, however, a **DataView** cannot be treated as a table and cannot provide a view of joined tables.</span></span> <span data-ttu-id="bbe8a-110">また、ソース テーブルの既存の列を除外したり、ソース テーブルにない列 (計算列など) を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-110">You also cannot exclude columns that exist in the source table, nor can you append columns, such as computational columns, that do not exist in the source table.</span></span>  
  
 <span data-ttu-id="bbe8a-111">を<xref:System.Data.DataView.DataViewManager%2A>使用すると、**データセット**内のすべてのテーブルのビュー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-111">You can use a <xref:System.Data.DataView.DataViewManager%2A> to manage view settings for all the tables in a **DataSet**.</span></span> <span data-ttu-id="bbe8a-112">**DataViewManager**を使用すると、各テーブルの既定の表示設定を簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-112">The **DataViewManager** provides you with a convenient way to manage default view settings for each table.</span></span> <span data-ttu-id="bbe8a-113">コントロールを**データセット**の複数のテーブルにバインドする場合は、 **DataViewManager**へのバインドが最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-113">When binding a control to more than one table of a **DataSet**, binding to a **DataViewManager** is the ideal choice.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbe8a-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bbe8a-114">In This Section</span></span>  
 [<span data-ttu-id="bbe8a-115">DataView の作成</span><span class="sxs-lookup"><span data-stu-id="bbe8a-115">Creating a DataView</span></span>](creating-a-dataview.md)  
 <span data-ttu-id="bbe8a-116">**DataTable**の**DataView**を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-116">Describes how to create a **DataView** for a **DataTable**.</span></span>  
  
 [<span data-ttu-id="bbe8a-117">データの並べ替えとフィルター処理</span><span class="sxs-lookup"><span data-stu-id="bbe8a-117">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)  
 <span data-ttu-id="bbe8a-118">特定のフィルター条件を満たすデータ行のサブセットを返す**DataView**のプロパティを設定する方法、または特定の並べ替え順序でデータを返す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-118">Describes how to set the properties of a **DataView** to return subsets of data rows meeting specific filter criteria, or to return data in a particular sort order.</span></span>  
  
 [<span data-ttu-id="bbe8a-119">DataRow および DataRowView</span><span class="sxs-lookup"><span data-stu-id="bbe8a-119">DataRows and DataRowViews</span></span>](datarows-and-datarowviews.md)  
 <span data-ttu-id="bbe8a-120">**DataView**によって公開されるデータにアクセスする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-120">Describes how to access the data exposed by the **DataView**.</span></span>  
  
 [<span data-ttu-id="bbe8a-121">行の検索</span><span class="sxs-lookup"><span data-stu-id="bbe8a-121">Finding Rows</span></span>](finding-rows.md)  
 <span data-ttu-id="bbe8a-122">**DataView**内の特定の行を検索する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-122">Describes how to find a particular row in a **DataView**.</span></span>  
  
 [<span data-ttu-id="bbe8a-123">ChildView とリレーション</span><span class="sxs-lookup"><span data-stu-id="bbe8a-123">ChildViews and Relations</span></span>](childviews-and-relations.md)  
 <span data-ttu-id="bbe8a-124">**DataView**を使用して親子関係からデータのビューを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-124">Describes how to create views of data from a parent-child relationship using a **DataView**.</span></span>  
  
 [<span data-ttu-id="bbe8a-125">DataView の変更</span><span class="sxs-lookup"><span data-stu-id="bbe8a-125">Modifying DataViews</span></span>](modifying-dataviews.md)  
 <span data-ttu-id="bbe8a-126">更新を有効または無効にするなど、 **DataView**を使用して基になる**DataTable**のデータを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-126">Describes how to modify the data in the underlying **DataTable** via the **DataView**, including enabling or disabling updates.</span></span>  
  
 [<span data-ttu-id="bbe8a-127">DataView イベントの処理</span><span class="sxs-lookup"><span data-stu-id="bbe8a-127">Handling DataView Events</span></span>](handling-dataview-events.md)  
 <span data-ttu-id="bbe8a-128">**DataView**の内容または順序が更新されるときに、 **ListChanged**イベントを使用して通知を受け取る方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-128">Describes how to use the **ListChanged** event to receive notification when the contents or order of a **DataView** is being updated.</span></span>  
  
 [<span data-ttu-id="bbe8a-129">DataViews の管理</span><span class="sxs-lookup"><span data-stu-id="bbe8a-129">Managing DataViews</span></span>](managing-dataviews.md)  
 <span data-ttu-id="bbe8a-130">**DataViewManager**を使用して、**データセット**内の各テーブルの**DataView**設定を管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-130">Describes how to use a **DataViewManager** to manage **DataView** settings for each table in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="bbe8a-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbe8a-131">Related Sections</span></span>  
 <span data-ttu-id="bbe8a-132">[ASP.NET Web アプリケーション](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bbe8a-132">[ASP.NET Web Applications](https://docs.microsoft.com/previous-versions/655cec97(v=vs.100))</span></span>  
 <span data-ttu-id="bbe8a-133">ASP.NET アプリケーション、Web フォームおよび Web サービスを作成する場合の概要と詳細なステップごとの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-133">Provides overviews and detailed, step-by-step procedures for creating ASP.NET applications, Web Forms, and Web Services.</span></span>  
  
 <span data-ttu-id="bbe8a-134">[Windows アプリケーション](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bbe8a-134">[Windows Applications](https://docs.microsoft.com/previous-versions/ms184421(v=vs.100))</span></span>  
 <span data-ttu-id="bbe8a-135">Windows フォームおよびコンソール アプリケーションの操作に関する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-135">Provides detailed information about working with Windows Forms and console applications.</span></span>  
  
 [<span data-ttu-id="bbe8a-136">DataSet、DataTable、および DataView</span><span class="sxs-lookup"><span data-stu-id="bbe8a-136">DataSets, DataTables, and DataViews</span></span>](index.md)  
 <span data-ttu-id="bbe8a-137">**DataSet**オブジェクトと、それを使用してアプリケーションデータを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-137">Describes the **DataSet** object and how you can use it to manage application data.</span></span>  
  
 [<span data-ttu-id="bbe8a-138">DataTables</span><span class="sxs-lookup"><span data-stu-id="bbe8a-138">DataTables</span></span>](datatables.md)  
 <span data-ttu-id="bbe8a-139">**DataTable**オブジェクトと、それを単独で、または**データセット**の一部として管理するために使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-139">Describes the **DataTable** object and how you can use it to manage application data by itself or as part of a **DataSet**.</span></span>  
  
 [<span data-ttu-id="bbe8a-140">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bbe8a-140">ADO.NET</span></span>](../index.md)  
 <span data-ttu-id="bbe8a-141">ADO.NET のアーキテクチャとコンポーネントについて説明し、ADO.NET を使用して既存のデータ ソースにアクセスしたり、アプリケーション データを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe8a-141">Describes the ADO.NET architecture and components, and how to use ADO.NET to access existing data sources and manage application data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe8a-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="bbe8a-142">See also</span></span>

- [<span data-ttu-id="bbe8a-143">ADO.NET の概要</span><span class="sxs-lookup"><span data-stu-id="bbe8a-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
