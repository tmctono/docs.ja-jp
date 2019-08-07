---
title: '方法: 移動履歴を遡る'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating back
- navigation [WPF], through navigation history (back)
ms.assetid: 9343234b-d864-441d-b8a7-d895cba80a87
ms.openlocfilehash: 86590c2794339ac22cbc8ec5e11224736133e870
ms.sourcegitcommit: 10736f243dd2296212e677e207102c463e5f143e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2019
ms.locfileid: "68817980"
---
# <a name="how-to-navigate-back-through-navigation-history"></a><span data-ttu-id="85ca9-102">方法: 移動履歴を遡る</span><span class="sxs-lookup"><span data-stu-id="85ca9-102">How to: Navigate Back Through Navigation History</span></span>
<span data-ttu-id="85ca9-103">この例は、"戻る" ナビゲーション履歴のエントリに移動する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="85ca9-103">This example illustrates how to navigate to entries in back navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85ca9-104">例</span><span class="sxs-lookup"><span data-stu-id="85ca9-104">Example</span></span>  
 <span data-ttu-id="85ca9-105">、、または Internet Explorer <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame>を使用して<xref:System.Windows.Navigation.NavigationService>、でホストされているコンテンツから実行されているコードは、一度に1つずつナビゲーション履歴に戻ることができます。</span><span class="sxs-lookup"><span data-stu-id="85ca9-105">Code that is running from content that is hosted in a <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService>, or Internet Explorer can navigate back through navigation history, one entry at a time.</span></span>  
  
 <span data-ttu-id="85ca9-106">1つ前のエントリに移動するには、最初に、 **GoBack**メソッドを呼び出して、 **CanGoBack**プロパティを調べて、1つ前のエントリに戻る前に、戻るナビゲーション履歴にエントリがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85ca9-106">Navigating back one entry requires first checking that there are entries in back navigation history, by inspecting the **CanGoBack** property, before navigating back one entry, by calling the **GoBack** method.</span></span> <span data-ttu-id="85ca9-107">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="85ca9-107">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="85ca9-108">**CanGoBack**と**GoBack**は、、 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame>、および<xref:System.Windows.Navigation.NavigationService>によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="85ca9-108">**CanGoBack** and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85ca9-109">**GoBack**を呼び出し、[戻る] ナビゲーション履歴<xref:System.InvalidOperationException>にエントリがない場合は、が発生します。</span><span class="sxs-lookup"><span data-stu-id="85ca9-109">If you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is raised.</span></span>
