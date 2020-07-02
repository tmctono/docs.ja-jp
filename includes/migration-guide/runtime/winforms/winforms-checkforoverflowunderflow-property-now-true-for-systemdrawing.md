---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620445"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="f7290-101">WinForm の CheckForOverflowUnderflow プロパティが System.Drawing に対して true に設定されるようになった</span><span class="sxs-lookup"><span data-stu-id="f7290-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="f7290-102">説明</span><span class="sxs-lookup"><span data-stu-id="f7290-102">Details</span></span>

<span data-ttu-id="f7290-103">System.Drawing.dll アセンブリの CheckForOverflowUnderflow プロパティが true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f7290-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f7290-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="f7290-104">Suggestion</span></span>

<span data-ttu-id="f7290-105">これまではオーバーフローが発生すると、その結果は自動的に切り捨てられました。</span><span class="sxs-lookup"><span data-stu-id="f7290-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="f7290-106">現在では、<xref:System.OverflowException?displayProperty=fullName> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f7290-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="f7290-107">名前</span><span class="sxs-lookup"><span data-stu-id="f7290-107">Name</span></span>    | <span data-ttu-id="f7290-108">[値]</span><span class="sxs-lookup"><span data-stu-id="f7290-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f7290-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="f7290-109">Scope</span></span>   |<span data-ttu-id="f7290-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="f7290-110">Edge</span></span>|
|<span data-ttu-id="f7290-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="f7290-111">Version</span></span>|<span data-ttu-id="f7290-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f7290-112">4.5</span></span>|
|<span data-ttu-id="f7290-113">種類</span><span class="sxs-lookup"><span data-stu-id="f7290-113">Type</span></span>|<span data-ttu-id="f7290-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="f7290-114">Runtime</span></span>|
