---
title: '方法: Windows フォームに ActiveX コントロールを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011155"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="8fddf-102">方法: Windows フォームに ActiveX コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="8fddf-102">How to: Add ActiveX Controls to Windows Forms</span></span>
<span data-ttu-id="8fddf-103">Windows フォーム コントロールをホストするには、Windows フォーム デザイナーが最適化され、中には、Windows フォームで ActiveX コントロールも記述できます。</span><span class="sxs-lookup"><span data-stu-id="8fddf-103">While the Windows Forms Designer is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8fddf-104">ActiveX コントロールを追加することがある場合に、Windows フォームのパフォーマンスの制限があります。</span><span class="sxs-lookup"><span data-stu-id="8fddf-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>  
  
 <span data-ttu-id="8fddf-105">ActiveX コントロールをフォームに追加する前に、ツールボックスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8fddf-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="8fddf-106">詳細については、次を参照してください。 [COM コンポーネント、ツールボックスのカスタマイズ ダイアログ ボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fddf-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8fddf-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="8fddf-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fddf-108">To change your settings, click **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="8fddf-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fddf-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="8fddf-110">Windows フォームに ActiveX コントロールを追加するには</span><span class="sxs-lookup"><span data-stu-id="8fddf-110">To add an ActiveX control to your Windows Form</span></span>  
  
- <span data-ttu-id="8fddf-111">ツールボックスにコントロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="8fddf-111">Double-click the control on the Toolbox.</span></span>  
  
     <span data-ttu-id="8fddf-112">Visual Studio では、プロジェクトのコントロールにすべての参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-112">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="8fddf-113">Windows フォームで ActiveX コントロールを使用する場合に留意すべき点の詳細については、次を参照してください。 [Windows フォームで ActiveX コントロールをホストしている場合の考慮事項](considerations-when-hosting-an-activex-control-on-a-windows-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-113">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8fddf-114">Windows フォーム ActiveX コントロール インポーター (AxImp.exe) は、ActiveX のダイナミック リンク ライブラリのインポート時に予想よりも、別の種類のイベント引数を作成します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-114">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="8fddf-115">AxImp.exe によって作成された引数は、次のような: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`、`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`が必要です。</span><span class="sxs-lookup"><span data-stu-id="8fddf-115">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="8fddf-116">この不規則性から正常に機能して、コードが回避しないことに注意します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-116">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="8fddf-117">詳細については、次を参照してください。 [Windows フォーム ActiveX コントロール インポーター (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-117">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fddf-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="8fddf-118">See also</span></span>

- [<span data-ttu-id="8fddf-119">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="8fddf-119">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="8fddf-120">[各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8fddf-120">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="8fddf-121">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="8fddf-121">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="8fddf-122">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="8fddf-122">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="8fddf-123">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="8fddf-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="8fddf-124">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="8fddf-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="8fddf-125">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="8fddf-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
