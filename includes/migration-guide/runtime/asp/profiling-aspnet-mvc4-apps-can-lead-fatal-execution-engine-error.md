---
ms.openlocfilehash: 107b34c7bd26e1396e8a6638d6929c15de92b8e4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67803163"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="4f262-101">ASP.Net MVC4 アプリのプロファイリングにより、致命的な実行エンジン エラーが発生する可能性がある</span><span class="sxs-lookup"><span data-stu-id="4f262-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4f262-102">説明</span><span class="sxs-lookup"><span data-stu-id="4f262-102">Details</span></span>|<span data-ttu-id="4f262-103">NGEN/プロファイル アセンブリを使用するプロファイラーにより、起動時にプロファイルされた ASP.NET MVC4 アプリケーションがクラッシュし、"致命的な実行エンジン例外" が示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f262-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="4f262-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="4f262-104">Suggestion</span></span>|<span data-ttu-id="4f262-105">この問題は、.NET Framework 4.5.2 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="4f262-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="4f262-106">プロファイラーは、イベント マスクで <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> を指定することで、この問題を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f262-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="4f262-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="4f262-107">Scope</span></span>|<span data-ttu-id="4f262-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="4f262-108">Edge</span></span>|
|<span data-ttu-id="4f262-109">Version</span><span class="sxs-lookup"><span data-stu-id="4f262-109">Version</span></span>|<span data-ttu-id="4f262-110">4.5</span><span class="sxs-lookup"><span data-stu-id="4f262-110">4.5</span></span>|
|<span data-ttu-id="4f262-111">型</span><span class="sxs-lookup"><span data-stu-id="4f262-111">Type</span></span>|<span data-ttu-id="4f262-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="4f262-112">Runtime</span></span>|

