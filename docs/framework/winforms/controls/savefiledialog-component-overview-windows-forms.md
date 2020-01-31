---
title: SaveFileDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 7609c29b7e932ecee7dc8a289617094bd8d480e2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743103"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="d43d8-102">SaveFileDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d43d8-102">SaveFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="d43d8-103">Windows フォームの <xref:System.Windows.Forms.SaveFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="d43d8-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="d43d8-104">これは、Windows によって使用される標準の **[ファイルの保存]** ダイアログボックスと同じです。</span><span class="sxs-lookup"><span data-stu-id="d43d8-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="d43d8-105">これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。</span><span class="sxs-lookup"><span data-stu-id="d43d8-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="d43d8-106">SaveFileDialog コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="d43d8-106">Working with the SaveFileDialog Component</span></span>

<span data-ttu-id="d43d8-107">独自のダイアログボックスを構成する代わりに、ユーザーがファイルを保存できるようにするための簡単なソリューションとして使用します。</span><span class="sxs-lookup"><span data-stu-id="d43d8-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="d43d8-108">標準の Windows ダイアログボックスに依存しているため、ユーザーにとって作成するアプリケーションの基本的な機能はすぐにわかります。</span><span class="sxs-lookup"><span data-stu-id="d43d8-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="d43d8-109">ただし、<xref:System.Windows.Forms.SaveFileDialog> コンポーネントを使用する場合は、独自のファイル保存ロジックを作成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d43d8-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>

<span data-ttu-id="d43d8-110"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用して、実行時にダイアログボックスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="d43d8-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="d43d8-111"><xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> メソッドを使用して、読み取り/書き込みモードでファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="d43d8-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>

<span data-ttu-id="d43d8-112">フォームに追加されると、Visual Studio の Windows フォームデザイナーの下部にあるトレイに <xref:System.Windows.Forms.SaveFileDialog> コンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d43d8-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="d43d8-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="d43d8-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="d43d8-114">SaveFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d43d8-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
