---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804438"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a><span data-ttu-id="05581-101">ASP.Net MVC4 アプリのプロファイリングにより、致命的な実行エンジン エラーが発生する可能性がある</span><span class="sxs-lookup"><span data-stu-id="05581-101">Profiling ASP.Net MVC4 apps can lead to Fatal Execution Engine Error</span></span>

|   |   |
|---|---|
|<span data-ttu-id="05581-102">説明</span><span class="sxs-lookup"><span data-stu-id="05581-102">Details</span></span>|<span data-ttu-id="05581-103">NGEN/プロファイル アセンブリを使用するプロファイラーにより、起動時にプロファイルされた ASP.NET MVC4 アプリケーションがクラッシュし、"致命的な実行エンジン例外" が示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="05581-103">Profilers using NGEN /Profile assemblies may crash profiled ASP.NET MVC4 applications on startup with a 'Fatal Execution Engine Exception'</span></span>|
|<span data-ttu-id="05581-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="05581-104">Suggestion</span></span>|<span data-ttu-id="05581-105">この問題は、.NET Framework 4.5.2 で修正されます。</span><span class="sxs-lookup"><span data-stu-id="05581-105">This issue is fixed in the .NET Framework 4.5.2.</span></span> <span data-ttu-id="05581-106">プロファイラーは、イベント マスクで <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> を指定することで、この問題を回避することもできます。</span><span class="sxs-lookup"><span data-stu-id="05581-106">Alternatively, the profiler may avoid this issue by specifying <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> in its event mask.</span></span>|
|<span data-ttu-id="05581-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="05581-107">Scope</span></span>|<span data-ttu-id="05581-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="05581-108">Edge</span></span>|
|<span data-ttu-id="05581-109">Version</span><span class="sxs-lookup"><span data-stu-id="05581-109">Version</span></span>|<span data-ttu-id="05581-110">4.5</span><span class="sxs-lookup"><span data-stu-id="05581-110">4.5</span></span>|
|<span data-ttu-id="05581-111">型</span><span class="sxs-lookup"><span data-stu-id="05581-111">Type</span></span>|<span data-ttu-id="05581-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="05581-112">Runtime</span></span>|
