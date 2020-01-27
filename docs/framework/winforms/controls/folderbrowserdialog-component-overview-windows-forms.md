---
title: FolderBrowserDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: 8b017ba08ae4205e930ac00177c89a89fde17d3b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745730"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="60621-102">FolderBrowserDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="60621-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="60621-103">Windows フォーム <xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントは、フォルダーの参照および選択に使用されるモーダルダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="60621-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="60621-104"><xref:System.Windows.Forms.FolderBrowserDialog> コンポーネント内から新しいフォルダーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="60621-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>

> [!NOTE]
> <span data-ttu-id="60621-105">フォルダーではなくファイルを選択するには、 [OpenFileDialog](openfiledialog-component-windows-forms.md)コンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="60621-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>

<span data-ttu-id="60621-106"><xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントは、実行時に <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="60621-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="60621-107">[<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>] プロパティを設定して、ダイアログボックスのツリービュー内に表示される最上位のフォルダーとサブフォルダーを決定します。</span><span class="sxs-lookup"><span data-stu-id="60621-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="60621-108">ダイアログボックスが表示されたら、<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> プロパティを使用して、選択されたフォルダーのパスを取得できます。</span><span class="sxs-lookup"><span data-stu-id="60621-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>

<span data-ttu-id="60621-109">フォームに追加されると、Visual Studio の Windows フォームデザイナーの下部にあるトレイに <xref:System.Windows.Forms.FolderBrowserDialog> コンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60621-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="60621-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="60621-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="60621-111">方法: Windows フォーム FolderBrowserDialog コンポーネントを使用してフォルダーを選択する</span><span class="sxs-lookup"><span data-stu-id="60621-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="60621-112">FolderBrowserDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="60621-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
