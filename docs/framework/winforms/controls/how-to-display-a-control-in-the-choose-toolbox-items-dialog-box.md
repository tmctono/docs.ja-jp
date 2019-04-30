---
title: '方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: d504ace9e5571246ae0e78e165a7ad2bc23fa481
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61954223"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="74c68-102">方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する</span><span class="sxs-lookup"><span data-stu-id="74c68-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>
<span data-ttu-id="74c68-103">を作成およびコントロールを配置することがそれらのコントロールに表示される、**ツールボックス アイテムの選択**] ダイアログ ボックスで、右クリックしたときに表示される、**ツールボックス**選択 **[アイテムの選択**します。</span><span class="sxs-lookup"><span data-stu-id="74c68-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="74c68-104">AssemblyFoldersEx の登録手順を使用して、このダイアログ ボックスに表示されるコントロールを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="74c68-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="74c68-105">ツールボックス アイテムの選択 ダイアログ ボックスで、コントロールを表示するには</span><span class="sxs-lookup"><span data-stu-id="74c68-105">To display your control in the Choose Toolbox Items dialog box</span></span>  
  
- <span data-ttu-id="74c68-106">コントロール アセンブリをグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="74c68-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="74c68-107">詳細については、「[方法 :アセンブリをグローバル アセンブリ キャッシュにインストールする](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="74c68-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>  
  
     <span data-ttu-id="74c68-108">- または -</span><span class="sxs-lookup"><span data-stu-id="74c68-108">-or-</span></span>  
  
- <span data-ttu-id="74c68-109">AssemblyFoldersEx の登録手順を使用して、コントロールとその関連付けられたデザイン時アセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="74c68-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="74c68-110">AssemblyFoldersEx は、サード パーティ ベンダーがサポートされるフレームワークの各バージョンのパスを格納する場所のレジストリの場所です。</span><span class="sxs-lookup"><span data-stu-id="74c68-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="74c68-111">デザイン時の解像度は、この参照アセンブリを検索するレジストリの場所で確認できます。</span><span class="sxs-lookup"><span data-stu-id="74c68-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="74c68-112">レジストリ スクリプトでは、ツールボックスに表示するコントロールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="74c68-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span> <span data-ttu-id="74c68-113">詳細については、次を参照してください。[カスタム コントロールおよびデザイン時アセンブリを展開する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))します。</span><span class="sxs-lookup"><span data-stu-id="74c68-113">For more information, see [Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74c68-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="74c68-114">See also</span></span>

- <span data-ttu-id="74c68-115">[[ツールボックス アイテムの選択] ダイアログ ボックス (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="74c68-115">[Choose Toolbox Items Dialog Box (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))</span></span>
- <span data-ttu-id="74c68-116">[カスタム コントロールおよびデザイン時アセンブリを展開します。](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="74c68-116">[Deploying a Custom Control and Design-time Assemblies](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))</span></span>
- [<span data-ttu-id="74c68-117">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="74c68-117">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="74c68-118">方法: アセンブリをグローバル アセンブリ キャッシュにインストールする</span><span class="sxs-lookup"><span data-stu-id="74c68-118">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="74c68-119">チュートリアル: カスタム コンポーネントでツールボックスが自動的に入力</span><span class="sxs-lookup"><span data-stu-id="74c68-119">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
