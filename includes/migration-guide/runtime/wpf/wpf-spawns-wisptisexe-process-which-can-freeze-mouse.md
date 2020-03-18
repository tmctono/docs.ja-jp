---
ms.openlocfilehash: cbd599f7467c3b360bbe1c76a65abfdb840a1530
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803215"
---
### <a name="wpf-spawns-a-wisptisexe-process-which-can-freeze-the-mouse"></a><span data-ttu-id="2f015-101">WPF が wisptis.exe プロセスを生成し、マウスがフリーズする可能性がある</span><span class="sxs-lookup"><span data-stu-id="2f015-101">WPF spawns a wisptis.exe process which can freeze the mouse</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2f015-102">説明</span><span class="sxs-lookup"><span data-stu-id="2f015-102">Details</span></span>|<span data-ttu-id="2f015-103">この問題は 4.5.2 から発生するようになり、<code>wisptis.exe</code> が生成され、マウス入力がフリーズする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2f015-103">An issue was introduced in 4.5.2 that causes <code>wisptis.exe</code> to be spawned that can freeze mouse input.</span></span>|
|<span data-ttu-id="2f015-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="2f015-104">Suggestion</span></span>|<span data-ttu-id="2f015-105">この問題はサービス リリースの .NET Framework 4.5.2 (修正プログラム ロールアップ 3026376) で、あるいは .NET Framework 4.6 にアップグレードすることで解決できます。</span><span class="sxs-lookup"><span data-stu-id="2f015-105">A fix for this issue is available in a servicing release of the .NET Framework 4.5.2 (hotfix rollup 3026376), or by upgrading to the .NET Framework 4.6</span></span>|
|<span data-ttu-id="2f015-106">スコープ</span><span class="sxs-lookup"><span data-stu-id="2f015-106">Scope</span></span>|<span data-ttu-id="2f015-107">Major</span><span class="sxs-lookup"><span data-stu-id="2f015-107">Major</span></span>|
|<span data-ttu-id="2f015-108">バージョン</span><span class="sxs-lookup"><span data-stu-id="2f015-108">Version</span></span>|<span data-ttu-id="2f015-109">4.5.2</span><span class="sxs-lookup"><span data-stu-id="2f015-109">4.5.2</span></span>|
|<span data-ttu-id="2f015-110">[種類]</span><span class="sxs-lookup"><span data-stu-id="2f015-110">Type</span></span>|<span data-ttu-id="2f015-111">ランタイム</span><span class="sxs-lookup"><span data-stu-id="2f015-111">Runtime</span></span>|
