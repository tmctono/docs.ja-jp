---
title: OpenFileDialog コンポーネントの概要
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: c519b373150a49ee41dbb0c503f7d5a4862477d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728437"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="ac146-102">OpenFileDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="ac146-102">OpenFileDialog Component Overview (Windows Forms)</span></span>

<span data-ttu-id="ac146-103">Windows フォームの <xref:System.Windows.Forms.OpenFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="ac146-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="ac146-104">これは、Windows オペレーティングシステムによって公開されているのと同じ **[ファイルを開く**] ダイアログボックスです。</span><span class="sxs-lookup"><span data-stu-id="ac146-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="ac146-105">これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。</span><span class="sxs-lookup"><span data-stu-id="ac146-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>

## <a name="use-this-component"></a><span data-ttu-id="ac146-106">このコンポーネントを使用する</span><span class="sxs-lookup"><span data-stu-id="ac146-106">Use this component</span></span>

<span data-ttu-id="ac146-107">このコンポーネントは、独自のダイアログボックスを構成する代わりに、ファイルを選択するための簡単なソリューションとして、Windows ベースのアプリケーション内で使用します。</span><span class="sxs-lookup"><span data-stu-id="ac146-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="ac146-108">Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac146-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="ac146-109">ただし、<xref:System.Windows.Forms.OpenFileDialog> コンポーネントを使用する場合は、独自のファイルオープンロジックを作成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="ac146-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>

<span data-ttu-id="ac146-110">実行時にダイアログを表示するには、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac146-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="ac146-111">ユーザーが <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> プロパティを使用して開くファイルを複数選択できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac146-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="ac146-112">また、<xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> プロパティを使用して、ダイアログボックスに読み取り専用チェックボックスが表示されるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="ac146-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="ac146-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> プロパティは、[読み取り専用] チェックボックスがオンになっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ac146-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="ac146-114">最後に、<xref:System.Windows.Forms.FileDialog.Filter%2A> プロパティは、ダイアログボックスの [ファイルの種類] ボックスに表示される選択を決定する、現在のファイル名のフィルター文字列を設定します。</span><span class="sxs-lookup"><span data-stu-id="ac146-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>

<span data-ttu-id="ac146-115">フォームに追加されると、Visual Studio の Windows フォームデザイナーの下部にあるトレイに <xref:System.Windows.Forms.OpenFileDialog> コンポーネントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac146-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac146-116">参照</span><span class="sxs-lookup"><span data-stu-id="ac146-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="ac146-117">OpenFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ac146-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
