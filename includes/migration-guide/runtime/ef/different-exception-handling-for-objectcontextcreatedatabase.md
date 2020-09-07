---
ms.openlocfilehash: 8c593fa6490451c6236f0d4390f09d4e9e4f0cbb
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496193"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a><span data-ttu-id="dd7d1-101">ObjectContext.CreateDatabase メソッドと DbProviderServices.CreateDatabase メソッドで異なる例外処理</span><span class="sxs-lookup"><span data-stu-id="dd7d1-101">Different exception handling for ObjectContext.CreateDatabase and DbProviderServices.CreateDatabase methods</span></span>

#### <a name="details"></a><span data-ttu-id="dd7d1-102">説明</span><span class="sxs-lookup"><span data-stu-id="dd7d1-102">Details</span></span>

<span data-ttu-id="dd7d1-103">.NET Framework 4.5 から、データベースの作成が失敗した場合、<code>CreateDatabase</code> メソッドは、空のデータベースの削除を試みます。</span><span class="sxs-lookup"><span data-stu-id="dd7d1-103">Beginning in .NET Framework 4.5, if database creation fails, <code>CreateDatabase</code> methods will attempt to drop the empty database.</span></span> <span data-ttu-id="dd7d1-104">その操作が成功した場合、元の <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> は伝播されます (.NET Framework 4.0 で常にスローされていた <xref:System.InvalidOperationException?displayProperty=fullName> の代わりに)</span><span class="sxs-lookup"><span data-stu-id="dd7d1-104">If that operation succeeds, the original <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> will be propagated (instead of the <xref:System.InvalidOperationException?displayProperty=fullName> that was always thrown in .NET Framework 4.0)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="dd7d1-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="dd7d1-105">Suggestion</span></span>

<span data-ttu-id="dd7d1-106"><xref:System.Data.Objects.ObjectContext.CreateDatabase> または <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> の実行中に <xref:System.InvalidOperationException?displayProperty=fullName> をキャッチするときには、SQLExceptions もキャッチする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd7d1-106">When catching an <xref:System.InvalidOperationException?displayProperty=fullName> while executing <xref:System.Data.Objects.ObjectContext.CreateDatabase> or <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, SQLExceptions should now also be caught.</span></span>

| <span data-ttu-id="dd7d1-107">名前</span><span class="sxs-lookup"><span data-stu-id="dd7d1-107">Name</span></span>    | <span data-ttu-id="dd7d1-108">[値]</span><span class="sxs-lookup"><span data-stu-id="dd7d1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="dd7d1-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="dd7d1-109">Scope</span></span>   |<span data-ttu-id="dd7d1-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="dd7d1-110">Minor</span></span>|
|<span data-ttu-id="dd7d1-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="dd7d1-111">Version</span></span>|<span data-ttu-id="dd7d1-112">4.5</span><span class="sxs-lookup"><span data-stu-id="dd7d1-112">4.5</span></span>|
|<span data-ttu-id="dd7d1-113">種類</span><span class="sxs-lookup"><span data-stu-id="dd7d1-113">Type</span></span>|<span data-ttu-id="dd7d1-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="dd7d1-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="dd7d1-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="dd7d1-115">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType>
- <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Data.Objects.ObjectContext.CreateDatabase`
- `M:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)`

-->
