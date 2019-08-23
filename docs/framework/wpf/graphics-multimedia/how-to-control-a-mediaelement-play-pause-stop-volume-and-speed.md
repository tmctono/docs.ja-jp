---
title: '方法: MediaElement (再生、一時停止、停止、ボリューム、速度) を制御する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930163"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="c45e7-102">方法: MediaElement (再生、一時停止、停止、ボリューム、速度) を制御する</span><span class="sxs-lookup"><span data-stu-id="c45e7-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="c45e7-103">次の例は、 <xref:System.Windows.Controls.MediaElement>を使用してメディアの再生を制御する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c45e7-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="c45e7-104">この例では、メディア内での再生、一時停止、停止、スキップを可能にする簡単なメディアプレーヤーを作成します。また、音量と速度を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="c45e7-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c45e7-105">例</span><span class="sxs-lookup"><span data-stu-id="c45e7-105">Example</span></span>  
 <span data-ttu-id="c45e7-106">次のコードでは、UI を作成します。</span><span class="sxs-lookup"><span data-stu-id="c45e7-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c45e7-107">メディア<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>を対話的<xref:System.Windows.Controls.MediaElement>に停止、一時停止、および再生できるようにするには、のプロパティをに`Manual`設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c45e7-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="c45e7-108">例</span><span class="sxs-lookup"><span data-stu-id="c45e7-108">Example</span></span>  
 <span data-ttu-id="c45e7-109">次のコードは、サンプル UI コントロールの機能を実装しています。</span><span class="sxs-lookup"><span data-stu-id="c45e7-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="c45e7-110">、 <xref:System.Windows.Controls.MediaElement.Play%2A>、 <xref:System.Windows.Controls.MediaElement.Pause%2A>および<xref:System.Windows.Controls.MediaElement.Stop%2A>の各メソッドは、それぞれ、メディアを再生、一時停止、および停止するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="c45e7-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="c45e7-111"><xref:System.Windows.Controls.MediaElement.Position%2A> のプロパティを変更すると、メディア内<xref:System.Windows.Controls.MediaElement>をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="c45e7-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="c45e7-112">最後に、プロパティ<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> とプロパティを使用して、メディアのボリュームと再生速度を調整します。<xref:System.Windows.Controls.MediaElement.Volume%2A></span><span class="sxs-lookup"><span data-stu-id="c45e7-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c45e7-113">関連項目</span><span class="sxs-lookup"><span data-stu-id="c45e7-113">See also</span></span>

- [<span data-ttu-id="c45e7-114">ストーリーボードを使用して MediaElement を制御する</span><span class="sxs-lookup"><span data-stu-id="c45e7-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
