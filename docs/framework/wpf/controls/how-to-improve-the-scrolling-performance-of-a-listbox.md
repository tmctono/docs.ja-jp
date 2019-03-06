---
title: '方法: ListBox のスクロール速度を向上させる'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364555"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="46031-102">方法: ListBox のスクロール速度を向上させる</span><span class="sxs-lookup"><span data-stu-id="46031-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="46031-103">場合、<xref:System.Windows.Controls.ListBox>多くの項目を格納、ユーザーがスクロールすると、ユーザー インターフェイスの応答が遅くなること、<xref:System.Windows.Controls.ListBox>をマウス ホイールを使用するかスクロール バーのつまみをドラッグします。</span><span class="sxs-lookup"><span data-stu-id="46031-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="46031-104">パフォーマンスを向上させることができます、<xref:System.Windows.Controls.ListBox>を設定してユーザーがスクロールすると、`VirtualizingStackPanel.VirtualizationMode`添付プロパティを<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>します。</span><span class="sxs-lookup"><span data-stu-id="46031-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46031-105">例</span><span class="sxs-lookup"><span data-stu-id="46031-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="46031-106">説明</span><span class="sxs-lookup"><span data-stu-id="46031-106">Description</span></span>  
<span data-ttu-id="46031-107">次の例では、作成、<xref:System.Windows.Controls.ListBox>設定と、`VirtualizingStackPanel.VirtualizationMode`添付プロパティを<xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>スクロール中にパフォーマンスを向上させる。</span><span class="sxs-lookup"><span data-stu-id="46031-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="46031-108">コード</span><span class="sxs-lookup"><span data-stu-id="46031-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="46031-109">次の例では、前の例を使用してデータを示します。</span><span class="sxs-lookup"><span data-stu-id="46031-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
