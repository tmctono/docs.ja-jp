---
title: '方法: VideoDrawing を使用してメディアを再生する'
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956951"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="caf35-102">方法: VideoDrawing を使用してメディアを再生する</span><span class="sxs-lookup"><span data-stu-id="caf35-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="caf35-103">オーディオファイルまたはビデオファイルを再生するには<xref:System.Windows.Media.VideoDrawing> 、 <xref:System.Windows.Media.MediaPlayer>とを使用します。</span><span class="sxs-lookup"><span data-stu-id="caf35-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="caf35-104">メディアを読み込んで再生するには、2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="caf35-104">There are two ways to load and play media.</span></span> <span data-ttu-id="caf35-105">1つ目の方法は<xref:System.Windows.Media.MediaPlayer> 、 <xref:System.Windows.Media.VideoDrawing>とを単独で使用することです。2番目の<xref:System.Windows.Media.MediaTimeline>方法は、 <xref:System.Windows.Media.MediaPlayer>と<xref:System.Windows.Media.VideoDrawing>で使用する独自のを作成することです。</span><span class="sxs-lookup"><span data-stu-id="caf35-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caf35-106">アプリケーションでメディアを配布するときは、イメージのようにプロジェクト リソースとしてメディア ファイルを使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="caf35-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="caf35-107">プロジェクト ファイルで、メディアの種類を `Content` に設定し、`CopyToOutputDirectory` を `PreserveNewest` または `Always` に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="caf35-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caf35-108">例</span><span class="sxs-lookup"><span data-stu-id="caf35-108">Example</span></span>  
 <span data-ttu-id="caf35-109">次の例では<xref:System.Windows.Media.VideoDrawing> 、と<xref:System.Windows.Media.MediaPlayer>を使用して、ビデオファイルを1回再生します。</span><span class="sxs-lookup"><span data-stu-id="caf35-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="caf35-110">メディアに対する追加のタイミング制御を取得するに<xref:System.Windows.Media.MediaTimeline>は、 <xref:System.Windows.Media.MediaPlayer> <xref:System.Windows.Media.VideoDrawing>オブジェクトとオブジェクトを使用してを使用します。</span><span class="sxs-lookup"><span data-stu-id="caf35-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="caf35-111">を<xref:System.Windows.Media.MediaTimeline>使用すると、ビデオを繰り返し表示するかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="caf35-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="caf35-112">例</span><span class="sxs-lookup"><span data-stu-id="caf35-112">Example</span></span>  
 <span data-ttu-id="caf35-113">次の例では<xref:System.Windows.Media.MediaTimeline> 、 <xref:System.Windows.Media.VideoDrawing>オブジェクト<xref:System.Windows.Media.MediaPlayer>とオブジェクトを使用して、ビデオを繰り返し再生します。</span><span class="sxs-lookup"><span data-stu-id="caf35-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="caf35-114">を<xref:System.Windows.Media.MediaTimeline>使用する場合は、の<xref:System.Windows.Media.Animation.Clock.Controller%2A>プロパティ<xref:System.Windows.Media.MediaClock>から返された<xref:System.Windows.Media.Animation.ClockController>対話型のを使用して、の<xref:System.Windows.Media.MediaPlayer>対話型メソッドではなくメディアの再生を制御することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="caf35-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf35-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="caf35-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="caf35-116">Drawing オブジェクトの概要</span><span class="sxs-lookup"><span data-stu-id="caf35-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
