---
title: '方法: フォームに標準メニュー項目を追加する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- menu items [Windows Forms], standard
- ToolStrip control [Windows Forms]
ms.assetid: 75db9126-e70c-4e81-921d-b83c0a4a9f50
ms.openlocfilehash: a95476ff3d182bf2a56e6527c9ee83c8c56af246
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583650"
---
# <a name="how-to-provide-standard-menu-items-to-a-form"></a><span data-ttu-id="ee7e8-102">方法: フォームに標準メニュー項目を追加する</span><span class="sxs-lookup"><span data-stu-id="ee7e8-102">How to: Provide Standard Menu Items to a Form</span></span>
<span data-ttu-id="ee7e8-103">フォームの標準のメニューを <xref:System.Windows.Forms.MenuStrip> コントロールに提供できます。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="ee7e8-104">Visual Studio でこの機能の広範なサポートがあります。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-104">There is extensive support for this feature in Visual Studio.</span></span>  
  
 <span data-ttu-id="ee7e8-105">[チュートリアル: フォームに標準メニュー項目を用意する](walkthrough-providing-standard-menu-items-to-a-form.md)します。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-105">Also see [Walkthrough: Providing Standard Menu Items to a Form](walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee7e8-106">例</span><span class="sxs-lookup"><span data-stu-id="ee7e8-106">Example</span></span>  
 <span data-ttu-id="ee7e8-107"><xref:System.Windows.Forms.MenuStrip> コントロールを使用して標準メニューを持つフォームを作成する方法を、次のコード例に示します。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-107">The following code example demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a form with a standard menu.</span></span> <span data-ttu-id="ee7e8-108">メニュー項目の選択は、<xref:System.Windows.Forms.StatusStrip> コントロールに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-108">Menu item selections are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ee7e8-109">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="ee7e8-109">Compiling the Code</span></span>  
 <span data-ttu-id="ee7e8-110">この例で必要な要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-110">This example requires:</span></span>  
  
- <span data-ttu-id="ee7e8-111">System、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。</span><span class="sxs-lookup"><span data-stu-id="ee7e8-111">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee7e8-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="ee7e8-112">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.StatusStrip>
- [<span data-ttu-id="ee7e8-113">MenuStrip コントロール</span><span class="sxs-lookup"><span data-stu-id="ee7e8-113">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
