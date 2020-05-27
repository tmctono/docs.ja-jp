---
ms.openlocfilehash: 0b2d3c1383246d4259c6d906ecf9dab927f4bdb1
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721093"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="62ef3-101">既定のコントロール フォントが Segoe UI 9 pt に変更されました</span><span class="sxs-lookup"><span data-stu-id="62ef3-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="62ef3-102">変更の説明</span><span class="sxs-lookup"><span data-stu-id="62ef3-102">Change description</span></span>

<span data-ttu-id="62ef3-103">.NET Framework では、<xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> プロパティは、`Microsoft Sans Serif 8 pt` に設定されていました。</span><span class="sxs-lookup"><span data-stu-id="62ef3-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="62ef3-104">次の画像は、既定のフォントを使用するウィンドウを示しています。</span><span class="sxs-lookup"><span data-stu-id="62ef3-104">The following image shows a window that uses the default font.</span></span>

![.NET Framework の既定のコントロール フォント](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="62ef3-106">.NET Core 3.0 以降では、既定のフォントは `Segoe UI 9 pt` (<xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType> と同じフォント) に設定されています。</span><span class="sxs-lookup"><span data-stu-id="62ef3-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="62ef3-107">この変更により、大きくなった新しい既定のフォント サイズに対応するために、フォームとコントロールのサイズが約 27% 大きくなっています。</span><span class="sxs-lookup"><span data-stu-id="62ef3-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="62ef3-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="62ef3-108">For example:</span></span>

![.NET Core の既定のコントロール フォント](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="62ef3-110">この変更は、[Windows ユーザー エクスペリエンス (UX) のガイドライン](/windows/win32/uxguide/vis-fonts#fonts-and-colors)に合わせて行われました。</span><span class="sxs-lookup"><span data-stu-id="62ef3-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="62ef3-111">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="62ef3-111">Version introduced</span></span>

<span data-ttu-id="62ef3-112">3.0</span><span class="sxs-lookup"><span data-stu-id="62ef3-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="62ef3-113">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="62ef3-113">Recommended action</span></span>

<span data-ttu-id="62ef3-114">フォームとコントロールのサイズが変更されているため、レンダリングがご使用のアプリケーションで正しく行われることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="62ef3-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="62ef3-115">元のフォントを維持するには、フォームの既定のフォントを `Microsoft Sans Serif 8 pt` に設定します。</span><span class="sxs-lookup"><span data-stu-id="62ef3-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="62ef3-116">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="62ef3-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="62ef3-117">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="62ef3-117">Category</span></span>

- <span data-ttu-id="62ef3-118">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="62ef3-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="62ef3-119">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="62ef3-119">Affected APIs</span></span>

<span data-ttu-id="62ef3-120">[なし] :</span><span class="sxs-lookup"><span data-stu-id="62ef3-120">None.</span></span>

<!--

#### Affected APIs

- Not detectable via API analysis

-->
