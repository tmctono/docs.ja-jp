---
title: '方法: VideoDrawing を使用してメディアを再生する'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203614"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="aa04e-102">方法: VideoDrawing を使用してメディアを再生する</span><span class="sxs-lookup"><span data-stu-id="aa04e-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="aa04e-103">使用するオーディオまたはビデオ ファイルを再生するには<xref:System.Windows.Media.VideoDrawing>と<xref:System.Windows.Media.MediaPlayer>します。</span><span class="sxs-lookup"><span data-stu-id="aa04e-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="aa04e-104">メディアを読み込んで再生するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="aa04e-104">There are two ways to load and play media.</span></span> <span data-ttu-id="aa04e-105">1 つ目は、使用する、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>自体を 2 番目の方法は、独自に作成する<xref:System.Windows.Media.MediaTimeline>で使用する、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>します。</span><span class="sxs-lookup"><span data-stu-id="aa04e-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa04e-106">アプリケーションでメディアを配布するときは、イメージのようにプロジェクト リソースとしてメディア ファイルを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="aa04e-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="aa04e-107">プロジェクト ファイルで、メディアの種類を `Content` に設定し、`CopyToOutputDirectory` を `PreserveNewest` または `Always` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa04e-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa04e-108">例</span><span class="sxs-lookup"><span data-stu-id="aa04e-108">Example</span></span>  
 <span data-ttu-id="aa04e-109">次の例では、<xref:System.Windows.Media.VideoDrawing>と<xref:System.Windows.Media.MediaPlayer>をビデオ ファイルを 1 回再生します。</span><span class="sxs-lookup"><span data-stu-id="aa04e-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="aa04e-110">使用して、メディアを介した追加のタイミングを制御する、<xref:System.Windows.Media.MediaTimeline>で、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aa04e-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="aa04e-111"><xref:System.Windows.Media.MediaTimeline>ビデオを繰り返す必要があるかどうかを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="aa04e-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa04e-112">例</span><span class="sxs-lookup"><span data-stu-id="aa04e-112">Example</span></span>  
 <span data-ttu-id="aa04e-113">次の例では、<xref:System.Windows.Media.MediaTimeline>で、<xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>ビデオを繰り返し再生するオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="aa04e-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="aa04e-114">使用すると、 <xref:System.Windows.Media.MediaTimeline>、対話型を使用する<xref:System.Windows.Media.Animation.ClockController>から返される、<xref:System.Windows.Media.Animation.Clock.Controller%2A>のプロパティ、<xref:System.Windows.Media.MediaClock>の対話型のメソッドではなくメディア再生を制御する<xref:System.Windows.Media.MediaPlayer>。</span><span class="sxs-lookup"><span data-stu-id="aa04e-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa04e-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa04e-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="aa04e-116">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="aa04e-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
