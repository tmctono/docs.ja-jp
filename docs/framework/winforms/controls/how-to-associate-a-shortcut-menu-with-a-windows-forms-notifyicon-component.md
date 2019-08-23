---
title: '方法: ショートカット メニューを Windows フォーム NotifyIcon コンポーネントに関連付ける'
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
ms.openlocfilehash: bf5602d0526fdd97f0cc14382339095a793f13c3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922764"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a><span data-ttu-id="5f0fb-102">方法: ショートカット メニューを Windows フォーム NotifyIcon コンポーネントに関連付ける</span><span class="sxs-lookup"><span data-stu-id="5f0fb-102">How to: Associate a Shortcut Menu with a Windows Forms NotifyIcon Component</span></span>
> [!NOTE]
> <span data-ttu-id="5f0fb-103"><xref:System.Windows.Forms.MainMenu> とは、<xref:System.Windows.Forms.ContextMenu>以前のバージョン<xref:System.Windows.Forms.MainMenu>のとのコントロールに置き換えて機能を追加しますが、を選択した場合は、下位互換性と将来の使用の両方で保持されます。<xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.MenuStrip></span><span class="sxs-lookup"><span data-stu-id="5f0fb-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="5f0fb-104">コンポーネント<xref:System.Windows.Forms.NotifyIcon>は、タスクバーの状態通知領域にアイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-104">The <xref:System.Windows.Forms.NotifyIcon> component displays an icon in the status notification area of the taskbar.</span></span> <span data-ttu-id="5f0fb-105">一般的に、アプリケーションでは、このアイコンを右クリックして、表示されるアプリケーションにコマンドを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-105">Commonly, applications enable you to right-click this icon to send commands to the application it represents.</span></span> <span data-ttu-id="5f0fb-106">コンポーネントを<xref:System.Windows.Forms.NotifyIcon>コンポーネント<xref:System.Windows.Forms.ContextMenu>に関連付けることによって、この機能をアプリケーションに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-106">By associating a <xref:System.Windows.Forms.ContextMenu> component with the <xref:System.Windows.Forms.NotifyIcon> component, you can add this functionality to your applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f0fb-107">タスクバーに<xref:System.Windows.Forms.NotifyIcon>コンポーネントのインスタンスを表示しているときに、起動時にアプリケーションを最小化する場合は、メインフォームの<xref:System.Windows.Forms.Form.WindowState%2A>プロパティ<xref:System.Windows.Forms.NotifyIcon>を<xref:System.Windows.Forms.FormWindowState.Minimized>に設定し、コンポーネントの<xref:System.Windows.Forms.NotifyIcon.Visible%2A>プロパティを確認します。がに`true`設定されています。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-107">If you want your application to be minimized at startup while displaying an instance of the <xref:System.Windows.Forms.NotifyIcon> component in the taskbar, set the main form's <xref:System.Windows.Forms.Form.WindowState%2A> property to <xref:System.Windows.Forms.FormWindowState.Minimized> and be sure the <xref:System.Windows.Forms.NotifyIcon> component's <xref:System.Windows.Forms.NotifyIcon.Visible%2A> property is set to `true`.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a><span data-ttu-id="5f0fb-108">デザイン時にショートカットメニューを NotifyIcon コンポーネントに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="5f0fb-108">To associate a shortcut menu with the NotifyIcon component at design time</span></span>  
  
1. <span data-ttu-id="5f0fb-109">コンポーネントを<xref:System.Windows.Forms.NotifyIcon>フォームに追加し、プロパティ<xref:System.Windows.Forms.NotifyIcon.Icon%2A>や<xref:System.Windows.Forms.NotifyIcon.Visible%2A>プロパティなどの重要なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-109">Add a <xref:System.Windows.Forms.NotifyIcon> component to your form, and set the important properties, such as the <xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties.</span></span>  
  
     <span data-ttu-id="5f0fb-110">詳細については、「[方法 :Windows フォーム NotifyIcon コンポーネント](app-icons-to-the-taskbar-with-wf-notifyicon.md)を使用して、アプリケーションアイコンをタスクバーに追加します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-110">For more information, see [How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component](app-icons-to-the-taskbar-with-wf-notifyicon.md).</span></span>  
  
2. <span data-ttu-id="5f0fb-111">コンポーネントを<xref:System.Windows.Forms.ContextMenu> Windows フォームに追加します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-111">Add a <xref:System.Windows.Forms.ContextMenu> component to your Windows Form.</span></span>  
  
     <span data-ttu-id="5f0fb-112">実行時に使用できるようにするコマンドを表すメニュー項目をショートカットメニューに追加します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-112">Add menu items to the shortcut menu representing the commands you want to make available at run time.</span></span> <span data-ttu-id="5f0fb-113">これは、アクセスキーなどのメニュー項目にメニューの機能強化を追加する場合にも適しています。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-113">This is also a good time to add menu enhancements to these menu items, such as access keys.</span></span>  
  
3. <span data-ttu-id="5f0fb-114">コンポーネントのプロパティを、追加したショートカットメニューに設定します。 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> <xref:System.Windows.Forms.NotifyIcon></span><span class="sxs-lookup"><span data-stu-id="5f0fb-114">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="5f0fb-115">このプロパティを設定すると、タスクバーのアイコンがクリックされたときにショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-115">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a><span data-ttu-id="5f0fb-116">プログラムによってショートカットメニューを NotifyIcon コンポーネントに関連付けるには</span><span class="sxs-lookup"><span data-stu-id="5f0fb-116">To associate a shortcut menu with the NotifyIcon component programmatically</span></span>  
  
1. <span data-ttu-id="5f0fb-117"><xref:System.Windows.Forms.NotifyIcon>クラスのインスタンス<xref:System.Windows.Forms.ContextMenu>とクラスを作成します。このとき、アプリケーションに必要なプロパティ設定<xref:System.Windows.Forms.NotifyIcon> (<xref:System.Windows.Forms.NotifyIcon.Icon%2A>および<xref:System.Windows.Forms.NotifyIcon.Visible%2A>コンポーネントのプロパティ、メニュー項目<xref:System.Windows.Forms.ContextMenu> 、コンポーネント)。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-117">Create an instance of the <xref:System.Windows.Forms.NotifyIcon> class and a <xref:System.Windows.Forms.ContextMenu> class, with whatever property settings are necessary for the application (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> and <xref:System.Windows.Forms.NotifyIcon.Visible%2A> properties for the <xref:System.Windows.Forms.NotifyIcon> component, menu items for the <xref:System.Windows.Forms.ContextMenu> component).</span></span>  
  
2. <span data-ttu-id="5f0fb-118">コンポーネントのプロパティを、追加したショートカットメニューに設定します。 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> <xref:System.Windows.Forms.NotifyIcon></span><span class="sxs-lookup"><span data-stu-id="5f0fb-118">Set the <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> property of the <xref:System.Windows.Forms.NotifyIcon> component to the shortcut menu that you added.</span></span>  
  
     <span data-ttu-id="5f0fb-119">このプロパティを設定すると、タスクバーのアイコンがクリックされたときにショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-119">With this property set, the shortcut menu will be displayed when the icon on the taskbar is clicked.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="5f0fb-120">次のコード例では、基本的なメニュー構造を作成します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-120">The following code example creates a basic menu structure.</span></span> <span data-ttu-id="5f0fb-121">メニューの選択肢は、開発中のアプリケーションに適したものにカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-121">You will need to customize the menu choices to those that fit the application you are developing.</span></span> <span data-ttu-id="5f0fb-122">また、これらのメニュー項目の<xref:System.Windows.Forms.MenuItem.Click>イベントを処理するコードを記述することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-122">Additionally, you will want to write code to handle the <xref:System.Windows.Forms.MenuItem.Click> events for these menu items.</span></span>  
  
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
> <span data-ttu-id="5f0fb-123">を初期化`notifyIcon1` `contextMenu1,`する必要があります。これを行うには、フォームのコンストラクターに次のステートメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5f0fb-123">You must initialize `notifyIcon1` and `contextMenu1,` which you can do by including the following statements in the constructor of your form:</span></span>  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f0fb-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="5f0fb-124">See also</span></span>

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [<span data-ttu-id="5f0fb-125">方法: Windows フォーム NotifyIcon コンポーネントを使用してアプリケーションアイコンをタスクバーに追加する</span><span class="sxs-lookup"><span data-stu-id="5f0fb-125">How to: Add Application Icons to the TaskBar with the Windows Forms NotifyIcon Component</span></span>](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [<span data-ttu-id="5f0fb-126">NotifyIcon コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5f0fb-126">NotifyIcon Component</span></span>](notifyicon-component-windows-forms.md)
- [<span data-ttu-id="5f0fb-127">NotifyIcon コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="5f0fb-127">NotifyIcon Component Overview</span></span>](notifyicon-component-overview-windows-forms.md)
