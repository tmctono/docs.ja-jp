---
ms.openlocfilehash: 22f8e3bb1ba72379b3f5fc87a077e5fe57f89bf8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858604"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="b0d3e-101">デバッガーですぐに null コアレッサー値が表示されない</span><span class="sxs-lookup"><span data-stu-id="b0d3e-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b0d3e-102">説明</span><span class="sxs-lookup"><span data-stu-id="b0d3e-102">Details</span></span>|<span data-ttu-id="b0d3e-103">.NET Framework 4.5 のバグにより、64 ビット版の Framework で実行中に代入演算が実行された直後に、デバッガーで null 合体演算で設定された値が表示されません。</span><span class="sxs-lookup"><span data-stu-id="b0d3e-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="b0d3e-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="b0d3e-104">Suggestion</span></span>|<span data-ttu-id="b0d3e-105">デバッガーでの操作に時間がかかると、ローカル/フィールドの値が正しく更新されなくなります。</span><span class="sxs-lookup"><span data-stu-id="b0d3e-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="b0d3e-106">この問題は .NET Framework 4.6 で修正されました。このバージョンの .NET Framework にアップグレードすれば、問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="b0d3e-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="b0d3e-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="b0d3e-107">Scope</span></span>|<span data-ttu-id="b0d3e-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="b0d3e-108">Edge</span></span>|
|<span data-ttu-id="b0d3e-109">バージョン</span><span class="sxs-lookup"><span data-stu-id="b0d3e-109">Version</span></span>|<span data-ttu-id="b0d3e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="b0d3e-110">4.5</span></span>|
|<span data-ttu-id="b0d3e-111">[種類]</span><span class="sxs-lookup"><span data-stu-id="b0d3e-111">Type</span></span>|<span data-ttu-id="b0d3e-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="b0d3e-112">Runtime</span></span>|
