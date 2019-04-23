---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804440"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="34ee7-101">WinForm の CheckForOverflowUnderflow プロパティが System.Drawing に対して true に設定されるようになった</span><span class="sxs-lookup"><span data-stu-id="34ee7-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="34ee7-102">説明</span><span class="sxs-lookup"><span data-stu-id="34ee7-102">Details</span></span>|<span data-ttu-id="34ee7-103">System.Drawing.dll アセンブリの CheckForOverflowUnderflow プロパティが true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="34ee7-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="34ee7-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="34ee7-104">Suggestion</span></span>|<span data-ttu-id="34ee7-105">これまではオーバーフローが発生すると、その結果は自動的に切り捨てられました。</span><span class="sxs-lookup"><span data-stu-id="34ee7-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="34ee7-106">現在では、<xref:System.OverflowException?displayProperty=name> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="34ee7-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="34ee7-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="34ee7-107">Scope</span></span>|<span data-ttu-id="34ee7-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="34ee7-108">Edge</span></span>|
|<span data-ttu-id="34ee7-109">Version</span><span class="sxs-lookup"><span data-stu-id="34ee7-109">Version</span></span>|<span data-ttu-id="34ee7-110">4.5</span><span class="sxs-lookup"><span data-stu-id="34ee7-110">4.5</span></span>|
|<span data-ttu-id="34ee7-111">型</span><span class="sxs-lookup"><span data-stu-id="34ee7-111">Type</span></span>|<span data-ttu-id="34ee7-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="34ee7-112">Runtime</span></span>|
