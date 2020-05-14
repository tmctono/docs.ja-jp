---
title: '方法: ダイアログ ボックスを開く'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947707"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="7a0a3-102">方法: ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="7a0a3-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="7a0a3-103">この例では、ダイアログ ボックスを開く方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7a0a3-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a0a3-104">例</span><span class="sxs-lookup"><span data-stu-id="7a0a3-104">Example</span></span>  
 <span data-ttu-id="7a0a3-105">ダイアログ ボックスはウィンドウであり、<xref:System.Windows.Window> をインスタンス化して <xref:System.Windows.Window.ShowDialog%2A> メソッドを呼び出すことにより開かれます。</span><span class="sxs-lookup"><span data-stu-id="7a0a3-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="7a0a3-106"><xref:System.Windows.Window.ShowDialog%2A> では、ウィンドウが開かれた後、新しいダイアログ ボックスが閉じられるまでは制御は戻りません。</span><span class="sxs-lookup"><span data-stu-id="7a0a3-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="7a0a3-107">この種のウィンドウは "*モーダル*" ウィンドウとも呼ばれ、ユーザーの入力が制限されます。</span><span class="sxs-lookup"><span data-stu-id="7a0a3-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="7a0a3-108">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="7a0a3-108">.NET Framework Security</span></span>  
 <span data-ttu-id="7a0a3-109"><xref:System.Windows.Window.ShowDialog%2A> を呼び出すには、すべてのウィンドウとユーザー入力イベントを無制限に使用するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="7a0a3-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a0a3-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="7a0a3-110">See also</span></span>

- [<span data-ttu-id="7a0a3-111">ダイアログ ボックスの結果を返す</span><span class="sxs-lookup"><span data-stu-id="7a0a3-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
