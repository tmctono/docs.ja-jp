---
title: '方法: Win32 ホスト コンテナーを使用してヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: ac5cae5bcd94dc8bf80ff95b8971914e1fa5ba2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62025107"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="c5793-102">方法: Win32 ホスト コンテナーを使用してヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="c5793-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="c5793-103">内のビジュアル オブジェクトを作成することができます、[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]ウィンドウで、ビジュアル オブジェクトのホスト ウィンドウ コンテナーを提供します。</span><span class="sxs-lookup"><span data-stu-id="c5793-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="c5793-104">格納されているビジュアル オブジェクト用のイベント処理機能を提供するには、ホスト ウィンドウ コンテナーのメッセージ フィルター ループに渡されるメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="c5793-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="c5793-105">参照してください[チュートリアル。Win32 アプリケーションでのビジュアル オブジェクトをホストしている](tutorial-hosting-visual-objects-in-a-win32-application.md)でのビジュアル オブジェクトをホストする方法の詳細について、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c5793-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5793-106">例</span><span class="sxs-lookup"><span data-stu-id="c5793-106">Example</span></span>  
 <span data-ttu-id="c5793-107">次のコードは、マウス イベント ハンドラーを設定する方法を示しています、[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]ビジュアル オブジェクトのホスト コンテナーとして使用されるウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c5793-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="c5793-108">次の例では、特定のマウス イベントをトラップするへの応答でヒット テストを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c5793-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="c5793-109"><xref:System.Windows.Interop.HwndSource>オブジェクトが表して[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]内でコンテンツを[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]ウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="c5793-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="c5793-110">値、<xref:System.Windows.Interop.HwndSource.RootVisual%2A>のプロパティ、<xref:System.Windows.Interop.HwndSource>オブジェクトは、ビジュアル ツリー階層内の最上位ノードを表します。</span><span class="sxs-lookup"><span data-stu-id="c5793-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="c5793-111">Win32 ホスト コンテナーを使用するオブジェクトのヒット テストの完全なサンプルを参照してください[Win32 の相互運用性サンプルによるヒット テストの](https://go.microsoft.com/fwlink/?LinkID=159995)します。</span><span class="sxs-lookup"><span data-stu-id="c5793-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5793-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="c5793-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="c5793-113">ビジュアル層でのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="c5793-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="c5793-114">チュートリアル: Win32 アプリケーションでのビジュアル オブジェクトのホスト</span><span class="sxs-lookup"><span data-stu-id="c5793-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
