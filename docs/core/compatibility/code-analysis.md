---
title: コード分析の破壊的変更
description: .NET ソース コード アナライザーの破壊的変更の一覧を示します。
ms.date: 08/22/2020
ms.openlocfilehash: 8b2b50c5f03a3ca971aefd0f2cf53624dfa82274
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465581"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="cbd02-103">コード分析の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="cbd02-103">Code analysis breaking changes</span></span>

<span data-ttu-id="cbd02-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="cbd02-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="cbd02-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="cbd02-105">Breaking change</span></span> | <span data-ttu-id="cbd02-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cbd02-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="cbd02-107">CA1831: 範囲ベースのインデクサーの代わりに AsSpan または AsMemory を使用します</span><span class="sxs-lookup"><span data-stu-id="cbd02-107">CA1831: Use AsSpan or AsMemory instead of Range-based indexer</span></span>](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | <span data-ttu-id="cbd02-108">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd02-108">5.0</span></span> |
| [<span data-ttu-id="cbd02-109">CA2014: stackalloc はループ内で使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cbd02-109">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="cbd02-110">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd02-110">5.0</span></span> |
| [<span data-ttu-id="cbd02-111">CA2015: MemoryManager から派生した型にはファイナライザーを定義しません\<T></span><span class="sxs-lookup"><span data-stu-id="cbd02-111">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="cbd02-112">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd02-112">5.0</span></span> |
| [<span data-ttu-id="cbd02-113">CA2247: TaskCompletionSource コンストラクターの引数は、TaskCreationOptions 値にする必要があります</span><span class="sxs-lookup"><span data-stu-id="cbd02-113">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="cbd02-114">5.0</span><span class="sxs-lookup"><span data-stu-id="cbd02-114">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="cbd02-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="cbd02-115">.NET 5.0</span></span>

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
