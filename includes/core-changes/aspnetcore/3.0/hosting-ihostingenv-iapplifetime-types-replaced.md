---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394337"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a><span data-ttu-id="e0745-101">ホスティング:IHostingEnvironment と IApplicationLifetime の型が不使用とマークされ、置き換えられました</span><span class="sxs-lookup"><span data-stu-id="e0745-101">Hosting: IHostingEnvironment and IApplicationLifetime types marked obsolete and replaced</span></span>

<span data-ttu-id="e0745-102">既存の `IHostingEnvironment` と `IApplicationLifetime` の型を置き換えるために新しい型が導入されました。</span><span class="sxs-lookup"><span data-stu-id="e0745-102">New types have been introduced to replace existing `IHostingEnvironment` and `IApplicationLifetime` types.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0745-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e0745-103">Version introduced</span></span>

<span data-ttu-id="e0745-104">3.0</span><span class="sxs-lookup"><span data-stu-id="e0745-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="e0745-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="e0745-105">Old behavior</span></span>

<span data-ttu-id="e0745-106">`Microsoft.Extensions.Hosting` および `Microsoft.AspNetCore.Hosting` の 2 つの `IHostingEnvironment` および `IApplicationLifetime` という型がありました。</span><span class="sxs-lookup"><span data-stu-id="e0745-106">There were two different `IHostingEnvironment` and `IApplicationLifetime` types from `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="e0745-107">新しい動作</span><span class="sxs-lookup"><span data-stu-id="e0745-107">New behavior</span></span>

<span data-ttu-id="e0745-108">古い型は不使用とマークされ、新しい型に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="e0745-108">The old types have been marked as obsolete and replaced with new types.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="e0745-109">変更理由</span><span class="sxs-lookup"><span data-stu-id="e0745-109">Reason for change</span></span>

<span data-ttu-id="e0745-110">`Microsoft.Extensions.Hosting` が ASP.NET Core 2.1 で導入されたときに、`IHostingEnvironment` や `IApplicationLifetime` などの一部の型が `Microsoft.AspNetCore.Hosting` からコピーされました。</span><span class="sxs-lookup"><span data-stu-id="e0745-110">When `Microsoft.Extensions.Hosting` was introduced in ASP.NET Core 2.1, some types like `IHostingEnvironment` and `IApplicationLifetime` were copied from `Microsoft.AspNetCore.Hosting`.</span></span> <span data-ttu-id="e0745-111">ASP.NET Core 3.0 の一部の変更により、アプリに `Microsoft.Extensions.Hosting` と `Microsoft.AspNetCore.Hosting` の両方の名前空間が含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0745-111">Some ASP.NET Core 3.0 changes cause apps to include both the `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting` namespaces.</span></span> <span data-ttu-id="e0745-112">これらの重複する型を使用すると、両方の名前空間が参照されるときに "あいまいな参照" コンパイラ エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e0745-112">Any use of those duplicate types causes an "ambiguous reference" compiler error when both namespaces are referenced.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0745-113">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="e0745-113">Recommended action</span></span>

<span data-ttu-id="e0745-114">次のように、古い型の使用を新しく導入された型に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e0745-114">Replaced any usages of the old types with the newly introduced types as below:</span></span>

<span data-ttu-id="e0745-115">**古い型 (警告):**</span><span class="sxs-lookup"><span data-stu-id="e0745-115">**Obsolete types (warning):**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

<span data-ttu-id="e0745-116">**新しい型:**</span><span class="sxs-lookup"><span data-stu-id="e0745-116">**New types:**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

<span data-ttu-id="e0745-117">新しい `IHostEnvironment`、`IsDevelopment` および `IsProduction` 拡張メソッドは、`Microsoft.Extensions.Hosting` 名前空間にあります。</span><span class="sxs-lookup"><span data-stu-id="e0745-117">The new `IHostEnvironment` `IsDevelopment` and `IsProduction` extension methods are in the `Microsoft.Extensions.Hosting` namespace.</span></span> <span data-ttu-id="e0745-118">その名前空間は、プロジェクトに追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0745-118">That namespace may need to be added to your project.</span></span>

#### <a name="category"></a><span data-ttu-id="e0745-119">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e0745-119">Category</span></span>

<span data-ttu-id="e0745-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0745-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0745-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e0745-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
