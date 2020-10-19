---
ms.openlocfilehash: 9c84c9f844a2a7efb9633c11634b069ef6b6033b
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "91804864"
---
### <a name="datagridview-no-longer-resets-fonts-for-customized-cell-styles"></a><span data-ttu-id="27bbb-101">カスタマイズされたセル スタイルのフォントが DataGridView によってリセットされなくなった</span><span class="sxs-lookup"><span data-stu-id="27bbb-101">DataGridView no longer resets fonts for customized cell styles</span></span>

<span data-ttu-id="27bbb-102">アンビエント フォントが変更されても、セル スタイル フォントがカスタマイズされている場合、アンビエント フォントと一致させるために既定のセルスタイル フォントが <xref:System.Windows.Forms.DataGridViewElement.DataGridView> によってリセットされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="27bbb-102">When the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> no longer resets default cell style fonts to match the ambient font if the cell style font has been customized.</span></span>

#### <a name="change-description"></a><span data-ttu-id="27bbb-103">変更内容</span><span class="sxs-lookup"><span data-stu-id="27bbb-103">Change description</span></span>

<span data-ttu-id="27bbb-104">以前のバージョンの .NET では、アンビエント フォントが変更されると、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>、および <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> の各プロパティのユーザー定義フォントが <xref:System.Windows.Forms.DataGridViewElement.DataGridView> によってリセットされ、オーバーライドされます。</span><span class="sxs-lookup"><span data-stu-id="27bbb-104">In previous .NET versions, if the ambient font changes, <xref:System.Windows.Forms.DataGridViewElement.DataGridView> resets and overrides user-defined fonts in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, and <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties.</span></span>

<span data-ttu-id="27bbb-105">.NET 5.0 以降では、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> のいずれかのプロパティでフォント設定を構成すると、アンビエント フォントが変更された場合でも、これらの設定が保持されます。</span><span class="sxs-lookup"><span data-stu-id="27bbb-105">Starting in .NET 5.0, if you configure font settings in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties, those settings are retained even when the ambient font changes.</span></span> <span data-ttu-id="27bbb-106">フォントをカスタマイズしないこれらのプロパティのフォントは、いずれもアンビエント フォントの設定に合わせて変更されます。</span><span class="sxs-lookup"><span data-stu-id="27bbb-106">For any of these properties that you don't customize the font, the font will change to match the ambient font settings.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="27bbb-107">変更理由</span><span class="sxs-lookup"><span data-stu-id="27bbb-107">Reason for change</span></span>

<span data-ttu-id="27bbb-108">[.NET Core 3.0 の既定のフォントの変更](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt)により、さまざまなセル スタイルの既定のフォント設定も変更されました。</span><span class="sxs-lookup"><span data-stu-id="27bbb-108">With the [change of the default font in .NET Core 3.0](../../../../docs/core/compatibility/winforms.md#default-control-font-changed-to-segoe-ui-9-pt), the default font settings for the various cell styles also changed.</span></span> <span data-ttu-id="27bbb-109">この動作は、<xref:System.Windows.Forms.DataGridViewElement.DataGridView> コントロールのカスタム スタイルに依存するアプリには望ましくなく、これらのアプリの .NET Framework から .NET 5.0 への移行を妨げます。</span><span class="sxs-lookup"><span data-stu-id="27bbb-109">This behavior is undesirable for apps that rely on custom styling in their <xref:System.Windows.Forms.DataGridViewElement.DataGridView> controls, and impeded the migration of these apps from .NET Framework to .NET 5.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="27bbb-110">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="27bbb-110">Version introduced</span></span>

<span data-ttu-id="27bbb-111">.NET 5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="27bbb-111">.NET 5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="27bbb-112">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="27bbb-112">Recommended action</span></span>

<span data-ttu-id="27bbb-113">お客様側では何もする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="27bbb-113">No action is required on your part.</span></span> <span data-ttu-id="27bbb-114">ただし、<xref:System.Windows.Forms.DataGridView.DefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>、<xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> のいずれかのプロパティでフォントをカスタマイズし、そのフォントをアンビエント フォントと一致させるには、各プロパティの <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> を `null` に設定します。</span><span class="sxs-lookup"><span data-stu-id="27bbb-114">However, if you've customized the font in the <xref:System.Windows.Forms.DataGridView.DefaultCellStyle>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle>, or <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle> properties and want the font to match the ambient font, set <xref:System.Windows.Forms.DataGridViewCellStyle.Font?displayProperty=nameWithType> to `null` for each property.</span></span>

#### <a name="category"></a><span data-ttu-id="27bbb-115">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="27bbb-115">Category</span></span>

- <span data-ttu-id="27bbb-116">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="27bbb-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="27bbb-117">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="27bbb-117">Affected APIs</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle?displayProperty=fullName>
- <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Windows.Forms.DataGridView.DefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle`
- `P:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle`

-->
