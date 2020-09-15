---
ms.openlocfilehash: 35fc4782ebbba33f5fc6668712af9d89d00cafe9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614975"
---
### <a name="wpf-changing-a-primary-key-when-displaying-ado-data-in-a-masterdetail-scenario"></a><span data-ttu-id="eddb6-101">WPF のマスター/詳細シナリオで ADO データを表示するときに主キーが変更される</span><span class="sxs-lookup"><span data-stu-id="eddb6-101">WPF Changing a primary key when displaying ADO data in a Master/Detail scenario</span></span>

#### <a name="details"></a><span data-ttu-id="eddb6-102">説明</span><span class="sxs-lookup"><span data-stu-id="eddb6-102">Details</span></span>

<span data-ttu-id="eddb6-103">`Order` 型の項目の ADO コレクションと、それを主キー &quot;OrderID&quot; によって `Detail` 型の項目のコレクションに関連付ける &quot;OrderDetails&quot; という関係があるとします。</span><span class="sxs-lookup"><span data-stu-id="eddb6-103">Suppose you have an ADO collection of items of type `Order`, with a relation named &quot;OrderDetails&quot; relating it to a collection of items of type `Detail` via the primary key &quot;OrderID&quot;.</span></span> <span data-ttu-id="eddb6-104">WPF アプリでは、特定の順序の詳細にリスト コントロールをバインドできます。</span><span class="sxs-lookup"><span data-stu-id="eddb6-104">In your WPF app, you can bind a list control to the details for a given order:</span></span>

```xaml
<ListBox ItemsSource="{Binding Path=OrderDetails}" >
```

<span data-ttu-id="eddb6-105">ここで、DataContext は `Order` です。</span><span class="sxs-lookup"><span data-stu-id="eddb6-105">where the DataContext is an `Order`.</span></span> <span data-ttu-id="eddb6-106">WPF により、`OrderDetails` プロパティの値 (`OrderID` がマスター項目の `OrderID` と一致するすべての `Detail` 項目のコレクション D) が取得されます。</span><span class="sxs-lookup"><span data-stu-id="eddb6-106">WPF gets the value of the `OrderDetails` property - a collection D of all the `Detail` items whose `OrderID` matches the `OrderID` of the master item.</span></span> <span data-ttu-id="eddb6-107">マスター項目の主キー `OrderID` を変更すると、動作の変更が発生します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-107">The behavior change arises when you change the primary key `OrderID` of the master item.</span></span> <span data-ttu-id="eddb6-108">ADO は、Details コレクション内の影響を受ける各レコード (つまり、コレクション D にコピーされたレコード) の `OrderID` を自動的に変更します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-108">ADO automatically changes the `OrderID` of each of the affected records in the Details collection (namely the ones copied into collection D).</span></span>  <span data-ttu-id="eddb6-109">では、D はどうなるのでしょうか?</span><span class="sxs-lookup"><span data-stu-id="eddb6-109">But what happens to D?</span></span>

- <span data-ttu-id="eddb6-110">以前の動作:コレクション D はクリアされます。</span><span class="sxs-lookup"><span data-stu-id="eddb6-110">Old behavior: Collection D is cleared.</span></span> <span data-ttu-id="eddb6-111">マスター項目では、プロパティ  *の変更通知が*発生しません`OrderDetails`。</span><span class="sxs-lookup"><span data-stu-id="eddb6-111">The master item does *not* raise a change notification for property `OrderDetails`.</span></span> <span data-ttu-id="eddb6-112">ListBox は、空になったコレクション D を引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-112">The ListBox continues to use collection D, which is now empty.</span></span>
- <span data-ttu-id="eddb6-113">新しい動作:コレクション D は変更されません。</span><span class="sxs-lookup"><span data-stu-id="eddb6-113">New behavior:  Collection D is unchanged.</span></span> <span data-ttu-id="eddb6-114">その各項目で、`OrderID` プロパティの変更通知が発生します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-114">Each of its items raises a change notification for the `OrderID` property.</span></span> <span data-ttu-id="eddb6-115">ListBox はコレクション D を引き続き使用し、新しい `OrderID` に関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-115">The ListBox continues to use collection D, and displays the details with the new `OrderID`.</span></span> <span data-ttu-id="eddb6-116">WPF は、別の方法 (`followParent` 引数を `true` に設定して ADO メソッド <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> を呼び出す) でコレクション D を作成することにより、新しい動作を実装します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-116">WPF implements the new behavior by creating collection D in a different way:  by calling the ADO method <xref:System.Data.DataRowView.CreateChildView(System.Data.DataRelation,System.Boolean)?displayProperty=nameWithType> with the `followParent` argument set to `true`.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eddb6-117">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="eddb6-117">Suggestion</span></span>

<span data-ttu-id="eddb6-118">アプリは、次の AppContext スイッチを使用して新しい動作を取得します。</span><span class="sxs-lookup"><span data-stu-id="eddb6-118">An app gets the new behavior by using the following AppContext switch.</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Data.DoNotUseFollowParentWhenBindingToADODataRelation=false"/>
  </runtime>
</configuration>
```

<span data-ttu-id="eddb6-119">スイッチの既定値は、.NET 4.7.1 以下を対象とするアプリでは `true` に設定され (古い動作)、.NET 4.7.2 以上を対象とするアプリでは `false` に設定されます (新しい動作)。</span><span class="sxs-lookup"><span data-stu-id="eddb6-119">The switch defaults to `true` (old behavior) for apps that target .NET 4.7.1 or below, and to `false` (new behavior) for apps that target .NET 4.7.2 or above.</span></span>

| <span data-ttu-id="eddb6-120">名前</span><span class="sxs-lookup"><span data-stu-id="eddb6-120">Name</span></span>    | <span data-ttu-id="eddb6-121">[値]</span><span class="sxs-lookup"><span data-stu-id="eddb6-121">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eddb6-122">スコープ</span><span class="sxs-lookup"><span data-stu-id="eddb6-122">Scope</span></span>   | <span data-ttu-id="eddb6-123">マイナー</span><span class="sxs-lookup"><span data-stu-id="eddb6-123">Minor</span></span>       |
| <span data-ttu-id="eddb6-124">バージョン</span><span class="sxs-lookup"><span data-stu-id="eddb6-124">Version</span></span> | <span data-ttu-id="eddb6-125">4.7.2</span><span class="sxs-lookup"><span data-stu-id="eddb6-125">4.7.2</span></span>       |
| <span data-ttu-id="eddb6-126">種類</span><span class="sxs-lookup"><span data-stu-id="eddb6-126">Type</span></span>    | <span data-ttu-id="eddb6-127">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="eddb6-127">Retargeting</span></span> |
