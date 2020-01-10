---
title: '方法 : Win32 ホスト コンテナーを使用してヒット テストを実行する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: b71783f2d061c9139de4449d8e0106eb00345894
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740182"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="d21fa-102">方法 : Win32 ホスト コンテナーを使用してヒット テストを実行する</span><span class="sxs-lookup"><span data-stu-id="d21fa-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="d21fa-103">ビジュアルオブジェクトのホストウィンドウコンテナーを指定することにより、Win32 ウィンドウ内にビジュアルオブジェクトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d21fa-103">You can create visual objects within a Win32 window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="d21fa-104">格納されているビジュアル オブジェクト用のイベント処理機能を提供するには、ホスト ウィンドウ コンテナーのメッセージ フィルター ループに渡されるメッセージを処理します。</span><span class="sxs-lookup"><span data-stu-id="d21fa-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="d21fa-105">Win32 ウィンドウでビジュアルオブジェクトをホストする方法の詳細については[、「チュートリアル: Win32 アプリケーションでのビジュアルオブジェクト](tutorial-hosting-visual-objects-in-a-win32-application.md)のホスト」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d21fa-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a Win32 window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d21fa-106">使用例</span><span class="sxs-lookup"><span data-stu-id="d21fa-106">Example</span></span>  
 <span data-ttu-id="d21fa-107">次のコードは、ビジュアルオブジェクトのホストコンテナーとして使用される Win32 ウィンドウのマウスイベントハンドラーを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d21fa-107">The following code shows how to set up mouse event handlers for a Win32 window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="d21fa-108">次の例は、特定のマウスイベントのトラップに応答してヒットテストを設定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="d21fa-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="d21fa-109"><xref:System.Windows.Interop.HwndSource> オブジェクトは、Win32 ウィンドウ内で [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] コンテンツを表示します。</span><span class="sxs-lookup"><span data-stu-id="d21fa-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a Win32 window.</span></span> <span data-ttu-id="d21fa-110"><xref:System.Windows.Interop.HwndSource> オブジェクトの <xref:System.Windows.Interop.HwndSource.RootVisual%2A> プロパティの値は、ビジュアルツリー階層内の最上位ノードを表します。</span><span class="sxs-lookup"><span data-stu-id="d21fa-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="d21fa-111">Win32 ホストコンテナーを使用したヒットテストオブジェクトの完全なサンプルについては、「 [Win32 相互運用のヒットテストのサンプル](https://go.microsoft.com/fwlink/?LinkID=159995)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d21fa-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d21fa-112">関連項目</span><span class="sxs-lookup"><span data-stu-id="d21fa-112">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="d21fa-113">ビジュアル層でのヒット テスト</span><span class="sxs-lookup"><span data-stu-id="d21fa-113">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="d21fa-114">チュートリアル : Win32 アプリケーションでのビジュアル オブジェクトのホスト</span><span class="sxs-lookup"><span data-stu-id="d21fa-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](tutorial-hosting-visual-objects-in-a-win32-application.md)
