---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235562"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="d9cf2-101">WinForm の CheckForOverflowUnderflow プロパティが System.Drawing に対して true に設定されるようになった</span><span class="sxs-lookup"><span data-stu-id="d9cf2-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d9cf2-102">説明</span><span class="sxs-lookup"><span data-stu-id="d9cf2-102">Details</span></span>|<span data-ttu-id="d9cf2-103">System.Drawing.dll アセンブリの CheckForOverflowUnderflow プロパティが true に設定されます。</span><span class="sxs-lookup"><span data-stu-id="d9cf2-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="d9cf2-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="d9cf2-104">Suggestion</span></span>|<span data-ttu-id="d9cf2-105">これまではオーバーフローが発生すると、その結果は自動的に切り捨てられました。</span><span class="sxs-lookup"><span data-stu-id="d9cf2-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="d9cf2-106">現在では、<xref:System.OverflowException?displayProperty=name> 例外がスローされます。</span><span class="sxs-lookup"><span data-stu-id="d9cf2-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="d9cf2-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="d9cf2-107">Scope</span></span>|<span data-ttu-id="d9cf2-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="d9cf2-108">Edge</span></span>|
|<span data-ttu-id="d9cf2-109">Version</span><span class="sxs-lookup"><span data-stu-id="d9cf2-109">Version</span></span>|<span data-ttu-id="d9cf2-110">4.5</span><span class="sxs-lookup"><span data-stu-id="d9cf2-110">4.5</span></span>|
|<span data-ttu-id="d9cf2-111">型</span><span class="sxs-lookup"><span data-stu-id="d9cf2-111">Type</span></span>|<span data-ttu-id="d9cf2-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="d9cf2-112">Runtime</span></span>|
