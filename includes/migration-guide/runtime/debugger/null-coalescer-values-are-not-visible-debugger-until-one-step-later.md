---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858604"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="63bd4-101">デバッガーですぐに null コアレッサー値が表示されない</span><span class="sxs-lookup"><span data-stu-id="63bd4-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="63bd4-102">説明</span><span class="sxs-lookup"><span data-stu-id="63bd4-102">Details</span></span>|<span data-ttu-id="63bd4-103">.NET Framework 4.5 のバグにより、64 ビット版の Framework で実行中に代入演算が実行された直後に、デバッガーで null 合体演算で設定された値が表示されません。</span><span class="sxs-lookup"><span data-stu-id="63bd4-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="63bd4-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="63bd4-104">Suggestion</span></span>|<span data-ttu-id="63bd4-105">デバッガーでの操作に時間がかかると、ローカル/フィールドの値が正しく更新されなくなります。</span><span class="sxs-lookup"><span data-stu-id="63bd4-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="63bd4-106">この問題は .NET Framework 4.6 で修正されました。このバージョンの .NET Framework にアップグレードすれば、問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="63bd4-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="63bd4-107">スコープ</span><span class="sxs-lookup"><span data-stu-id="63bd4-107">Scope</span></span>|<span data-ttu-id="63bd4-108">エッジ</span><span class="sxs-lookup"><span data-stu-id="63bd4-108">Edge</span></span>|
|<span data-ttu-id="63bd4-109">Version</span><span class="sxs-lookup"><span data-stu-id="63bd4-109">Version</span></span>|<span data-ttu-id="63bd4-110">4.5</span><span class="sxs-lookup"><span data-stu-id="63bd4-110">4.5</span></span>|
|<span data-ttu-id="63bd4-111">型</span><span class="sxs-lookup"><span data-stu-id="63bd4-111">Type</span></span>|<span data-ttu-id="63bd4-112">ランタイム</span><span class="sxs-lookup"><span data-stu-id="63bd4-112">Runtime</span></span>|

