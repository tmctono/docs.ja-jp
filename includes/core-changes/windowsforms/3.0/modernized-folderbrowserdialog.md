---
ms.openlocfilehash: 645df8080abd21e4db95903a301a36b79a698858
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888128"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="cccb3-101">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="cccb3-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="cccb3-102"><xref:System.Windows.Forms.FolderBrowserDialog> コントロールが、.NET Core の Windows フォーム アプリケーションで変更されています。</span><span class="sxs-lookup"><span data-stu-id="cccb3-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cccb3-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="cccb3-103">Change description</span></span>

<span data-ttu-id="cccb3-104">.NET Framework で Windows フォームは <xref:System.Windows.Forms.FolderBrowserDialog> コントロールに対し、次のダイアログを使用します。</span><span class="sxs-lookup"><span data-stu-id="cccb3-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![.NET Framework の FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="cccb3-106">.NET Core 3.0 では、Windows フォームは、Windows Vista で導入された次の新しい COM ベースのコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="cccb3-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![.NET Core の FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="cccb3-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="cccb3-108">Version introduced</span></span>

<span data-ttu-id="cccb3-109">3.0</span><span class="sxs-lookup"><span data-stu-id="cccb3-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cccb3-110">推奨アクション</span><span class="sxs-lookup"><span data-stu-id="cccb3-110">Recommended action</span></span>

<span data-ttu-id="cccb3-111">このダイアログは、自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="cccb3-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="cccb3-112">元のダイアログを保持したい場合、ダイアログを表示する前に、次のコード断片で示されるとおり、<xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="cccb3-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="cccb3-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="cccb3-113">Category</span></span>

<span data-ttu-id="cccb3-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="cccb3-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cccb3-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="cccb3-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!--

### Affected APIs

- `T:System.Windows.Forms.FolderBrowserDialog`

-->
