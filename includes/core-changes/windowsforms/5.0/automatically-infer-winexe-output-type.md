---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679001"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="3b80a-101">WPF アプリと WinForms アプリで OutputType が WinExe に設定されている</span><span class="sxs-lookup"><span data-stu-id="3b80a-101">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="3b80a-102">`OutputType` は、Windows Presentation Foundation (WPF) アプリと Windows フォーム アプリでは、自動的に `WinExe` に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3b80a-102">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="3b80a-103">`OutputType` が `WinExe` に設定されている場合、アプリの実行時にコンソール ウィンドウは開きません。</span><span class="sxs-lookup"><span data-stu-id="3b80a-103">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3b80a-104">変更内容</span><span class="sxs-lookup"><span data-stu-id="3b80a-104">Change description</span></span>

<span data-ttu-id="3b80a-105">以前のバージョンの .NET では、プロジェクト ファイルで `OutputType` に指定されている値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="3b80a-105">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="3b80a-106">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3b80a-106">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="3b80a-107">.NET 5.0 以降では、WPF アプリと Windows フォーム アプリで `OutputType` が `WinExe` に自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="3b80a-107">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="3b80a-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3b80a-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a><span data-ttu-id="3b80a-109">変更理由</span><span class="sxs-lookup"><span data-stu-id="3b80a-109">Reason for change</span></span>

<span data-ttu-id="3b80a-110">WPF アプリまたは Windows フォーム アプリの実行時に、ほとんどのユーザーがコンソール ウィンドウを開かないことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="3b80a-110">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="3b80a-111">さらに、[これらの種類のアプリケーションでは .NET SDK が使用され](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) (Windows Desktop SDK が使用されるのではなく)、正しい既定値が設定されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3b80a-111">In addition, [now that these application types use the .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="3b80a-112">さらに、iOS と Android を対象としたサポートが追加されると、これらすべてで同じ出力の種類が使用される場合に、複数のプラットフォーム間で複数のターゲットを指定することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="3b80a-112">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3b80a-113">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="3b80a-113">Version introduced</span></span>

<span data-ttu-id="3b80a-114">.NET 5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="3b80a-114">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3b80a-115">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="3b80a-115">Recommended action</span></span>

<span data-ttu-id="3b80a-116">ユーザー側の対応は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="3b80a-116">No action is required in your part.</span></span> <span data-ttu-id="3b80a-117">ただし、以前の動作に戻す場合は、プロジェクト ファイルの `DisableWinExeOutputInference` プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="3b80a-117">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a><span data-ttu-id="3b80a-118">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="3b80a-118">Category</span></span>

- <span data-ttu-id="3b80a-119">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="3b80a-119">Windows Forms</span></span>
- <span data-ttu-id="3b80a-120">Windows Presentation Foundation (WPF)</span><span class="sxs-lookup"><span data-stu-id="3b80a-120">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3b80a-121">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="3b80a-121">Affected APIs</span></span>

<span data-ttu-id="3b80a-122">API 分析では検出できません。</span><span class="sxs-lookup"><span data-stu-id="3b80a-122">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
