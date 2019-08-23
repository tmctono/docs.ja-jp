---
title: '方法: ダイアログ ボックスの結果を返す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968230"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="37c88-102">方法: ダイアログ ボックスの結果を返す</span><span class="sxs-lookup"><span data-stu-id="37c88-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="37c88-103">この例では、を呼び出す<xref:System.Windows.Window.ShowDialog%2A>ことによって開かれたウィンドウのダイアログの結果を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37c88-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37c88-104">例</span><span class="sxs-lookup"><span data-stu-id="37c88-104">Example</span></span>  
 <span data-ttu-id="37c88-105">ダイアログボックスを閉じる前に、 <xref:System.Windows.Window.DialogResult%2A>ユーザーがダイアログボックスを閉じ<xref:System.Nullable%601>た方法を示すを<xref:System.Boolean>使用して、プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="37c88-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="37c88-106">この値は、に<xref:System.Windows.Window.ShowDialog%2A>よって返されます。これにより、クライアントコードは、ダイアログボックスの終了方法、および結果の処理方法を決定できます。</span><span class="sxs-lookup"><span data-stu-id="37c88-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37c88-107"><xref:System.Windows.Window.DialogResult%2A>を呼び出す<xref:System.Windows.Window.ShowDialog%2A>ことによってウィンドウが開かれた場合にのみ設定できます。</span><span class="sxs-lookup"><span data-stu-id="37c88-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="37c88-108">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="37c88-108">.NET Framework Security</span></span>  
 <span data-ttu-id="37c88-109">を<xref:System.Windows.Window.ShowDialog%2A>呼び出すには、制限なしですべての windows およびユーザー入力イベントを使用するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="37c88-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
