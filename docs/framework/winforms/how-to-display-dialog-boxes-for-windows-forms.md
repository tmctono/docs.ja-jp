---
title: '方法: Windows フォームのダイアログ ボックスを表示する'
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
ms.openlocfilehash: b99f2273dae88faf86448da6e1d2986a83803abf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61802584"
---
# <a name="how-to-display-dialog-boxes-for-windows-forms"></a><span data-ttu-id="242ca-102">方法: Windows フォームのダイアログ ボックスを表示する</span><span class="sxs-lookup"><span data-stu-id="242ca-102">How to: Display Dialog Boxes for Windows Forms</span></span>
<span data-ttu-id="242ca-103">同様に、アプリケーションでその他の形式を表示するには、ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="242ca-103">You display a dialog box in the same way you display any other form in an application.</span></span> <span data-ttu-id="242ca-104">スタートアップ フォームは、アプリケーションの実行時に自動的に読み込みます。</span><span class="sxs-lookup"><span data-stu-id="242ca-104">The startup form loads automatically when the application is run.</span></span> <span data-ttu-id="242ca-105">2 番目のフォームまたはダイアログ ボックスをアプリケーションで表示するために、読み込む、表示するコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="242ca-105">To make a second form or dialog box appear in the application, write code to load and display it.</span></span> <span data-ttu-id="242ca-106">同様に、フォームまたはダイアログ ボックスを非アンロードしたり非表示にするコードを記述します。</span><span class="sxs-lookup"><span data-stu-id="242ca-106">Similarly, to make the form or dialog box disappear, write code to unload or hide it.</span></span>  
  
### <a name="to-display-a-dialog-box"></a><span data-ttu-id="242ca-107">ダイアログ ボックスを表示するには</span><span class="sxs-lookup"><span data-stu-id="242ca-107">To display a dialog box</span></span>  
  
1. <span data-ttu-id="242ca-108">ダイアログ ボックスを開くイベント ハンドラーに移動します。</span><span class="sxs-lookup"><span data-stu-id="242ca-108">Navigate to the event handler with which you want to open the dialog box.</span></span> <span data-ttu-id="242ca-109">これは、ボタンがクリックされたときに、メニュー コマンドが選択した場合、または他のイベントが発生したときに発生することができます。</span><span class="sxs-lookup"><span data-stu-id="242ca-109">This can happen when a menu command is selected, when a button is clicked, or when any other event occurs.</span></span>  
  
2. <span data-ttu-id="242ca-110">イベント ハンドラーでは、ダイアログ ボックスを開くコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="242ca-110">In the event handler, add code to open the dialog box.</span></span> <span data-ttu-id="242ca-111">この例では、ボタン クリック イベントを使用して、ダイアログ ボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="242ca-111">In this example, a button-click event is used to show the dialog box:</span></span>  
  
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
