---
ms.openlocfilehash: 9a2d6a25a8ab1b8bf65b947557802e0805a7f826
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617200"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="3cde3-101">foreach 反復子変数は、イテレーション内をスコープとするようになったため、クロージャ キャプチャのセマンティクスが (C#5 では) 異なります。</span><span class="sxs-lookup"><span data-stu-id="3cde3-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

#### <a name="details"></a><span data-ttu-id="3cde3-102">説明</span><span class="sxs-lookup"><span data-stu-id="3cde3-102">Details</span></span>

<span data-ttu-id="3cde3-103">C#5 (Visual Studio 2012) 以降では、`foreach` 反復子変数は、イテレーション内をスコープとします。</span><span class="sxs-lookup"><span data-stu-id="3cde3-103">Beginning with C# 5 (Visual Studio 2012), `foreach` iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="3cde3-104">このため、変数が `foreach` のクロージャに含まれないことに依存していたコードは機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="3cde3-104">This can cause breaks if code was previously depending on the variables to not be included in the `foreach`'s closure.</span></span> <span data-ttu-id="3cde3-105">この変更による症状は、デリゲートに渡された反復子変数が、デリゲートが呼び出された時点での値ではなく、デリゲートの作成時点での値として扱われることです。</span><span class="sxs-lookup"><span data-stu-id="3cde3-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3cde3-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="3cde3-106">Suggestion</span></span>

<span data-ttu-id="3cde3-107">理想的には、新しいコンパイラの動作を予期するように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cde3-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="3cde3-108">古いセマンティクスが必要な場合は、反復子変数を、ループのスコープ外に明示的に配置される別の変数に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="3cde3-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>

| <span data-ttu-id="3cde3-109">名前</span><span class="sxs-lookup"><span data-stu-id="3cde3-109">Name</span></span>    | <span data-ttu-id="3cde3-110">[値]</span><span class="sxs-lookup"><span data-stu-id="3cde3-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3cde3-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="3cde3-111">Scope</span></span>   | <span data-ttu-id="3cde3-112">Major</span><span class="sxs-lookup"><span data-stu-id="3cde3-112">Major</span></span>       |
| <span data-ttu-id="3cde3-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="3cde3-113">Version</span></span> | <span data-ttu-id="3cde3-114">4.5</span><span class="sxs-lookup"><span data-stu-id="3cde3-114">4.5</span></span>         |
| <span data-ttu-id="3cde3-115">種類</span><span class="sxs-lookup"><span data-stu-id="3cde3-115">Type</span></span>    | <span data-ttu-id="3cde3-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="3cde3-116">Retargeting</span></span> |
