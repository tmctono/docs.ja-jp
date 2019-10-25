---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394431"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="b9d49-101">Razor: 実行時コンパイルをパッケージに移動</span><span class="sxs-lookup"><span data-stu-id="b9d49-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="b9d49-102">Razor ビューおよび Razor Pages の実行時コンパイルのサポートが個別のパッケージに移動されました。</span><span class="sxs-lookup"><span data-stu-id="b9d49-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b9d49-103">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="b9d49-103">Version introduced</span></span>

<span data-ttu-id="b9d49-104">3.0</span><span class="sxs-lookup"><span data-stu-id="b9d49-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b9d49-105">以前の動作</span><span class="sxs-lookup"><span data-stu-id="b9d49-105">Old behavior</span></span>

<span data-ttu-id="b9d49-106">追加のパッケージを必要とせずに、実行時コンパイルを利用できます。</span><span class="sxs-lookup"><span data-stu-id="b9d49-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b9d49-107">新しい動作</span><span class="sxs-lookup"><span data-stu-id="b9d49-107">New behavior</span></span>

<span data-ttu-id="b9d49-108">この機能は、`Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` パッケージに移動されました。</span><span class="sxs-lookup"><span data-stu-id="b9d49-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="b9d49-109">次の API は、実行時コンパイルをサポートするために、以前は `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` で使用できました。</span><span class="sxs-lookup"><span data-stu-id="b9d49-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="b9d49-110">これらの API は、`Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions` を介して使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b9d49-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="b9d49-111">また、`Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` が削除されました。</span><span class="sxs-lookup"><span data-stu-id="b9d49-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="b9d49-112">ファイルの変更時の再コンパイルは、`Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` パッケージを参照することによって既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="b9d49-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="b9d49-113">変更理由</span><span class="sxs-lookup"><span data-stu-id="b9d49-113">Reason for change</span></span>

<span data-ttu-id="b9d49-114">この変更は、ASP.NET Core 共有フレームワークの Roslyn への依存関係を削除するために必要でした。</span><span class="sxs-lookup"><span data-stu-id="b9d49-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b9d49-115">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="b9d49-115">Recommended action</span></span>

<span data-ttu-id="b9d49-116">Razor ファイルの実行時コンパイルまたは再コンパイルを必要とするアプリでは、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9d49-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="b9d49-117">`Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` パッケージへの参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="b9d49-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="b9d49-118">プロジェクトの `Startup.ConfigureServices` メソッドを更新して、`AddMvcRazorRuntimeCompilation` の呼び出しを含めます。</span><span class="sxs-lookup"><span data-stu-id="b9d49-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="b9d49-119">たとえば、`Startup.ConfigureServices` では次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b9d49-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="b9d49-120">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="b9d49-120">Category</span></span>

<span data-ttu-id="b9d49-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b9d49-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b9d49-122">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="b9d49-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
