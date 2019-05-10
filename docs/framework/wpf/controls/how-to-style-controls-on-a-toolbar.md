---
title: '方法: ToolBar のコントロールのスタイルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 90ff02747d762b5853a1f60eb99be574503e27f7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "64640843"
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="77cb9-102">方法: ToolBar のコントロールのスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="77cb9-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="77cb9-103"><xref:System.Windows.Controls.ToolBar>定義<xref:System.Windows.ResourceKey>内のコントロールのスタイルを指定するオブジェクト、<xref:System.Windows.Controls.ToolBar>します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="77cb9-104">内のコントロールのスタイルを設定する、 <xref:System.Windows.Controls.ToolBar>、設定、`x:key`するスタイルの属性を<xref:System.Windows.ResourceKey>で定義されている<xref:System.Windows.Controls.ToolBar>します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="77cb9-105"><xref:System.Windows.Controls.ToolBar> 、次の定義<xref:System.Windows.ResourceKey>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="77cb9-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="77cb9-106">例</span><span class="sxs-lookup"><span data-stu-id="77cb9-106">Example</span></span>  
 <span data-ttu-id="77cb9-107">次の例では、内のコントロールのスタイルを定義する、<xref:System.Windows.Controls.ToolBar>します。</span><span class="sxs-lookup"><span data-stu-id="77cb9-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="77cb9-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="77cb9-108">See also</span></span>

- [<span data-ttu-id="77cb9-109">スタイルとテンプレート</span><span class="sxs-lookup"><span data-stu-id="77cb9-109">Styling and Templating</span></span>](styling-and-templating.md)
