---
title: '方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: f47eb29bf9ae077555f352d10c667bac4ade9373
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968330"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="09aa7-102">方法: デザイナーを使用して Windows フォーム DataGridView コントロールで行が追加および削除されないようにする</span><span class="sxs-lookup"><span data-stu-id="09aa7-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="09aa7-103">場合によっては、ユーザーが <xref:System.Windows.Forms.DataGridView> コントロールに新しいデータ行を入力したり、既存の行を削除したりできないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09aa7-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="09aa7-104">コントロールの下部に新しいレコードがある場合は、新しい行が特別な行に入力されます。</span><span class="sxs-lookup"><span data-stu-id="09aa7-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="09aa7-105">行の追加を無効にした場合、新しいレコードの行は表示されません。</span><span class="sxs-lookup"><span data-stu-id="09aa7-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="09aa7-106">行の削除とセルの編集を無効にすることで、コントロールを完全に読み取り専用にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09aa7-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="09aa7-107">次の手順では、 <xref:System.Windows.Forms.DataGridView>コントロールを含むフォームを含む**Windows アプリケーション**プロジェクトが必要です。</span><span class="sxs-lookup"><span data-stu-id="09aa7-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="09aa7-108">このようなプロジェクトの設定の詳細につい[ては、「方法:Windows フォームアプリケーションプロジェクト](/visualstudio/ide/step-1-create-a-windows-forms-application-project)を作成し[、次の操作を行います。Windows フォーム](how-to-add-controls-to-windows-forms.md)にコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="09aa7-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="09aa7-109">行の追加と削除を防止するには</span><span class="sxs-lookup"><span data-stu-id="09aa7-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="09aa7-110">スマート タグ グリフをクリックします (![スマート タグ グリフ](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) の右上隅で、 <xref:System.Windows.Forms.DataGridView> 、制御し、オフ、 **追加を有効にする** **削除を有効にする** チェック ボックス。</span><span class="sxs-lookup"><span data-stu-id="09aa7-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09aa7-111">コントロールを完全に読み取り専用にするには、[**編集を有効に**する] チェックボックスもオフにします。</span><span class="sxs-lookup"><span data-stu-id="09aa7-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="09aa7-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="09aa7-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="09aa7-113">方法: Windows フォーム アプリケーション プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="09aa7-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="09aa7-114">方法: コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="09aa7-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
