---
ms.openlocfilehash: b697bbf6844759de8babd4245667e7b333884ff8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538926"
---
### <a name="ca2200-rethrow-to-preserve-stack-details"></a><span data-ttu-id="45ae9-101">CA2200:スタック詳細を保持するために再度スローします</span><span class="sxs-lookup"><span data-stu-id="45ae9-101">CA2200: Rethrow to preserve stack details</span></span>

<span data-ttu-id="45ae9-102">.NET 5.0 以降では、.NET コード アナライザー ルール [CA2200](/visualstudio/code-quality/ca2200) が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="45ae9-102">.NET code analyzer rule [CA2200](/visualstudio/code-quality/ca2200) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="45ae9-103">これでは、`throw` ステートメントに例外が明示的に指定された、例外が再スローされるすべての `catch` ブロックに対し、ビルド警告を生成します。</span><span class="sxs-lookup"><span data-stu-id="45ae9-103">It produces a build warning for any `catch` blocks that rethrow an exception and the exception is explicitly specified in the `throw` statement.</span></span>

#### <a name="change-description"></a><span data-ttu-id="45ae9-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="45ae9-104">Change description</span></span>

<span data-ttu-id="45ae9-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="45ae9-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="45ae9-106">これらのルールのいくつかは、[CA2200](/visualstudio/code-quality/ca2200) を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="45ae9-106">Several of these rules are enabled, by default, including [CA2200](/visualstudio/code-quality/ca2200).</span></span> <span data-ttu-id="45ae9-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45ae9-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="45ae9-108">ルール CA2200 では、例外変数が `throw` ステートメントに指定されている、例外が再スローされるコードにフラグを立ます。</span><span class="sxs-lookup"><span data-stu-id="45ae9-108">Rule CA2200 flags code where exceptions are rethrown and the exception variable is specified in the `throw` statement.</span></span> <span data-ttu-id="45ae9-109">例外がスローされると、その情報の一部はスタック トレースになります。</span><span class="sxs-lookup"><span data-stu-id="45ae9-109">When an exception is thrown, part of the information it carries is the stack trace.</span></span> <span data-ttu-id="45ae9-110">スタック トレースとは、例外をスローするメソッドで始まり、例外をキャッチするメソッドで終了する、メソッド呼び出しを階層化した一覧です。</span><span class="sxs-lookup"><span data-stu-id="45ae9-110">The stack trace is a list of the method call hierarchy that starts with the method that throws the exception and ends with the method that catches the exception.</span></span> <span data-ttu-id="45ae9-111">`throw` ステートメントに例外を指定して例外が再スローされると、スタック トレースが現在のメソッドで再開され、例外をスローした元のメソッドと現在のメソッド間のメソッド呼び出しの一覧が失われます。</span><span class="sxs-lookup"><span data-stu-id="45ae9-111">If an exception is rethrown by specifying the exception in the `throw` statement, the stack trace restarts at the current method and the list of method calls between the original method that threw the exception and the current method is lost.</span></span> <span data-ttu-id="45ae9-112">元のスタック トレースの情報を例外で保持するには、例外を指定せずに `throw` ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="45ae9-112">To keep the original stack trace information with the exception, use the `throw` statement without specifying the exception.</span></span>

<span data-ttu-id="45ae9-113">次のコード スニペットでは、ルール CA2200 で警告が生成されません。</span><span class="sxs-lookup"><span data-stu-id="45ae9-113">The following code snippet does not produce a warning for rule CA2200.</span></span> <span data-ttu-id="45ae9-114">ただし、コメント化された行では、違反がトリガー "*されます*"。</span><span class="sxs-lookup"><span data-stu-id="45ae9-114">The commented line *would* trigger a violation, however.</span></span>

```csharp
catch (ArithmeticException e)
{
    // throw e;
    throw;
}
```

#### <a name="version-introduced"></a><span data-ttu-id="45ae9-115">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="45ae9-115">Version introduced</span></span>

<span data-ttu-id="45ae9-116">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="45ae9-116">5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="45ae9-117">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="45ae9-117">Recommended action</span></span>

- <span data-ttu-id="45ae9-118">例外を明示的に指定せずに、例外を再スローします。</span><span class="sxs-lookup"><span data-stu-id="45ae9-118">Rethrow exceptions without specifying the exception explicitly.</span></span> <span data-ttu-id="45ae9-119">詳細については、[CA2200](/visualstudio/code-quality/ca2200) に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="45ae9-119">For more information, see [CA2200](/visualstudio/code-quality/ca2200).</span></span>

- <span data-ttu-id="45ae9-120">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="45ae9-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="45ae9-121">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45ae9-121">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="45ae9-122">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="45ae9-122">Category</span></span>

<span data-ttu-id="45ae9-123">コード分析</span><span class="sxs-lookup"><span data-stu-id="45ae9-123">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="45ae9-124">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="45ae9-124">Affected APIs</span></span>

<span data-ttu-id="45ae9-125">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="45ae9-125">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->