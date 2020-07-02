---
ms.openlocfilehash: 907c4aa5573c392a68afad0a4d937eadcd556440
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620295"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="1e56c-101">デバッガーですぐに null コアレッサー値が表示されない</span><span class="sxs-lookup"><span data-stu-id="1e56c-101">Null coalescer values are not visible in debugger until one step later</span></span>

#### <a name="details"></a><span data-ttu-id="1e56c-102">説明</span><span class="sxs-lookup"><span data-stu-id="1e56c-102">Details</span></span>

<span data-ttu-id="1e56c-103">.NET Framework 4.5 のバグにより、64 ビット版の Framework で実行中に代入演算が実行された直後に、デバッガーで null 合体演算で設定された値が表示されません。</span><span class="sxs-lookup"><span data-stu-id="1e56c-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1e56c-104">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="1e56c-104">Suggestion</span></span>

<span data-ttu-id="1e56c-105">デバッガーでの操作に時間がかかると、ローカル/フィールドの値が正しく更新されなくなります。</span><span class="sxs-lookup"><span data-stu-id="1e56c-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="1e56c-106">この問題は .NET Framework 4.6 で修正されました。このバージョンの .NET Framework にアップグレードすれば、問題は解決します。</span><span class="sxs-lookup"><span data-stu-id="1e56c-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>

| <span data-ttu-id="1e56c-107">名前</span><span class="sxs-lookup"><span data-stu-id="1e56c-107">Name</span></span>    | <span data-ttu-id="1e56c-108">[値]</span><span class="sxs-lookup"><span data-stu-id="1e56c-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1e56c-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="1e56c-109">Scope</span></span>   |<span data-ttu-id="1e56c-110">エッジ</span><span class="sxs-lookup"><span data-stu-id="1e56c-110">Edge</span></span>|
|<span data-ttu-id="1e56c-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="1e56c-111">Version</span></span>|<span data-ttu-id="1e56c-112">4.5</span><span class="sxs-lookup"><span data-stu-id="1e56c-112">4.5</span></span>|
|<span data-ttu-id="1e56c-113">種類</span><span class="sxs-lookup"><span data-stu-id="1e56c-113">Type</span></span>|<span data-ttu-id="1e56c-114">ランタイム</span><span class="sxs-lookup"><span data-stu-id="1e56c-114">Runtime</span></span>|
