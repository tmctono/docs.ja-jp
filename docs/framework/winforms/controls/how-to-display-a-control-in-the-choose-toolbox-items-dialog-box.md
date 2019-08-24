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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9a6938b4fe651e13f3ec96642db6027143f1f028
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015897"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a><span data-ttu-id="6ff7e-102">方法: [ツールボックス アイテムの選択] ダイアログ ボックスにコントロールを表示する</span><span class="sxs-lookup"><span data-stu-id="6ff7e-102">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>

<span data-ttu-id="6ff7e-103">コントロールを開発および配布するときに、Visual Studio の **[ツールボックスアイテムの選択]** ダイアログボックスにこれらのコントロールを表示することをお勧めします。これは、**ツール**ボックスを右クリックして **[アイテムの選択]** をクリックすると表示されます。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-103">As you develop and distribute controls, you may want those controls to appear in the **Choose Toolbox Items** dialog box of Visual Studio, which is displayed when you right-click the **Toolbox** and select **Choose Items**.</span></span> <span data-ttu-id="6ff7e-104">このダイアログボックスにコントロールが表示されるようにするには、AssemblyFoldersEx 登録プロシージャを使用します。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-104">You can enable your control to appear in this dialog box by using the AssemblyFoldersEx registration procedure.</span></span>

<span data-ttu-id="6ff7e-105">[ツールボックスアイテムの選択] ダイアログボックスにコントロールを表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-105">To display your control in the Choose Toolbox Items dialog box:</span></span>

- <span data-ttu-id="6ff7e-106">コントロールアセンブリをグローバルアセンブリキャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-106">Install your control assembly to the global assembly cache.</span></span> <span data-ttu-id="6ff7e-107">詳細については、「[方法 :アセンブリをグローバル アセンブリ キャッシュにインストールする](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span><span class="sxs-lookup"><span data-stu-id="6ff7e-107">For more information, see [How to: Install an Assembly into the Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)</span></span>

  <span data-ttu-id="6ff7e-108">\- または -</span><span class="sxs-lookup"><span data-stu-id="6ff7e-108">-or-</span></span>

- <span data-ttu-id="6ff7e-109">AssemblyFoldersEx 登録プロシージャを使用して、コントロールとそれに関連付けられたデザイン時アセンブリを登録します。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-109">Register your control and its associated design-time assemblies by using the AssemblyFoldersEx registration procedure.</span></span> <span data-ttu-id="6ff7e-110">AssemblyFoldersEx は、サードパーティベンダーがサポートする各バージョンのフレームワークのパスを格納するレジストリの場所です。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-110">AssemblyFoldersEx is a registry location where third-party vendors store paths for each version of the framework that they support.</span></span> <span data-ttu-id="6ff7e-111">デザイン時の解決では、このレジストリの場所で参照アセンブリを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-111">Design-time resolution can look in this registry location to find reference assemblies.</span></span> <span data-ttu-id="6ff7e-112">レジストリスクリプトでは、ツールボックスに表示するコントロールを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6ff7e-112">The registry script can specify the controls you want to appear in the Toolbox.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ff7e-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="6ff7e-113">See also</span></span>

- [<span data-ttu-id="6ff7e-114">デザイン時の Windows フォーム コントロールの開発</span><span class="sxs-lookup"><span data-stu-id="6ff7e-114">Developing Windows Forms Controls at Design Time</span></span>](developing-windows-forms-controls-at-design-time.md)
- [<span data-ttu-id="6ff7e-115">方法: アセンブリをグローバル アセンブリ キャッシュにインストールする</span><span class="sxs-lookup"><span data-stu-id="6ff7e-115">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="6ff7e-116">チュートリアル: ツールボックスへのカスタムコンポーネントの自動設定</span><span class="sxs-lookup"><span data-stu-id="6ff7e-116">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
