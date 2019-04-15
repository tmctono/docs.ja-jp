---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235636"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="2ac7a-101">MinFreeMemoryPercentageToActiveService が順守されるようになった</span><span class="sxs-lookup"><span data-stu-id="2ac7a-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2ac7a-102">説明</span><span class="sxs-lookup"><span data-stu-id="2ac7a-102">Details</span></span>|<span data-ttu-id="2ac7a-103">この設定は、WCF サービスをアクティブにするためにサーバー上で使用できなければならない最小メモリを設定します。</span><span class="sxs-lookup"><span data-stu-id="2ac7a-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="2ac7a-104"><xref:System.OutOfMemoryException?displayProperty=name> 例外が発生しないようにデザインされています。</span><span class="sxs-lookup"><span data-stu-id="2ac7a-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=name> exceptions.</span></span> <span data-ttu-id="2ac7a-105">.NET Framework 4.5 では、この設定には効果はありません。</span><span class="sxs-lookup"><span data-stu-id="2ac7a-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="2ac7a-106">.NET Framework 4.5.1 では、この設定が守られます。</span><span class="sxs-lookup"><span data-stu-id="2ac7a-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>|
|<span data-ttu-id="2ac7a-107">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2ac7a-107">Suggestion</span></span>|<span data-ttu-id="2ac7a-108">Web サーバーで使用できる空きメモリが構成設定によって定義されたパーセンテージよりも小さい場合、例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="2ac7a-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="2ac7a-109">制約されたメモリ環境で正常に開始し、実行された WCF サービスが今度は失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="2ac7a-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>|
|<span data-ttu-id="2ac7a-110">スコープ</span><span class="sxs-lookup"><span data-stu-id="2ac7a-110">Scope</span></span>|<span data-ttu-id="2ac7a-111">マイナー</span><span class="sxs-lookup"><span data-stu-id="2ac7a-111">Minor</span></span>|
|<span data-ttu-id="2ac7a-112">Version</span><span class="sxs-lookup"><span data-stu-id="2ac7a-112">Version</span></span>|<span data-ttu-id="2ac7a-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="2ac7a-113">4.5.1</span></span>|
|<span data-ttu-id="2ac7a-114">型</span><span class="sxs-lookup"><span data-stu-id="2ac7a-114">Type</span></span>|<span data-ttu-id="2ac7a-115">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2ac7a-115">Runtime</span></span>|
