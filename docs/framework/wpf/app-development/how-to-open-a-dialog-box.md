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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947707"
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="1dfd9-102">方法: ダイアログ ボックスを開く</span><span class="sxs-lookup"><span data-stu-id="1dfd9-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="1dfd9-103">この例では、ダイアログ ボックスを開く方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1dfd9-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dfd9-104">例</span><span class="sxs-lookup"><span data-stu-id="1dfd9-104">Example</span></span>  
 <span data-ttu-id="1dfd9-105">ダイアログ ボックスがインスタンス化によって開かれたウィンドウ<xref:System.Windows.Window>を呼び出すと、<xref:System.Windows.Window.ShowDialog%2A>メソッド。</span><span class="sxs-lookup"><span data-stu-id="1dfd9-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="1dfd9-106"><xref:System.Windows.Window.ShowDialog%2A> ウィンドウが開き、新しいダイアログ ボックスが閉じられたまで返されません。</span><span class="sxs-lookup"><span data-stu-id="1dfd9-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="1dfd9-107">この種類のウィンドウとも呼ばれますが、*モーダル*ウィンドウで、し、ユーザー入力を制限します。</span><span class="sxs-lookup"><span data-stu-id="1dfd9-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="1dfd9-108">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="1dfd9-108">.NET Framework Security</span></span>  
 <span data-ttu-id="1dfd9-109">呼び出す<xref:System.Windows.Window.ShowDialog%2A>すべての windows と無制限のユーザー入力イベントを使用する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="1dfd9-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dfd9-110">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dfd9-110">See also</span></span>

- [<span data-ttu-id="1dfd9-111">ダイアログ ボックスの結果を返す</span><span class="sxs-lookup"><span data-stu-id="1dfd9-111">Return a Dialog Box Result</span></span>](how-to-return-a-dialog-box-result.md)
