---
title: '方法: バッファリングされたグラフィックスを手動で管理する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flicker [Windows Forms], reducing by manually managing graphics
- graphics [Windows Forms], managing buffered
ms.assetid: 4c2a90ee-bbbe-4ff6-9170-1b06c195c918
ms.openlocfilehash: 6010d52750b20c07db51917621f8643e9d9b47d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968598"
---
# <a name="how-to-manually-manage-buffered-graphics"></a><span data-ttu-id="09447-102">方法: バッファリングされたグラフィックスを手動で管理する</span><span class="sxs-lookup"><span data-stu-id="09447-102">How to: Manually Manage Buffered Graphics</span></span>
<span data-ttu-id="09447-103">より高度なダブルバッファリングのシナリオでは、.NET Framework クラスを使用して、独自のダブルバッファリングロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="09447-103">For more advanced double buffering scenarios, you can use the .NET Framework classes to implement your own double-buffering logic.</span></span> <span data-ttu-id="09447-104">個々のグラフィックスバッファーの割り当てと管理を行うクラスは<xref:System.Drawing.BufferedGraphicsContext> 、クラスです。</span><span class="sxs-lookup"><span data-stu-id="09447-104">The class responsible for allocating and managing individual graphics buffers is the <xref:System.Drawing.BufferedGraphicsContext> class.</span></span> <span data-ttu-id="09447-105">すべてのアプリケーションには、 <xref:System.Drawing.BufferedGraphicsContext>そのアプリケーションのすべての既定のダブルバッファリングを管理する独自の既定値があります。</span><span class="sxs-lookup"><span data-stu-id="09447-105">Every application has its own default <xref:System.Drawing.BufferedGraphicsContext> that manages all of the default double buffering for that application.</span></span> <span data-ttu-id="09447-106">このインスタンスへの参照を取得するには、 <xref:System.Drawing.BufferedGraphicsManager.Current%2A>を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="09447-106">You can retrieve a reference to this instance by calling the <xref:System.Drawing.BufferedGraphicsManager.Current%2A>.</span></span>  
  
### <a name="to-obtain-a-reference-to-the-default-bufferedgraphicscontext"></a><span data-ttu-id="09447-107">既定の BufferedGraphicsContext への参照を取得するには</span><span class="sxs-lookup"><span data-stu-id="09447-107">To obtain a reference to the default BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="09447-108">次のコード例に示すように、プロパティを設定します。<xref:System.Drawing.BufferedGraphicsManager.Current%2A></span><span class="sxs-lookup"><span data-stu-id="09447-108">Set the <xref:System.Drawing.BufferedGraphicsManager.Current%2A> property, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#11)]  
  
    > [!NOTE]
    > <span data-ttu-id="09447-109">クラスから<xref:System.Drawing.BufferedGraphicsContext> `Dispose` 受け取る参照に対してメソッドを呼び出す必要はありません<xref:System.Drawing.BufferedGraphicsManager> 。</span><span class="sxs-lookup"><span data-stu-id="09447-109">You do not need to call the `Dispose` method on the <xref:System.Drawing.BufferedGraphicsContext> reference that you receive from the <xref:System.Drawing.BufferedGraphicsManager> class.</span></span> <span data-ttu-id="09447-110">は<xref:System.Drawing.BufferedGraphicsManager> 、既定<xref:System.Drawing.BufferedGraphicsContext>のインスタンスのメモリ割り当てと分布をすべて処理します。</span><span class="sxs-lookup"><span data-stu-id="09447-110">The <xref:System.Drawing.BufferedGraphicsManager> handles all of the memory allocation and distribution for default <xref:System.Drawing.BufferedGraphicsContext> instances.</span></span>  
  
     <span data-ttu-id="09447-111">アニメーションなどのグラフィックを多用するアプリケーションの場合は、 <xref:System.Drawing.BufferedGraphicsContext> <xref:System.Drawing.BufferedGraphicsManager>ではなく<xref:System.Drawing.BufferedGraphicsContext>専用のを使用して、パフォーマンスを向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="09447-111">For graphically intensive applications such as animation, you can sometimes improve performance by using a dedicated <xref:System.Drawing.BufferedGraphicsContext> instead of the <xref:System.Drawing.BufferedGraphicsContext> provided by the <xref:System.Drawing.BufferedGraphicsManager>.</span></span> <span data-ttu-id="09447-112">これにより、アプリケーションに関連付けられている他のすべてのバッファリングされたグラフィックスを管理する際のパフォーマンスオーバーヘッドを発生させずに、グラフィックスバッファーを個別に作成して管理できます。ただし、アプリケーションで使用されるメモリの方が多くなります。</span><span class="sxs-lookup"><span data-stu-id="09447-112">This enables you to create and manage graphics buffers individually, without incurring the performance overhead of managing all the other buffered graphics associated with your application, though the memory consumed by the application will be greater.</span></span>  
  
### <a name="to-create-a-dedicated-bufferedgraphicscontext"></a><span data-ttu-id="09447-113">専用の BufferedGraphicsContext を作成するには</span><span class="sxs-lookup"><span data-stu-id="09447-113">To create a dedicated BufferedGraphicsContext</span></span>  
  
- <span data-ttu-id="09447-114">次のコード例に示すように<xref:System.Drawing.BufferedGraphicsContext> 、クラスの新しいインスタンスを宣言して作成します。</span><span class="sxs-lookup"><span data-stu-id="09447-114">Declare and create a new instance of the <xref:System.Drawing.BufferedGraphicsContext> class, as shown in the following code example.</span></span>  
  
     [!code-csharp[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.LegacyBufferedGraphics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.LegacyBufferedGraphics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="09447-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="09447-115">See also</span></span>

- <xref:System.Drawing.BufferedGraphicsContext>
- [<span data-ttu-id="09447-116">ダブル バッファリングされたグラフィックス</span><span class="sxs-lookup"><span data-stu-id="09447-116">Double Buffered Graphics</span></span>](double-buffered-graphics.md)
- [<span data-ttu-id="09447-117">方法: バッファリングされるグラフィックスを手動でレンダリングする</span><span class="sxs-lookup"><span data-stu-id="09447-117">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)
