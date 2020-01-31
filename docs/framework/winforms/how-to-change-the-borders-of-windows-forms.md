---
title: フォームの境界線の変更
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, changing the borders
ms.assetid: b3d5fa56-80c6-4b10-b505-f9672307ed55
ms.openlocfilehash: 2c8eb25b44c7406e4312f432f2d69524346f94d6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739570"
---
# <a name="how-to-change-the-borders-of-windows-forms"></a><span data-ttu-id="dfc72-102">方法 : Windows フォームの境界線を変更する</span><span class="sxs-lookup"><span data-stu-id="dfc72-102">How to: Change the Borders of Windows Forms</span></span>
<span data-ttu-id="dfc72-103">Windows フォームの外観や動作を決定する際にはさまざまな境界線スタイルを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dfc72-103">You have several border styles to choose from when you are determining the appearance and behavior of your Windows Forms.</span></span> <span data-ttu-id="dfc72-104"><xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを変更して、フォームのサイズ変更動作を制御できます。</span><span class="sxs-lookup"><span data-stu-id="dfc72-104">By changing the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property, you can control the resizing behavior of the form.</span></span> <span data-ttu-id="dfc72-105">また、<xref:System.Windows.Forms.Form.FormBorderStyle%2A> を設定すると、キャプション バーの表示方法や、キャプション バーに表示されるボタンを変更できます。</span><span class="sxs-lookup"><span data-stu-id="dfc72-105">In addition, setting the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> affects how the caption bar is displayed as well as what buttons might appear on it.</span></span> <span data-ttu-id="dfc72-106">詳細については、「 <xref:System.Windows.Forms.FormBorderStyle>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfc72-106">For more information, see <xref:System.Windows.Forms.FormBorderStyle>.</span></span>  
  
 <span data-ttu-id="dfc72-107">Visual Studio では、このタスクに対する広範なサポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="dfc72-107">There is extensive support for this task in Visual Studio.</span></span>  
  
 <span data-ttu-id="dfc72-108">「[方法: デザイナーを使用して Windows フォームの境界線を変更する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfc72-108">See also [How to: Change the Borders of Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/yettzh3e(v=vs.100)).</span></span>  
  
### <a name="to-set-the-border-style-of-windows-forms-programmatically"></a><span data-ttu-id="dfc72-109">プログラムで Windows フォームの境界線スタイルを設定するには</span><span class="sxs-lookup"><span data-stu-id="dfc72-109">To set the border style of Windows Forms programmatically</span></span>  
  
- <span data-ttu-id="dfc72-110"><xref:System.Windows.Forms.Form.FormBorderStyle%2A> プロパティを任意のスタイルに設定します。</span><span class="sxs-lookup"><span data-stu-id="dfc72-110">Set the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to the style you want.</span></span> <span data-ttu-id="dfc72-111">次のコード例では、`DlgBx1` フォームの境界線スタイルを <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>に設定します。</span><span class="sxs-lookup"><span data-stu-id="dfc72-111">The following code example sets the border style of form `DlgBx1` to <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>.</span></span>  
  
    ```vb  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog  
    ```  
  
    ```csharp  
    DlgBx1.FormBorderStyle = System.Windows.Forms.FormBorderStyle.FixedDialog;  
    ```  
  
    ```cpp  
    DlgBx1->FormBorderStyle =  
       System::Windows::Forms::FormBorderStyle::FixedDialog;  
    ```  
  
     <span data-ttu-id="dfc72-112">「[方法: デザイン時にダイアログボックスを作成する](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100))」も参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfc72-112">Also see [How to: Create Dialog Boxes at Design Time](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/55cz5x2c(v=vs.100)).</span></span>  
  
     <span data-ttu-id="dfc72-113">また、オプションの **[最小化]** ボタンと **[最大化]** ボタンを提供するフォームの境界線スタイルを選択した場合は、これらのボタンのいずれかまたは両方を機能させるかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="dfc72-113">Additionally, if you have chosen a border style for the form that provides optional **Minimize** and **Maximize** buttons, you can specify whether you want either or both of these buttons to be functional.</span></span> <span data-ttu-id="dfc72-114">これらのボタンは、ユーザーの操作感を細かく調節する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="dfc72-114">These buttons are useful when you want to closely control the user experience.</span></span> <span data-ttu-id="dfc72-115">既定では、 **[最小化]** ボタンと **[最大化]** ボタンが有効になり、それらの機能は **[プロパティ]** ウィンドウで操作されます。</span><span class="sxs-lookup"><span data-stu-id="dfc72-115">The **Minimize** and **Maximize** buttons are enabled by default, and their functionality is manipulated through the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfc72-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="dfc72-116">See also</span></span>

- <xref:System.Windows.Forms.FormBorderStyle>
- <xref:System.Windows.Forms.FormBorderStyle.FixedDialog>
- [<span data-ttu-id="dfc72-117">Windows フォームについて</span><span class="sxs-lookup"><span data-stu-id="dfc72-117">Getting Started with Windows Forms</span></span>](getting-started-with-windows-forms.md)
