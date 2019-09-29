---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216913"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="76108-101">`Control.DefaultFont` の `Segoe UI 9pt` への変更</span><span class="sxs-lookup"><span data-stu-id="76108-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span>

#### <a name="change-description"></a><span data-ttu-id="76108-102">変更の説明</span><span class="sxs-lookup"><span data-stu-id="76108-102">Change description</span></span>

<span data-ttu-id="76108-103">.NET Framework では、<xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> プロパティは、`Microsoft Sans Serif 8pt` に設定されていました。</span><span class="sxs-lookup"><span data-stu-id="76108-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="76108-104">次は、既定のフォントを使用するウィンドウの図です。</span><span class="sxs-lookup"><span data-stu-id="76108-104">The following figure shows a window that uses the default font.</span></span>

![.NET Framework の既定のコントロール フォント](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="76108-106">これは、.NET Core の .NET Core 3.0 以降で `Segoe UI 9pt` に設定されています (<xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType> と同じフォント)。</span><span class="sxs-lookup"><span data-stu-id="76108-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="76108-107">この変更により、大きくなった新しい既定のフォント サイズに対応するために、フォームとコントロールのサイズが約 27% 大きくなっています。</span><span class="sxs-lookup"><span data-stu-id="76108-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="76108-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="76108-108">For example:</span></span>

![.NET Core の既定のコントロールのフォント](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="76108-110">この変更は、[Windows UX のガイドライン](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors)に合わせて行われました。</span><span class="sxs-lookup"><span data-stu-id="76108-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="76108-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="76108-111">Version introduced</span></span>

<span data-ttu-id="76108-112">3.0</span><span class="sxs-lookup"><span data-stu-id="76108-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="76108-113">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="76108-113">Recommended action</span></span>

<span data-ttu-id="76108-114">フォームとコントロールのサイズが変更されているため、レンダリングがご使用のアプリケーションで正しく行われることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="76108-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="76108-115">元のフォントを維持するには、フォームの既定のフォントを `Microsoft Sans Serif 8pt` に設定します。</span><span class="sxs-lookup"><span data-stu-id="76108-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="76108-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="76108-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="76108-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="76108-117">Category</span></span>

- <span data-ttu-id="76108-118">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="76108-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76108-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="76108-119">Affected APIs</span></span>

<span data-ttu-id="76108-120">なし。</span><span class="sxs-lookup"><span data-stu-id="76108-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
