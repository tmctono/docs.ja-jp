---
ms.openlocfilehash: 1c9c899d77dd69e185281d98bfec18ce73d80815
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394379"
---
### <a name="kestrel-empty-https-assembly-removed"></a><span data-ttu-id="ab437-101">Kestrel: 空の HTTPS アセンブリを削除</span><span class="sxs-lookup"><span data-stu-id="ab437-101">Kestrel: Empty HTTPS assembly removed</span></span>

<span data-ttu-id="ab437-102">アセンブリ <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> が削除されました。</span><span class="sxs-lookup"><span data-stu-id="ab437-102">The assembly <xref:Microsoft.AspNetCore.Server.Kestrel.Https?displayProperty=fullName> has been removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="ab437-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="ab437-103">Version introduced</span></span>

<span data-ttu-id="ab437-104">3.0</span><span class="sxs-lookup"><span data-stu-id="ab437-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="ab437-105">変更理由</span><span class="sxs-lookup"><span data-stu-id="ab437-105">Reason for change</span></span>

<span data-ttu-id="ab437-106">ASP.NET Core 2.1 では、`Microsoft.AspNetCore.Server.Kestrel.Https` のコンテンツが <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName> に移動されました。</span><span class="sxs-lookup"><span data-stu-id="ab437-106">In ASP.NET Core 2.1, the contents of `Microsoft.AspNetCore.Server.Kestrel.Https` were moved to <xref:Microsoft.AspNetCore.Server.Kestrel.Core?displayProperty=fullName>.</span></span> <span data-ttu-id="ab437-107">この変更は、`[TypeForwardedTo]` 属性を使用して非破壊的な方法で行われました。</span><span class="sxs-lookup"><span data-stu-id="ab437-107">This change was done in a non-breaking way using `[TypeForwardedTo]` attributes.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ab437-108">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="ab437-108">Recommended action</span></span>

- <span data-ttu-id="ab437-109">`Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 を参照するライブラリでは、ASP.NET Core のすべての依存関係を 2.1 以降に更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab437-109">Libraries referencing `Microsoft.AspNetCore.Server.Kestrel.Https` 2.0 should update all ASP.NET Core dependencies to 2.1 or later.</span></span> <span data-ttu-id="ab437-110">そうしないと、ASP.NET Core 3.0 アプリに読み込んだときに破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab437-110">Otherwise, they may break when loaded into an ASP.NET Core 3.0 app.</span></span>
- <span data-ttu-id="ab437-111">ASP.NET Core 2.1 以降をターゲットとするアプリとライブラリでは、`Microsoft.AspNetCore.Server.Kestrel.Https` NuGet パッケージへの直接参照をすべて削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ab437-111">Apps and libraries targeting ASP.NET Core 2.1 and later should remove any direct references to the `Microsoft.AspNetCore.Server.Kestrel.Https` NuGet package.</span></span>

#### <a name="category"></a><span data-ttu-id="ab437-112">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="ab437-112">Category</span></span>

<span data-ttu-id="ab437-113">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ab437-113">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ab437-114">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="ab437-114">Affected APIs</span></span>

<span data-ttu-id="ab437-115">None</span><span class="sxs-lookup"><span data-stu-id="ab437-115">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
