---
ms.openlocfilehash: a7cf6210e288d3521f1df248927f0e7cfaf45cab
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119120"
---
### <a name="modernization-of-the-folderbrowserdialog"></a><span data-ttu-id="54e6a-101">FolderBrowserDialog の最新化</span><span class="sxs-lookup"><span data-stu-id="54e6a-101">Modernization of the FolderBrowserDialog</span></span>

<span data-ttu-id="54e6a-102"><xref:System.Windows.Forms.FolderBrowserDialog> コントロールが、.NET Core の Windows フォーム アプリケーションで変更されています。</span><span class="sxs-lookup"><span data-stu-id="54e6a-102">The <xref:System.Windows.Forms.FolderBrowserDialog> control has changed in Windows Forms applications for .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="54e6a-103">変更の説明</span><span class="sxs-lookup"><span data-stu-id="54e6a-103">Change description</span></span>

<span data-ttu-id="54e6a-104">.NET Framework で Windows フォームは <xref:System.Windows.Forms.FolderBrowserDialog> コントロールに対し、次のダイアログを使用します。</span><span class="sxs-lookup"><span data-stu-id="54e6a-104">In the .NET Framework, Windows forms uses the following dialog for the <xref:System.Windows.Forms.FolderBrowserDialog> control:</span></span>

![.NET Framework の FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-framework.png)

<span data-ttu-id="54e6a-106">.NET Core 3.0 では、Windows フォームは、Windows Vista で導入された次の新しい COM ベースのコントロールを使用します。</span><span class="sxs-lookup"><span data-stu-id="54e6a-106">In .NET Core 3.0, Windows Forms users a newer COM-based control that was introduced in Windows Vista:</span></span>

![.NET Core の FolderBrowserDialogControl](~/docs/images/core-changes/windowsforms/modernized-folderbrowserdialog/folderdlg-core.png)

#### <a name="version-introduced"></a><span data-ttu-id="54e6a-108">導入されたバージョン</span><span class="sxs-lookup"><span data-stu-id="54e6a-108">Version introduced</span></span>

<span data-ttu-id="54e6a-109">3.0</span><span class="sxs-lookup"><span data-stu-id="54e6a-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="54e6a-110">推奨される操作</span><span class="sxs-lookup"><span data-stu-id="54e6a-110">Recommended action</span></span>

<span data-ttu-id="54e6a-111">このダイアログは、自動的にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="54e6a-111">The dialog will be upgraded automatically.</span></span>

<span data-ttu-id="54e6a-112">元のダイアログを保持したい場合、ダイアログを表示する前に、次のコード断片で示されるとおり、<xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> プロパティを `false` に設定します。</span><span class="sxs-lookup"><span data-stu-id="54e6a-112">If you desire to retain the original dialog, set the <xref:System.Windows.Forms.FolderBrowserDialog.AutoUpgradeEnabled?displayProperty=nameWithType> property to `false` before showing the dialog, as illustrated by the following code fragment:</span></span>

```csharp
var dialog = new FolderBrowserDialog();
dialog.AutoUpgradeEnabled = false;
dialog.ShowDialog();
```

#### <a name="category"></a><span data-ttu-id="54e6a-113">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="54e6a-113">Category</span></span>

<span data-ttu-id="54e6a-114">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="54e6a-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="54e6a-115">影響を受ける API</span><span class="sxs-lookup"><span data-stu-id="54e6a-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>

<!-- 

### Affected APIs

- `System.Windows.Forms.FolderBrowserDialog`

-->