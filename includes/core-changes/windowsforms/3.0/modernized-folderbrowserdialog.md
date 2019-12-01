---
ms.openlocfilehash: 24141f4b95cda2ae382a923da034e75c329b8555
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643857"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="f106b-101">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="f106b-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="f106b-102"><xref:System.Windows.Forms.FolderBrowserDialog> コントロールが、.NET Core の Windows フォーム アプリケーションで変更されています。</span><span class="sxs-lookup"><span data-stu-id="f106b-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f106b-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="f106b-103">Change description</span></span>

<span data-ttu-id="f106b-104">.NET Framework で Windows フォームは <xref:System.Windows.Forms.FolderBrowserDialog> コントロールに対し、次のダイアログを使用します。</span><span class="sxs-lookup"><span data-stu-id="f106b-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![.NET Framework の FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="f106b-106">.NET Core 3.0 では、Windows フォームは、Windows Vista で導入された次の新しい COM ベースのコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="f106b-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![.NET Core の FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="f106b-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="f106b-108">Version introduced</span></span>

<span data-ttu-id="f106b-109">3.0</span><span class="sxs-lookup"><span data-stu-id="f106b-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f106b-110">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="f106b-110">Recommended action</span></span>

<span data-ttu-id="f106b-111">このダイアログは、自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="f106b-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="f106b-112">元のダイアログを保持したい場合、ダイアログを表示する前に、次のコード断片で示されるとおり、<xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f106b-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="f106b-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="f106b-113">Category</span></span>

<span data-ttu-id="f106b-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="f106b-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f106b-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="f106b-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->
