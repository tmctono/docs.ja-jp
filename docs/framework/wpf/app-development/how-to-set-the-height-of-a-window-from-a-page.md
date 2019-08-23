---
title: '方法: ページからウィンドウの高さを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting height from a page
- pages [WPF], setting window height from
- height of window [WPF], setting from a page
ms.assetid: 4e4488ff-ab5c-4ee9-81a4-e1addb55c5cc
ms.openlocfilehash: c1041af88241011b51c96d7b61423344a32b25ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940800"
---
# <a name="how-to-set-the-height-of-a-window-from-a-page"></a><span data-ttu-id="1a6db-102">方法: ページからウィンドウの高さを設定する</span><span class="sxs-lookup"><span data-stu-id="1a6db-102">How to: Set the Height of a Window from a Page</span></span>
<span data-ttu-id="1a6db-103">この例は、 <xref:System.Windows.Controls.Page>からウィンドウの高さを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="1a6db-103">This example illustrates how to set the height of the window from a <xref:System.Windows.Controls.Page>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a6db-104">例</span><span class="sxs-lookup"><span data-stu-id="1a6db-104">Example</span></span>  
 <span data-ttu-id="1a6db-105">では、を設定<xref:System.Windows.Controls.Page.WindowHeight%2A>することによって、ホストウィンドウの高さを設定できます。<xref:System.Windows.Controls.Page></span><span class="sxs-lookup"><span data-stu-id="1a6db-105">A <xref:System.Windows.Controls.Page> can set the height of its host window by setting <xref:System.Windows.Controls.Page.WindowHeight%2A>.</span></span> <span data-ttu-id="1a6db-106">このプロパティを使用<xref:System.Windows.Controls.Page>すると、は、それをホストするウィンドウの種類に関する明示的な知識を持つことができません。</span><span class="sxs-lookup"><span data-stu-id="1a6db-106">This property allows the <xref:System.Windows.Controls.Page> to not have explicit knowledge of the type of window that hosts it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1a6db-107">を使用して<xref:System.Windows.Controls.Page.WindowHeight%2A> <xref:System.Windows.Controls.Page>ウィンドウの高さを設定するには、がウィンドウの子である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a6db-107">To set the height of a window using <xref:System.Windows.Controls.Page.WindowHeight%2A>, a <xref:System.Windows.Controls.Page> must be the child of a window.</span></span>  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowHeightXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowHeightPage.xaml#setpagewindowheightxaml)]
