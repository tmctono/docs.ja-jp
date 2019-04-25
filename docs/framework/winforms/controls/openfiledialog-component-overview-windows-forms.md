---
title: OpenFileDialog コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: ec275a5923d332d23205c79442fa23bc6e402e3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61804560"
---
# <a name="openfiledialog-component-overview-windows-forms"></a><span data-ttu-id="d7d06-102">OpenFileDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="d7d06-102">OpenFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="d7d06-103">Windows フォームの <xref:System.Windows.Forms.OpenFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="d7d06-103">The Windows Forms <xref:System.Windows.Forms.OpenFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="d7d06-104">これは同じ**ファイルを開く** ダイアログ ボックスが、Windows オペレーティング システムによって公開されています。</span><span class="sxs-lookup"><span data-stu-id="d7d06-104">It is the same **Open File** dialog box exposed by the Windows operating system.</span></span> <span data-ttu-id="d7d06-105">これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。</span><span class="sxs-lookup"><span data-stu-id="d7d06-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="using-this-component"></a><span data-ttu-id="d7d06-106">このコンポーネントを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7d06-106">Using this Component</span></span>  
 <span data-ttu-id="d7d06-107">簡単な解決策として、Windows ベースのアプリケーション内でこのコンポーネントを使用して、ファイル選択ダイアログ ボックスを構成する代わりにします。</span><span class="sxs-lookup"><span data-stu-id="d7d06-107">Use this component within your Windows-based application as a simple solution for file selection in lieu of configuring your own dialog box.</span></span> <span data-ttu-id="d7d06-108">Windows の標準のダイアログ ボックスを使用して、ユーザーがすぐに慣れる基本的な機能を持つアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d7d06-108">By relying on standard Windows dialog boxes, you create applications whose basic functionality is immediately familiar to users.</span></span> <span data-ttu-id="d7d06-109">ただし、時に使用して、<xref:System.Windows.Forms.OpenFileDialog>コンポーネント、独自のファイルを開くロジックを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7d06-109">Be aware, however, that when using the <xref:System.Windows.Forms.OpenFileDialog> component, you must write your own file-opening logic.</span></span>  
  
 <span data-ttu-id="d7d06-110">使用して、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッド実行時にダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="d7d06-110">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog at run time.</span></span> <span data-ttu-id="d7d06-111">ユーザーで開くファイルを複数選択を有効にすることができます、<xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="d7d06-111">You can enable users to multi-select files to be opened with the <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> property.</span></span> <span data-ttu-id="d7d06-112">また、使用することができます、<xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A>プロパティのかどうか、ダイアログ ボックスでは読み取り専用チェック ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7d06-112">Additionally, you can use the <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> property to determine if a read-only check box appears in the dialog box.</span></span> <span data-ttu-id="d7d06-113"><xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A>プロパティは読み取り専用のチェック ボックスがオンになっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d7d06-113">The <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> property indicates whether the read-only check box is selected.</span></span> <span data-ttu-id="d7d06-114">最後に、<xref:System.Windows.Forms.FileDialog.Filter%2A>プロパティ設定の現在のファイル名フィルターの文字列 ダイアログ ボックスで、"ファイルの種類 ボックスに表示される選択肢を決定します。</span><span class="sxs-lookup"><span data-stu-id="d7d06-114">Finally, the <xref:System.Windows.Forms.FileDialog.Filter%2A> property sets the current file name filter string, which determines the choices that appear in the "Files of type" box in the dialog box.</span></span>  
  
 <span data-ttu-id="d7d06-115">フォームに追加されたとき、<xref:System.Windows.Forms.OpenFileDialog>コンポーネント、Windows フォーム デザイナーの下部にあるトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7d06-115">When it is added to a form, the <xref:System.Windows.Forms.OpenFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d06-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="d7d06-116">See also</span></span>

- <xref:System.Windows.Forms.OpenFileDialog>
- [<span data-ttu-id="d7d06-117">OpenFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d7d06-117">OpenFileDialog Component</span></span>](openfiledialog-component-windows-forms.md)
