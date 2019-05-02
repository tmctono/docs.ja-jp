---
title: 基本フォームの外観を変更した場合の影響
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: 6c87b3d29a1c55b2a7517da78a1951d94676dd68
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756820"
---
# <a name="effects-of-modifying-a-base-forms-appearance"></a><span data-ttu-id="0233d-102">基本フォームの外観を変更した場合の影響</span><span class="sxs-lookup"><span data-stu-id="0233d-102">Effects of Modifying a Base Form's Appearance</span></span>
<span data-ttu-id="0233d-103">アプリケーションの開発中に、同じプロジェクト (または他のプロジェクト) 内の他のフォームの継承元となる、基本フォームの外観の変更が必要になることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="0233d-103">During application development, you may often need to change the appearance of the base form from which other forms in the project (or in other projects) are inheriting.</span></span>  
  
 <span data-ttu-id="0233d-104">デザイン時にプロパティの設定の変更やコントロールの追加または削除によって基本フォームの外観を変更した場合、基本フォームを含むプロジェクトをビルドしたときに、継承されたフォームに変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="0233d-104">At design time, changes to the base form's appearance (be it the setting of properties or the addition and subtraction of controls) are reflected on inherited forms when the project containing the base form is built.</span></span> <span data-ttu-id="0233d-105">基本フォームの変更を保存するだけでは、変更は反映されません。</span><span class="sxs-lookup"><span data-stu-id="0233d-105">It is not sufficient for you to simply save the changes to the base form.</span></span> <span data-ttu-id="0233d-106">プロジェクトをビルドするには、**[ビルド]** メニューの **[ビルド]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0233d-106">To build a project, choose **Build** from the **Build** menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0233d-107">実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0233d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0233d-108">設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0233d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0233d-109">詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0233d-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
 <span data-ttu-id="0233d-110">実行時に基本フォームに変更を加えても、既にインスタンス化されている継承されたフォームには反映されません。</span><span class="sxs-lookup"><span data-stu-id="0233d-110">Modifications made to the base form at run time have no affect on inherited forms that are already instantiated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0233d-111">関連項目</span><span class="sxs-lookup"><span data-stu-id="0233d-111">See also</span></span>

- [<span data-ttu-id="0233d-112">base</span><span class="sxs-lookup"><span data-stu-id="0233d-112">base</span></span>](~/docs/csharp/language-reference/keywords/base.md)
- [<span data-ttu-id="0233d-113">方法: Windows フォームを継承する</span><span class="sxs-lookup"><span data-stu-id="0233d-113">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="0233d-114">Windows フォームのビジュアルの継承</span><span class="sxs-lookup"><span data-stu-id="0233d-114">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
