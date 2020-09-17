---
title: コード分析の破壊的変更
description: .NET ソース コード アナライザーの破壊的変更の一覧を示します。
ms.date: 09/02/2020
ms.openlocfilehash: 20badd69b316e1d87700b3c5061a71d648b71c64
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065206"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="c964c-103">コード分析の破壊的変更</span><span class="sxs-lookup"><span data-stu-id="c964c-103">Code analysis breaking changes</span></span>

<span data-ttu-id="c964c-104">このページでは、次の破壊的変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="c964c-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c964c-105">互換性に影響する変更点</span><span class="sxs-lookup"><span data-stu-id="c964c-105">Breaking change</span></span> | <span data-ttu-id="c964c-106">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="c964c-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="c964c-107">CA1416:プラットフォームの互換性</span><span class="sxs-lookup"><span data-stu-id="c964c-107">CA1416: Platform compatibility</span></span>](#ca1416-platform-compatibility) | <span data-ttu-id="c964c-108">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-108">5.0</span></span> |
| [<span data-ttu-id="c964c-109">CA1417:P/Invoke 用の文字列パラメーターの OutAttribute</span><span class="sxs-lookup"><span data-stu-id="c964c-109">CA1417: OutAttribute on string parameter for P/Invoke</span></span>](#ca1417-outattribute-on-string-parameter-for-pinvoke) | <span data-ttu-id="c964c-110">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-110">5.0</span></span> |
| [<span data-ttu-id="c964c-111">CA1831: 文字列に範囲ベースのインデクサーの代わりに AsSpan を使用します</span><span class="sxs-lookup"><span data-stu-id="c964c-111">CA1831: Use AsSpan instead of Range-based indexers for string</span></span>](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | <span data-ttu-id="c964c-112">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-112">5.0</span></span> |
| [<span data-ttu-id="c964c-113">CA2013: 値の型と共に ReferenceEquals を使用しないでください</span><span class="sxs-lookup"><span data-stu-id="c964c-113">CA2013: Do not use ReferenceEquals with value types</span></span>](#ca2013-do-not-use-referenceequals-with-value-types) | <span data-ttu-id="c964c-114">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-114">5.0</span></span> |
| [<span data-ttu-id="c964c-115">CA2014: stackalloc はループ内で使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c964c-115">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="c964c-116">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-116">5.0</span></span> |
| [<span data-ttu-id="c964c-117">CA2015: MemoryManager から派生した型にはファイナライザーを定義しません\<T></span><span class="sxs-lookup"><span data-stu-id="c964c-117">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="c964c-118">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-118">5.0</span></span> |
| [<span data-ttu-id="c964c-119">CA2247: TaskCompletionSource コンストラクターの引数は、TaskCreationOptions 値にする必要があります</span><span class="sxs-lookup"><span data-stu-id="c964c-119">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="c964c-120">5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-120">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c964c-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c964c-121">.NET 5.0</span></span>

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
