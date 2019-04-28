---
title: '方法: トリガーを使用して、ListView で選択された項目のスタイルを設定する'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: ad64382b871bae9114a1e63257de3f8595376923
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696199"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="67fbb-102">方法: トリガーを使用して、ListView で選択された項目のスタイルを設定する</span><span class="sxs-lookup"><span data-stu-id="67fbb-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="67fbb-103">この例は、定義する方法を示します<xref:System.Windows.Style.Triggers%2A>の<xref:System.Windows.Controls.ListViewItem>コントロールようにプロパティ値を<xref:System.Windows.Controls.ListViewItem>変更、<xref:System.Windows.Style>の<xref:System.Windows.Controls.ListViewItem>対応する変更点。</span><span class="sxs-lookup"><span data-stu-id="67fbb-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67fbb-104">例</span><span class="sxs-lookup"><span data-stu-id="67fbb-104">Example</span></span>  
 <span data-ttu-id="67fbb-105">場合は、<xref:System.Windows.Style>の<xref:System.Windows.Controls.ListViewItem>プロパティの変更に応答を変更するには、定義<xref:System.Windows.Style.Triggers%2A>の<xref:System.Windows.Style>を変更します。</span><span class="sxs-lookup"><span data-stu-id="67fbb-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="67fbb-106">次の例では、定義、<xref:System.Windows.Trigger>設定を<xref:System.Windows.Controls.Control.Foreground%2A>プロパティを<xref:System.Windows.Media.Brushes.Blue%2A>し、変更、<xref:System.Windows.FrameworkElement.Cursor%2A>を表示する、<xref:System.Windows.Input.CursorType.Hand>ときに、<xref:System.Windows.UIElement.IsMouseOver%2A>プロパティに対する変更を`true`します。</span><span class="sxs-lookup"><span data-stu-id="67fbb-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="67fbb-107">次の例では、定義、<xref:System.Windows.MultiTrigger>設定、<xref:System.Windows.Controls.Control.Foreground%2A>のプロパティを<xref:System.Windows.Controls.ListViewItem>に<xref:System.Windows.Media.Brushes.Yellow%2A>ときに、<xref:System.Windows.Controls.ListViewItem>選択されている項目とキーボード フォーカスがあります。</span><span class="sxs-lookup"><span data-stu-id="67fbb-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="67fbb-108">関連項目</span><span class="sxs-lookup"><span data-stu-id="67fbb-108">See also</span></span>

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [<span data-ttu-id="67fbb-109">方法トピック</span><span class="sxs-lookup"><span data-stu-id="67fbb-109">How-to Topics</span></span>](listview-how-to-topics.md)
- [<span data-ttu-id="67fbb-110">ListView の概要</span><span class="sxs-lookup"><span data-stu-id="67fbb-110">ListView Overview</span></span>](listview-overview.md)
- [<span data-ttu-id="67fbb-111">GridView の概要</span><span class="sxs-lookup"><span data-stu-id="67fbb-111">GridView Overview</span></span>](gridview-overview.md)
