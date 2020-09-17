---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656343"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="efd21-101">WinForms と WPF アプリで Microsoft.NET.Sdk が使用される</span><span class="sxs-lookup"><span data-stu-id="efd21-101">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="efd21-102">Windows フォームと Windows Presentation Framework (WPF) アプリで、.NET Core WinForms および WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`) ではなく、.NET SDK (`Microsoft.NET.Sdk`) が使用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="efd21-102">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

#### <a name="change-description"></a><span data-ttu-id="efd21-103">変更内容</span><span class="sxs-lookup"><span data-stu-id="efd21-103">Change description</span></span>

<span data-ttu-id="efd21-104">以前のバージョンの .NET Core では、WinForms および WPF アプリで別の[プロジェクト SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`) が使用されていました。</span><span class="sxs-lookup"><span data-stu-id="efd21-104">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="efd21-105">.NET 5.0 以降、WinForms および WPF SDK の両方で .NET SDK (`Microsoft.NET.Sdk`) が統合されました。</span><span class="sxs-lookup"><span data-stu-id="efd21-105">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="efd21-106">また、.NET 5 では、`netcoreapp` と `netstandard` が新しい[ターゲット フレーム ワークモニカー (TFM)](../../../../docs/standard/frameworks.md) に置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="efd21-106">In addition, new [target framework monikers (TFM)](../../../../docs/standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="efd21-107">次の例では、WPF プロジェクト ファイルを .NET 5.0 以降に変更する場合に、行う必要がある変更を示しています。</span><span class="sxs-lookup"><span data-stu-id="efd21-107">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="efd21-108">以前の .NET Core バージョンの場合:</span><span class="sxs-lookup"><span data-stu-id="efd21-108">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="efd21-109">.NET 5.0 以降のバージョンの場合:</span><span class="sxs-lookup"><span data-stu-id="efd21-109">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a><span data-ttu-id="efd21-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="efd21-110">Version introduced</span></span>

<span data-ttu-id="efd21-111">.NET 5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="efd21-111">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="efd21-112">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="efd21-112">Recommended action</span></span>

<span data-ttu-id="efd21-113">お使いの WPF または Windows フォーム プロジェクト ファイル:</span><span class="sxs-lookup"><span data-stu-id="efd21-113">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="efd21-114">`Sdk` 属性を `Microsoft.NET.Sdk` に更新します。</span><span class="sxs-lookup"><span data-stu-id="efd21-114">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="efd21-115">`TargetFramework` プロパティを `net5.0-windows` に更新します。</span><span class="sxs-lookup"><span data-stu-id="efd21-115">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

#### <a name="category"></a><span data-ttu-id="efd21-116">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="efd21-116">Category</span></span>

- <span data-ttu-id="efd21-117">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="efd21-117">Windows Forms</span></span>
- <span data-ttu-id="efd21-118">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="efd21-118">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="efd21-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="efd21-119">Affected APIs</span></span>

<span data-ttu-id="efd21-120">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="efd21-120">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
