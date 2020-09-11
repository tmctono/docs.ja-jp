---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465583"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="d6573-101">CA2247:TaskCompletionSource コンストラクターの引数は、TaskCreationOptions 値にする必要があります</span><span class="sxs-lookup"><span data-stu-id="d6573-101">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="d6573-102">.NET コード アナライザー ルール [CA2247](/visualstudio/code-quality/ca2247) は、.NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d6573-102">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="d6573-103"><xref:System.Threading.Tasks.TaskContinuationOptions> 型の引数を渡す <xref:System.Threading.Tasks.TaskCompletionSource%601> コンストラクターへの呼び出しに対して、ビルドの警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="d6573-103">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d6573-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="d6573-104">Change description</span></span>

<span data-ttu-id="d6573-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d6573-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="d6573-106">これらのルールのいくつかは、[CA2247](/visualstudio/code-quality/ca2247) を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="d6573-106">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="d6573-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6573-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="d6573-108">ルール CA2247 によって、<xref:System.Threading.Tasks.TaskContinuationOptions> 型の引数を渡す <xref:System.Threading.Tasks.TaskCompletionSource%601> コンストラクターへの呼び出しが検索されます。</span><span class="sxs-lookup"><span data-stu-id="d6573-108">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="d6573-109"><xref:System.Threading.Tasks.TaskCompletionSource%601> 型には、<xref:System.Threading.Tasks.TaskCreationOptions> 値を受け入れるコンストラクターと、<xref:System.Object> を受け入れる別のコンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="d6573-109">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="d6573-110"><xref:System.Threading.Tasks.TaskCreationOptions> 値ではなく <xref:System.Threading.Tasks.TaskContinuationOptions> 値を誤って渡した場合、<xref:System.Object> パラメーターを持つコンストラクターが実行時に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="d6573-110">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="d6573-111">コードは、コンパイルされ、実行されますが、意図した動作を含みません。</span><span class="sxs-lookup"><span data-stu-id="d6573-111">Your code will compile and run but won't have the intended behavior.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d6573-112">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="d6573-112">Version introduced</span></span>

<span data-ttu-id="d6573-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="d6573-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d6573-114">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="d6573-114">Recommended action</span></span>

- <span data-ttu-id="d6573-115"><xref:System.Threading.Tasks.TaskContinuationOptions> 引数を、対応する <xref:System.Threading.Tasks.TaskCreationOptions> 値に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="d6573-115">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="d6573-116">ほぼ常にコード内のバグが強調表示されるため、この警告を表示しないでください。</span><span class="sxs-lookup"><span data-stu-id="d6573-116">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="d6573-117">詳細については、[CA2247](/visualstudio/code-quality/ca2247) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6573-117">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="d6573-118">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="d6573-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="d6573-119">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6573-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="d6573-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="d6573-120">Category</span></span>

<span data-ttu-id="d6573-121">コード分析</span><span class="sxs-lookup"><span data-stu-id="d6573-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d6573-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="d6573-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
