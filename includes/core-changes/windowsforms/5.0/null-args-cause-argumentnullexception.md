---
ms.openlocfilehash: 59e7b55516d79aa5c574a8869698e1a18576ef41
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770775"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="a9ccd-101">WinForms メソッドで ArgumentNullException がスローされるようになった</span><span class="sxs-lookup"><span data-stu-id="a9ccd-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="a9ccd-102">一部の Windows フォーム メソッドで、null 引数について <xref:System.ArgumentNullException> がスローされるようになりました。以前は <xref:System.NullReferenceException> がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a9ccd-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="a9ccd-103">Change description</span></span>

<span data-ttu-id="a9ccd-104">以前は、null の引数が渡された場合、特定の Windows フォーム メソッドでは <xref:System.NullReferenceException> がスローされていました。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="a9ccd-105">.NET 5.0 以降、これらのメソッドでは、null 引数に対して <xref:System.ArgumentNullException> が代わりにスローされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="a9ccd-106"><xref:System.ArgumentNullException> をスローすることは、.NET ランタイムの動作に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="a9ccd-107">また、引数が null であることと、どの引数がそうであるのかが明確に伝えられることで、デバッグ エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a9ccd-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a9ccd-108">Version introduced</span></span>

<span data-ttu-id="a9ccd-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a9ccd-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a9ccd-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="a9ccd-110">Recommended action</span></span>

<span data-ttu-id="a9ccd-111">これらのメソッドのいずれかを呼び出す場合、コードでは現在 null 引数について <xref:System.NullReferenceException> をキャッチする場合は、代わりに <xref:System.ArgumentNullException> をキャッチします。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="a9ccd-112">さらに、リストされているメソッドに null 引数が渡されないようにコードを更新することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="a9ccd-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a9ccd-113">Category</span></span>

<span data-ttu-id="a9ccd-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="a9ccd-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a9ccd-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="a9ccd-115">Affected APIs</span></span>

<span data-ttu-id="a9ccd-116">次の表では、影響を受けるメソッドとパラメーターを示します。</span><span class="sxs-lookup"><span data-stu-id="a9ccd-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="a9ccd-117">メソッド</span><span class="sxs-lookup"><span data-stu-id="a9ccd-117">Method</span></span> | <span data-ttu-id="a9ccd-118">パラメーター名</span><span class="sxs-lookup"><span data-stu-id="a9ccd-118">Parameter name</span></span> | <span data-ttu-id="a9ccd-119">追加されたバージョン</span><span class="sxs-lookup"><span data-stu-id="a9ccd-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="a9ccd-120">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-120">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="a9ccd-121">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-121">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="a9ccd-122">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-122">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="a9ccd-123">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-123">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="a9ccd-124">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-124">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="a9ccd-125">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-125">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="a9ccd-126">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-126">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="a9ccd-127">Preview 1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-127">Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="a9ccd-128">Preview 2</span><span class="sxs-lookup"><span data-stu-id="a9ccd-128">Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="a9ccd-129">Preview 2</span><span class="sxs-lookup"><span data-stu-id="a9ccd-129">Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="a9ccd-130">Preview 5</span><span class="sxs-lookup"><span data-stu-id="a9ccd-130">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="a9ccd-131">Preview 5</span><span class="sxs-lookup"><span data-stu-id="a9ccd-131">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="a9ccd-132">Preview 5</span><span class="sxs-lookup"><span data-stu-id="a9ccd-132">Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="a9ccd-133">Preview 5</span><span class="sxs-lookup"><span data-stu-id="a9ccd-133">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="a9ccd-134">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-134">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="a9ccd-135">`owner`、`value`</span><span class="sxs-lookup"><span data-stu-id="a9ccd-135">`owner`, `value`</span></span> | <span data-ttu-id="a9ccd-136">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-136">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="a9ccd-137">`owner`、`value`</span><span class="sxs-lookup"><span data-stu-id="a9ccd-137">`owner`, `value`</span></span> | <span data-ttu-id="a9ccd-138">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-138">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="a9ccd-139">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-139">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="a9ccd-140">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-140">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="a9ccd-141">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-141">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="a9ccd-142">Preview 6</span><span class="sxs-lookup"><span data-stu-id="a9ccd-142">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListView.SelectedIndexCollection.%23ctor(System.Windows.Forms.ListView)> | `owner` | <span data-ttu-id="a9ccd-143">Preview 7</span><span class="sxs-lookup"><span data-stu-id="a9ccd-143">Preview 7</span></span> |
> | <xref:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="a9ccd-144">`key` が `null` または空です</span><span class="sxs-lookup"><span data-stu-id="a9ccd-144">`key` is `null` or empty</span></span> | <span data-ttu-id="a9ccd-145">Preview 8</span><span class="sxs-lookup"><span data-stu-id="a9ccd-145">Preview 8</span></span> |
> | <xref:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="a9ccd-146">`key` が `null` または空です</span><span class="sxs-lookup"><span data-stu-id="a9ccd-146">`key` is `null` or empty</span></span> | <span data-ttu-id="a9ccd-147">RC1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-147">RC1</span></span> |
> | <xref:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="a9ccd-148">RC1</span><span class="sxs-lookup"><span data-stu-id="a9ccd-148">RC1</span></span> |

<!-- 

#### Affected APIs

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
- `M:System.Windows.Forms.ListViewGroup.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.#ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System#Collections#ICollection#CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListView.SelectedIndexCollection.#ctor(System.Windows.Forms.ListView)`
- `M:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)`

-->
