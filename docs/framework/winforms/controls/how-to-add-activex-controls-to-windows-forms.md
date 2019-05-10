---
title: '方法: Windows フォームに ActiveX コントロールを追加する'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 17311adade187ef3c8e4e639299e6c5cbbcd98a9
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210390"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a><span data-ttu-id="375d5-102">方法: Windows フォームに ActiveX コントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="375d5-102">How to: Add ActiveX Controls to Windows Forms</span></span>

<span data-ttu-id="375d5-103">Windows フォーム コントロールをホストするには、Visual Studio での Windows フォーム デザイナーが最適化され、中には、Windows フォームで ActiveX コントロールも記述できます。</span><span class="sxs-lookup"><span data-stu-id="375d5-103">While the Windows Forms Designer in Visual Studio is optimized to host Windows Forms controls, you can also put ActiveX controls on Windows Forms.</span></span>

> [!CAUTION]
> <span data-ttu-id="375d5-104">ActiveX コントロールを追加することがある場合に、Windows フォームのパフォーマンスの制限があります。</span><span class="sxs-lookup"><span data-stu-id="375d5-104">There are performance limitations for Windows Forms when ActiveX controls are added to them.</span></span>

<span data-ttu-id="375d5-105">ActiveX コントロールをフォームに追加する前に、ツールボックスに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="375d5-105">Before you add ActiveX controls to your form, you must add them to the Toolbox.</span></span> <span data-ttu-id="375d5-106">詳細については、次を参照してください。 [COM コンポーネント、ツールボックスのカスタマイズ ダイアログ ボックス](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="375d5-106">For more information, see [COM Components, Customize Toolbox Dialog Box](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).</span></span>

## <a name="add-an-activex-control-to-your-windows-form"></a><span data-ttu-id="375d5-107">Windows フォームに ActiveX コントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="375d5-107">Add an ActiveX control to your Windows Form</span></span>

<span data-ttu-id="375d5-108">Windows フォームに ActiveX コントロールを追加するには、ツールボックスにコントロールをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="375d5-108">To add an ActiveX control to your Windows Form, double-click the control on the Toolbox.</span></span>

<span data-ttu-id="375d5-109">Visual Studio では、プロジェクトのコントロールにすべての参照を追加します。</span><span class="sxs-lookup"><span data-stu-id="375d5-109">Visual Studio adds all references to the control in your project.</span></span> <span data-ttu-id="375d5-110">Windows フォームで ActiveX コントロールを使用する場合に留意すべき点の詳細については、次を参照してください。 [Windows フォームで ActiveX コントロールをホストしている場合の考慮事項](considerations-when-hosting-an-activex-control-on-a-windows-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="375d5-110">For more information about things to keep in mind when using ActiveX controls on Windows Forms, see [Considerations When Hosting an ActiveX Control on a Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).</span></span>

> [!NOTE]
> <span data-ttu-id="375d5-111">Windows フォーム ActiveX コントロール インポーター (AxImp.exe) は、ActiveX のダイナミック リンク ライブラリのインポート時に予想よりも、別の種類のイベント引数を作成します。</span><span class="sxs-lookup"><span data-stu-id="375d5-111">The Windows Forms ActiveX Control Importer (AxImp.exe) creates event arguments of a different type than expected upon importation of ActiveX dynamic link libraries.</span></span> <span data-ttu-id="375d5-112">AxImp.exe によって作成された引数は、次のような: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`、`Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)`が必要です。</span><span class="sxs-lookup"><span data-stu-id="375d5-112">The arguments created by AxImp.exe are similar to the following: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, when `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` is expected.</span></span> <span data-ttu-id="375d5-113">この不規則性から正常に機能して、コードが回避しないことに注意します。</span><span class="sxs-lookup"><span data-stu-id="375d5-113">Be aware that this irregularity does not prevent code from functioning normally.</span></span> <span data-ttu-id="375d5-114">詳細については、次を参照してください。 [Windows フォーム ActiveX コントロール インポーター (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md)します。</span><span class="sxs-lookup"><span data-stu-id="375d5-114">For details, see [Windows Forms ActiveX Control Importer (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="375d5-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="375d5-115">See also</span></span>

- [<span data-ttu-id="375d5-116">Windows フォーム コントロール</span><span class="sxs-lookup"><span data-stu-id="375d5-116">Windows Forms Controls</span></span>](index.md)
- <span data-ttu-id="375d5-117">[各言語およびライブラリにおける、コントロールとプログラミング可能オブジェクトの比較](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="375d5-117">[Controls and Programmable Objects Compared in Various Languages and Libraries](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))</span></span>
- [<span data-ttu-id="375d5-118">方法: Windows フォームにコントロールを追加します。</span><span class="sxs-lookup"><span data-stu-id="375d5-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="375d5-119">Windows フォームでのコントロールの配置</span><span class="sxs-lookup"><span data-stu-id="375d5-119">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="375d5-120">各 Windows フォーム コントロールのラベル設定とショートカットの作成</span><span class="sxs-lookup"><span data-stu-id="375d5-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="375d5-121">Windows フォームで使用するコントロール</span><span class="sxs-lookup"><span data-stu-id="375d5-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="375d5-122">Windows フォーム コントロールの機能別一覧</span><span class="sxs-lookup"><span data-stu-id="375d5-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
