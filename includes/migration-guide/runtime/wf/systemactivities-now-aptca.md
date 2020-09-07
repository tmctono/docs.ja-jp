---
ms.openlocfilehash: 51ac10e6b4cc9c757cb7f68d7d665982bcb57d4e
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496384"
---
### <a name="systemactivities-is-now-aptca"></a><span data-ttu-id="1338d-101">System.Activities が APTCA に</span><span class="sxs-lookup"><span data-stu-id="1338d-101">System.Activities is now APTCA</span></span>

#### <a name="details"></a><span data-ttu-id="1338d-102">説明</span><span class="sxs-lookup"><span data-stu-id="1338d-102">Details</span></span>

<span data-ttu-id="1338d-103">アセンブリは <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> 属性でマークされています。</span><span class="sxs-lookup"><span data-stu-id="1338d-103">The assembly is marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute?displayProperty=fullName> attribute.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1338d-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1338d-104">Suggestion</span></span>

<span data-ttu-id="1338d-105">派生クラスに <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>のマークを付けることはできません。</span><span class="sxs-lookup"><span data-stu-id="1338d-105">Derived classes cannot be marked with the <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>.</span></span> <span data-ttu-id="1338d-106">以前は、派生型に <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>マークを付ける必要がありました。</span><span class="sxs-lookup"><span data-stu-id="1338d-106">Previously, derived types had to be marked with the <xref:System.Security.SecurityCriticalAttribute?displayProperty=fullName>.</span></span> <span data-ttu-id="1338d-107">ただし、この変更によって生じる実質的な影響はないはずです。</span><span class="sxs-lookup"><span data-stu-id="1338d-107">However, this change should have no real impact.</span></span>

| <span data-ttu-id="1338d-108">名前</span><span class="sxs-lookup"><span data-stu-id="1338d-108">Name</span></span>    | <span data-ttu-id="1338d-109">[値]</span><span class="sxs-lookup"><span data-stu-id="1338d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1338d-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="1338d-110">Scope</span></span>   |<span data-ttu-id="1338d-111">エッジ</span><span class="sxs-lookup"><span data-stu-id="1338d-111">Edge</span></span>|
|<span data-ttu-id="1338d-112">バージョン</span><span class="sxs-lookup"><span data-stu-id="1338d-112">Version</span></span>|<span data-ttu-id="1338d-113">4.5</span><span class="sxs-lookup"><span data-stu-id="1338d-113">4.5</span></span>|
|<span data-ttu-id="1338d-114">種類</span><span class="sxs-lookup"><span data-stu-id="1338d-114">Type</span></span>|<span data-ttu-id="1338d-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1338d-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1338d-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1338d-116">Affected APIs</span></span>

<span data-ttu-id="1338d-117">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="1338d-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
