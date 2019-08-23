---
title: '方法: 移動履歴の前後への移動'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961352"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="25026-102">方法: 移動履歴の前後への移動</span><span class="sxs-lookup"><span data-stu-id="25026-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="25026-103">この例では、ナビゲーション履歴のエントリに前方または後方に移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="25026-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25026-104">例</span><span class="sxs-lookup"><span data-stu-id="25026-104">Example</span></span>  
 <span data-ttu-id="25026-105">次のホストのコンテンツから実行されるコードは、一度に1つずつ、ナビゲーション履歴を前方または後方に移動できます。</span><span class="sxs-lookup"><span data-stu-id="25026-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="25026-106"><xref:System.Windows.Navigation.NavigationWindow>従っ<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="25026-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="25026-107"><xref:System.Windows.Controls.Frame>従っ<xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="25026-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="25026-108">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="25026-108">Internet Explorer</span></span>  
  
 <span data-ttu-id="25026-109">1つ前のエントリに移動する前に、まず、 **CanGoForward**プロパティを調べることによって、"進む" ナビゲーション履歴にエントリがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25026-109">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="25026-110">1つ前のエントリに移動するには、 **Goforward**メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25026-110">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="25026-111">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="25026-111">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="25026-112">1つ前のエントリに移動するには、まず、 **CanGoBack**プロパティを調べて、[戻る] ナビゲーション履歴にエントリがあることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25026-112">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="25026-113">1つ前のエントリに移動するには、 **GoBack**メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="25026-113">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="25026-114">これを次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="25026-114">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="25026-115">**CanGoForward**、 **goforward**、 **CanGoBack**、および**GoBack**は、、 <xref:System.Windows.Navigation.NavigationWindow> <xref:System.Windows.Controls.Frame>、および<xref:System.Windows.Navigation.NavigationService>によって実装されます。</span><span class="sxs-lookup"><span data-stu-id="25026-115">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25026-116">**Goforward**を呼び出し、"進む" ナビゲーション履歴にエントリがない場合、または**GoBack**を呼び出し、[戻る] ナビゲーション<xref:System.InvalidOperationException>履歴にエントリがない場合は、がスローされます。</span><span class="sxs-lookup"><span data-stu-id="25026-116">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
