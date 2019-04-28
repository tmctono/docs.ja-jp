---
title: FolderBrowserDialog コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- FolderBrowserDialog
helpviewer_keywords:
- FolderBrowserDialog component [Windows Forms], about FolderBrowserDialog
- directories [Windows Forms], enabling browsing in applications
- folders [Windows Forms], enabling browsing in applications
ms.assetid: 796b622c-3ba9-4356-93bb-e217fc52f2c7
ms.openlocfilehash: aae18167b29c71ad692cc6ba447457cd079374b4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651468"
---
# <a name="folderbrowserdialog-component-overview-windows-forms"></a><span data-ttu-id="5c722-102">FolderBrowserDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="5c722-102">FolderBrowserDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="5c722-103">Windows フォーム<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネントは参照およびフォルダーの選択に使用するモーダル ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="5c722-103">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component is a modal dialog box that is used for browsing and selecting folders.</span></span> <span data-ttu-id="5c722-104">内から新しいフォルダーを作成することも、<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="5c722-104">New folders can also be created from within the <xref:System.Windows.Forms.FolderBrowserDialog> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c722-105">使用して、フォルダーではなくファイルを選択する、 [OpenFileDialog](openfiledialog-component-windows-forms.md)コンポーネント。</span><span class="sxs-lookup"><span data-stu-id="5c722-105">To select files, instead of folders, use the [OpenFileDialog](openfiledialog-component-windows-forms.md) component.</span></span>  
  
 <span data-ttu-id="5c722-106"><xref:System.Windows.Forms.FolderBrowserDialog>を使用して実行時にコンポーネントが表示されます、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="5c722-106">The <xref:System.Windows.Forms.FolderBrowserDialog> component is displayed at run time using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span> <span data-ttu-id="5c722-107">設定、<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>プロパティを最上位のフォルダーと、ダイアログ ボックスのツリー ビュー内に表示されるすべてのサブフォルダーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c722-107">Set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property to determine the top-most folder and any subfolders that will appear within the tree view of the dialog box.</span></span> <span data-ttu-id="5c722-108">ダイアログ ボックスが表示されると、使用できます、<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>プロパティが選択されているフォルダーのパスを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c722-108">Once the dialog box has been shown, you can use the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property to get the path of the folder that was selected.</span></span>  
  
 <span data-ttu-id="5c722-109">フォームに追加されたとき、<xref:System.Windows.Forms.FolderBrowserDialog>コンポーネント、Windows フォーム デザイナーの下部にあるトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c722-109">When it is added to a form, the <xref:System.Windows.Forms.FolderBrowserDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c722-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c722-110">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="5c722-111">方法: Windows フォーム FolderBrowserDialog コンポーネントを含むフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c722-111">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>](how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component.md)
- [<span data-ttu-id="5c722-112">FolderBrowserDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5c722-112">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
