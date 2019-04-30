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
ms.openlocfilehash: 4c20ebfab45a24cf34b1476fb94dae6913fb4d99
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947759"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a><span data-ttu-id="f3cdf-102">方法: 移動履歴の前後への移動</span><span class="sxs-lookup"><span data-stu-id="f3cdf-102">How to: Navigate Forward or Back Through Navigation History</span></span>
<span data-ttu-id="f3cdf-103">この例では、ナビゲーション履歴にエントリに前後を移動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-103">This example illustrates how to navigate forward or back to entries in navigation history.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3cdf-104">例</span><span class="sxs-lookup"><span data-stu-id="f3cdf-104">Example</span></span>  
 <span data-ttu-id="f3cdf-105">次のホスト内のコンテンツから実行するコードは、ナビゲーション履歴、一度に 1 つのエントリを前後に移動できます。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-105">Code that runs from content in the following hosts can navigate forward or back through navigation history, one entry at a time.</span></span>  
  
- <span data-ttu-id="f3cdf-106"><xref:System.Windows.Navigation.NavigationWindow> 使用してください。 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="f3cdf-106"><xref:System.Windows.Navigation.NavigationWindow> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- <span data-ttu-id="f3cdf-107"><xref:System.Windows.Controls.Frame> 使用してください。 <xref:System.Windows.Navigation.NavigationService></span><span class="sxs-lookup"><span data-stu-id="f3cdf-107"><xref:System.Windows.Controls.Frame> using <xref:System.Windows.Navigation.NavigationService></span></span>  
  
- [!INCLUDE[TLA#tla_iegeneric](../../../../includes/tlasharptla-iegeneric-md.md)]  
  
 <span data-ttu-id="f3cdf-108">前方の 1 つのエントリを移動する前にする必要があります最初ことを確認エントリ"進む"ナビゲーション履歴を調べることによって、 **CanGoForward**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-108">Before you can navigate forward one entry, you must first check that there are entries in forward navigation history by inspecting the **CanGoForward** property.</span></span> <span data-ttu-id="f3cdf-109">転送の 1 つのエントリを移動するを呼び出す、 **GoForward**メソッド。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-109">To navigate forward one entry, you call the **GoForward** method.</span></span> <span data-ttu-id="f3cdf-110">これは、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-110">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 <span data-ttu-id="f3cdf-111">1 つのエントリをバックアップ移動するを調べることによって"戻る"ナビゲーション履歴にエントリが表示されている最初に確認する必要があります、 **CanGoBack**プロパティ。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-111">Before you can navigate back one entry, you must first check that there are entries in back navigation history by inspecting the **CanGoBack** property.</span></span> <span data-ttu-id="f3cdf-112">1 つ戻りますエントリを移動するを呼び出す、 **GoBack**メソッド。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-112">To navigate back one entry, you call the **GoBack** method.</span></span> <span data-ttu-id="f3cdf-113">これは、次の例に示します。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-113">This is illustrated in the following example:</span></span>  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 <span data-ttu-id="f3cdf-114">**CanGoForward**、 **GoForward**、 **CanGoBack**、および**GoBack**によって実装される<xref:System.Windows.Navigation.NavigationWindow>、 <xref:System.Windows.Controls.Frame>、および<xref:System.Windows.Navigation.NavigationService>します。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-114">**CanGoForward**, **GoForward**, **CanGoBack**, and **GoBack** are implemented by <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>, and <xref:System.Windows.Navigation.NavigationService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f3cdf-115">呼び出す場合**GoForward**、"進む"ナビゲーション履歴にエントリがないと、または呼び出す場合**GoBack**、戻るナビゲーション履歴にエントリがないと、<xref:System.InvalidOperationException>がスローされます。</span><span class="sxs-lookup"><span data-stu-id="f3cdf-115">If you call **GoForward**, and there are no entries in forward navigation history, or if you call **GoBack**, and there are no entries in back navigation history, an <xref:System.InvalidOperationException> is thrown.</span></span>
