---
ms.openlocfilehash: 6c2aff4abf558307d599ff7533c82286e037bc71
ms.sourcegitcommit: 1274a1a4a4c7e2eaf56b38da76ef7cec789726ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91406150"
---
### <a name="systemsecuritycryptography-apis-not-supported-on-blazor-webassembly"></a><span data-ttu-id="448d2-101">Blazor WebAssembly で System.Security.Cryptography API がサポートされない</span><span class="sxs-lookup"><span data-stu-id="448d2-101">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>

<span data-ttu-id="448d2-102"><xref:System.Security.Cryptography> API は、ブラウザーで実行されると、実行時に <xref:System.PlatformNotSupportedException> をスローします。</span><span class="sxs-lookup"><span data-stu-id="448d2-102"><xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> at run time when run on a browser.</span></span>

#### <a name="change-description"></a><span data-ttu-id="448d2-103">変更内容</span><span class="sxs-lookup"><span data-stu-id="448d2-103">Change description</span></span>

<span data-ttu-id="448d2-104">以前のバージョンの .NET では、ほとんどの <xref:System.Security.Cryptography> API が Blazor WebAssembly で使用できません。</span><span class="sxs-lookup"><span data-stu-id="448d2-104">In previous .NET versions, most of the <xref:System.Security.Cryptography> APIs aren't available to Blazor WebAssembly apps.</span></span> <span data-ttu-id="448d2-105">.NET 5.0 以降、Blazor WebAssembly アプリでは .NET 5 API の全アクセス領域が対象になりますが、ブラウザー サンドボックスの制約によりすべての .NET 5 API がサポートされているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="448d2-105">Starting in .NET 5.0, Blazor WebAssembly apps target the full .NET 5 API surface area, however, not all .NET 5 APIs are supported due to browser sandbox constraints.</span></span> <span data-ttu-id="448d2-106">.NET 5.0 以降のバージョンでは、サポートされていない <xref:System.Security.Cryptography> API を WebAssembly で実行すると <xref:System.PlatformNotSupportedException> がスローされます。</span><span class="sxs-lookup"><span data-stu-id="448d2-106">In .NET 5.0 and later versions, the unsupported <xref:System.Security.Cryptography> APIs throw a <xref:System.PlatformNotSupportedException> when running on WebAssembly.</span></span>

> [!TIP]
> <span data-ttu-id="448d2-107">ブラウザー プラットフォームをサポートするプロジェクトをビルドすると、[プラットフォーム互換性アナライザー](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility)によって、影響を受ける API の呼び出しにフラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="448d2-107">The [Platform compatibility analyzer](../../../../docs/core/compatibility/code-analysis.md#ca1416-platform-compatibility) will flag any calls to the affected APIs when you build a project that supports the browser platform.</span></span> <span data-ttu-id="448d2-108">このアナライザーは、.NET 5.0 以降のアプリでは既定で実行されます。</span><span class="sxs-lookup"><span data-stu-id="448d2-108">This analyzer runs by default in .NET 5.0 and later apps.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="448d2-109">変更理由</span><span class="sxs-lookup"><span data-stu-id="448d2-109">Reason for change</span></span>

<span data-ttu-id="448d2-110">Microsoft では、Blazor WebAssembly 構成の依存関係として OpenSSL を公開することができません。</span><span class="sxs-lookup"><span data-stu-id="448d2-110">Microsoft is unable to ship OpenSSL as a dependency in the Blazor WebAssembly configuration.</span></span> <span data-ttu-id="448d2-111">私たちは、ブラウザーの `SubtleCrypto` API と統合することでこれを回避しようとしました。</span><span class="sxs-lookup"><span data-stu-id="448d2-111">We attempted to work around this by trying to integrate with the browser's `SubtleCrypto` API.</span></span> <span data-ttu-id="448d2-112">残念ながら、それには大幅な API の変更が必要であり、統合は困難でした。</span><span class="sxs-lookup"><span data-stu-id="448d2-112">Unfortunately, it required significant API changes that made it too hard to integrate.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="448d2-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="448d2-113">Version introduced</span></span>

<span data-ttu-id="448d2-114">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="448d2-114">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="448d2-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="448d2-115">Recommended action</span></span>

<span data-ttu-id="448d2-116">現時点では、推奨される回避策はありません。</span><span class="sxs-lookup"><span data-stu-id="448d2-116">There are no good workarounds to suggest at this time.</span></span>

#### <a name="category"></a><span data-ttu-id="448d2-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="448d2-117">Category</span></span>

- <span data-ttu-id="448d2-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="448d2-118">ASP.NET Core</span></span>
- <span data-ttu-id="448d2-119">暗号</span><span class="sxs-lookup"><span data-stu-id="448d2-119">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="448d2-120">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="448d2-120">Affected APIs</span></span>

<span data-ttu-id="448d2-121">次を除くすべての <xref:System.Security.Cryptography?displayProperty=fullName> API:</span><span class="sxs-lookup"><span data-stu-id="448d2-121">All <xref:System.Security.Cryptography?displayProperty=fullName> APIs except the following:</span></span>

- `System.Security.Cryptography.RandomNumberGenerator`
- `System.Security.Cryptography.IncrementalHash`
- `System.Security.Cryptography.SHA1`
- `System.Security.Cryptography.SHA256`
- `System.Security.Cryptography.SHA384`
- `System.Security.Cryptography.SHA512`
- `System.Security.Cryptography.SHA1Managed`
- `System.Security.Cryptography.SHA256Managed`
- `System.Security.Cryptography.SHA384Managed`
- `System.Security.Cryptography.SHA512Managed`

<!--

#### Affected APIs

- `T:System.Security.Cryptography`

-->
