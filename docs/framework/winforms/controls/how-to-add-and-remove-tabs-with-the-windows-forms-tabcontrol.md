---
title: '方法: Windows フォーム TabControl のタブを追加および削除する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 938f1210eaa3479822e752327123737a3286fe9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624059"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="41e03-102">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="41e03-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="41e03-103">既定で、<xref:System.Windows.Forms.TabControl>コントロールでは、2 つ含まれている<xref:System.Windows.Forms.TabPage>コントロール。</span><span class="sxs-lookup"><span data-stu-id="41e03-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="41e03-104">を通じてこれらのタブにアクセスすることができます、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="41e03-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="41e03-105">プログラムでタブを追加するには</span><span class="sxs-lookup"><span data-stu-id="41e03-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="41e03-106">使用して、<xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>のメソッド、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="41e03-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="41e03-107">プログラムにより、タブを削除するには</span><span class="sxs-lookup"><span data-stu-id="41e03-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="41e03-108">選択したタブを削除するを使用して、<xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A>のメソッド、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="41e03-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="41e03-109">- または -</span><span class="sxs-lookup"><span data-stu-id="41e03-109">-or-</span></span>  
  
- <span data-ttu-id="41e03-110">すべてのタブを削除するには、使用、<xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A>のメソッド、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="41e03-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="41e03-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="41e03-111">See also</span></span>

- [<span data-ttu-id="41e03-112">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="41e03-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="41e03-113">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="41e03-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="41e03-114">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="41e03-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="41e03-115">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="41e03-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
