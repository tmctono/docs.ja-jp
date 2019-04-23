---
ms.openlocfilehash: 1805c26f1eff46719f30de8a14ca6d35f01948a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774335"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a><span data-ttu-id="21bd0-101">foreach 反復子変数は、イテレーション内をスコープとするようになったため、クロージャ キャプチャのセマンティクスが (C#5 では) 異なります。</span><span class="sxs-lookup"><span data-stu-id="21bd0-101">Foreach iterator variable is now scoped within the iteration, so closure capturing semantics are different (in C#5)</span></span>

|   |   |
|---|---|
|<span data-ttu-id="21bd0-102">説明</span><span class="sxs-lookup"><span data-stu-id="21bd0-102">Details</span></span>|<span data-ttu-id="21bd0-103">C#5 (Visual Studio 2012) 以降では、<code>foreach</code> 反復子変数は、イテレーション内をスコープとします。</span><span class="sxs-lookup"><span data-stu-id="21bd0-103">Beginning with C# 5 (Visual Studio 2012), <code>foreach</code> iterator variables are scoped within the iteration.</span></span> <span data-ttu-id="21bd0-104">このため、変数が <code>foreach</code> のクロージャに含まれないことに依存していたコードは機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="21bd0-104">This can cause breaks if code was previously depending on the variables to not be included in the <code>foreach</code>'s closure.</span></span> <span data-ttu-id="21bd0-105">この変更による症状は、デリゲートに渡された反復子変数が、デリゲートが呼び出された時点での値ではなく、デリゲートの作成時点での値として扱われることです。</span><span class="sxs-lookup"><span data-stu-id="21bd0-105">The symptom of this change is that an iterator variable passed to a delegate is treated as the value it has at the time the delegate is created, rather than the value it has at the time the delegate is invoked.</span></span>|
|<span data-ttu-id="21bd0-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="21bd0-106">Suggestion</span></span>|<span data-ttu-id="21bd0-107">理想的には、新しいコンパイラの動作を予期するように、コードを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="21bd0-107">Ideally, code should be updated to expect the new compiler behavior.</span></span> <span data-ttu-id="21bd0-108">古いセマンティクスが必要な場合は、反復子変数を、ループのスコープ外に明示的に配置される別の変数に置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="21bd0-108">If the old semantics are required, the iterator variable can be replaced with a separate variable which is explicitly placed outside of the loop's scope.</span></span>|
|<span data-ttu-id="21bd0-109">スコープ</span><span class="sxs-lookup"><span data-stu-id="21bd0-109">Scope</span></span>|<span data-ttu-id="21bd0-110">Major</span><span class="sxs-lookup"><span data-stu-id="21bd0-110">Major</span></span>|
|<span data-ttu-id="21bd0-111">バージョン</span><span class="sxs-lookup"><span data-stu-id="21bd0-111">Version</span></span>|<span data-ttu-id="21bd0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="21bd0-112">4.5</span></span>|
|<span data-ttu-id="21bd0-113">型</span><span class="sxs-lookup"><span data-stu-id="21bd0-113">Type</span></span>|<span data-ttu-id="21bd0-114">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="21bd0-114">Retargeting</span></span>|
