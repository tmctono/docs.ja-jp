---
title: ColorDialog コンポーネントの外観の変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746640"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="329f0-102">方法 : Windows フォーム ColorDialog コンポーネントの表示形式を変更する</span><span class="sxs-lookup"><span data-stu-id="329f0-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="329f0-103">Windows フォーム <xref:System.Windows.Forms.ColorDialog> コンポーネントの外観は、多くのプロパティを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="329f0-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="329f0-104">ダイアログボックスには2つのセクションがあります。1つは基本色を示し、もう1つはユーザーがカスタムカラーを定義できるようにするものです。</span><span class="sxs-lookup"><span data-stu-id="329f0-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="329f0-105">ほとんどのプロパティは、ダイアログボックスからユーザーが選択できる色を制限します。</span><span class="sxs-lookup"><span data-stu-id="329f0-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="329f0-106"><xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> プロパティが `true`に設定されている場合、ユーザーはカスタム色を定義できます。</span><span class="sxs-lookup"><span data-stu-id="329f0-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="329f0-107">ダイアログボックスを拡張してカスタムの色を定義すると、<xref:System.Windows.Forms.ColorDialog.FullOpen%2A> プロパティが `true` ます。それ以外の場合は、ユーザーは [カスタムカラーの定義] ボタンをクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="329f0-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="329f0-108"><xref:System.Windows.Forms.ColorDialog.AnyColor%2A> プロパティが `true`に設定されている場合、ダイアログボックスには、基本色のセットで使用可能なすべての色が表示されます。</span><span class="sxs-lookup"><span data-stu-id="329f0-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="329f0-109"><xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> プロパティが `true`に設定されている場合、ユーザーはディザーカラーを選択できません。選択できるのは純色のみです。</span><span class="sxs-lookup"><span data-stu-id="329f0-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="329f0-110"><xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> プロパティが `true`に設定されている場合、ダイアログボックスに [ヘルプ] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="329f0-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="329f0-111">ユーザーが [ヘルプ] ボタンをクリックすると、<xref:System.Windows.Forms.ColorDialog> コンポーネントの <xref:System.Windows.Forms.CommonDialog.HelpRequest> イベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="329f0-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="329f0-112">[色] ダイアログボックスの外観を構成するには</span><span class="sxs-lookup"><span data-stu-id="329f0-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="329f0-113"><xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>、<xref:System.Windows.Forms.ColorDialog.AnyColor%2A>、<xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>、および <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> プロパティを目的の値に設定します。</span><span class="sxs-lookup"><span data-stu-id="329f0-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="329f0-114">関連項目</span><span class="sxs-lookup"><span data-stu-id="329f0-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="329f0-115">ColorDialog コンポーネント</span><span class="sxs-lookup"><span data-stu-id="329f0-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="329f0-116">ColorDialog コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="329f0-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
