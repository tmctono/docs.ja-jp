---
title: '[方法] ダイアログ ボックスを表示する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, displaying
- Windows Forms dialog boxes [Windows Forms], displaying
- Windows Forms, calling one form from another
- dialog boxes [Windows Forms], displaying for Windows Forms
ms.assetid: aaac1b38-c651-495a-8d3d-5a9bfb32fee3
ms.openlocfilehash: 3625080c7c322e297a9de92e4f95a40c0caf3e72
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181970"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="23f05-102">方法 : Windows フォームのダイアログ ボックスを表示する</span><span class="sxs-lookup"><span data-stu-id="23f05-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="23f05-103">ダイアログ ボックスは、アプリケーションで他のフォームを表示する場合と同じ方法で表示します。</span><span class="sxs-lookup"><span data-stu-id="23f05-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="23f05-104">アプリケーションの実行時にスタートアップ フォームが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="23f05-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="23f05-105">アプリケーションに 2 番目のフォームまたはダイアログ ボックスを表示するには、読み込んで表示するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="23f05-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="23f05-106">同様に、フォームまたはダイアログ ボックスを非表示にするには、アンロードまたは非表示にするコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="23f05-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="23f05-107">ダイアログ ボックスを表示するには</span><span class="sxs-lookup"><span data-stu-id="23f05-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="23f05-108">ダイアログ ボックスを開くイベント ハンドラーに移動します。</span><span class="sxs-lookup"><span data-stu-id="23f05-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="23f05-109">これは、メニュー コマンドが選択されたとき、ボタンがクリックされたとき、またはその他のイベントが発生したときに発生します。</span><span class="sxs-lookup"><span data-stu-id="23f05-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="23f05-110">イベント ハンドラーで、ダイアログ ボックスを開くコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="23f05-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="23f05-111">この例では、ボタンクリックイベントを使用してダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="23f05-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim dlg1 as new Form()  
       dlg1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)
    {  
       Form dlg1 = new Form();  
       dlg1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:
      void button1_Click(System::Object ^ sender,  
        System::EventArgs ^ e)  
      {  
        Form ^ dlg1 = gcnew Form();  
        dlg1->ShowDialog();  
      }  
    ```
