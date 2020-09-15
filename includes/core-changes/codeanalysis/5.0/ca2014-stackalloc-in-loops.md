---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065180"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="a762c-101">CA2014: stackalloc はループ内で使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="a762c-101">CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="a762c-102">.NET コード アナライザー ルール [CA2014](/visualstudio/code-quality/ca2014) は、.NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a762c-102">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="a762c-103">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) 式がループ内で使用される C# コードに対して、ビルドの警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="a762c-103">It produces a build warning for any C# code where a [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a762c-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="a762c-104">Change description</span></span>

<span data-ttu-id="a762c-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a762c-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="a762c-106">これらのルールのいくつかは、[CA2014](/visualstudio/code-quality/ca2014) を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a762c-106">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="a762c-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a762c-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="a762c-108">[stackalloc 式](../../../../docs/csharp/language-reference/operators/stackalloc.md)がループ内で使用されるルール CA2014 によって、C# コードが検索されます。</span><span class="sxs-lookup"><span data-stu-id="a762c-108">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../docs/csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="a762c-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) によって、現在のスタック フレームからメモリが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="a762c-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="a762c-110">現在のメソッド呼び出しが戻るまでメモリは解放されません。これにより、スタック オーバーフローにつながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a762c-110">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="a762c-111">スタック オーバーフローの例外をキャッチできないため、スタック オーバーフローが発生した場合はアプリが終了します。</span><span class="sxs-lookup"><span data-stu-id="a762c-111">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a762c-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a762c-112">Version introduced</span></span>

<span data-ttu-id="a762c-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="a762c-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a762c-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="a762c-114">Recommended action</span></span>

- <span data-ttu-id="a762c-115">ループ内での [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) の使用を避けます。</span><span class="sxs-lookup"><span data-stu-id="a762c-115">Avoid using [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="a762c-116">ループの外側でメモリ ブロックを割り当て、それをループ内で再利用してください。</span><span class="sxs-lookup"><span data-stu-id="a762c-116">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="a762c-117">詳細については、[CA2014](/visualstudio/code-quality/ca2014) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a762c-117">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="a762c-118">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="a762c-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="a762c-119">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a762c-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="a762c-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a762c-120">Category</span></span>

<span data-ttu-id="a762c-121">コード分析</span><span class="sxs-lookup"><span data-stu-id="a762c-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a762c-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a762c-122">Affected APIs</span></span>

<span data-ttu-id="a762c-123">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="a762c-123">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
