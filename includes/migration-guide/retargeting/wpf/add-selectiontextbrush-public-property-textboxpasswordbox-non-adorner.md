---
ms.openlocfilehash: aade03c29ff16053a97683499cf719a98ae33f3f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616274"
---
### <a name="add-selectiontextbrush-public-property-to-textboxpasswordbox-non-adorner-selection"></a><span data-ttu-id="6bb42-101">TextBox/PasswordBox の非装飾選択に SelectionTextBrush パブリック プロパティを追加する</span><span class="sxs-lookup"><span data-stu-id="6bb42-101">Add SelectionTextBrush public property to TextBox/PasswordBox non-adorner selection</span></span>

#### <a name="details"></a><span data-ttu-id="6bb42-102">説明</span><span class="sxs-lookup"><span data-stu-id="6bb42-102">Details</span></span>

<span data-ttu-id="6bb42-103"><xref:System.Windows.Controls.TextBox> と <xref:System.Windows.Controls.PasswordBox> の[非装飾ベースのテキスト選択](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md)を使用する WPF アプリケーションでは、開発者は、選択されたテキストのレンダリングを変更するために、新しく追加された SelectionTextBrush プロパティを設定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6bb42-103">In WPF applications using [non-adorner based text selection](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-TextBox-PasswordBox-text-selection-does-not-follow-system-colors.md) for <xref:System.Windows.Controls.TextBox> and <xref:System.Windows.Controls.PasswordBox>, developers may now set the newly added SelectionTextBrush property in order to alter the rendering of the selected text.</span></span>  <span data-ttu-id="6bb42-104">既定では、<xref:System.Windows.SystemColors.HighlightTextBrushKey> でこの色が変更されます。</span><span class="sxs-lookup"><span data-stu-id="6bb42-104">By default, this color changes with <xref:System.Windows.SystemColors.HighlightTextBrushKey>.</span></span>  <span data-ttu-id="6bb42-105">非装飾ベースのテキスト選択が有効でない場合は、このプロパティで何も行われません。</span><span class="sxs-lookup"><span data-stu-id="6bb42-105">If non-adorner based text selection is not enabled, this property does nothing.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6bb42-106">提案される解決策</span><span class="sxs-lookup"><span data-stu-id="6bb42-106">Suggestion</span></span>

<span data-ttu-id="6bb42-107">非装飾ベースのテキスト選択が有効になったら、<xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> および <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> プロパティを使用して、選択されたテキストの外観を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="6bb42-107">Once non-adorner based text selection is enabled, you can use the <xref:System.Windows.Controls.PasswordBox.SelectionTextBrush?displayProperty=nameWithType> and <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush> property to change the appearance of the selected text.</span></span> <span data-ttu-id="6bb42-108">これは XAML を使用して実行できます。</span><span class="sxs-lookup"><span data-stu-id="6bb42-108">This can be achieved using XAML:</span></span>

<pre><code class="lang-xaml">&lt;TextBox SelectionBrush=&quot;Red&quot; SelectionTextBrush=&quot;White&quot;  SelectionOpacity=&quot;0.5&quot;&#13;&#10;Foreground=&quot;Blue&quot; CaretBrush=&quot;Blue&quot;&gt;&#13;&#10;This is some text.&#13;&#10;&lt;/TextBox&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="6bb42-109">名前</span><span class="sxs-lookup"><span data-stu-id="6bb42-109">Name</span></span>    | <span data-ttu-id="6bb42-110">[値]</span><span class="sxs-lookup"><span data-stu-id="6bb42-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6bb42-111">スコープ</span><span class="sxs-lookup"><span data-stu-id="6bb42-111">Scope</span></span>   | <span data-ttu-id="6bb42-112">Major</span><span class="sxs-lookup"><span data-stu-id="6bb42-112">Major</span></span>       |
| <span data-ttu-id="6bb42-113">バージョン</span><span class="sxs-lookup"><span data-stu-id="6bb42-113">Version</span></span> | <span data-ttu-id="6bb42-114">4.8</span><span class="sxs-lookup"><span data-stu-id="6bb42-114">4.8</span></span>         |
| <span data-ttu-id="6bb42-115">種類</span><span class="sxs-lookup"><span data-stu-id="6bb42-115">Type</span></span>    | <span data-ttu-id="6bb42-116">再ターゲット中</span><span class="sxs-lookup"><span data-stu-id="6bb42-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="6bb42-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="6bb42-117">Affected APIs</span></span>

- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrushProperty?displayProperty=nameWithType>
- <xref:System.Windows.Controls.Primitives.TextBoxBase.SelectionTextBrush?displayProperty=nameWithType>
- [<span data-ttu-id="6bb42-118">System.Windows.Controls.TextBox</span><span class="sxs-lookup"><span data-stu-id="6bb42-118">System.Windows.Controls.TextBox</span></span>](xref:System.Windows.Controls.TextBox)
- [<span data-ttu-id="6bb42-119">System.Windows.Controls.PasswordBox</span><span class="sxs-lookup"><span data-stu-id="6bb42-119">System.Windows.Controls.PasswordBox</span></span>](xref:System.Windows.Controls.PasswordBox)
