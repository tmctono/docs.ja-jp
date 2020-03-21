---
title: ショートカット メニューを NotifyIcon コンポーネントに関連付ける
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182263"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="af33f-102">方法 : ショートカット メニューを Windows フォーム NotifyIcon コンポーネントに関連付ける</span><span class="sxs-lookup"><span data-stu-id="af33f-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="af33f-103">以前<xref:System.Windows.Forms.MenuStrip>の<xref:System.Windows.Forms.ContextMenuStrip>バージョンの<xref:System.Windows.Forms.MainMenu>コントロールと<xref:System.Windows.Forms.ContextMenu>コントロールに機能を置き換えて<xref:System.Windows.Forms.MainMenu>追加<xref:System.Windows.Forms.ContextMenu>しますが、後方互換性と将来の使用の両方を選択した場合は保持されます。</span><span class="sxs-lookup"><span data-stu-id="af33f-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="af33f-104">コンポーネント<xref:System.Windows.Forms.NotifyIcon>は、タスク バーの状態通知領域にアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="af33f-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="af33f-105">通常、アプリケーションでは、このアイコンを右クリックして、それが表すアプリケーションにコマンドを送信できます。</span><span class="sxs-lookup"><span data-stu-id="af33f-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="af33f-106"><xref:System.Windows.Forms.ContextMenu>コンポーネントを<xref:System.Windows.Forms.NotifyIcon>コンポーネントに関連付けることで、この機能をアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="af33f-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af33f-107">タスク バーに<xref:System.Windows.Forms.NotifyIcon>コンポーネントのインスタンスを表示しながら起動時にアプリケーションを最小化する場合は、メイン フォームの<xref:System.Windows.Forms.Form.WindowState%2A>プロパティを に<xref:System.Windows.Forms.FormWindowState.Minimized>設定し、<xref:System.Windows.Forms.NotifyIcon>コンポーネントの<xref:System.Windows.Forms.NotifyIcon.Visible%2A>プロパティが に`true`設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="af33f-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="af33f-108">デザイン時にショートカット メニューを NotifyIcon コンポーネントに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="af33f-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="af33f-109">フォームに<xref:System.Windows.Forms.NotifyIcon>コンポーネントを追加し、 プロパティや プロパティなどの重要なプロパティ<xref:System.Windows.Forms.NotifyIcon.Icon%2A>を<xref:System.Windows.Forms.NotifyIcon.Visible%2A>設定します。</span><span class="sxs-lookup"><span data-stu-id="af33f-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="af33f-110">詳細については、「[方法 : Windows フォームの NotifyIcon コンポーネントを使用してタスク バーにアプリケーション アイコンを追加](app-icons-to-the-taskbar-with-wf-notifyicon.md)する 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af33f-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="af33f-111">コンポーネントを<xref:System.Windows.Forms.ContextMenu>Windows フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="af33f-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="af33f-112">実行時に使用できるようにするコマンドを表すメニュー項目をショートカット メニューに追加します。</span><span class="sxs-lookup"><span data-stu-id="af33f-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="af33f-113">また、アクセス キーなどのメニュー項目にメニューの機能強化を追加する場合にも適しています。</span><span class="sxs-lookup"><span data-stu-id="af33f-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="af33f-114">追加した<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>ショートカット メニュー<xref:System.Windows.Forms.NotifyIcon>にコンポーネントのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="af33f-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="af33f-115">このプロパティを設定すると、タスク バーのアイコンをクリックするとショートカット メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af33f-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="af33f-116">プログラムでショートカット メニューを NotifyIcon コンポーネントに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="af33f-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="af33f-117"><xref:System.Windows.Forms.NotifyIcon>アプリケーションに必要な<xref:System.Windows.Forms.ContextMenu>プロパティ設定 (<xref:System.Windows.Forms.NotifyIcon.Icon%2A><xref:System.Windows.Forms.NotifyIcon.Visible%2A><xref:System.Windows.Forms.NotifyIcon>およびコンポーネントのプロパティ、コンポーネントのメニュー項目) を使用して、クラスとクラスのインスタンスを<xref:System.Windows.Forms.ContextMenu>作成します。</span><span class="sxs-lookup"><span data-stu-id="af33f-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="af33f-118">追加した<xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A>ショートカット メニュー<xref:System.Windows.Forms.NotifyIcon>にコンポーネントのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="af33f-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="af33f-119">このプロパティを設定すると、タスク バーのアイコンをクリックするとショートカット メニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af33f-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="af33f-120">基本的なメニュー構造を作成するコード例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="af33f-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="af33f-121">開発中のアプリケーションに合わせてメニューの選択肢をカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="af33f-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="af33f-122">また、これらのメニュー項目の<xref:System.Windows.Forms.MenuItem.Click>イベントを処理するコードを記述する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af33f-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _
          (System.Environment.GetFolderPath _
          (System.Environment.SpecialFolder.Personal)  _
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> <span data-ttu-id="af33f-123">フォームのコンストラクター`notifyIcon1`に`contextMenu1,`次のステートメントを含めることで、初期化し、実行できる操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="af33f-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="af33f-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="af33f-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="af33f-125">方法 : Windows フォームの NotifyIcon コンポーネントによってタスクバーにアプリケーション アイコンを追加する</span><span class="sxs-lookup"><span data-stu-id="af33f-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="af33f-126">NotifyIcon コンポーネント</span><span class="sxs-lookup"><span data-stu-id="af33f-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="af33f-127">NotifyIcon コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="af33f-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
