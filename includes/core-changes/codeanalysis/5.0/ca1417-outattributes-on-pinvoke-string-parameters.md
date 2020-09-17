---
ms.openlocfilehash: ada458ffeeba95d4989507f90c789b159f359797
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065168"
---
### <a name="ca1417-outattribute-on-string-parameter-for-pinvoke"></a><span data-ttu-id="e69d4-101">CA1417:P/Invoke 用の文字列パラメーターの OutAttribute</span><span class="sxs-lookup"><span data-stu-id="e69d4-101">CA1417: OutAttribute on string parameter for P/Invoke</span></span>

<span data-ttu-id="e69d4-102">.NET コード アナライザー ルール [CA1417](/visualstudio/code-quality/ca1417) は、.NET 5.0 以降では既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e69d4-102">.NET code analyzer rule [CA1417](/visualstudio/code-quality/ca1417) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="e69d4-103"><xref:System.String> パラメーターが値渡しされ、<xref:System.Runtime.InteropServices.OutAttribute> でマークされる[プラットフォーム呼び出し (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) メソッド定義に対して、ビルド警告が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e69d4-103">It produces a build warning for any [Platform Invoke (P/Invoke)](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is passed by value and marked with <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e69d4-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="e69d4-104">Change description</span></span>

<span data-ttu-id="e69d4-105">.NET 5.0 以降、.NET SDK には [.NET ソース コード アナライザー](../../../../docs/fundamentals/productivity/code-analysis.md)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e69d4-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="e69d4-106">これらのルールのいくつかは、[CA1417](/visualstudio/code-quality/ca1417) を含め、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e69d4-106">Several of these rules are enabled, by default, including [CA1417](/visualstudio/code-quality/ca1417).</span></span> <span data-ttu-id="e69d4-107">このルールに違反し、警告をエラーとして扱うように構成されているコードがプロジェクトに含まれている場合、この変更によってビルドが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e69d4-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="e69d4-108"><xref:System.String> パラメーターが <xref:System.Runtime.InteropServices.OutAttribute> 属性でマークされ、値渡しされる [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) メソッド定義には、ルール CA1417 によってフラグが立てられます。</span><span class="sxs-lookup"><span data-stu-id="e69d4-108">Rule CA1417 flags [P/Invoke](../../../../docs/standard/native-interop/pinvoke.md) method definitions where a <xref:System.String> parameter is marked with the <xref:System.Runtime.InteropServices.OutAttribute> attribute and is passed by value.</span></span> <span data-ttu-id="e69d4-109">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="e69d4-109">For example:</span></span>

```csharp
[DllImport("MyLibrary")]
private static extern void PIMethod([Out] string s);
```

<span data-ttu-id="e69d4-110">.NET ランタイムでは、インターン プールと呼ばれるテーブルが保持されます。これには、プログラム内の各一意のリテラル文字列への単一の参照が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e69d4-110">The .NET runtime maintains a table, called the intern pool, that contains a single reference to each unique literal string in a program.</span></span> <span data-ttu-id="e69d4-111"><xref:System.Runtime.InteropServices.OutAttribute> でマークされたインターン文字列が P/Invoke メソッドに値渡しされる場合、ランタイムが不安定になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e69d4-111">If an interned string marked with <xref:System.Runtime.InteropServices.OutAttribute> is passed by value to a P/Invoke method, the runtime can be destabilized.</span></span> <span data-ttu-id="e69d4-112">文字列インターンの詳細については、<xref:System.String.Intern(System.String)?displayProperty=nameWithType> に関する注釈を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69d4-112">For more information about string interning, see the remarks for <xref:System.String.Intern(System.String)?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e69d4-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="e69d4-113">Version introduced</span></span>

<span data-ttu-id="e69d4-114">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="e69d4-114">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e69d4-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="e69d4-115">Recommended action</span></span>

- <span data-ttu-id="e69d4-116">変更された文字列データを呼び出し元にマーシャリングする必要がある場合は、代わりに文字列を参照渡しにします。</span><span class="sxs-lookup"><span data-stu-id="e69d4-116">If you need to marshal modified string data back to the caller, pass the string by reference instead.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(out string s);
  ```

- <span data-ttu-id="e69d4-117">変更した文字列データを呼び出し元にマーシャリングする必要がない場合は、<xref:System.Runtime.InteropServices.OutAttribute> を削除するだけです。</span><span class="sxs-lookup"><span data-stu-id="e69d4-117">If you don't need to marshal modified string data back to the caller, simply remove the <xref:System.Runtime.InteropServices.OutAttribute>.</span></span>

  ```csharp
  [DllImport("MyLibrary")]
  private static extern void PIMethod(string s);
  ```

  <span data-ttu-id="e69d4-118">詳細については、[CA1417](/visualstudio/code-quality/ca1417) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69d4-118">For more information, see [CA1417](/visualstudio/code-quality/ca1417).</span></span>

- <span data-ttu-id="e69d4-119">コード分析を完全に無効にするには、プロジェクト ファイルで `EnableNETAnalyzers` を `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e69d4-119">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="e69d4-120">詳細については、「[EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e69d4-120">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="e69d4-121">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="e69d4-121">Category</span></span>

<span data-ttu-id="e69d4-122">コード分析</span><span class="sxs-lookup"><span data-stu-id="e69d4-122">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e69d4-123">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="e69d4-123">Affected APIs</span></span>

<span data-ttu-id="e69d4-124">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="e69d4-124">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
