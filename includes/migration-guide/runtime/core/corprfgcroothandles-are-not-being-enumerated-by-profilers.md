---
ms.openlocfilehash: 4f52535e54607cc824500f9c6a14964a1dec9d32
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620210"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="37ca9-101">COR_PRF_GC_ROOT_HANDLE がプロファイラーで列挙されていない</span><span class="sxs-lookup"><span data-stu-id="37ca9-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="37ca9-102">説明</span><span class="sxs-lookup"><span data-stu-id="37ca9-102">Details</span></span>

<span data-ttu-id="37ca9-103">.NET Framework v4.5.1 では、プロファイル API <code>RootReferences2()</code> が正しく <code>COR_PRF_GC_ROOT_HANDLE</code> を返しません (代わりに、<code>COR_PRF_GC_ROOT_OTHER</code> として返される)。</span><span class="sxs-lookup"><span data-stu-id="37ca9-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="37ca9-104">この問題は、.NET Framework 4.6 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="37ca9-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="37ca9-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="37ca9-105">Suggestion</span></span>

<span data-ttu-id="37ca9-106">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="37ca9-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="37ca9-107">名前</span><span class="sxs-lookup"><span data-stu-id="37ca9-107">Name</span></span>    | <span data-ttu-id="37ca9-108">[値]</span><span class="sxs-lookup"><span data-stu-id="37ca9-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="37ca9-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="37ca9-109">Scope</span></span>   |<span data-ttu-id="37ca9-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="37ca9-110">Minor</span></span>|
|<span data-ttu-id="37ca9-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="37ca9-111">Version</span></span>|<span data-ttu-id="37ca9-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="37ca9-112">4.5.1</span></span>|
|<span data-ttu-id="37ca9-113">種類</span><span class="sxs-lookup"><span data-stu-id="37ca9-113">Type</span></span>|<span data-ttu-id="37ca9-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="37ca9-114">Runtime</span></span>|
