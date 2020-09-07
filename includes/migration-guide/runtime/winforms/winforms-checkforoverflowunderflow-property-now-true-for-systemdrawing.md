---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496122"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="1a2c1-101">WinForm の CheckForOverflowUnderflow プロパティが System.Drawing に対して true に設定されるようになった</span><span class="sxs-lookup"><span data-stu-id="1a2c1-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="1a2c1-102">説明</span><span class="sxs-lookup"><span data-stu-id="1a2c1-102">Details</span></span>

<span data-ttu-id="1a2c1-103">System.Drawing.dll アセンブリの CheckForOverflowUnderflow プロパティが true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1a2c1-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1a2c1-104">Suggestion</span></span>

<span data-ttu-id="1a2c1-105">これまではオーバーフローが発生すると、その結果は自動的に切り捨てられました。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="1a2c1-106">現在では、<xref:System.OverflowException?displayProperty=fullName> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="1a2c1-107">名前</span><span class="sxs-lookup"><span data-stu-id="1a2c1-107">Name</span></span>    | <span data-ttu-id="1a2c1-108">[値]</span><span class="sxs-lookup"><span data-stu-id="1a2c1-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1a2c1-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="1a2c1-109">Scope</span></span>   |<span data-ttu-id="1a2c1-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="1a2c1-110">Edge</span></span>|
|<span data-ttu-id="1a2c1-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="1a2c1-111">Version</span></span>|<span data-ttu-id="1a2c1-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1a2c1-112">4.5</span></span>|
|<span data-ttu-id="1a2c1-113">種類</span><span class="sxs-lookup"><span data-stu-id="1a2c1-113">Type</span></span>|<span data-ttu-id="1a2c1-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1a2c1-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1a2c1-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="1a2c1-115">Affected APIs</span></span>

<span data-ttu-id="1a2c1-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="1a2c1-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
