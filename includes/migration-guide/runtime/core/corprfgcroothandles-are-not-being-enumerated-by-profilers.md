---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858572"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a><span data-ttu-id="b1b69-101">COR_PRF_GC_ROOT_HANDLE がプロファイラーで列挙されていない</span><span class="sxs-lookup"><span data-stu-id="b1b69-101">COR_PRF_GC_ROOT_HANDLEs are not being enumerated by profilers</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b1b69-102">説明</span><span class="sxs-lookup"><span data-stu-id="b1b69-102">Details</span></span>|<span data-ttu-id="b1b69-103">.NET Framework v4.5.1 では、プロファイル API <code>RootReferences2()</code> が正しく <code>COR_PRF_GC_ROOT_HANDLE</code> を返しません (代わりに、<code>COR_PRF_GC_ROOT_OTHER</code> として返される)。</span><span class="sxs-lookup"><span data-stu-id="b1b69-103">In the .NET Framework v4.5.1, the profiling API <code>RootReferences2()</code> is incorrectly never returning <code>COR_PRF_GC_ROOT_HANDLE</code> (they are returned as <code>COR_PRF_GC_ROOT_OTHER</code> instead).</span></span> <span data-ttu-id="b1b69-104">この問題は、.NET Framework 4.6 以降で修正されています。</span><span class="sxs-lookup"><span data-stu-id="b1b69-104">This issue is fixed beginning in the .NET Framework 4.6.</span></span>|
|<span data-ttu-id="b1b69-105">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b1b69-105">Suggestion</span></span>|<span data-ttu-id="b1b69-106">この問題は .NET Framework 4.6 で修正されたため、このバージョンの .NET Framework にアップグレードすることによって対処できます。</span><span class="sxs-lookup"><span data-stu-id="b1b69-106">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span>|
|<span data-ttu-id="b1b69-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="b1b69-107">Scope</span></span>|<span data-ttu-id="b1b69-108">Minor</span><span class="sxs-lookup"><span data-stu-id="b1b69-108">Minor</span></span>|
|<span data-ttu-id="b1b69-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="b1b69-109">Version</span></span>|<span data-ttu-id="b1b69-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b1b69-110">4.5.1</span></span>|
|<span data-ttu-id="b1b69-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="b1b69-111">Type</span></span>|<span data-ttu-id="b1b69-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b1b69-112">Runtime</span></span>|
