---
title: '方法: ダイアログ ボックスの結果を返す'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: b574a5bbc08d947371837116915c2fc8c13ec81d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62006709"
---
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="37d57-102">方法: ダイアログ ボックスの結果を返す</span><span class="sxs-lookup"><span data-stu-id="37d57-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="37d57-103">この例は、呼び出すことによって開かれたウィンドウのダイアログの結果を取得する方法を示します<xref:System.Windows.Window.ShowDialog%2A>します。</span><span class="sxs-lookup"><span data-stu-id="37d57-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37d57-104">例</span><span class="sxs-lookup"><span data-stu-id="37d57-104">Example</span></span>  
 <span data-ttu-id="37d57-105">ダイアログ ボックスを閉じる前にその<xref:System.Windows.Window.DialogResult%2A>でプロパティを設定する必要があります、 <xref:System.Nullable%601> <xref:System.Boolean>ユーザーがダイアログ ボックスを閉じた方法を示します。</span><span class="sxs-lookup"><span data-stu-id="37d57-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="37d57-106">この値がによって返される<xref:System.Windows.Window.ShowDialog%2A> ダイアログ ボックスが閉じられた方法と、その結果、結果を処理する方法を決定するクライアント コードを許可します。</span><span class="sxs-lookup"><span data-stu-id="37d57-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37d57-107"><xref:System.Windows.Window.DialogResult%2A> 呼び出すことによって、ウィンドウが開かれた場合にのみ設定できます<xref:System.Windows.Window.ShowDialog%2A>します。</span><span class="sxs-lookup"><span data-stu-id="37d57-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="37d57-108">.NET Framework セキュリティ</span><span class="sxs-lookup"><span data-stu-id="37d57-108">.NET Framework Security</span></span>  
 <span data-ttu-id="37d57-109">呼び出す<xref:System.Windows.Window.ShowDialog%2A>すべての windows と無制限のユーザー入力イベントを使用する権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="37d57-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
