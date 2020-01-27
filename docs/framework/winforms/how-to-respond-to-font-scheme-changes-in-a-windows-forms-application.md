---
title: Windows フォームアプリでのフォントスキームの変更に応答する
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, font scheme changes
ms.assetid: 4db27702-22e7-43bf-a07d-9a004549853c
ms.openlocfilehash: e3b96139a7cfd4b268d81b1da58229527e2beb87
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739228"
---
# <a name="how-to-respond-to-font-scheme-changes-in-a-windows-forms-application"></a><span data-ttu-id="83c8b-102">方法 : Windows フォーム アプリケーションでのフォント パターンの変更に応答する</span><span class="sxs-lookup"><span data-stu-id="83c8b-102">How to: Respond to Font Scheme Changes in a Windows Forms Application</span></span>
<span data-ttu-id="83c8b-103">Windows オペレーティングシステムでは、ユーザーはシステム全体のフォント設定を変更して、既定のフォントのサイズを大きくまたは小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="83c8b-103">In the Windows operating systems, a user can change the system-wide font settings to make the default font appear larger or smaller.</span></span> <span data-ttu-id="83c8b-104">これらのフォント設定を変更することは、視覚に障碍のあるユーザーや、画面上のテキストを読み込むために大きな種類を必要とするユーザーにとって非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="83c8b-104">Changing these font settings is critical for users who are visually impaired and require larger type to read the text on their screens.</span></span> <span data-ttu-id="83c8b-105">これらの変更に対応するように Windows フォームアプリケーションを調整するには、フォントスキームが変更されたときに、フォームとすべての含まれるテキストのサイズを増減します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-105">You can adjust your Windows Forms application to react to these changes by increasing or decreasing the size of the form and all contained text whenever the font scheme changes.</span></span> <span data-ttu-id="83c8b-106">フォントサイズの変化に合わせてフォームを動的に調整するには、フォームにコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-106">If you want your form to accommodate changes in font sizes dynamically, you can add code to your form.</span></span>  
  
 <span data-ttu-id="83c8b-107">通常、Windows フォームで使用される既定のフォントは、`GetStockObject(DEFAULT_GUI_FONT)`への <xref:Microsoft.Win32> 名前空間呼び出しによって返されるフォントです。</span><span class="sxs-lookup"><span data-stu-id="83c8b-107">Typically, the default font used by Windows Forms is the font returned by the <xref:Microsoft.Win32> namespace call to `GetStockObject(DEFAULT_GUI_FONT)`.</span></span> <span data-ttu-id="83c8b-108">この呼び出しによって返されるフォントは、画面の解像度が変更された場合にのみ変更されます。</span><span class="sxs-lookup"><span data-stu-id="83c8b-108">The font returned by this call only changes when the screen resolution changes.</span></span> <span data-ttu-id="83c8b-109">次の手順に示すように、コードでは既定のフォントを <xref:System.Drawing.SystemFonts.IconTitleFont%2A> に変更して、フォントサイズの変更に応答する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83c8b-109">As shown in the following procedure, your code must change the default font to <xref:System.Drawing.SystemFonts.IconTitleFont%2A> to respond to changes in font size.</span></span>  
  
### <a name="to-use-the-desktop-font-and-respond-to-font-scheme-changes"></a><span data-ttu-id="83c8b-110">デスクトップフォントを使用してフォント設定の変更に応答するには</span><span class="sxs-lookup"><span data-stu-id="83c8b-110">To use the desktop font and respond to font scheme changes</span></span>  
  
1. <span data-ttu-id="83c8b-111">フォームを作成し、必要なコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-111">Create your form, and add the controls you want to it.</span></span> <span data-ttu-id="83c8b-112">詳細については、「[方法: コマンドラインから Windows フォームアプリケーションを作成](how-to-create-a-windows-forms-application-from-the-command-line.md)する」および「 [Windows フォームで使用するコントロール](./controls/controls-to-use-on-windows-forms.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="83c8b-112">For more information, see [How to: Create a Windows Forms Application from the Command Line](how-to-create-a-windows-forms-application-from-the-command-line.md) and [Controls to Use on Windows Forms](./controls/controls-to-use-on-windows-forms.md).</span></span>  
  
2. <span data-ttu-id="83c8b-113"><xref:Microsoft.Win32> 名前空間への参照をコードに追加します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-113">Add a reference to the <xref:Microsoft.Win32> namespace to your code.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#2](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#2)]
     [!code-vb[WinFormsAutoScaling#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="83c8b-114">フォームのコンストラクターに次のコードを追加して、必要なイベントハンドラーをフックし、フォームで使用されている既定のフォントを変更します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-114">Add the following code to the constructor of your form to hook up required event handlers, and to change the default font in use for the form.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#3](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#3)]
     [!code-vb[WinFormsAutoScaling#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="83c8b-115"><xref:Microsoft.Win32.UserPreferenceCategory.Window> カテゴリが変更されたときにフォームが自動的に拡大縮小されるようにする <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> イベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-115">Implement a handler for the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event that causes the form to scale automatically when the <xref:Microsoft.Win32.UserPreferenceCategory.Window> category changes.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#4](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#4)]
     [!code-vb[WinFormsAutoScaling#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#4)]  
  
5. <span data-ttu-id="83c8b-116">最後に、<xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> イベントハンドラーをデタッチする <xref:System.Windows.Forms.Form.FormClosing> イベントのハンドラーを実装します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-116">Finally, implement a handler for the <xref:System.Windows.Forms.Form.FormClosing> event that detaches the <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged> event handler.</span></span>  
  
     > [!IMPORTANT]
     > <span data-ttu-id="83c8b-117">このコードを含めないと、アプリケーションでメモリリークが発生します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-117">Failure to include this code will cause your application to leak memory.</span></span>  
  
     [!code-csharp[WinFormsAutoScaling#5](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#5)]
     [!code-vb[WinFormsAutoScaling#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#5)]  
  
6. <span data-ttu-id="83c8b-118">コードをコンパイルして実行します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-118">Compile and run the code.</span></span>  
  
### <a name="to-manually-change-the-font-scheme-in-windows-xp"></a><span data-ttu-id="83c8b-119">Windows XP でフォントスキームを手動で変更するには</span><span class="sxs-lookup"><span data-stu-id="83c8b-119">To manually change the font scheme in Windows XP</span></span>  
  
1. <span data-ttu-id="83c8b-120">Windows フォームアプリケーションの実行中に、Windows デスクトップを右クリックし、ショートカットメニューの **[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="83c8b-120">While your Windows Forms application is running, right-click the Windows desktop and choose **Properties** from the shortcut menu.</span></span>  
  
2. <span data-ttu-id="83c8b-121">**[表示プロパティ]** ダイアログボックスで、 **[外観]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="83c8b-121">In the **Display Properties** dialog box, click the **Appearance** tab.</span></span>  
  
3. <span data-ttu-id="83c8b-122">**[フォントサイズ]** ボックスの一覧で、新しいフォントサイズを選択します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-122">From the **Font Size** drop-down list box, select a new font size.</span></span>  
  
     <span data-ttu-id="83c8b-123">このフォームは、デスクトップフォントスキームの実行時の変更に反応するようになります。</span><span class="sxs-lookup"><span data-stu-id="83c8b-123">You'll notice that the form now reacts to run-time changes in the desktop font scheme.</span></span> <span data-ttu-id="83c8b-124">ユーザーが**通常**のフォント、**大きなフォント**、および**特大のフォント**を変更すると、フォントが変更され、適切に拡大縮小されます。</span><span class="sxs-lookup"><span data-stu-id="83c8b-124">When the user changes between **Normal**, **Large Fonts**, and **Extra Large Fonts**, the form changes font and scales correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83c8b-125">使用例</span><span class="sxs-lookup"><span data-stu-id="83c8b-125">Example</span></span>  
 [!code-csharp[WinFormsAutoScaling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/WinFormsAutoScaling/CS/Form1.cs#1)]
 [!code-vb[WinFormsAutoScaling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WinFormsAutoScaling/VB/Form1.vb#1)]  
  
 <span data-ttu-id="83c8b-126">このコード例のコンストラクターには `InitializeComponent`の呼び出しが含まれています。これは、Visual Studio で新しい Windows フォームプロジェクトを作成するときに定義されます。</span><span class="sxs-lookup"><span data-stu-id="83c8b-126">The constructor in this code example contains a call to `InitializeComponent`, which is defined when you create a new Windows Forms project in Visual Studio.</span></span> <span data-ttu-id="83c8b-127">コマンドラインでアプリケーションをビルドする場合は、このコード行を削除します。</span><span class="sxs-lookup"><span data-stu-id="83c8b-127">Remove this line of code if you are building your application on the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c8b-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="83c8b-128">See also</span></span>

- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- [<span data-ttu-id="83c8b-129">Windows フォームにおける自動スケーリング</span><span class="sxs-lookup"><span data-stu-id="83c8b-129">Automatic Scaling in Windows Forms</span></span>](automatic-scaling-in-windows-forms.md)
