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
ms.openlocfilehash: 723e05803b1f7d2bc56476248987085dbe5e23f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011113"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="edb46-102">方法: Windows フォーム TabControl のタブを追加および削除する</span><span class="sxs-lookup"><span data-stu-id="edb46-102">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="edb46-103">既定で、<xref:System.Windows.Forms.TabControl>コントロールでは、2 つ含まれている<xref:System.Windows.Forms.TabPage>コントロール。</span><span class="sxs-lookup"><span data-stu-id="edb46-103">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="edb46-104">を通じてこれらのタブにアクセスすることができます、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="edb46-104">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="edb46-105">プログラムでタブを追加するには</span><span class="sxs-lookup"><span data-stu-id="edb46-105">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="edb46-106">使用して、<xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A>のメソッド、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="edb46-106">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="edb46-107">プログラムにより、タブを削除するには</span><span class="sxs-lookup"><span data-stu-id="edb46-107">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="edb46-108">選択したタブを削除するを使用して、<xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A>のメソッド、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="edb46-108">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="edb46-109">- または -</span><span class="sxs-lookup"><span data-stu-id="edb46-109">-or-</span></span>  
  
- <span data-ttu-id="edb46-110">すべてのタブを削除するには、使用、<xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A>のメソッド、<xref:System.Windows.Forms.TabControl.TabPages%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="edb46-110">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="edb46-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="edb46-111">See also</span></span>

- [<span data-ttu-id="edb46-112">TabControl コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="edb46-112">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="edb46-113">方法: タブ ページにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="edb46-113">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="edb46-114">方法: タブ ページを無効にします。</span><span class="sxs-lookup"><span data-stu-id="edb46-114">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="edb46-115">方法: Windows フォーム TabControl の外観を変更します。</span><span class="sxs-lookup"><span data-stu-id="edb46-115">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
