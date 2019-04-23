---
title: '方法: ポップアップ ヘルプを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: f805840ea3b1a8aef6a289dba064c468a4da0cb0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331482"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="e5a71-102">方法: ポップアップ ヘルプを表示する</span><span class="sxs-lookup"><span data-stu-id="e5a71-102">How to: Display Pop-up Help</span></span>
<span data-ttu-id="e5a71-103">Windows フォーム上のヘルプを表示する 1 つの方法は、使用、**ヘルプ**を通じてアクセス可能なタイトル バーの右側にあるボタンをクリック、<xref:System.Windows.Forms.Form.HelpButton%2A>プロパティ。</span><span class="sxs-lookup"><span data-stu-id="e5a71-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="e5a71-104">この種類のヘルプの表示は、ダイアログ ボックスでの使用に適しています。</span><span class="sxs-lookup"><span data-stu-id="e5a71-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="e5a71-105">モーダル形式で表示されるダイアログ ボックス (<xref:System.Windows.Forms.Form.ShowDialog%2A> メソッドを使用) は、別のウィンドウにフォーカスを移動するときはモーダル ダイアログ ボックスを閉じる必要があるため、外部のヘルプ システムを起動する場合は問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="e5a71-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="e5a71-106">さらを使用して、**ヘルプ**ボタンがあることが必要ですありません**最小化**ボタンまたは**最大化**タイトル バーに表示されるボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a71-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="e5a71-107">フォームは、通常はあるが、これは、標準のダイアログ ボックスの規約では、**最小化**と**最大化**ボタン。</span><span class="sxs-lookup"><span data-stu-id="e5a71-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>  
  
 <span data-ttu-id="e5a71-108">また、ポップアップ ヘルプを実装している場合でも、<xref:System.Windows.Forms.HelpProvider> コンポーネントを使用して、コントロールをヘルプ システムのファイルにリンクできることにも注意してください。</span><span class="sxs-lookup"><span data-stu-id="e5a71-108">Be aware that you can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="e5a71-109">詳細については、次を参照してください。 [Windows アプリケーションでヘルプを提供する](how-to-provide-help-in-a-windows-application.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5a71-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5a71-110">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e5a71-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e5a71-111">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a71-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e5a71-112">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5a71-112">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-display-pop-up-help"></a><span data-ttu-id="e5a71-113">ポップアップ ヘルプを表示するには</span><span class="sxs-lookup"><span data-stu-id="e5a71-113">To display pop-up Help</span></span>  
  
1. <span data-ttu-id="e5a71-114">ドラッグ、 [HelpProvider](../controls/helpprovider-component-windows-forms.md)コンポーネントをツールボックスからフォームにします。</span><span class="sxs-lookup"><span data-stu-id="e5a71-114">Drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>  
  
     <span data-ttu-id="e5a71-115">これは、Windows フォーム デザイナーの下部にあるトレイ内に配置されます。</span><span class="sxs-lookup"><span data-stu-id="e5a71-115">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>  
  
2. <span data-ttu-id="e5a71-116">[プロパティ] ウィンドウで、<xref:System.Windows.Forms.Form.HelpButton%2A> プロパティを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e5a71-116">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="e5a71-117">これで、フォームのタイトル バーの右側に疑問符の付いたボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5a71-117">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>  
  
3. <span data-ttu-id="e5a71-118"><xref:System.Windows.Forms.Form.HelpButton%2A> が表示されるには、フォームの <xref:System.Windows.Forms.Form.MinimizeBox%2A> プロパティと <xref:System.Windows.Forms.Form.MaximizeBox%2A> プロパティを `false` に設定し、<xref:System.Windows.Forms.Form.ControlBox%2A> プロパティを `true` に設定し、<xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを<xref:System.Windows.Forms.FormBorderStyle.FixedSingle>、<xref:System.Windows.Forms.FormBorderStyle.Fixed3D>、<xref:System.Windows.Forms.FormBorderStyle.FixedDialog>、または <xref:System.Windows.Forms.FormBorderStyle.Sizable> のいずれかの値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5a71-118">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>  
  
4. <span data-ttu-id="e5a71-119">フォーム上のヘルプを表示し、[プロパティ] ウィンドウのヘルプの文字列を設定するコントロールを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5a71-119">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="e5a71-120">これは、文字列のようなウィンドウに表示されるテキストを[ツールヒント](../controls/tooltip-component-windows-forms.md)します。</span><span class="sxs-lookup"><span data-stu-id="e5a71-120">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>  
  
5. <span data-ttu-id="e5a71-121">**F5**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e5a71-121">Press **F5**.</span></span>  
  
6. <span data-ttu-id="e5a71-122">キーを押して、**ヘルプ**タイトル バーにボタンをクリックし、ヘルプ文字列を設定するコントロールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5a71-122">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5a71-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="e5a71-123">See also</span></span>

- [<span data-ttu-id="e5a71-124">ツールヒントを使用したコントロールのヘルプ</span><span class="sxs-lookup"><span data-stu-id="e5a71-124">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="e5a71-125">Windows フォームでのヘルプの統合</span><span class="sxs-lookup"><span data-stu-id="e5a71-125">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="e5a71-126">Windows フォーム</span><span class="sxs-lookup"><span data-stu-id="e5a71-126">Windows Forms</span></span>](../index.md)
