---
title: '方法: Windows フォームに ActiveX コントロールを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 8c4c6c3f96c49401b032e360314794cc800c0551
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987061"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="fb709-102">方法: Windows フォームに ActiveX コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="fb709-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="fb709-103">Visual Studio の Windows フォームデザイナーは Windows フォームコントロールをホストするように最適化されていますが、Windows フォームに ActiveX コントロールを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb709-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="fb709-104">ActiveX コントロールが追加されたときの Windows フォームには、パフォーマンス上の制限があります。</span><span class="sxs-lookup"><span data-stu-id="fb709-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="fb709-105">ActiveX コントロールをフォームに追加する前に、そのコントロールをツールボックスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb709-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="fb709-106">詳細については、「 [COM コンポーネント、[ツールボックスのカスタマイズ] ダイアログボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb709-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="fb709-107">Windows フォームへの ActiveX コントロールの追加</span><span class="sxs-lookup"><span data-stu-id="fb709-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="fb709-108">Windows フォームに ActiveX コントロールを追加するには、ツールボックスのコントロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb709-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="fb709-109">Visual Studio は、プロジェクト内のコントロールへのすべての参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="fb709-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="fb709-110">Windows フォームで ActiveX コントロールを使用する場合の注意事項の詳細については、「 [Windows フォームで Activex コントロールをホストする場合の考慮事項](considerations-when-hosting-an-activex-control-on-a-windows-form.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb709-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fb709-111">Activex コントロールインポーター (Aximp.exe) Windows フォームは、ActiveX ダイナミックリンクライブラリをインポートするときに、予期しない種類のイベント引数を作成します。</span><span class="sxs-lookup"><span data-stu-id="fb709-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="fb709-112">Aximp.exe によって作成される引数は`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`、が必要な場合`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fb709-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="fb709-113">この irregularity では、コードが正常に機能しないようにすることはできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb709-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="fb709-114">詳細については、「 [Windows フォーム ActiveX コントロールインポーター (aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb709-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fb709-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb709-115">See also</span></span>

- [<span data-ttu-id="fb709-116">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="fb709-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="fb709-117">[各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fb709-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="fb709-118">方法: コントロールを Windows フォームに追加する</span><span class="sxs-lookup"><span data-stu-id="fb709-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="fb709-119">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="fb709-119">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="fb709-120">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="fb709-120">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="fb709-121">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="fb709-121">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
