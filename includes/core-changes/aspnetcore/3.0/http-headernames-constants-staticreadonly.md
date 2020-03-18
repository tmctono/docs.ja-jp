---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901579"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="f4ac9-101">HTTP:HeaderNames の定数を静的読み取り専用に変更</span><span class="sxs-lookup"><span data-stu-id="f4ac9-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="f4ac9-102">ASP.NET Core 3.0 Preview 5 以降、<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> のフィールドが `const` から `static readonly` に変更されました。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="f4ac9-103">ディスカッションについては、[dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-103">For discussion, see [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f4ac9-104">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f4ac9-104">Version introduced</span></span>

<span data-ttu-id="f4ac9-105">3.0</span><span class="sxs-lookup"><span data-stu-id="f4ac9-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="f4ac9-106">以前の動作</span><span class="sxs-lookup"><span data-stu-id="f4ac9-106">Old behavior</span></span>

<span data-ttu-id="f4ac9-107">これらのフィールドは以前は `const` でした。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="f4ac9-108">新しい動作</span><span class="sxs-lookup"><span data-stu-id="f4ac9-108">New behavior</span></span>

<span data-ttu-id="f4ac9-109">これらのフィールドは `static readonly` になりました。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="f4ac9-110">変更理由</span><span class="sxs-lookup"><span data-stu-id="f4ac9-110">Reason for change</span></span>

<span data-ttu-id="f4ac9-111">変更:</span><span class="sxs-lookup"><span data-stu-id="f4ac9-111">The change:</span></span>

* <span data-ttu-id="f4ac9-112">アセンブリ境界を越えて値が埋め込まれるのを防ぎ、必要に応じて値を修正できるようにします。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="f4ac9-113">参照の等価性チェックの高速化を可能にします。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f4ac9-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="f4ac9-114">Recommended action</span></span>

<span data-ttu-id="f4ac9-115">3\.0 に対して再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-115">Recompile against 3.0.</span></span> <span data-ttu-id="f4ac9-116">これらのフィールドを次の方法で使用しているソース コードはそれを実行できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="f4ac9-117">属性引数として使用</span><span class="sxs-lookup"><span data-stu-id="f4ac9-117">As an attribute argument</span></span>
* <span data-ttu-id="f4ac9-118">`switch` ステートメントで `case` として使用</span><span class="sxs-lookup"><span data-stu-id="f4ac9-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="f4ac9-119">別の `const` を定義するときに使用</span><span class="sxs-lookup"><span data-stu-id="f4ac9-119">When defining another `const`</span></span>

<span data-ttu-id="f4ac9-120">この破壊的変更を回避するには、ヘッダー名の自己定義型の定数または文字列リテラルの使用に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="f4ac9-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="f4ac9-121">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f4ac9-121">Category</span></span>

<span data-ttu-id="f4ac9-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f4ac9-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f4ac9-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f4ac9-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
