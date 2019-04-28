---
title: SaveFileDialog コンポーネントの概要 (Windows フォーム)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: b06c4d510cefdc7558944995594fd209b6121cb1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904671"
---
# <a name="savefiledialog-component-overview-windows-forms"></a><span data-ttu-id="f9883-102">SaveFileDialog コンポーネントの概要 (Windows フォーム)</span><span class="sxs-lookup"><span data-stu-id="f9883-102">SaveFileDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="f9883-103">Windows フォームの <xref:System.Windows.Forms.SaveFileDialog> コンポーネントは、事前構成済みのダイアログ ボックスです。</span><span class="sxs-lookup"><span data-stu-id="f9883-103">The Windows Forms <xref:System.Windows.Forms.SaveFileDialog> component is a pre-configured dialog box.</span></span> <span data-ttu-id="f9883-104">これは、標準と同じ**ファイルを保存**Windows で使用されるダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f9883-104">It is the same as the standard **Save File** dialog box used by Windows.</span></span> <span data-ttu-id="f9883-105">これは、<xref:System.Windows.Forms.CommonDialog> クラスを継承しています。</span><span class="sxs-lookup"><span data-stu-id="f9883-105">It inherits from the <xref:System.Windows.Forms.CommonDialog> class.</span></span>  
  
## <a name="working-with-the-savefiledialog-component"></a><span data-ttu-id="f9883-106">SaveFileDialog コンポーネントの操作</span><span class="sxs-lookup"><span data-stu-id="f9883-106">Working with the SaveFileDialog Component</span></span>  
 <span data-ttu-id="f9883-107">ダイアログ ボックスを構成する代わりにファイルを保存するユーザーを有効にするための単純なソリューションとして使用します。</span><span class="sxs-lookup"><span data-stu-id="f9883-107">Use it as a simple solution for enabling users to save files instead of configuring your own dialog box.</span></span> <span data-ttu-id="f9883-108">標準の Windows ダイアログ ボックスで証明書利用者では、作成したアプリケーションの基本的な機能はすぐに、ユーザーにとって馴染み深いです。</span><span class="sxs-lookup"><span data-stu-id="f9883-108">By relying on standard Windows dialog boxes, the basic functionality of applications you create is immediately familiar to users.</span></span> <span data-ttu-id="f9883-109">ただし、時に使用して、<xref:System.Windows.Forms.SaveFileDialog>コンポーネント、独自のファイルの保存ロジックを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9883-109">Be aware, however, that when using the <xref:System.Windows.Forms.SaveFileDialog> component, you must write your own file-saving logic.</span></span>  
  
 <span data-ttu-id="f9883-110">使用することができます、<xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>メソッドを実行時にダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f9883-110">You can use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box at run time.</span></span> <span data-ttu-id="f9883-111">読み取り/書き込みモードを使用してファイルを開くことができます、<xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="f9883-111">You can open a file in read/write mode using the <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method.</span></span>  
  
 <span data-ttu-id="f9883-112">フォームに追加されたとき、<xref:System.Windows.Forms.SaveFileDialog>コンポーネント、Windows フォーム デザイナーの下部にあるトレイに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9883-112">When it is added to a form, the <xref:System.Windows.Forms.SaveFileDialog> component appears in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9883-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9883-113">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="f9883-114">SaveFileDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f9883-114">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)
