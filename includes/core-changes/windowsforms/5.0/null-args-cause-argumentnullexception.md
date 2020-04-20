---
ms.openlocfilehash: fc0eec26073c299887b4748d0ad37e21c7294e84
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2020
ms.locfileid: "81274796"
---
### <a name="winforms-apis-now-throw-argumentnullexception"></a><span data-ttu-id="eb887-101">WinForms API で ArgumentNullException がスローされる</span><span class="sxs-lookup"><span data-stu-id="eb887-101">WinForms APIs now throw ArgumentNullException</span></span>

<span data-ttu-id="eb887-102">一部の Windows フォーム メソッドで、null 引数について <xref:System.ArgumentNullException> がスローされるようになりました。以前は <xref:System.NullReferenceException> がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="eb887-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="eb887-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="eb887-103">Change description</span></span>

<span data-ttu-id="eb887-104">以前は、null の引数が渡された場合、特定の Windows フォーム メソッドでは <xref:System.NullReferenceException> がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="eb887-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="eb887-105">.NET 5.0 以降、これらのメソッドで、null 引数について <xref:System.ArgumentNullException> が代わりにスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eb887-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments instead.</span></span>

<span data-ttu-id="eb887-106"><xref:System.ArgumentNullException> をスローすることは、.NET ランタイムの動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="eb887-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="eb887-107">また、引数が null であることと、どの引数がそうであるのかが明確に伝えられることで、デバッグ エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="eb887-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="eb887-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="eb887-108">Version introduced</span></span>

<span data-ttu-id="eb887-109">.NET 5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="eb887-109">.NET 5.0 Preview 1</span></span>\
<span data-ttu-id="eb887-110">.NET 5.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="eb887-110">.NET 5.0 Preview 2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="eb887-111">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="eb887-111">Recommended action</span></span>

<span data-ttu-id="eb887-112">これらのメソッドのいずれかを呼び出す場合、コードでは現在 null 引数について <xref:System.NullReferenceException> をキャッチする場合は、代わりに <xref:System.ArgumentNullException> をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="eb887-112">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="eb887-113">さらに、リストされているメソッドに null 引数が渡されないようにコードを更新することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="eb887-113">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="eb887-114">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="eb887-114">Category</span></span>

<span data-ttu-id="eb887-115">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="eb887-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="eb887-116">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="eb887-116">Affected APIs</span></span>

<span data-ttu-id="eb887-117">.NET 5.0 Preview 1 以降:</span><span class="sxs-lookup"><span data-stu-id="eb887-117">Starting in .NET 5.0 Preview 1:</span></span>

- <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)>
- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType>

<span data-ttu-id="eb887-118">.NET 5.0 Preview 2 以降:</span><span class="sxs-lookup"><span data-stu-id="eb887-118">Starting in .NET 5.0 Preview 2:</span></span>

- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType>
- <span data-ttu-id="eb887-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (<xref:System.IO.Stream> パラメーターのみ)</span><span class="sxs-lookup"><span data-stu-id="eb887-119"><xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> (for the <xref:System.IO.Stream> parameter only)</span></span>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`

-->
