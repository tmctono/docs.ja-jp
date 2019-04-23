---
title: '方法: Windows フォームの NotifyIcon コンポーネントによってタスクバーにアプリケーション アイコンを追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TrayIcon
helpviewer_keywords:
- status area icons
- icons [Windows Forms], adding to taskbar
- NotifyIcon component
- taskbar [Windows Forms], adding icons
ms.assetid: d28c0fe6-aaf2-4df7-ad74-928d861a8510
ms.openlocfilehash: 52c18b959361079aac6b95dc5d4584bf464a306a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304520"
---
# <a name="how-to-add-application-icons-to-the-taskbar-with-the-windows-forms-notifyicon-component"></a><span data-ttu-id="f6d2a-102">方法: Windows フォームの NotifyIcon コンポーネントによってタスクバーにアプリケーション アイコンを追加する</span><span class="sxs-lookup"><span data-stu-id="f6d2a-102">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>
<span data-ttu-id="f6d2a-103">Windows フォーム<xref:System.Windows.Forms.NotifyIcon>コンポーネントは、タスク バーの状態通知領域に 1 つのアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-103">The Windows Forms <xref:System.Windows.Forms.NotifyIcon> component displays a single icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="f6d2a-104">を、ステータス領域に複数のアイコンを表示するには、複数がする必要があります<xref:System.Windows.Forms.NotifyIcon>フォーム上のコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-104">To display multiple icons in the status area, you must have multiple <xref:System.Windows.Forms.NotifyIcon> components on your form.</span></span> <span data-ttu-id="f6d2a-105">コントロールに表示されるアイコンを設定するには、使用、<xref:System.Windows.Forms.NotifyIcon.Icon%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-105">To set the icon displayed for a control, use the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="f6d2a-106">コードを記述することも、<xref:System.Windows.Forms.NotifyIcon.DoubleClick>ユーザー アイコンをダブルクリックしたときの動作のためのイベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-106">You can also write code in the <xref:System.Windows.Forms.NotifyIcon.DoubleClick> event handler so that something happens when the user double-clicks the icon.</span></span> <span data-ttu-id="f6d2a-107">たとえば、アイコンで表される、バック グラウンド プロセスを構成するユーザーの表示 ダイアログ ボックスを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-107">For example, you could make a dialog box appear for the user to configure the background process represented by the icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6d2a-108"><xref:System.Windows.Forms.NotifyIcon>コンポーネントは、通知の目的でのみ、アクションまたはイベントが発生したアラートのユーザーに使用または何らかのステータスの変更が発生しました。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-108">The <xref:System.Windows.Forms.NotifyIcon> component is used for notification purposes only, to alert users that an action or event has occurred or there has been a change in status of some sort.</span></span> <span data-ttu-id="f6d2a-109">によるアプリケーションの標準的な操作のメニューのツールバー、およびその他のユーザー インターフェイス要素を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-109">You should use menus, toolbars, and other user-interface elements for standard interaction with applications.</span></span>  
  
### <a name="to-set-the-icon"></a><span data-ttu-id="f6d2a-110">アイコンを設定するには</span><span class="sxs-lookup"><span data-stu-id="f6d2a-110">To set the icon</span></span>  
  
1. <span data-ttu-id="f6d2a-111">値を割り当てる、<xref:System.Windows.Forms.NotifyIcon.Icon%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-111">Assign a value to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property.</span></span> <span data-ttu-id="f6d2a-112">値型でなければなりません`System.Drawing.Icon`.ico ファイルから読み込むことができるとします。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-112">The value must be of type `System.Drawing.Icon` and can be loaded from an .ico file.</span></span> <span data-ttu-id="f6d2a-113">コードで、または、省略記号ボタンをクリックして、アイコン ファイルを指定できます (![VisualStudioEllipsesButton スクリーン ショット](../media/vbellipsesbutton.png "vbEllipsesButton")) 横に、<xref:System.Windows.Forms.NotifyIcon.Icon%2A>プロパティ、 **プロパティ**ウィンドウとでファイルを選択し、**オープン**表示されるダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-113">You can specify the icon file in code or by clicking the ellipsis button (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> property in the **Properties** window, and then selecting the file in the **Open** dialog box that appears.</span></span>  
  
2. <span data-ttu-id="f6d2a-114"><xref:System.Windows.Forms.NotifyIcon.Visible%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-114">Set the <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property to `true`.</span></span>  
  
3. <span data-ttu-id="f6d2a-115">設定、<xref:System.Windows.Forms.NotifyIcon.Text%2A>プロパティを適切なツールヒント文字列。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-115">Set the <xref:System.Windows.Forms.NotifyIcon.Text%2A> property to an appropriate ToolTip string.</span></span>  
  
     <span data-ttu-id="f6d2a-116">アイコンの場所は次のコード例で、パスが設定、 **My Documents**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-116">In the following code example, the path set for the location of the icon is the **My Documents** folder.</span></span> <span data-ttu-id="f6d2a-117">この場所は、Windows オペレーティング システムを実行しているほとんどのコンピューターにはでこのフォルダーが含まれていると想定できるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-117">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="f6d2a-118">この場所を選択すると、ユーザーは最小限のシステム アクセスのレベルでアプリケーションを安全に実行もできます。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-118">Choosing this location also enables users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="f6d2a-119">次の例では、使用して、フォームが必要です、<xref:System.Windows.Forms.NotifyIcon>コントロールが既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-119">The following example requires a form with a <xref:System.Windows.Forms.NotifyIcon> control already added.</span></span> <span data-ttu-id="f6d2a-120">という名前のアイコン ファイルも必要があります。`Icon.ico`します。</span><span class="sxs-lookup"><span data-stu-id="f6d2a-120">It also requires an icon file named `Icon.ico`.</span></span>  
  
    ```vb  
    ' You should replace the bold icon in the sample below  
    ' with an icon of your own choosing.  
    NotifyIcon1.Icon = New _   
       System.Drawing.Icon(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Icon.ico")  
    NotifyIcon1.Visible = True  
    NotifyIcon1.Text = "Antivirus program"  
    ```  
  
    ```csharp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    notifyIcon1.Icon =   
       new System.Drawing.Icon (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Icon.ico");  
    notifyIcon1.Visible = true;  
    notifyIcon1.Text = "Antivirus program";  
    ```  
  
    ```cpp  
    // You should replace the bold icon in the sample below  
    // with an icon of your own choosing.  
    notifyIcon1->Icon = gcnew   
       System::Drawing::Icon(String::Concat  
       (System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Icon.ico"));  
    notifyIcon1->Visible = true;  
    notifyIcon1->Text = "Antivirus program";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f6d2a-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6d2a-121">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="f6d2a-122">方法: ショートカット メニューを Windows フォームの NotifyIcon コンポーネントに関連付ける</span><span class="sxs-lookup"><span data-stu-id="f6d2a-122">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>](how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component.md)
- [<span data-ttu-id="f6d2a-123">NotifyIcon コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6d2a-123">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="f6d2a-124">NotifyIcon コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="f6d2a-124">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
