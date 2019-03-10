---
title: '方法: Windows フォーム アプリケーションでフォント パターンの変更に応答します。'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: 4c34a65ed8ddabfb99451e055048502cb7617e4f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715972"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="f29cf-102">方法: Windows フォーム アプリケーションでフォント パターンの変更に応答します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="f29cf-103">Windows オペレーティング システムでは、ユーザーが表示される既定のフォントのサイズを変更するシステム全体のフォント設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="f29cf-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="f29cf-104">これらのフォント設定を変更することは、視覚障害のある、各自の画面にテキストを読み取るより大きい型を必要とするユーザーにとって重要です。</span><span class="sxs-lookup"><span data-stu-id="f29cf-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="f29cf-105">フォントの設定を変更するたびに、フォームと含まれているすべてのテキストのサイズを増減してこれらの変更に対応するため、Windows フォーム アプリケーションを調整することができます。</span><span class="sxs-lookup"><span data-stu-id="f29cf-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="f29cf-106">フォント サイズの変更を動的に対応するために、フォームを設定する場合は、フォームにコードを追加できます。</span><span class="sxs-lookup"><span data-stu-id="f29cf-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="f29cf-107">通常、Windows フォームで使用される既定のフォントは、によって返されるフォント、<xref:Microsoft.Win32>名前空間の呼び出し`GetStockObject(DEFAULT_GUI_FONT)`します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="f29cf-108">この呼び出しによって返されたフォントは、画面の解像度が変更されたときにのみ変更します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="f29cf-109">コードの既定のフォントを変更する必要があります、次の手順に示すように<xref:System.Drawing.SystemFonts.IconTitleFont%2A>フォント サイズの変更に応答します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="f29cf-110">デスクトップのフォントを使用して、フォント パターンの変更に応答するには</span><span class="sxs-lookup"><span data-stu-id="f29cf-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1.  <span data-ttu-id="f29cf-111">フォームを作成し、目的のコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="f29cf-112">詳細については、「[方法 :コマンドラインから Windows フォーム アプリケーションを作成](how-to-create-a-windows-forms-application-from-the-command-line.md)と[Windows フォームで使用するコントロール](./controls/controls-to-use-on-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="f29cf-113">参照を追加、<xref:Microsoft.Win32>をコードに名前空間。</span><span class="sxs-lookup"><span data-stu-id="f29cf-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3.  <span data-ttu-id="f29cf-114">必要なイベントのハンドラーをフックし、フォームの使用中の既定のフォントを変更するのには、フォームのコンス トラクターに次のコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4.  <span data-ttu-id="f29cf-115">ハンドラーを実装、<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>イベントは、フォームを自動的にスケーリングするときに、<xref:Microsoft.Win32.UserPreferenceCategory.Window>カテゴリの変更。</span><span class="sxs-lookup"><span data-stu-id="f29cf-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5.  <span data-ttu-id="f29cf-116">最後のハンドラーを実装、<xref:System.Windows.Forms.Form.FormClosing>デタッチ イベント、<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>イベント ハンドラー。</span><span class="sxs-lookup"><span data-stu-id="f29cf-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="f29cf-117">このコードを含めないと、アプリケーションでメモリ リークが発生します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6.  <span data-ttu-id="f29cf-118">コードをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="f29cf-119">Windows XP では、フォントのスキームを手動で変更するには</span><span class="sxs-lookup"><span data-stu-id="f29cf-119">To manually change the font scheme in Windows XP</span></span>  
  
1.  <span data-ttu-id="f29cf-120">Windows デスクトップを右クリックして、Windows フォーム アプリケーションの実行中に**プロパティ**ショートカット メニューから。</span><span class="sxs-lookup"><span data-stu-id="f29cf-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="f29cf-121">**表示プロパティ**ダイアログ ボックスで、をクリックして、**外観**タブ。</span><span class="sxs-lookup"><span data-stu-id="f29cf-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3.  <span data-ttu-id="f29cf-122">**フォント サイズ**ドロップダウン リスト ボックスで、新しいフォントのサイズを選択します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="f29cf-123">フォームがデスクトップ フォント パターンの実行時の変更に反応ようになりましたことがわかります。</span><span class="sxs-lookup"><span data-stu-id="f29cf-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="f29cf-124">間、ユーザーが変更されたとき**標準**、**大きいフォント**、および**特大フォント**フォームのフォントを変更し、スケールが適切です。</span><span class="sxs-lookup"><span data-stu-id="f29cf-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f29cf-125">例</span><span class="sxs-lookup"><span data-stu-id="f29cf-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="f29cf-126">このコード例では constructer にはへの呼び出しが含まれています`InitializeComponent`、これは Visual Studio で新しい Windows フォーム プロジェクトを作成するときに定義されています。</span><span class="sxs-lookup"><span data-stu-id="f29cf-126">The constructer in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="f29cf-127">コマンドラインでアプリケーションを構築している場合は、次のコード行を削除します。</span><span class="sxs-lookup"><span data-stu-id="f29cf-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f29cf-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="f29cf-128">See also</span></span>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="f29cf-129">Windows フォームにおける自動スケーリング</span><span class="sxs-lookup"><span data-stu-id="f29cf-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
