---
title: '方法: ページからウィンドウの高さを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c99ea134478635f368b71443f43e4d8f772cb5aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007311"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="6823e-102">方法: ページからウィンドウの高さを設定する</span><span class="sxs-lookup"><span data-stu-id="6823e-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="6823e-103">この例からウィンドウの高さを設定する方法を示しています、<xref:System.Windows.Controls.Page>します。</span><span class="sxs-lookup"><span data-stu-id="6823e-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6823e-104">例</span><span class="sxs-lookup"><span data-stu-id="6823e-104">Example</span></span>  
 <span data-ttu-id="6823e-105">A<xref:System.Windows.Controls.Page>を設定して、そのホスト ウィンドウの高さを設定できます<xref:System.Windows.Controls.Page.WindowHeight%2A>します。</span><span class="sxs-lookup"><span data-stu-id="6823e-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="6823e-106">このプロパティにより、<xref:System.Windows.Controls.Page>をそれをホストするウィンドウの種類の明示的な知識を持たない。</span><span class="sxs-lookup"><span data-stu-id="6823e-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6823e-107">使用してウィンドウの高さを設定する<xref:System.Windows.Controls.Page.WindowHeight%2A>、<xref:System.Windows.Controls.Page>ウィンドウの子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6823e-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
