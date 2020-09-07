---
ms.openlocfilehash: 25437dcc0c814ed2265b2efb34316af48b372ebd
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496183"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="a1761-101">COR_PRF_GC_ROOT_HANDLE がプロファイラーで列挙されていない</span><span class="sxs-lookup"><span data-stu-id="a1761-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

#### <a name="details"></a><span data-ttu-id="a1761-102">説明</span><span class="sxs-lookup"><span data-stu-id="a1761-102">Details</span></span>

<span data-ttu-id="a1761-103">.NET Framework v4.5.1 では、プロファイル API <code>RootReferences2()</code> が正しく <code>COR_PRF_GC_ROOT_HANDLE</code> を返しません (代わりに、<code>COR_PRF_GC_ROOT_OTHER</code> として返される)。</span><span class="sxs-lookup"><span data-stu-id="a1761-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="a1761-104">この問題は、.NET Framework 4.6 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="a1761-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a1761-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="a1761-105">Suggestion</span></span>

<span data-ttu-id="a1761-106">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="a1761-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>

| <span data-ttu-id="a1761-107">名前</span><span class="sxs-lookup"><span data-stu-id="a1761-107">Name</span></span>    | <span data-ttu-id="a1761-108">[値]</span><span class="sxs-lookup"><span data-stu-id="a1761-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a1761-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="a1761-109">Scope</span></span>   |<span data-ttu-id="a1761-110">マイナー</span><span class="sxs-lookup"><span data-stu-id="a1761-110">Minor</span></span>|
|<span data-ttu-id="a1761-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="a1761-111">Version</span></span>|<span data-ttu-id="a1761-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="a1761-112">4.5.1</span></span>|
|<span data-ttu-id="a1761-113">種類</span><span class="sxs-lookup"><span data-stu-id="a1761-113">Type</span></span>|<span data-ttu-id="a1761-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="a1761-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a1761-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a1761-115">Affected APIs</span></span>

<span data-ttu-id="a1761-116">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="a1761-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
